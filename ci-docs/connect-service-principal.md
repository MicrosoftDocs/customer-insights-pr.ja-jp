---
title: Azure サービス プリンシパルを利用した Azure Data Lake Storage アカウントへの接続
description: Azure サービス プリンシパルを使用して、独自の Data Lake に接続します。
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304203"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Azure サービス プリンシパルを利用した Azure Data Lake Storage アカウントへの接続

Dynamics 365 Customer Insights はストレージ アカウント キーの代わりに Azure サービス プリンシパルを使用して Azure Data Lake Storage のアカウントと接続するオプションを提供します。

Azure サービスを使用する自動ツールには、制限されたアクセス許可が必要です。 Azureは、完全な権限を持つユーザーとしてアプリケーションにサインインさせる代わりに、サービス プリンシパルを提供します。 サービス プリンシパルを使用して安全に[Common Data Model フォルダーをデータ ソースとして追加または編集](connect-common-data-model.md) したり、[環境を作成または更新](create-environment.md) したりできます。

## <a name="prerequisites"></a>前提条件

- サービス プリンシパルを使用する Data Lake ストレージ アカウントは、Gen2 である必要があります。 Azure Data Lake Gen1 ストレージ アカウントはサポートしていません。
- Data Lake ストレージ アカウントでは[階層型名前空間が有効](/azure/storage/blobs/data-lake-storage-namespace) になっている必要があります。
- 新しいサービス プリンシパルを作成する際は、Azure テナント管理者のアクセス許可が必要です。

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Customer Insights の Azure サービス プリンシパルを作成する

Customer Insights の新しいサービス プリンシパルを作成する前に、それが組織にすでに存在するかどうかを確認してください。 ほとんどの場合、すでに存在しています。

### <a name="look-for-an-existing-service-principal"></a>既存のサービス プリンシパルの検索

1. [Azure 管理ポータル](https://portal.azure.com) に移動し、サインインにログインします。

2. **Azure サービス** で **Azure Active Directory** を選択します。

3. **管理** 配下の **Microsoft アプリケーション** を選択します。

4. **`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` で始まるアプリケーション ID** のフィルターを追加するか、または `Dynamics 365 AI for Customer Insights` の名前を検索します。

5. 一致するレコードがあれば、そのサービス プリンシパルがすでに存在していることになります。 ストレージ アカウントにアクセスするためにサービス プリンシパルに[アクセス許可を付与します](#grant-permissions-to-the-service-principal-to-access-the-storage-account)。

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="既存のサービス プリンシパルを示すスクリーンショット。":::

6. 結果が返されない場合は、[新しいサービス プリンシパルを作成します](#create-a-new-service-principal)。

### <a name="create-a-new-service-principal"></a>新しいサービス プリンシパルを作成する

1. 最新の Azure Active Directory PowerShell for Graph をインストールします。 詳細については、[Azure Active Directory PowerShell for Graph のインストール](/powershell/azure/active-directory/install-adv2)にアクセスしてください。

   1. PC のキーボードで Windows キーを押下し、**Windows PowerShell** を検索して **管理者として実行** を選択します。

   1. 開いた PowerShell ウィンドウで、`Install-Module AzureAD` を入力します。

2. Azure AD PowerShell モジュールで Customer Insights のサービス プリンシパルを作成します。

   1. PowerShell ウィンドウで、`Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure` を入力します。 *[あなたのディレクトリ ID]* をサービスプリンシパルを作成する Azure サブスクリプションの実際のディレクトリ ID と置き換えます。 環境名パラメーター `AzureEnvironmentName` は任意です。
  
   1. `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` を入力します。 このコマンドは、選択した Azure サブスクリプションに Customer Insights のサービス プリンシパルを作成します。

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>ストレージ アカウントにアクセスするためにアクセス許可をサービス プリンシパルに付与する

Customer Insights で使用するストレージ アカウントのサービス プリンシパルにアクセス許可を付与するには、次のロールのいずれかをストレージ アカウントまたはコンテナーに割り当てる必要があります。

|資格情報|要件|
|----------|------------|
|現在ログインしているユーザー|**役割**: ストレージ ブロブ データ リーダー、ストレージ ブロブ コントリビューター、またはストレージ ブロブ オーナー。<br>**レベル**: ストレージ アカウントまたはコンテナーで付与されたアクセス許可です。</br>|
|Customer Insights サービス プリンシパル -<br>データ ソースとしての Azure Data Lake Storage の使用</br>|オプション 1<ul><li>**役割**: ストレージ ブロブ データ リーダー、ストレージ ブロブ コントリビューター、またはストレージ ブロブ オーナー。</li><li>**レベル**: ストレージ アカウントで付与されたアクセス許可です。</li></ul>オプション 2 *(ストレージ アカウントへのサービス プリンシパル アクセスの共有なし)*<ul><li>**役割 1**: ストレージ ブロブ データ リーダー、ストレージ ブロブ コントリビューター、またはストレージ ブロブ オーナー。</li><li>**レベル**: コンテナーで付与されたアクセス許可です。</li><li>**役割 2**: ストレージ ブログ データ デリゲーター。</li><li>**レベル**: ストレージ アカウントで付与されたアクセス許可です。</li></ul>|
|Customer Insights サービス プリンシパル - <br>Azure Data Lake Storage を出力または宛先として使用する</br>|オプション 1<ul><li>**役割**: ストレージ ブロブ データ リーダー コントリビューター、またはストレージ ブロブ オーナー。</li><li>**レベル**: ストレージ アカウントで付与されたアクセス許可です。</li></ul>オプション 2 *(ストレージ アカウントへのサービス プリンシパル アクセスの共有なし)*<ul><li>**役割**: ストレージ ブロブ データ リーダー コントリビューター、またはストレージ ブロブ オーナー。</li><li>**レベル**: コンテナーで付与されたアクセス許可です。</li><li>**役割 2**: ストレージ ブログ デリゲーター。</li><li>**レベル**: ストレージ アカウントで付与されたアクセス許可です。</li></ul>|

1. [Azure 管理ポータル](https://portal.azure.com) に移動し、サインインにログインします。

1. Customer Insights のサービス プリンシパルがアクセスできるようにするストレージ アカウントを開きます。

1. 左側のペインで、**アクセスの制御 (IAM)** を選択し、**追加** > **ロールの割り当て追加** を選択します。

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="役割の割り当てを追加する際の Azure ポータルを示すスクリーンショット。":::

1. **役割の割り当てを追加する** ペインで、次のプロパティを設定します:
   - **役割**: 前述の資格情報に基づくストレージ Blob データ閲覧者、ストレージ Blob 共同作成者、またはストレージ Blob 所有者。
   - **アクセス権の割り当て先**: **ユーザー、グループ、サービス プリンシパル**
   - メンバーの **選択**: **Customer Insights 向けの Dynamics 365 AI** (この手順の前半で確認した[サービス プリンシパル](#create-a-new-service-principal))

1. **レビュー+ 割り当て** を選択します。

変更が反映されるまでに最大 15 分かかる場合があります。

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Customer Insights のストレージ アカウント添付ファイルに Azure リソース ID または Azure サブスクリプションの詳細を入力します

Customer Insights で Data Lake ストレージ アカウントをアタッチして、[出力データを保存](manage-environments.md) したり、[データソースとして使用](connect-dataverse-managed-lake.md) したりできます。 [リソースベース](#resource-based-storage-account-connection) または [サブスクリプションベース ](#subscription-based-storage-account-connection) のアプローチを選択し、次の手順に従います。

### <a name="resource-based-storage-account-connection"></a>リソースベースのストレージ アカウント接続

1. [Azure 管理ポータル](https://portal.azure.com) に移動し、サブスクリプションにサインインし、ストレージ アカウントを開きます。

1. 左のペインから **設定** > **エンドポイント** の順に移動します。

1. ストレージ アカウントのリソース ID 値をコピーします。

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="ストレージ アカウントのリソース ID をコピーします。":::

1. Customer Insights で、ストレージ アカウントの接続画面に表示されるリソース フィールドにリソース ID を挿入します。

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="ストレージ アカウントのリソース ID 情報を入力します。":::

1. Customer Insights の残りの手順に進み、ストレージ アカウントを添付します。

### <a name="subscription-based-storage-account-connection"></a>サブスクリプション ベースのストレージ アカウント接続

1. [Azure 管理ポータル](https://portal.azure.com) に移動し、サブスクリプションにサインインし、ストレージ アカウントを開きます。

1. 左側のペインで、**設定** > **プロパティ** にアクセスします。

1. **サブスクリプション**、**リソースグループ**、そしてそのストレージ アカウントの **名前** をレビューして、Customer Insights で正しい値を選択していることを確認します。

1. Customer Insights で、ストレージ アカウントをアタッチするときに、対応するフィールドの値を選択します。

1. Customer Insights の残りの手順に進み、ストレージ アカウントを添付します。

[!INCLUDE [footer-include](includes/footer-banner.md)]
