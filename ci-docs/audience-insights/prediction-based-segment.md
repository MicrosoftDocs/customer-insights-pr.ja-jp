---
title: 予測出力に基づくセグメント
description: 予測モデルの出力エンティティに基づいてセグメントを作成します。
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741435"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="d7cf1-103">予測モデルに基づいたセグメントの作成 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d7cf1-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="d7cf1-104">予測の結果は、顧客のサブセットにのみ適用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d7cf1-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="d7cf1-105">予測モデルの結果からセグメントを作成することで、推奨事項のパーソナライズが向上します。</span><span class="sxs-lookup"><span data-stu-id="d7cf1-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="d7cf1-106">たとえば、特定の種類のサービスを希望する顧客に特定の推奨事項を提供する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d7cf1-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d7cf1-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="d7cf1-107">Prerequisites</span></span>

- <span data-ttu-id="d7cf1-108">少なくとも Customer Insights の[共同作成者権限](permissions.md) があること。</span><span class="sxs-lookup"><span data-stu-id="d7cf1-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="d7cf1-109">Customer Insights で構成された製品推奨、トランザクション離反、サブスクリプション離反、または顧客生涯価値モデル。</span><span class="sxs-lookup"><span data-stu-id="d7cf1-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="d7cf1-110">さまざまなモデルを設定するための要件を確認します:</span><span class="sxs-lookup"><span data-stu-id="d7cf1-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="d7cf1-111">製品推奨モデル</span><span class="sxs-lookup"><span data-stu-id="d7cf1-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="d7cf1-112">サブスクリプション離反モデル</span><span class="sxs-lookup"><span data-stu-id="d7cf1-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="d7cf1-113">トランザクション離反モデル</span><span class="sxs-lookup"><span data-stu-id="d7cf1-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="d7cf1-114">顧客の生涯価値モデル</span><span class="sxs-lookup"><span data-stu-id="d7cf1-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="d7cf1-115">予測に基づいて顧客セグメントを作成する</span><span class="sxs-lookup"><span data-stu-id="d7cf1-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="d7cf1-116">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d7cf1-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d7cf1-117">確認するモデルの横にある垂直方向の省略記号を選択して、**ビュー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d7cf1-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="d7cf1-118">結果ページで **セグメントの作成** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d7cf1-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="d7cf1-119">結果ページの詳細については、モデルに関する記事を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d7cf1-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="セグメントの作成アクションが強調表示された予測結果ページのスクリーンショット。":::

1. <span data-ttu-id="d7cf1-121">選択されたモデルの出力エンティティに基づいて新しいセグメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="d7cf1-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="d7cf1-122">詳細については、[セグメントの作成と管理](segments.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d7cf1-122">For more information, see [Create and manage segments](segments.md).</span></span>