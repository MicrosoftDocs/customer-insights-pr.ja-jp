---
title: Common Data Model における Customer Insights エンティティ スキーマ
description: Common Data Model のエンティティに関する作業。
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9e7a6e944d37d25f4c25846644278b39b3ddd08e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269290"
---
# <a name="entity-schemas-in-common-data-model"></a>Common Data Model のエンティティ スキーマ

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](https://docs.microsoft.com/common-data-model/) は宣言的な仕様であり、ビジネスと生産性アプリケーションの全体で一般的に使用される概念とアクティビティを表す標準エンティティの定義です。 このモデルは実測データ、および分析データにも拡張されています。 Common Data Model は、アクティビティおよびサービス レベル アグリーメントなど、ベンダー、従業員、および顧客間の対話だけでなく、取引先企業、部署、ケース、連絡先、潜在顧客、営業案件、製品など、適切に定義されたモジュール形式の拡張可能なビジネス エンティティを提供します。 誰もが Common Data Model の定義に基づいて拡張し、さらなるビジネス固有のアイデアを取り込むことができます。

この共有データ モデルにより、データの統一された定義を提供され、アプリケーションとデータ インテグレータの共同作業が容易になります。 Common Data Model には、標準的なエンティティー、関連付け、階層、特性などを備えた豊富なメタデータ システムが含まれています。 これは、Dynamics 365 アプリ を起点としており、260を超える標準エンティティを持つ GitHub でオープンソース化されています。 内外のパートナーからなる大規模なシステムは、Common Data Model に業種固有の概念を提供します。

現在、Power BI データフロー、Azure Data Services を含む複数のシステムとプラットフォームが Common Data Model を実装しています。 既に Common Data Service、 Dynamics 365、 Power Apps、 Power BI、 と 次期 Azure データサービスで対応をしており、 [オープン データ イニシアティブ](https://www.microsoft.com/open-data-initiative)に直接的な価値をもたらします。

## <a name="customer-insights-entity-schemas"></a>Customer Insights のエンティティのスキーマ

顧客の360度のビューを確立し、拡張性を実装した Common Data Model で Customer Insights モデルを利用できるようにするために、次のエンティティ スキーマを公開しました:

| エンティティ | 説明 |
|---------|---------|
|[CustomerActivity](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | 業務に対する観察的な視点を持つユーザーが実行する活動です。 |
|[CustomerProfile](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | 事業活動を行った、または行う可能性のある個人または組織です。 |
|[MeasureDefinition](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | 0 個以上のディメンションで区分された KPI の定義です (例：月間アクティブユーザー、顧客別支出合計、顧客獲得費用の平均) |
|[セグメント](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | 共通した特徴を持つメンバーのグループを定義します。 |
|[SegmentMembership](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | 特定のセグメントに加わっているメンバーです。 |

詳細については、[Common Data Model の Customer Insights エンティティ スキーマ](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview) を参照してください。

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Common Data Model エンティティ ナビゲーターを使用してエンティティを表示する

[Common Data Model のエンティティ ナビゲータ](https://microsoft.github.io/CDM/) にエンティティを表示できます。 **GitHub からロードする** を選択します **foundationCommon** > **crmCommon** > **solutions** > **customerInsights** に移動すると、Customer Insights エンティティと定義のリストが表示されます。
> [!div class="mx-imgBorder"]
> ![CustomerActivity エンティティを表示するC DM エンティティ ナビゲーター](media/CDM-entity-navigator.png "CustomerActivity エンティティを表示するC DM エンティティ ナビゲーター")


[!INCLUDE[footer-include](../includes/footer-banner.md)]