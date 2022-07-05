---
title: 予測モデルに基づいてセグメントを作成する
description: 予測モデルの出力エンティティに基づいてセグメントを作成します。
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: d67594f2467c1a0fde84b1ba0bd1afa4025e7b71
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081381"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>予測モデルに基づいたセグメントの作成 (プレビュー)

予測の結果は、顧客のサブセットにのみ適用される場合があります。 予測モデルの結果からセグメントを作成することで、推奨事項のパーソナライズが向上します。 たとえば、特定の種類のサービスを希望する顧客に特定の推奨事項を提供する場合があります。 

## <a name="prerequisites"></a>前提条件

- 少なくとも Customer Insights の[共同作成者権限](permissions.md) があること。

- Customer Insights で構成された製品推奨、トランザクション離反、サブスクリプション離反、または顧客生涯価値モデル。 さまざまなモデルを設定するための要件を確認します:

  - [製品推奨モデル](predict-product-recommendation.md)
  - [サブスクリプション離反モデル](predict-subscription-churn.md)
  - [トランザクション離反モデル](predict-transactional-churn.md)
  - [顧客の生涯価値モデル](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>予測に基づいて顧客セグメントを作成する

1. **インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。

1. 確認するモデルの横にある垂直方向の省略記号を選択して、**ビュー** を選択します。

1. 結果ページで **セグメントの作成** を選択します。 結果ページの詳細については、モデルに関する記事を確認してください。

   :::image type="content" source="media/prediction-create-segment.png" alt-text="セグメントの作成アクションが強調表示された予測結果ページのスクリーンショット。":::

1. 選択されたモデルの出力エンティティに基づいて新しいセグメントを作成します。 詳細については、[セグメントの作成と管理](segments.md) をご覧ください。