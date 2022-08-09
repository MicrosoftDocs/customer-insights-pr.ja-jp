---
title: クイック セグメントを使用した単純なセグメントの作成
description: 顧客の簡単なセグメントを作成して、さまざまな属性に基づいてグループ化します。
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171137"
---
# <a name="create-simple-segments-with-quick-segments"></a>クイック セグメントを使用した単純なセグメントの作成

クイック セグメントでは、1 つの演算子で簡単なセグメントをすばやく作成して、より迅速なインサイトを得ることができます。 クイック セグメントは、**個人の顧客** の環境でのみサポートされます。

## <a name="create-a-new-segment-with-quick-segments"></a>クイック セグメントを使用して新しいセグメントを作成する

1. **セグメント** に移動します。

1. **新規** > **作成元** を選択します。
   - **プロファイル** オプションを選択して、*統合された顧客* エンティティに基づくセグメントを構築します。
   - **メジャー** オプションを選択して、以前に作成したメジャーに対してセグメントを構築します。
   - **インテリジェンス** オプションを選択して、**予測** または **カスタム モデル** 機能のいずれかを使用して生成した出力エンティティの 1 つにセグメントを構築します。

1. **新規簡易セグメント** ダイアログ ボックスで、**フィールド** ドロップダウンから属性を選択します。 選択に基づいて、システムはさまざまな値を提供します。
   - カテゴリ フィールドに対しては、上位 10 件の顧客数が表示されます。 **値** を選択して、**レビュー** を選択します。
   - 数値属性の場合、システムは各顧客のパーセンタイルに該当する属性値を表示します。 **演算子** と **値** を選択して、次に **レビュー** を選択します。

1. システムは、**推定セグメント サイズ** を提供します。 定義したセグメントを生成するか、戻って別のフィールドを選択します。

   :::image type="content" source="media/quick-segment-name.png" alt-text="クイック セグメントの名前と見積もり。":::

1. セグメントに **名前** と **出力エンティティ名** を指定します。 必要に応じて、[タグ](work-with-tags-columns.md#manage-tags)を追加します。

1. **保存** を選択して、セグメントを作成します。 **セグメント** ページが表示されます。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>次の手順

[セグメントをエクスポート](export-destinations.md)して、[カスタマー カードとの統合](customer-card-add-in.md)を確認し、他のアプリケーションでセグメントを使用することができます。

[!INCLUDE [footer-include](includes/footer-banner.md)]
