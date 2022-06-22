---
title: データ統合を確認する
description: データ統合手順を確認し、統合された顧客プロファイルを作成して、結果を確認する
ms.date: 06/02/2022
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
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844092"
---
# <a name="review-data-unification"></a>データ統合を確認する

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

統合プロセスのこの最後の手順は、プロセスの手順の概要を示し、統合プロファイルを作成する前に変更を加える機会を提供します。

:::image type="content" source="media/m3_review.png" alt-text="顧客プロファイルのレビューと作成のスクリーンショット。":::

## <a name="review-the-data-unification-steps"></a>データ統合手順を確認する

1. 確認して変更を加えるには、データ統合手順のいずれかで **編集** を選択します。

1. 選択に満足している場合は、**顧客プロファイルの作成** を選択します。 統合された顧客プロファイルの作成中に、**統合** ページが表示されます。 **ソースフィールド** 以外のすべてのタイルでは、**キュー処理済み** または **更新** の状態が表示されます。

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="キュー処理済み、または更新を示すタイルを含む Unify ページのスクリーンショット。":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

統合アルゴリズムは完了するまでに時間がかかり、完了するまで構成を変更できません。 統合プロセスが完了すると、*顧客* と呼ばれる統合された顧客プロファイル エンティティが **プロファイル** セクションの **エンティティ** ページに一覧表示されます。 最初に成功した統合実行により、統合された *顧客* エンティティが作成されます。 以降のすべての実行では、そのエンティティが展開されます。

## <a name="review-the-results-of-data-unification"></a>データ統合の結果を確認する

統合後、**データ** > **統合** ページに統合された顧客プロファイルの数が表示されます。 統合プロセスの各手順の結果は、各タイルに表示されます。 たとえば、**ソース フィールド** はマップされた属性 (フィールド) の数を示し、**重複レコード** は見つかった重複レコードの数を示します。

:::image type="content" source="media/m3_unified.png" alt-text="データが統合された後のデータ統合ページのスクリーンショット。":::

> [!TIP]
> **一致条件** タイルは、複数のエンティティが選択されている場合にのみ表示されます。

結果、特に[一致規則](data-unification-update.md#manage-match-rules) の品質を確認し、必要に応じてそれらを調整することをお勧めします。

必要に応じて、[統合設定を変更](data-unification-update.md) して、統合プロファイルを再実行します。

## <a name="next-step"></a>次のステップ

[活動](activities.md)、[エンリッチメント](enrichment-hub.md)、[関連付け](relationships.md)、または[メジャー](measures.md) を構成して、顧客に関するより多くの分析情報を得ます 。

[!INCLUDE[footer-include](includes/footer-banner.md)]
