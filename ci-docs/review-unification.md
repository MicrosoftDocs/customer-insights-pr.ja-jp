---
title: データ統合を確認する
description: データ統合手順を確認し、統合された顧客プロファイルを作成して、結果を確認する
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303973"
---
# <a name="review-data-unification"></a>データ統合を確認する

変更の概要を確認し、統合プロファイルを作成して、結果を確認します。

## <a name="review-and-create-customer-profiles"></a>顧客プロファイルを確認し、作成する

統合プロセスのこの最後の手順は、プロセスの手順の概要を示し、統合プロファイルを作成する前に変更を加える機会を提供します。

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="顧客プロファイルのレビューと作成のスクリーンショット。":::

1. 確認して変更を加えるには、データ統合手順のいずれかで **編集** を選択します。

1. 選択に満足している場合は、**顧客プロファイルの作成** (または B-to-B の **取引先企業プロファイルの作成** ) を選択します。 統合された顧客プロファイルの作成中に、**統合** ページが表示されます。

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="キュー処理済み、または更新を示すタイルを含む Unify ページのスクリーンショット。":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

統合アルゴリズムは完了するまでに時間がかかり、完了するまで構成を変更できません。

## <a name="view-the-results-of-data-unification"></a>データ統合の結果を表示する

統合後、**データ** > **統合** ページに統合された顧客プロファイル  (または B-to-B の取引先企業プロファイル) の数が表示されます。 統合プロセスの各手順の結果は、各タイルに表示されます。 たとえば、**ソース フィールド** はマップされた属性 (フィールド) の数を示し、**重複レコード** は見つかった重複レコードの数を示します。

:::image type="content" source="media/m3_unified.png" alt-text="データが統合された後のデータ統合ページのスクリーンショット。":::

> [!TIP]
> **一致条件** タイルは、複数のエンティティが選択されている場合にのみ表示されます。

結果、特に[一致規則](data-unification-update.md#manage-match-rules) の品質を確認し、必要に応じてそれらを調整することをお勧めします。

必要に応じて、[統合設定を変更](data-unification-update.md) して、統合プロファイルを再実行します。

### <a name="verify-output-entities-from-data-unification"></a>データ統合からの出力エンティティを確認する

**データ** > **エンティティ** に移動し、出力エンティティを確認します。

*顧客* と呼ばれる統合された顧客プロファイル エンティティは、**プロファイル** セクションに表示されます。 最初に成功した統合実行により、統合された *顧客* エンティティが作成されます。 以降のすべての実行では、そのエンティティが展開されます。

重複排除エンティティおよび合成エンティティが作成され、**システム** セクションに表示されます。 各ソース エンティティの重複排除エンティティは、**Deduplication_DataSource_Entity** という名前で作成されます。 **ConflationMatchPairs** エンティティには、エンティティ間照合の情報が含まれます。

重複排除出力エンティティには、次の情報が含まれています。
- ID/キー
  - 主キーと代替 ID フィールド。 代替 ID フィールドは、レコードに対して識別されたすべての代替 ID で構成されます。
  - Deduplication_GroupId フィールドには、指定された重複排除フィールドに基づいてすべての類似レコードをグループ化するエンティティ内で識別されたグループまたはクラスターが表示されます。 これは、システム処理の目的で使用されます。 手動の重複排除ルールが指定されておらず、システム定義の重複排除ルールが適用されている場合、このフィールドが重複排除出力エンティティに表示されていない可能性があります。
  - Deduplication_WinnerId: このフィールドには、識別されたグループまたはクラスターからの勝者 ID が含まれます。 Deduplication_WinnerId がレコードの主キー値と同じである場合、そのレコードが勝者レコードであることを意味します。
- 重複排除ルールを定義するために使用されるフィールド。
- [ルール] フィールドと [スコア] フィールドは、どの重複排除ルールが適用され、照合アルゴリズムによってスコアが返されことを示します。

## <a name="next-step"></a>次の手順

- B-to-B の場合、オプションで[取引先担当者の統合](data-unification-contacts.md)を実行します。

- B-to-C の場合、[活動](activities.md)、[エンリッチメント](enrichment-hub.md)、[関連付け](relationships.md)、または[メジャー](measures.md)を構成して、顧客に関するより多くの分析情報を得ます。

[!INCLUDE[footer-include](includes/footer-banner.md)]
