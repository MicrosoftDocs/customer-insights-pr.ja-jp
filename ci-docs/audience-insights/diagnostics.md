---
title: Azure Monitor を使用して Dynamics 365 Customer Insights を監査する
description: Microsoft Azure モニターにログを送信する方法について説明します。
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 2e0801c2b6af591e48a7df485a8523903c07617c
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354414"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Azure Monitor を使用して、Dynamics 365 Customer Insights でログを転送する (プレビュー)

Dynamics 365 Customer Insights は、Azure Monitor との直接統合を提供します。 Azure Monitor リソース ログを使用すると、ログを監視して [Azure ストレージ](https://azure.microsoft.com/services/storage/)、[ Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) に送信するか、またはそれらを [Azure イベント ハブ](https://azure.microsoft.com/services/event-hubs/) にストリーミングします。

Customer Insights は、次のイベント ログを送信します。

- **監査イベント**
  - **APIEvent** - Dynamics 365 Customer Insights UI を介して行われる変更の追跡を有効にします。
- **運用イベント**
  - **WorkflowEvent** - ワークフローにより、[データ ソース](data-sources.md)をセットアップし、データを[統一](data-unification.md)して、[エンリッチ](enrichment-hub.md)し、最後に他のシステムに[エクスポート](export-destinations.md)します。 これらのすべての手順は、個別に実行することも (たとえば、単一のエクスポートをトリガーする)、調整することもできます (たとえば、統合プロセスをトリガーするデータソースからのデータ更新により、追加のエンリッチメントがプルされ、完了したらデータを別のシステムにエクスポートします)。 詳細については、[WorkflowEvent スキーマ](#workflow-event-schema)を参照してください。
  - **APIEvent** - Dynamics 365 Customer Insights に対する顧客インスタンスへのすべての API 呼び出し。 詳細については、[APIEvent スキーマ](#api-event-schema)を参照してください。

## <a name="set-up-the-diagnostic-settings"></a>診断設定をセットアップする

### <a name="prerequisites"></a>前提条件

Customer Insights で診断を構成するには、次の前提条件が満たされている必要があります。

- 有効な [Azure サブスクリプション](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)がある。
- Customer Insights の[管理者](permissions.md#administrator)権限がある。
- Azure の宛先リソースでの **共同作成者** と **ユーザー アクセス管理者** の役割がある。 リソースには、Azure Storage アカウント、Azure イベント ハブ、または Azure Log Analytics ワークスペースを使用できます。 詳細については、[Azure ポータルを使用して Azure 役割の割り当てを追加または削除する](/azure/role-based-access-control/role-assignments-portal)を参照してください。
- Azure Storage、Azure イベント ハブ、または Azure Log Analytics の[宛先要件](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements)が満たされている。
- リソースが属するリソースグループで、最低 **閲覧者** の役割がある。

### <a name="set-up-diagnostics-with-azure-monitor"></a>Azure Monitor を使用して診断を設定する

1. Customer Insights で、**システム** > **診断** を選択して、このインスタンスを構成した診断の宛先を確認します。

1. **宛先の追加** を選択します。

   > [!div class="mx-imgBorder"]
   > ![診断の接続](media/diagnostics-pane.png "診断の接続")

1. **診断先の名前** フィールドに名前を入力します。

1. 宛先リソースを使って Azure サブスクリプションの **テナント** を選択して、**ログイン** を選択します。

1. **リソース タイプ** (ストレージ アカウント、イベント ハブ、またはログ分析) を選択します。

1. 宛先リソースの **サブスクリプション** を選択します。

1. 宛先リソースの **リソース グループ** を選択します。

1. **リソース** を選択します。

1. **データのプライバシーとコンプライアンス** に関する声明を確認します。

1. **システムに接続する** を選択して、宛先リソースに接続します。 API が使用中でイベントを生成している場合、ログは 15 分後に宛先に表示され始めます。

### <a name="remove-a-destination"></a>宛先を削除する

1. **システム** > **診断** に移動します。

1. 一覧から診断の宛先を選択します。

1. **アクション** 列で、**削除** アイコンを選択します。

1. ログ転送を停止するには、削除を確認します。 Azure サブスクリプションのリソースは削除されません。 **アクション** 列のリンクをクリックして、選択したリソースの Azure ポータルを開き、そこで削除します。

## <a name="log-categories-and-event-schemas"></a>ログ カテゴリとイベント スキーマ

現在[API イベント](apis.md)およびワークフロー イベントがサポートされており、次のカテゴリとスキーマが適用されます。
ログ スキーマは[ Azure Monitor 共通スキーマ](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema)に従っています。

### <a name="categories"></a>カテゴリ

Customer Insights には、次の 2 つのカテゴリがあります。

- **イベントの監査**: [API イベント](#api-event-schema)を選択して、サービスの構成変更を追跡します。 `POST|PUT|DELETE|PATCH` 操作はこのカテゴリに入ります。
- **運用イベント**: サービスの使用中に生成された [API イベント](#api-event-schema)または[ワークフロー イベント](#workflow-event-schema)。  例えば、ワークフローの `GET` リクエストまたは実行イベント。

## <a name="configuration-on-the-destination-resource"></a>宛先リソースの構成

リソース タイプの選択に基づいて、次の手順が自動的に適用されます。

### <a name="storage-account"></a>Storage account

Customer Insights サービス プリンシパルは、選択したリソースに **ストレージ アカウント共同作成者** 権限を取得して、選択した名前空間の下に 2 つのコンテナーを作成します。

- **監査イベント** を含む `insight-logs-audit`
- **運用イベント** を含む `insight-logs-operational`

### <a name="event-hub"></a>イベント ハブ

Customer Insights サービス プリンシパルは、選択したリソースに **Azure イベント ハブ データ所有者** 権限を取得して、選択した名前空間の下に 2 つ Event Hubs を作成します。

- **監査イベント** を含む `insight-logs-audit`
- **運用イベント** を含む `insight-logs-operational`

### <a name="log-analytics"></a>Log Analytics

Customer Insights サービス プリンシパルは、リソースに **ログ分析共同作成者** 権限を取得します。 ログは、選択した Log Analytics ワークスペースの **ログ** > **テーブル** > **ログ管理** で利用可能になります。 **ログ管理** ソリューションを展開して、`CIEventsAudit` と `CIEventsOperational` テーブルを見つけます。

- **監査イベント** を含む `CIEventsAudit`
- **運用イベント** を含む `CIEventsOperational`

**クエリ** ウィンドウの下で、**監査** ソリューションを展開して、`CIEvents` を検索して提供されたクエリ例を見つけます。

## <a name="event-schemas"></a>イベント スキーマ

API イベントとワークフロー イベントには共通の構造と詳細があり、それらは異なります。[API イベント スキーマ](#api-event-schema)また[ワークフロー イベント スキーマ](#workflow-event-schema)を参照してください。

### <a name="api-event-schema"></a>API イベント スキーマ

| フィールド             | データ型  | 必須/任意 | Description       | 例        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | タイムスタンプ | 必須          | イベントのタイムスタンプ (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | 必須          | イベントを発行したインスタンスの ResourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | 必須          | このイベントによって表される操作の名前。                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | 必須          | イベントの ログ カテゴリ。 `Operational` または `Audit` のいずれかです。 すべての POST/PUT/PATCH/DELETE HTTP リクエストは `Audit` で、他のすべては `Operational` でタグ付けされています | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | 必須          | イベントの状態。 `Success`、`ClientError`、`Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | 任意出席者          | イベントの結果ステータス。 操作が REST API 呼び出しに対応する場合、それは HTTP ステータス コードです。        | `200`             |
| `durationMs`      | Long      | 任意出席者          | 操作の期間 (ミリ秒)。     | `133`     |
| `callerIpAddress` | String    | 任意出席者          | 操作が公開されている IP アドレスからの API 呼び出しに対応している場合は、呼び出し元の IP アドレス。                                                 | `144.318.99.233`         |
| `identity`        | String    | 任意出席者          | 操作を行ったユーザーまたはアプリケーションの ID を説明する JSON オブジェクト。       | [ID](#identity-schema) セクションを参照してください。     |  |
| `properties`      | String    | 任意出席者          | イベントの特定のカテゴリに対するより多くのプロパティを持つ JSON オブジェクト。      | [プロパティ](#api-properties-schema) セクションを参照してください。    |
| `level`           | String    | 必須          | イベントの重要度レベル。    | `Informational`、`Warning`、`Error`、または `Critical`。           |
| `uri`             | String    | 任意出席者          | 絶対リクエスト URI。    |               |

#### <a name="identity-schema"></a>ID スキーマ

`identity` JSON オブジェクトには次の構造があります

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| フィールド                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | ユーザーまたはアプリに割り当てられた役割。 詳細については、[ユーザー権限](permissions.md)を参照してください。                                     |
| `Authorization.RequiredRoles` | 操作を行うために必要な役割。 `Admin` 役割はすべての操作を実行できます。                                                    |
| `Claims`                      | ユーザーまたはアプリの JSON Web トークン (JWT) のクレーム。 クレーム プロパティは組織および Azure Active Directory 構成ごとに異なります。 |

#### <a name="api-properties-schema"></a>API プロパティ スキーマ

[API イベント](apis.md)には次のプロパティがあります。

| フィールド                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | 常に `ApiEvent` で、ログ イベントを API イベントとしてマークします。                                                                 |
| `properties.userAgent`       | リクエストまたは `unknown` を送信するブラウザー エージェント。                                                                        |
| `properties.method`          | HTTP メソッド: `GET/POST/PUT/PATCH/HEAD`。                                                                                |
| `properties.path`            | リクエストの相対パス。                                                                                          |
| `properties.origin`          | フェッチがどこから来たかを示す URI または `unknown`。                                                                  |
| `properties.operationStatus` | HTTP 状態コードの `Success` < 400 <br> HTTP 状態コードの `ClientError` < 500 <br> HTTP ステータスの `Error` > = 500 |
| `properties.tenantId`        | 組織 ID                                                                                                        |
| `properties.tenantName`      | 組織名です。                                                                                              |
| `properties.callerObjectId`  | 呼び出し元の Azure Active Directory ObjectId。                                                                         |
| `properties.instanceId`      | Customer Insights `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>ワークフロー イベント スキーマ

ワークフローには複数のステップが含まれています。 [データ ソースを取り込む](data-sources.md)、データを[統一](data-unification.md)、[エンリッチ](enrichment-hub.md)、[エクスポート](export-destinations.md)します。 これらのステップはすべて、個別に実行することも、次のプロセスで調整することもできます。 

#### <a name="operation-types"></a>操作の種類

| OperationType     | グループ                                     |
| ----------------- | ----------------------------------------- |
| インジェスト         | [データ ソース](data-sources.md)           |
| DataPreparation   | [データ ソース](data-sources.md)           |
| マップ               | [データ統合](data-unification.md)   |
| 照合             | [データ統合](data-unification.md)   |
| マージ             | [データ統合](data-unification.md)   |
| ProfileStore      | [顧客プロファイル](customer-profiles.md) |
| 検索する            | [顧客プロファイル](customer-profiles.md) |
| 活動​          | [活動](activities.md)                  |
| AttributeMeasures | [セグメントとメジャー](segments.md)      |
| EntityMeasures    | [セグメントとメジャー](segments.md)      |
| メジャー          | [セグメントとメジャー](segments.md)      |
| セグメント化      | [セグメントとメジャー](segments.md)      |
| エンリッチメント        | [エンリッチメント](enrichment-hub.md)                                          |
| インテリジェンス      | [予測](predictions-overview.md)                                          |
| AiBuilder         | [予測](predictions-overview.md)                                          |
| 分析情報          | [予測](predictions-overview.md)                                          |
| Export            | [エクスポート](export-destinations.md)                                          |
| ModelManagement   | [予測](custom-models.md)                                           |
| Relationship      | [データ統合](relationships.md)                                           |

#### <a name="field-description"></a>フィールドの説明

| フィールド           | データ型  | 必須/任意 | Description                                                                                                                                                   | 例                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | タイムスタンプ | 必須          | イベントのタイムスタンプ (UTC)。                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | 必須          | イベントを発行したインスタンスの ResourceId。                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | 必須          | このイベントによって表される操作の名前。 `{OperationType}.[WorkFlow|Task][Started|Completed]`。 参考のために[操作の種類](#operation-types)を参照してください。 | `Segmentation.WorkflowStarted`、<br> `Segmentation.TaskStarted`、 <br> `Segmentation.TaskCompleted`、 <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | 必須          | イベントの ログ カテゴリ。 常にワークフローイベントの `Operational`                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | 必須          | イベントの状態。 `Running`、`Skipped`、`Successful`、`Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Long      | 任意出席者          | 操作の期間 (ミリ秒)。                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | 任意出席者          | イベントの特定のカテゴリに対するより多くのプロパティを持つ JSON オブジェクト。                                                                                        | サブ セクションの[ワークフローのプロパティ](#workflow-properties-schema)を参照してください                                                                                                       |
| `level`         | String    | 必須          | イベントの重要度レベル。                                                                                                                                  | `Informational`、`Warning`、または `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>ワークフロー プロパティ スキーマ

ワークフロー イベントには次のプロパティがあります。

| フィールド              | Workflow | Task | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | 有効      | 有効  | 常に `WorkflowEvent` で、ログ イベントをワークフロー イベントとしてマークします。                                                                                                                                                                                                |
| `properties.workflowJobId`                   | 有効      | 有効  | ワークフロー実行の識別子。 ワークフロー実行内のすべてのワークフローイベントとタスクイベントには、同じ `workflowJobId` があります。                                                                                                                                   |
| `properties.operationType`                   | 有効      | 有効  | 操作の識別子。[操作の種類]を参照してください。(#operation-types)                                                                                                                                                                                       |
| `properties.tasksCount`                      | 有効      | 無効   | ワークフローのみ。 ワークフロー トリガーのタスクの数。                                                                                                                                                                                                       |
| `properties.submittedBy`                     | 有効      | 無効   | 省略可能。 ワークフロー イベントのみ。 ワークフローをトリガーしたユーザーの Azure Active Directory [objectId](/azure/marketplace/find-tenant-object-id#find-user-object-id)については、`properties.workflowSubmissionKind` も参照してください。                                   |
| `properties.workflowType`                    | 有効      | 無効   | `full` または `incremental` 更新。                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | 有効      | 無効   | `OnDemand` または `Scheduled`。                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | 有効      | 無効   | `Running` または `Successful`。                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | 有効      | 有効  | UTC タイムスタンプ`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | 有効      | 有効  | UTC タイムスタンプ`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | 有効      | 有効  | UTC タイムスタンプ`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | 有効      | 有効  | Customer Insights `instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | 無効       | 有効  | - OperationType = `Export` の場合、識別子はエクスポート構成の guid です。 <br> - OperationType = `Enrichment` の場合、それはエンリッチメントの guid です <br> - OperationType `Measures` と `Segmentation` の場合、識別子はエンティティ名です。 |
| `properties.friendlyName`                    | 無効       | 有効  | エクスポートまたは処理されるエンティティのユーザーフレンドり名。                                                                                                                                                                                           |
| `properties.error`                           | 無効       | 有効  | 省略可能。 詳細付きのエラー メッセージ。                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | 無効       | 有効  | 省略可能。 OperationType `Export` のみの場合。 エクスポートの種類を識別します。 詳細については、[エクスポート先の概要](export-destinations.md) を参照してください。                                                                                          |
| `properties.additionalInfo.AffectedEntities` | 無効       | 有効  | 省略可能。 OperationType `Export` のみの場合。 エクスポートで構成されたエンティティのリストが含まれます。                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | 無効       | 有効  | 省略可能。 OperationType `Export` のみの場合。 エクスポートの詳細メッセージ。                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | 無効       | 有効  | 省略可能。 OperationType `Segmentation` のみの場合。 セグメントに含まれるメンバーの総数を示します。                                                                                                                                                    |
