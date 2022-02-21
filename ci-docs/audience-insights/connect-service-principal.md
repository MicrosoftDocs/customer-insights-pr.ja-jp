---
title: サービス プリンシパルを利用した Azure Data Lake Storage アカウントへの接続
description: Azure サービス プリンシパルを使用して、独自の Data Lake に接続します。
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1af01e5579f85d7c8bc8976a003f53ef2dd280d1
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088153"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Azure サービス プリンシパルを利用した Azure Data Lake Storage アカウントへの接続

この記事では、ストレージ アカウント キーの代わりに Azure サービス プリンシパルを使用して Dynamics 365 Customer Insights を Azure Data Lake Storage アカウントに接続する方法について説明しています。 

Azure サービスを使用する自動ツールは、常に制限されたアクセス許可が必要です。 Azureは、完全な権限を持つユーザーとしてアプリケーションにサインインさせる代わりに、サービス プリンシパルを提供します。 サービス プリンシパルを使用して安全に[ Common Data Model フォルダーをデータ ソースとして追加または編集](connect-common-data-model.md)したり、[環境を作成または更新](create-environment.md)したりできます。

> [!IMPORTANT]
> - サービス プリンシパルを使用する Data Lake Storage アカウントは、Gen2 であり、[階層型名前空間を有効化](/azure/storage/blobs/data-lake-storage-namespace) する必要があります。 Azure Data Lake Gen1 ストレージ アカウントはサポートしていません。
> - サービス プリンシパルを作成するには、Azure サブスクリプションの管理者権限が必要です。

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Customer Insights の Azure サービス プリンシパルを作成する

Customer Insights の新しいサービス プリンシパルを作成する前に、それが組織にすでに存在するかどうかを確認してください。

### <a name="look-for-an-existing-service-principal"></a>既存のサービス プリンシパルの検索

1. [Azure 管理ポータル](https://portal.azure.com) に移動し、サインインにログインします。

2. **Azure サービス** で **Azure Active Directory** を選択します。

3. **管理** で、**エンタープライズ アプリケーション** を選択します。

4. Microsoft のアプリケーション ID を検索します:
   - 対象ユーザー インサイト: `Dynamics 365 AI for Customer Insights` という名前の `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`
   - エンゲージメント インサイト: `Dynamics 365 AI for Customer Insights engagement insights` という名前の `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd`

5. 一致するレコードがあれば、そのサービス プリンシパルがすでに存在していることになります。 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="既存のサービス プリンシパルを示すスクリーンショット。":::
   
6. 結果が返されない場合は、新しいサービス プリンシパルを作成します。

>[!NOTE]
>Dynamics 365 Customer Insights の能力をフルに活用するためには、両方のアプリをサービス プリンシパルに追加することをお勧めします。

### <a name="create-a-new-service-principal"></a>新しいサービス プリンシパルを作成する

1. 最新の Azure Active Directory PowerShell for Graph をインストールします。 詳細については、[Azure Active Directory PowerShell for Graph のインストール](/powershell/azure/active-directory/install-adv2)にアクセスしてください。

   1. PC で、キーボードの Windows キーを選択し、**Windows PowerShell** を検索し、**管理者として実行** を選択します。
   
   1. 開いた PowerShell ウィンドウで、`Install-Module AzureAD` を入力します。

2. Azure AD PowerShell モジュールで Customer Insights のサービス プリンシパルを作成します。

   1. PowerShell ウィンドウで、`Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` を入力します。 *テナント ID* を、サービス プリンシパルを作成するテナントの実際の ID に置き換えます。 環境名パラメーター `AzureEnvironmentName` は任意です。
  
   1. `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` を入力します。 このコマンドは、選択したテナントの対象者に関するインサイトにサービス プリンシパルを作成します。 

   1. `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"` を入力します。 このコマンドは、選択したテナントにエンゲージメント インサイトのサービス プリンシパルを作成します。

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

対象ユーザーの分析情報に Data Lake Storage アカウントをアタッチして、[出力データの保存](manage-environments.md)や、[データ ソースとしての使用](connect-common-data-service-lake.md)ができます。 このオプションを使用すると、リソース ベースのアプローチとサブスクリプション ベースのアプローチのどちらかを選択できます。 選択したアプローチに応じて、次のセクションのいずれかの手順に従います。

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
