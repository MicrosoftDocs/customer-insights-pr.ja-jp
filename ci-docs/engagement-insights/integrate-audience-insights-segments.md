---
title: 対象ユーザー インサイトのセグメントを使用して、エンゲージメント インサイトのレポートをフィルターする
description: 対象ユーザー インサイトのセグメントを利用して、エンゲージメント インサイトで取得した顧客の Web サイト上の行動データをインタラクティブに分析します。
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230492"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>対象ユーザー インサイトのセグメントを使用して、エンゲージメント インサイトのレポートをフィルターする

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

エンゲージメント インサイトでは、エンゲージメント インサイトで取得した Web サイト上の行動データをインタラクティブに分析する際に、対象ユーザー インサイトのセグメントを使用できます。

## <a name="prerequisite"></a>前提条件

- 対象ユーザー インサイトのセグメント データがリンクされているエンゲージメント インサイト環境で、セグメントと顧客プロファイルが作成されます。 詳細情報: [対象ユーザー インサイトとエンゲージメント インサイトの間にリンクを作成する](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>対象者インサイトのセグメントを作成する 

> [!IMPORTANT]
> 対象ユーザー インサイトのセグメントがエンゲージメント インサイトに表示するには、まず[マージとダウンストリームのプロセスを実行する](../audience-insights/merge-entities.md)必要があります。 ダウンストリームのプロセスでは、対象ユーザー インサイトのセグメントをエンゲージメント インサイトと共有するための固有のテーブルを生成することが重要です。 (システムの更新がスケジュールされている場合、自動的にダウンストリームのプロセスが含まれます。)

対象ユーザー セグメントは、エンゲージメント インサイトの既成のレポート、または作成したカスタム レポートで使用できます。 詳細については、[既成のプロファイル レポート](profile-reports.md)と[カスタム レポートの作成と編集](custom-reports.md)にアクセスしてください。

**対象ユーザー インサイトのセグメントを使用して、エンゲージメント インサイトのレポートをフィルターする方法**

1. ご利用の **ワークスペース** ページで、**データ** を選択し、続いて **セグメント** タブを選択します。

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="セグメント タブを選択する。":::

   >[!NOTE]
   > 対象ユーザー インサイトのセグメントを選択すると、対象ユーザー インサイトが表示され、そのセグメントがどのように作成されたのかを表わすルールやロジックを確認することができます。 対象ユーザー インサイト セグメントの詳細については、[セグメントの表示と作成](../audience-insights/segments.md)にアクセスしてください。

2. 既成のレポート、または [カスタム レポートの作成](custom-reports.md)を選択し、続いて **条件の追加** を選択します。 (この例では、**ページ ビュー** レポートを選択します。)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="条件を追加します。":::

3. **セグメントでフィルター** を選択し、**セグメント タイプ** のリストを展開し、**人口統計** を選択します。

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="人口統計セグメント タイプを選択します。":::

4. **セグメント名** リストを展開し、対象ユーザー インサイトのセグメントを選択します。

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="セグメントの選択。":::

5. 行動 (エンゲージメント インサイト) や人口統計 (対象ユーザー インサイト) のセグメントなど、1 つ以上のセグメントを適用することができます。 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="ページ ビュー レポートは、米国の顧客とホームページ セグメントに限定されています。":::

前述の画像では、**米国の顧客** と **ホームページ** セグメントが選択されているため、**ページビュー** レポートではこれら 2 つのセグメントのみが表示されます。 


>[!NOTE]
> 対象ユーザー インサイトのセグメントを使用して、エンゲージメント インサイトの標準レポート、カスタム レポート、ファンネルをフィルターできます。 


[!INCLUDE[footer-include](../includes/footer-banner.md)]