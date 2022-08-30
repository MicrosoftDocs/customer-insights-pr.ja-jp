---
title: Microsoft Dataverse での Customer Insights データの使用
description: Customer Insights と Microsoft Dataverse の接続方法と、Dataverse にエクスポートする出力エンティティを説明します。
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303835"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse での Customer Insights データの使用

Customer Insights には、[Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) で出力エンティティを使用できるようにするオプションがあります。 この統合により、ローコード/ノーコード アプローチによる簡単なデータ共有とカスタム開発が可能になります。 Dataverse 環境では、[出力エンティティ](#output-entities)をテーブルとして使用できます。 Dataverse テーブルに基づいて他のアプリケーションのデータを使用できます。 これらのテーブルにより、Power Automate でのワークフローの自動化や、Power Apps でのアプリ構築などのシナリオが有効になります。

自分の Dataverse 環境を接続すると、[Power Platform データフローとゲートウェイを使用してオンプレミス データ ソースからデータを取り込む](connect-power-query.md#add-data-from-on-premises-data-sources)こともできます。

## <a name="prerequisites"></a>前提条件

- Customer Insights と Dataverse 環境は同じリージョンでホストする必要があります。
- Dataverse 環境でグローバル管理者ロールをセットアップします。 特定のセキュリティ グループにこの [Dataverse 環境が関連付けられいる](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment)か確認して、それらのセキュリティ グループに自分が追加されていることを確認してください。
- 接続する Dataverse 環境に関連付けられた Customer Insights 環境は他に存在しません。 [Dataverse 環境への既存の接続を削除する](#remove-an-existing-connection-to-a-dataverse-environment)方法について説明します。
- 環境を [Azure Data Lake Storage の使用](own-data-lake-storage.md) に構成する場合に単一のストレージ アカウントに接続された Microsoft Dataverse 環境。

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse ストレージ容量権利

Customer Insights サブスクリプションは、組織の既存の [Dataverse ストレージ容量](/power-platform/admin/capacity-storage) に対して追加容量の権利を与えます。 追加される容量は、サブスクリプションが使用するプロファイルの数によって異なります。

**用例:**

100,000 の顧客プロファイルごとに 15 GB のデータベース ストレージと 20 GB のファイル ストレージを取得するとします。 サブスクリプションに 300,000 の顧客プロファイルが含まれている場合、合計ストレージ容量は 45 GB (3 x 15 GB) のデータベース ストレージと 60 GB のファイル ストレージ (3 x 20 GB) です。 同様に、3 万アカウントの B-to-B サブスクリプションがある場合、合計ストレージ容量は 45 GB (3 x 15 GB) データベース ストレージと60 GB ファイル ストレージ (3 x 20 GB) です。

ログ容量は増分ではなく、組織によって固定されています。

詳細な容量権利の詳細については、[Dynamics 365 のライセンス ガイド](https://go.microsoft.com/fwlink/?LinkId=866544) を参照してください。

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Dataverse 環境を Customer Insights に接続する

**Microsoft Dataverse** ステップによって、[Customer Insights 環境を作成する](create-environment.md) 際に Customer Insights を Dataverse 環境に接続できます。

:::image type="content" source="media/dataverse-provisioning.png" alt-text="新しい環境に対して自動で有効化された、Microsoft Dataverse とのデータ共有。":::

1. URL を入力して Dataverse 環境を作成するか、空白のままにして作成します。

   > [!NOTE]
   > Customer Insights と Dataverse の間の接続を確立した後、Dataverse 環境の組織名を変更しないでください。 組織の名前は Dataverse URL で使用され、名前の変更により、Customer Insights との接続が切断されます。

   [Power Platform 管理者は Dataverse 環境を作成できるユーザーを制御できます](/power-platform/admin/control-environment-creation)。 新しい Customer Insights 環境を設定しようとしてもできない場合、管理者が自身を除くすべてのユーザーに対して Dataverse の環境作成を無効化していることがあります。

1. 独自の Data Lake ストレージ アカウントを使用している場合:
   1. Dataverse との **データ共有を有効にする** を選択します。
   1. **アクセス許可の識別子** を入力します。 アクセス許可の識別子を取得するために、[独自の Azure Data Lake Storage から Dataverse との共有を有効にします](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)。

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>独自の Azure Data Lake Storage から Dataverse とのデータ共有を有効にする (プレビュー)

[独自の Azure Data Lake Storage アカウント](own-data-lake-storage.md) で、Customer Insights 環境のユーザー設定に最終的にストレージ アカウントの `customerinsights` コンテナーで **ストレージ Blob データ閲覧者** アクセス許可があるかを検証します。

### <a name="limitations"></a>制限

- Dataverse 組織と Azure Data Lake Storage アカウントの間に唯一の 1 対 1 のマッピングが存在すること。 Dataverse 組織をストレージ アカウントに接続すると、別のストレージ アカウントに接続できない。 この制限により、Dataverse が複数のストレージ アカウントからデータを取り込むことを防ぎます。
- Azure Data Lake Storage アカウントにアクセスする際に Azure 非公開リンクの設定が必要な場合、ファイアウォールの背後に存在するため、データの共有が機能しません。 Dataverse は現在、非公開リンクによる非公開エンドポイントへの接続に対応していません。

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>独自の Azure Data Lake Storage でセキュリティ グループを設定する

1. Azure サブスクリプションに 2 つのセキュリティ グループを作成します。1 つは **閲覧者** セキュリティ グループで、もう 1 つは **共同作成者** セキュリティ グループです。さらに、Microsoft Dataverse サービスを両方のセキュリティ グループの所有者として設定します。

1. これらのセキュリティ グループを通して、ストレージ アカウントの `customerinsights` コンテナーのアクセス制御リスト (ACL) を管理します。
   1. Microsoft Dataverse サービスと、Dynamics 365 Marketing などの任意の Dataverse ベースのビジネスアプリケーションを、**読み取り専用** アクセス許可を持つ **閲覧者** セキュリティ グループに追加します。
   1. Customers Insights アプリケーション *のみ* を **共同作成者** セキュリティ グループに追加して、プロファイルと分析情報を書き込むための **読み取りと書き込み** の両方のアクセス許可を付与します。

### <a name="set-up-powershell"></a>PowerShell の設定

PowerShell スクリプトを実行するように PowerShell をセットアップします。

1. 最新バージョンの [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) をインストールします。
   1. PC で、キーボードの Windows キーを選択し、**Windows PowerShell** を検索し、**管理者として実行** を選択します。
   1. 開いた PowerShell ウィンドウで、`Install-Module AzureAD` を入力します。

1. 3 つのモジュールをインポートします。
   1. PowerShell ウィンドウで `Install-Module -Name Az.Accounts` と入力してから次の手順に従います。
   1. `Install-Module -Name Az.Resources` と `Install-Module -Name Az.Storage` に対して繰り返します。

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>PowerShell スクリプトを実行してアクセス許可識別子を取得する

1. エンジニアの [GitHub リポジトリ](https://github.com/trin-msft/byol)から実行する必要のある 2 つの PowerShell スクリプトをダウンロードします。
   - `CreateSecurityGroups.ps1`: テナント管理者のアクセス許可が必要です。
   - `ByolSetup.ps1`: ストレージ アカウント/コンテナー レベルでのストレージ Blob データ所有者のアクセス許可が必要です。 このスクリプトにより、個人用のアクセス許可が作成されます。 スクリプトを正常に実行した後、ロールの割り当てを手動で削除できます。

1. Azure Data Lake Storage を含む Azure サブスクリプション ID を指定して、Windows PowerShell で `CreateSecurityGroups.ps1` を実行します。 エディターで PowerShell スクリプトを開き、追加情報と実装されているロジックを確認します。

   このスクリプトは、Azure サブスクリプションに 2 つのセキュリティ グループを作成します。1 つは 閲覧者グループ用で、もう 1 つは共同制作者グループ用です。 Microsoft Dataverse サービスは、これら両方のセキュリティ グループの所有者です。

1. このスクリプトで生成された両方のセキュリティ グループ ID 値を保存して、`ByolSetup.ps1` スクリプトで使用します。

   > [!NOTE]
   > テナントでのセキュリティ グループの作成を無効にできます。 その場合、手動セットアップが必要になり、Azure AD 管理者が[セキュリティ グループの作成を有効にする](/azure/active-directory/enterprise-users/groups-self-service-management)必要があります。

1. Azure Data Lake Storage を含む Azure サブスクリプション ID、ストレージ アカウント名、リソース グループ名、および閲覧者および共同作成者のセキュリティ グループ ID 値を指定して、Windows PowerShell で `ByolSetup.ps1` を実行します。 エディターで PowerShell スクリプトを開き、追加情報と実装されているロジックを確認します。

   このスクリプトは、Microsoft Dataverse サービスおよび任意の Dataverse ベースのビジネス アプリケーションに必要なロールベースのアクセス制御を追加します。 また、`CreateSecurityGroups.ps1` スクリプトで作成されたセキュリティ グループの `customerinsights` コンテナーのアクセス制御リスト (ACL) を更新します。 共同作成者グループには *rwx* アクセス許可が付与され、閲覧者グループには *r-x* アクセス許可のみ付与されます。

1. 次のような出力スクリプトをコピーします: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. コピーした出力文字列を、Microsoft Dataverse の環境構成ステップの **アクセス許可の識別子** フィールドに入力します。

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="独自の Azure Data Lake Storage から Microsoft Dataverse とのデータ共有を有効にするための構成オプション。":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Dataverse 環境への既存の接続を削除する

Dataverse 環境に接続すると、**この CDS 組織は、すでに別の Customer Insights インスタンスに接続されています** というエラー メッセージが表示されます。これは、Dataverse 環境が Customer Insights 環境ですでに使用されていることを意味します。 Dataverse 環境のグローバル管理者として既存の接続を削除できます。 変更の反映に数時間かかる場合があります。

1. [Power Apps](https://make.powerapps.com) に移動します。
1. 環境ピッカーから環境を選択します。
1. **ソリューション** に移動します。
1. **Dynamics 365 Customer Insights 顧客カード アドイン (プレビュー)** という名前のソリューションをアンインストールまたは削除します。

OR

1. Dataverse 環境を開きます。
1. **詳細設定** > **ソリューション** に移動します。
1. **CustomerInsightsCustomerCard** ソリューションをアンインストールします。

依存関係が原因で接続の削除に失敗した場合は、その依存関係も削除する必要があります。 詳細については [依存関係の削除](/power-platform/alm/removing-dependencies) を参照してください。

## <a name="output-entities"></a>出力エンティティ

Customer Insights からの一部の出力エンティティは、Dataverse のテーブルとして利用できます。 以下のセクションでは、これらのテーブルの想定されるスキーマについて説明します。

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [エンリッチメント](#enrichment)
- [予測](#prediction)
- [セグメント メンバーシップ](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

このテーブルには、Customer Insights の統合された顧客プロファイルが含まれています。 統合された顧客プロファイルのスキーマは、データ統合プロセスで使用されるエンティティと属性によって異なります。 顧客プロファイル スキーマには通常、[CustomerProfile の Common Data Model 定義](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) の属性のサブセットが含まれます。

### <a name="alternatekey"></a>AlternateKey

AlternativeKey テーブルには、統合プロセスに参加したエンティティのキーが含まれています。

|Column  |型  |内容  |
|---------|---------|---------|
|DataSourceName    |String         | データ ソースの名前。 例: `datasource5`        |
|EntityName        | String        | Customer Insights におけるエンティティの名前。 例: `contact1`        |
|AlternateValue    |String         |顧客 ID にマップされる代替 ID。 例: `cntid_1078`         |
|KeyRing           | 複数行テキスト        | JSON 値  </br> サンプル: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | 統合された顧客プロファイルの ID。         |
|AlternateKeyId     | GUID         |  msdynci_identifier に基づく AlternateKey の確定的 GUID       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> サンプル: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

このテーブルには、Customer Insights で利用できるユーザーによる活動が含まれています。

| Column            | タイプ        | 説明設定                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | 顧客プロファイル ID                                                                      |
| ActivityId        | String      | 顧客活動の内部 ID (主キー)                                       |
| SourceEntityName  | String      | ソース エンティティの名前                                                                |
| SourceActivityId  | String      | ソース エンティティからの主キー                                                       |
| ActivityType      | String      | セマンティック活動の種類またはカスタム活動の名前                                        |
| ActivityTimeStamp | DATETIME    | 活動のタイム スタンプ                                                                      |
| 肩書き             | String      | 活動のタイトルまたは名前                                                               |
| 説明設定       | String      | 活動の説明                                                                     |
| URL               | String      | 活動に固有の外部 URL へのリンク                                         |
| SemanticData      | JSON 文字列 | 活動の種類に固有のセマンティック マッピング フィールドのキーと値のペアのリストが含まれています |
| RangeIndex        | String      | 活動タイムラインと有効範囲クエリの並べ替えに使用される Unix タイムスタンプ |
| mydynci_unifiedactivityid   | GUID | 顧客活動の内部 ID (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

このテーブルには、顧客属性に基づくメジャーの出力データが含まれています。

| Column             | 型             | 内容                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | 顧客プロファイル ID        |
| メジャー           | JSON 文字列      | 特定の顧客のメジャー名と値のキーと値のペアのリストが含まれています | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | 顧客プロファイル ID |


### <a name="enrichment"></a>エンリッチメント

このテーブルには、エンリッチ プロセスの出力が含まれています。

| Column               | 型             |  内容                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | 顧客プロファイル ID                                 |
| EnrichmentProvider   | String           | エンリッチメントのプロバイダーの名前                                  |
| EnrichmentType       | String           | エンリッチメントの種類                                      |
| 値               | JSON 文字列      | エンリッチメント プロセスが生成した属性のリスト |
| msdynci_enrichmentid | GUID             | msdynci_identifier から生成された確定的 GUID |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>予測

このテーブルには、モデル予測の出力が含まれています。

| Column               | タイプ        | 説明設定                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | 顧客プロファイル ID                                  |
| ModelProvider        | String      | モデルのプロバイダーの名前                                      |
| モデル                | String      | モデル名                                                |
| 値               | JSON 文字列 | モデルが生成した属性のリスト |
| msdynci_predictionid | GUID        | msdynci_identifier から生成された確定的 GUID | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>セグメント メンバーシップ

このテーブルは、顧客プロファイルのセグメント メンバーシップ情報を含みます。

| Column        | タイプ | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | 顧客プロファイル ID        |
| SegmentProvider      | String       | セグメントを公開するアプリ。      |
| SegmentMembershipType | String       | このセグメント メンバーシップ レコードの顧客のタイプ。 顧客、取引先担当者、取引先企業など、複数のタイプをサポートします。 既定: 顧客  |
| セグメント       | JSON 文字列  | 顧客プロファイルがメンバーになっている一意のセグメントのリスト      |
| msdynci_identifier  | String   | セグメント メンバーシップ レコードを表す一意の識別子。 `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | `msdynci_identifier` から生成した確定的 GUID          |


[!INCLUDE [footer-include](includes/footer-banner.md)]
