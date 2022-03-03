---
title: Microsoft Dataverse の Customer Insights データ
description: Customer Insights エンティティを Microsoft Dataverse のテーブルとして使用します。
ms.date: 11/25/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9f730f5856221592cddf34b714beeaca24c52130
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355435"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse での Customer Insights データの使用

Customer Insights には、[Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md) で出力エンティティを使用できるようにするオプションがあります。 この統合により、ローコード / ノーコード アプローチによる簡単なデータ共有とカスタム開発が可能になります。 出力エンティティは、Dataverse のテーブルとして使用できます。 これらのテーブルは、[Power Automate による自動化されたワークフロー](/power-automate/getting-started)、[モデル駆動型アプリ](/powerapps/maker/model-driven-apps/)、Power Apps による [キャンバス アプリ](/powerapps/maker/canvas-apps/) のようなシナリオを可能にします。 Dataverse テーブルに基づいている他のアプリケーションのデータを使用できます。 現在の実装は主に、利用可能な対象者インサイト エンティティからのデータを、指定した顧客 ID に対してフェッチできる検索をサポートしています。

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Dataverse 環境を Customer Insights に接続する

**既存の Dataverse 環境を持つ組織**

すでに Dataverse 使用している組織は、管理者が対象者に関するインサイトを設定するときに [既存の Dataverse 環境のいずれかを使用](create-environment.md) できます。 Dataverse 環境に URL を提供することで、新しい対象者に関するインサイトの環境に接続されます。 可能な限り最高のパフォーマンスを確保するために、Customer Insights と Dataverse 環境は同じリージョンでホストする必要があります。

**新しい組織**

Customer Insights を設定するときに新しい組織を作成すると、自動的に新しい Dataverse 環境が取得されます。

> [!NOTE]
> 組織が既にテナントで Dataverse を使用している場合、[Dataverse 環境の作成は管理者によって制御される](/power-platform/admin/control-environment-creation.md) ことを覚えておくことが重要です。たとえば、組織アカウントを使用して、新しい対象者に関するインサイトの環境を設定していて、管理者が管理者以外のすべてのユーザーの Dataverse 試用環境の作成を無効にした場合、新しい試用環境を作成することはできません。
> 
> Customer Insights で作成された Dataverse 試用環境には 3 GB のストレージがあり、テナントに与えられる全体的な容量にはカウントされません。 有料サブスクリプションでは、データベース用に 15 GB、ファイル ストレージ用に 20 GB の Dataverse 使用権を取得します。

## <a name="output-entities"></a>出力エンティティ

対象者に関するインサイトからの一部の出力エンティティは、Dataverse のテーブルとして利用できます。 以下のセクションでは、これらのテーブルの想定されるスキーマについて説明します。

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
|EntityName        | String        | 対象者に関するインサイトのエンティティの名前。 例: `contact1`        |
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
| SegmentProvider      | String       | セグメントを公開するアプリ。 既定: 対象ユーザーに関するインサイト         |
| SegmentMembershipType | String       | このセグメント メンバーシップ レコードの顧客のタイプ。 顧客、取引先担当者、取引先企業など、複数のタイプをサポートします。 既定: 顧客  |
| セグメント       | JSON 文字列  | 顧客プロファイルがメンバーになっている一意のセグメントのリスト      |
| msdynci_identifier  | String   | セグメント メンバーシップ レコードを表す一意の識別子。 `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | `msdynci_identifier` から生成した確定的 GUID          |
