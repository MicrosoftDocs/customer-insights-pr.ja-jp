---
title: 人口統計ディメンションを使用して行動データを分割する (キュレーションされたディメンション)
description: 統一されたプロファイルのキュレーション ディメンションを使用して、対象ユーザーインサイトの顧客プロファイル プロパティを有効にします。
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "8233053"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>人口統計ディメンションを使用して行動データを分割する

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

統一されたプロファイルの人口統計ディメンションを使用することで、エンゲージメント インサイトのユーザーは、対象ユーザーインサイトのプロファイル プロパティにアクセスできます。 これらのプロパティは、Web サイトやモバイル アプリのエンゲージメント インサイトで取得したデータを含む行動データのインタラクティブな分析に使用することができます。

>[!NOTE]
> エンゲージメント インサイトには、イベント プロパティのすぐに使用できる分析コードが含まれます。 詳細情報: [ディメンションの表示と作成](dimensions.md)

## <a name="prerequisite"></a>前提条件

- 顧客プロファイルデータがあるエンゲージメント インサイト環境と、顧客プロファイルが作成される対象ユーザーインサイト環境がリンクされています。 詳細情報: [対象ユーザー インサイトとエンゲージメント インサイトの間にリンクを作成する](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> 対象ユーザーインサイトとエンゲージメント インサイトの環境間のリンクを作成した後、エンゲージメント インサイトのディメンションとして有用な顧客プロファイルのプロパティに特化したデータのみを必要とする場合があります。 詳細については、[対象ユーザー インサイトの統合プロファイルの属性とセグメントを有効にする](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments)にアクセスしてください。

## <a name="create-a-new-custom-report"></a>新しいカスタム レポートを作成する

1. 左側のペインで、**カスタム** > **新しいレポート** を選択し、次に必要なメトリックを選択します。 (この例では、**時間別のページ ビュー** を選択しています。)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="指標を選択する。":::

2. 視覚化エディターで、**ディメンション** を選択し、続いて **ディメンション タイプ** ドロップダウン メニューの **人口統計** を選択します。

    :::image type="content" source="media/curated-dimensions2.png" alt-text="人口統計を選択します。":::

3. **Signal.Customer.*xxx*** ディメンションを選択します。 (この例では Signal.Customer.Country を表示しています。)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="ディメンションを選択する。":::
  
## <a name="limitations"></a>制限

現在、行動データの分割に使用できるのは、人口統計ディメンションのみです。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
