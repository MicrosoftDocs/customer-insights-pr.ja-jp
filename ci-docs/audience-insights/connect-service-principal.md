---
title: サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する
description: 対象者に関するインサイトの Azure サービス プリンシパルを使用して、対象者に関するインサイトに接続するときに、独自のデータ レイクに接続します。
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267728"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>対象者に関するインサイトの Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する

Azure サービスを使用する自動ツールは、常に制限されたアクセス許可が必要です。 Azureは、完全な権限を持つユーザーとしてアプリケーションにサインインさせる代わりに、サービス プリンシパルを提供します。 ストレージ アカウント キーの代わりに、Azure サービス プリンシパルを使用して、対象者に関するインサイトを Azure Data Lake Storage Gen2 アカウントに接続する方法について説明します。 

サービス プリンシパルを使用して、安全に [Common Data Model フォルダーをデータ ソースとして追加または編集](connect-common-data-model.md) したり、[新しい環境を作成、または既存の環境を更新](manage-environments.md#create-an-environment-in-an-existing-organization) したりできます。

> [!IMPORTANT]
> - サービス プリンシパルを使用する予定の Azure Data Lake Gen2 ストレージ アカウントでは、[階層名前空間 (HNS) が有効](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace)である必要があります。
> - サービス プリンシパルを作成するには、Azure サブスクリプションに対する管理者のアクセス許可が必要です。

## <a name="create-azure-service-principal-for-audience-insights"></a>対象者に関するインサイトに Azure サービス プリンシパルを作成する

対象者に関するインサイトに新しいサービス プリンシパルを作成する前に、組織にすでに存在するかどうかを確認してください。

### <a name="look-for-an-existing-service-principal"></a>既存のサービス プリンシパルの検索

1. [Azure 管理ポータル](https://portal.azure.com) に移動し、サインインにログインします。

2. Azure サービスから **Azure Active Directory** を選択します。

3. **管理** で、**エンタープライズ アプリケーション** を選択します。

4. 対象者に関するインサイトのファースト パーティ アプリケーション ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` または 名前 `Dynamics 365 AI for Customer Insights` を検索します。

5. 一致するレコードが見つかった場合は、対象者に関するインサイトにサービス プリンシパルが存在することを意味します。 再度作成する必要はありません。
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="既存のサービス プリンシパルを示すスクリーンショット。":::
   
6. 結果が返されない場合は、新しいサービス プリンシパルを作成します。

### <a name="create-a-new-service-principal"></a>新しいサービス プリンシパルを作成する

1. **Graph 用 Azure Active Directory PowerShell** の最新バージョンをインストールします。 詳細については、[Graph 用 Azure Active Directory PowerShell のインストール](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) を参照してください。
   - PC で、キーボードの Windows キーを選択し、**Windows PowerShell** を検索して、**管理者として実行** します。
   
   - 開いた PowerShell ウィンドウで、`Install-Module AzureAD` を入力します。

2. Azure AD PowerShell モジュールを使用して、対象者に関するインサイトにサービス プリンシパルを作成します。
   - PowerShell ウィンドウで、`Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` を入力します。 "テナント ID" を、サービス プリンシパルを作成するテナントの実際の ID に置き換えます。 環境名パラメーター `AzureEnvironmentName` は任意です。
  
   - `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` を入力します。 このコマンドは、選択したテナントの対象者に関するインサイトにサービス プリンシパルを作成します。  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>ストレージ アカウントにアクセスするためにアクセス許可をサービス プリンシパルに付与する

Azure portal に移動して、対象者に関するインサイトで使用するストレージ アカウントのサービス プリンシパルにアクセス許可を付与します。

1. [Azure 管理ポータル](https://portal.azure.com) に移動し、サインインにログインします。

1. 対象者に関するインサイトのサービス プリンシパルにアクセスさせるストレージ アカウントを開きます。

1. ナビゲーション ウィンドウから **アクセス制御 (IAM)** を選択し、**追加** > **ロール割り当ての追加** を選択します。
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="ロール割り当てを追加中の Azure ポータルを示すスクリーンショット。":::
   
1. **ロール割り当ての追加** ペインで、次のプロパティを設定します:
   - ロール: *ストレージ Blob データ共同作成者*
   - アクセスの割当て先: *ユーザー、グループ、またはサービス プリンシパル*
   - 選択: *Dynamics 365 AI for Customer Insights* ([作成したサービス プリンシパル](#create-a-new-service-principal))

1.  **保存** を選択します。

変更が反映されるまでに最大 15 分かかる場合があります。

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>対象者に関するインサイトのストレージ アカウント添付ファイルに Azure リソース ID または Azure サブスクリプションの詳細を入力します。

対象者に関するインサイトに Azure Data Lake ストレージ アカウントを添付し、[出力データを保存](manage-environments.md) または [データ ソースとして使用](connect-common-data-service-lake.md) します。 Azure Data Lake オプションを選択すると、リソース ベースまたはサブスクリプション ベースのアプローチのどちらかを選択できます。

以下の手順に従って、選択したアプローチに関する必要な情報を指定します。

### <a name="resource-based-storage-account-connection"></a>リソースベースのストレージ アカウント接続

1. [Azure 管理ポータル](https://portal.azure.com) に移動し、サブスクリプションにサインインし、ストレージ アカウントを開きます。

1. ナビゲーション ウィンドウで **設定** > **プロパティ** に移動します。

1. ストレージ アカウントのリソース ID 値をコピーします。

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="ストレージ アカウントのリソース ID をコピーします。":::

1. 対象者に関するインサイトで、ストレージ アカウント接続画面に表示されるリソース フィールドに、リソース ID を挿入します。

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="ストレージ アカウントのリソース ID 情報を入力します。":::   
   
1. 対象者に関するインサイトの残りの手順を続行して、ストレージ アカウントを添付します。

### <a name="subscription-based-storage-account-connection"></a>サブスクリプション ベースのストレージ アカウント接続

1. [Azure 管理ポータル](https://portal.azure.com) に移動し、サブスクリプションにサインインし、ストレージ アカウントを開きます。

1. ナビゲーション ウィンドウで **設定** > **プロパティ** に移動します。

1. **サブスクリプション**、**リソース グループ**、ストレージ アカウントの **名前** を確認して、対象者に関するインサイトで適切な値を選択していることを確認します。

1. 対象者に関するインサイトで、ストレージ アカウントを添付するときに、値または対応するフィールドを選択します。
   
1. 対象者に関するインサイトの残りの手順を続行して、ストレージ アカウントを添付します。


[!INCLUDE[footer-include](../includes/footer-banner.md)]