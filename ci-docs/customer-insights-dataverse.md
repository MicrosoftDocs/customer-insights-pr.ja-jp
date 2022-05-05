---
title: Microsoft Dataverse の Customer Insights データ
description: Customer Insights エンティティを Microsoft Dataverse のテーブルとして使用します。
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 85995cbd7f797810bfb6ecdc8a24d56542f0b5a9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646601"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse での Customer Insights データの使用

Customer Insights には、[Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) で出力エンティティを使用できるようにするオプションがあります。 この統合により、ローコード/ノーコード アプローチによる簡単なデータ共有とカスタム開発が可能になります。 Dataverse 環境では、[出力エンティティ](#output-entities)をテーブルとして使用できます。 Dataverse テーブルに基づいて他のアプリケーションのデータを使用できます。 これらのテーブルにより、Power Automate でのワークフローの自動化や、Power Apps でのアプリ構築などのシナリオが有効になります。 現在の実装は主に、使用可能な Customer Insights エントリのデータを指定した顧客 ID に対して取得できる検索をサポートしています。

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Dataverse 環境を Customer Insights に接続する

**既存の組織**

管理者は、環境を作成する際に、Customer Insights を構成して[既存の Dataverse 環境を使用](create-environment.md)することができます。 Dataverse 環境に URL を提供することによって、それは彼らの新しい Customer Insights 環境に接続しています。 Customer Insights と Dataverse 環境は同じリージョンでホストする必要があります。 

既存の Dataverse 環境を使用しない場合、システムはテナント内に Customer Insights データ用の新しい環境を作成します。 

> [!NOTE]
> 組織がすでにテナントで Dataverse を使用している場合、[Dataverse 環境の作成は管理者によって制御されている](/power-platform/admin/control-environment-creation) ことを覚えておくことが重要です。たとえば、組織のアカウントを使用して新しい Customer Insights 環境をセットアップしていて、管理者以外のすべてのユーザー向けの Dataverse 試用環境では、管理者が新しい試用環境を作成することはできません。
> 
> Customer Insights で作成された Dataverse 試用環境には 3 GB のストレージがあり、テナントに与えられる全体的な容量にはカウントされません。 有料サブスクリプションでは、データベース用に 15 GB、ファイル ストレージ用に 20 GB の Dataverse 使用権を取得します。

**新しい組織**

Customer Insights の設定時に新しい組織を作成すると、自動的に新しい Dataverse 環境が組織に作成されます。

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

このテーブルには、Customer Insights の統合された顧客プロファイルが含まれています。 統合された顧客プロファイルのスキーマは、結合プロセスで使用されるエンティティと属性によって異なります。 顧客プロファイル スキーマには通常、[CustomerProfile の Common Data Model 定義](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) の属性のサブセットが含まれます。

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

| Column            | 型        | 内容                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | 顧客プロファイル ID                                                                      |
| ActivityId        | String      | 顧客活動の内部 ID (主キー)                                       |
| SourceEntityName  | String      | ソース エンティティの名前                                                                |
| SourceActivityId  | String      | ソース エンティティからの主キー                                                       |
| ActivityType      | String      | セマンティック活動の種類またはカスタム活動の名前                                        |
| ActivityTimeStamp | DATETIME    | 活動のタイム スタンプ                                                                      |
| 敬称             | String      | 活動のタイトルまたは名前                                                               |
| 内容       | String      | 活動の説明                                                                     |
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

| Column               | 型        | 内容                                          |
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
