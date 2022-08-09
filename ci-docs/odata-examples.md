---
title: Customer Insights API の OData クエリの例
description: Open Data Protocol (OData) が Customer Insights API にクエリを実行してデータを確認するためによく使用される例。
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8843fc04e4e6eaba0019d932c54f62561ffbdb92
ms.sourcegitcommit: f3c12ad445d5f91a88f91a7bbc40790ebcfaa826
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "9121568"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Customer Insights API の OData クエリの例

Open Data Protocol (OData) は、HTTP などのコア プロトコルに基づいて構築されたデータ アクセス プロトコルです。 Web 用の REST のような一般的に受け入れられている方法論を使用します。 OData サービスを使用するために使用できるさまざまな種類のライブラリとツールがあります。

この記事では、[Customer Insights APIs](apis.md) に基づいて独自の実装を構築するのに役立つ、頻繁に要求されるクエリの例をいくつか示します。

クエリ サンプルを変更して、ターゲット環境で機能するようにする必要があります。 

- {instanceId} がクエリする Customer Insights 環境の GUID は {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` です。 [ListAllInstances 操作](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) を使用すると、アクセスできる {InstanceId} を見つけることができます。
- {CID}: 統合された顧客レコードの GUID。 例: `ce759201f786d590bf2134bff576c369`。
- {AlternateKey}: データ ソースの顧客レコードの主キーの識別子。 例: `CNTID_1002`
- {DSname}: Customer Insights に取り込まれるデータ ソースのエンティティ名を持つ文字列。 例: `Website_contacts`。
- {SegmentName}: Customer Insights のセグメントの出力エンティティ名を含む文字列。 例: `Male_under_40`。

## <a name="customer"></a>大変お世話になっております

次の表には、*顧客* エンティティの一連のサンプル クエリが含まれています。

|クエリの種類 |例  | Note  |
|---------|---------|---------|
|1 つの顧客 ID     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|代替キー    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  代替キーは統合された顧客エンティティに保持される       |
|選択   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|含む    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|代替キー + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|検索する  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   検索文字列の上位 10 件の結果を返す      |
|セグメント メンバーシップ  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | セグメント化エンティティから事前設定された行数を返します。      |
|顧客のセグメント メンバーシップ | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | 指定されたセグメントのメンバーである場合、顧客プロファイルを返します     |

## <a name="unified-activity"></a>統合した活動

次の表には、*UnifiedActivity* エンティティの一連のサンプル クエリが含まれています。

|クエリの種類 |例  | Note  |
|---------|---------|---------|
|CID の活動     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | 特定の顧客プロファイルの活動を一覧表示する |
|活動の概算時間    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  概算時間の顧客プロファイルの活動       |
|活動の種類    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|表示名による活動     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|活動の並び替え    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  活動を昇順または降順で並べ替える       |
|セグメント メンバーシップから拡大した活動  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>その他の例

次の表には、他のエンティティの一連のサンプル クエリが含まれています。

|クエリの種類 |例  | Note  |
|---------|---------|---------|
|CID のメジャー    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|CID のエンリッチされたブランド    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|CID のエンリッチされた関心    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|句内 + 展開     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>対応していない OData クエリ

Customer Insights は次のクエリに対応していません:

- 取り込んだソース エンティティの `$filter`。 Customer Insights が作成するシステム エンティティに対してのみ、$filter クエリを実行できます。 
- `$search` クエリによる `$expand`。 例: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- 属性のサブセットのみを選択している場合は、`$select` による `$expand`。 例: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- 特定の顧客に対して強化したブランドや関心のアフィニティを `$expand` します。 例: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- 代替キーによって予測モデルの出力エンティティをクエリします。 例: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
