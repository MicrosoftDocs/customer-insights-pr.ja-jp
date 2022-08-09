---
title: リアルタイム データ インジェスト (プレビュー)
description: Customer Insights のリアルタイム機能に関する一般情報。
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 403cc9dbd3bddcf67f59b5cb0be936af4d268fc2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195664"
---
# <a name="real-time-data-ingestion-preview"></a>リアルタイム データ インジェスト (プレビュー)

ほぼリアルタイムの機能により、顧客が製品やサービスに対して行った最新の対話を数秒で確認できます。

[スケジュールされた更新](system.md#schedule-tab) には、多数のレコードといくつかの複雑な操作が含まれます。 まず、データはデータ ソースから取得されます。 次に、データが統合され、追加情報が追加されます。 このプロセスを実行するたびに、数分から数時間かかることがあります。

リアルタイム機能は、後続のスケジュールされた更新が、このデータをデータ ソースから取得するまで、データを即座に使用できるようにします。

リアルタイムの更新には有効期限があり、その後はデータ ソースからの値を上書きしなくなります。

- プロファイルの更新は 4 時間保持されます
- アクティビティは 30 日間保持されます

これらの値は、変更可能な API 呼び出しパラメーターです。 これらは、ソース データの内容が変更されていないことを保証することを目指しています。 リアルタイムの更新をより長く含める場合は、データ ソースに追加して、次のスケジュールされた更新時に取得されるようにする必要があります。

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>統合された顧客プロファイル フィールドのリアルタイム更新

更新されたプロファイルは、数秒以内に顧客カード ビューまたはその他のビジュアル化で表示されます。

データの統合が行われた後にリアルタイムの操作が行われるため、統合された顧客プロファイルにのみ適用されます。 したがって、リアルタイムのプロファイル変更は、メジャー、セグメント メンバーシップ、またはエンリッチメントを更新しません。

### <a name="limitations"></a>制限

- 顧客プロファイルは更新できますが、作成または削除することはできません。
- Power BI のような外部システムへのリアルタイム更新のエクスポートは、現時点では不可能です。

## <a name="real-time-creation-of-activities"></a>活動のリアルタイム作成

リアルタイム API を使用すると、ソース システム (個々のソース レコード) から統合顧客プロファイルに、新しい活動を公開できます。 新しいアクティビティは、その統合された顧客プロファイルのタイムラインで、数秒で統合されたアクティビティとして利用できます。 タイムラインは、顧客カード ビューまたは構成したその他のタイムライン統合で確認できます。

> [!NOTE]
>
> - 活動は不変です。 いったん作成されると、変更されません。
> - 現在、セグメントとメジャーは新しいアクティビティに基づいて更新されません。
> - リアルタイム API を介してのみ追加された活動はエクスポートの一部ではなく、PowerBI に表示されません。

リアルタイム API に接続する方法は 2 つあります:

- [Dynamics 365 Customer Insights コネクタ](/connectors/customerinsights/)を使用して[間接的に](#connect-via-the-dynamics-365-customer-insights-connector)
- コードを使用して[直接](#connect-directly-to-the-real-time-api)

どちらの方法でも次の前提条件が適用されます。

- Customer Insights 環境
- 統合顧客プロファイル
- 構成および実行される活動
- アカウントを認証する共同作成者または管理者アクセス許可

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Dynamics 365 Customer Insights コネクタ経由で接続

リアルタイム API は、専用 Power Platform コネクタ、[Dynamics 365 Customer Insights コネクタ](/connectors/customerinsights/) からデータを取り込むことができます。コードを記述してデプロイする必要はありません。    
コネクタは、API と同じリアルタイム アクションを実行できます。 プレミアム コネクタの有効なライセンスが必要です。 詳細については、[Power Apps と Power Automate のライセンスの FAQ](/power-platform/admin/powerapps-flow-licensing-faq)を参照してください。

- Power Platform [Power Apps や Power Automate](/connectors/)
- Azure [Logic Apps](/azure/connectors/apis-list)

フローの作成の詳細については、[Power Automate ドキュメンテーション](/power-automate/)を参照してください。

## <a name="connect-directly-to-the-real-time-api"></a>リアルタイム API に直接接続する

独自のパイプラインを構築し、リアルタイム API に直接接続することで、リアルタイム機能を使用できます。    
ソース システムの形式または UnifiedActivity 形式で活動を投稿できます。 /api/instances/{instanceId}/manage/entities/UnifiedActivity への API 呼び出しを行って形式を取得します。

パラメーターや応答など、この API の詳細については、[Customer Insights API リファレンス](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) の **EntityData** のセクションにあります。 詳細については、[Customer Insights API の使用](apis.md) を参照してください。

## <a name="understand-your-real-time-usage-with-telemetry"></a>テレメトリを使用してリアルタイムの使用状況を把握する

リアルタイム API への要求の量の概要と、システムで発生する可能性のある問題に関する情報を取得します。 [リアルタイム テレメトリにアクセス](system.md#api-usage-tab)できます。 


[!INCLUDE [footer-include](includes/footer-banner.md)]
