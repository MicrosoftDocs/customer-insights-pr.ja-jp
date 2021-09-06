---
title: サービス プリンシパルを利用した Azure Data Lake Storage アカウントへの接続
description: Azure サービス プリンシパルを使用して、独自の Data Lake に接続します。
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461154"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Azure サービス プリンシパルを利用した Azure Data Lake Storage アカウントへの接続
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Azure サービスを使用する自動ツールは、常に制限されたアクセス許可が必要です。 Azureは、完全な権限を持つユーザーとしてアプリケーションにサインインさせる代わりに、サービス プリンシパルを提供します。 ここでは、ストレージ アカウントキーの代わりに Azure サービス プリンシパルを使用して、Dynamics 365 Customer Insights と Azure Data Lake Storage のアカウントを接続する方法について説明します。 

サービス プリンシパルを使用して、[データソースとして Common Data Model フォルダを安全に追加・編集](connect-common-data-model.md)したり、[環境を作成・更新](get-started-paid.md)したりすることができます。<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - 使用する Data Lake Storage のアカウント<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> サービス プリンシパルは[階層名前空間が有効](/azure/storage/blobs/data-lake-storage-namespace)になっている必要があります。
> - サービス プリンシパルを作成するには、Azure サブスクリプションに対する管理者のアクセス許可が必要です。

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Customer Insights の Azure サービス プリンシパルを作成する

対象ユーザー インサイトやエンゲージメント インサイトに向けた新しいサービス プリンシパルを作成する前に、すでに組織内に存在していないかどうかを確認してください。

### <a name="look-for-an-existing-service-principal"></a>既存のサービス プリンシパルの検索

1. [Azure 管理ポータル](https://portal.azure.com) に移動し、サインインにログインします。

2. **Azure サービス** で **Azure Active Directory** を選択します。

3. **管理** で、**エンタープライズ アプリケーション** を選択します。

4. マイクロソフトを検索します<!--note from editor: Via Microsoft Writing Style Guide.--> アプリケーション ID:
   - 対象ユーザー インサイト: `Dynamics 365 AI for Customer Insights` という名前の `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`
   - エンゲージメント インサイト: `Dynamics 365 AI for Customer Insights engagement insights` という名前の `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd`

5. 一致するレコードがあれば、そのサービス プリンシパルがすでに存在していることになります。 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="既存のサービス プリンシパルを示すスクリーンショット。":::
   
6. 結果が返されない場合は、新しいサービス プリンシパルを作成します。

>[!NOTE]
>Dynamics 365 Customer Insights の能力をフルに活用するためには、両方のアプリをサービス プリンシパルに追加することをお勧めします。<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>新しいサービス プリンシパルを作成する
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. 最新の Azure Active Directory PowerShell for Graph をインストールします。 詳細については、[Azure Active Directory PowerShell for Graph のインストール](/powershell/azure/active-directory/install-adv2)にアクセスしてください。

   1. PC で、キーボードの Windows キーを選択し、**Windows PowerShell** を検索し、**管理者として実行** を選択します。<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. 開いた PowerShell ウィンドウで、`Install-Module AzureAD` を入力します。

2. Azure AD PowerShell モジュールで Customer Insights のサービス プリンシパルを作成します。

   1. PowerShell ウィンドウで、`Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` を入力します。 *"[ご利用のテナント ID]"* を置換える<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> サービス プリンシパルを作成するテナントの実際の ID を使用します。 環境名パラメーター `AzureEnvironmentName` は任意です。
  
   1. `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` を入力します。 このコマンドは、選択したテナントの対象者に関するインサイトにサービス プリンシパルを作成します。 

   1. `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"` を入力します。 このコマンドは、エンゲージメント インサイトのサービス プリンシパルを作成します<!--note from editor: Edit okay?--> これを選択したテナントで実施します。

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>ストレージ アカウントにアクセスするためにアクセス許可をサービス プリンシパルに付与する

Azure portal に移動して、対象者に関するインサイトで使用するストレージ アカウントのサービス プリンシパルにアクセス許可を付与します。

1. [Azure 管理ポータル](https://portal.azure.com) に移動し、サインインにログインします。

1. 対象者に関するインサイトのサービス プリンシパルにアクセスさせるストレージ アカウントを開きます。

1. 左側のペインで、**アクセスの制御 (IAM)** を選択し、**追加** > **ロールの割り当て追加** を選択します。

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="役割の割り当てを追加する際の Azure ポータルを示すスクリーンショット。":::

1. **役割の割り当てを追加する** ペインで、次のプロパティを設定します:
   - ロール: **ストレージ Blob データ共同作成者**
   - アクセスの割当て先: **ユーザー、グループ、またはサービス プリンシパル**
   - **Customer Insights 用 Dynamics 365 AI** と **Dynamics 365 AI for CustomerInsights エンゲージメント インサイト** (この手順の前半で作成した 2 つの[サービス プリンシパル](#create-a-new-service-principal) ) を選択します

1.  **保存** を選択します。

変更が反映されるまでに最大 15 分かかる場合があります。

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>対象者に関するインサイトのストレージ アカウント添付ファイルに Azure リソース ID または Azure サブスクリプションの詳細を入力します

次の処理を行うことができます<!--note from editor: Edit suggested only if this section is optional.--> 対象ユーザー インサイトで Data Lake Storage アカウントをアタッチして、[出力データを保存](manage-environments.md)したり、[データソースとして使用](connect-common-data-service-lake.md)したりできます。 このオプションを使用すると、リソース ベースのアプローチとサブスクリプション ベースのアプローチのどちらかを選択できます。 選択したアプローチに応じて、次のセクションのいずれかの手順に従います。<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>リソースベースのストレージ アカウント接続

1. [Azure 管理ポータル](https://portal.azure.com) に移動し、サブスクリプションにサインインし、ストレージ アカウントを開きます。

1. 左側のペインで、**設定** > **プロパティ** にアクセスします。

1. ストレージ アカウントのリソース ID 値をコピーします。

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="ストレージ アカウントのリソース ID をコピーします。":::

1. 対象ユーザーインサイトで、ストレージ アカウント接続画面に表示されるリソース フィールドにリソース ID を挿入します。

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="ストレージ アカウントのリソース ID 情報を入力します。":::   

1. 対象者に関するインサイトの残りの手順を続行して、ストレージ アカウントを添付します。

### <a name="subscription-based-storage-account-connection"></a>サブスクリプション ベースのストレージ アカウント接続

1. [Azure 管理ポータル](https://portal.azure.com) に移動し、サブスクリプションにサインインし、ストレージ アカウントを開きます。

1. 左側のペインで、**設定** > **プロパティ** にアクセスします。

1. **サブスクリプション**、**リソース グループ**、ストレージ アカウントの **名前** を確認して、対象者に関するインサイトで適切な値を選択していることを確認します。

1. 対象ユーザーインサイトで、ストレージ アカウントをアタッチする際に、対応するフィールドの値を選択します。

1. 対象者に関するインサイトの残りの手順を続行して、ストレージ アカウントを添付します。


[!INCLUDE[footer-include](../includes/footer-banner.md)]