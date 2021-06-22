---
title: サポートされている予測シナリオの概要
description: Dynamics 365 Customer Insights アプリケーションで対応する予測シナリオとオプション。
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095723"
---
# <a name="predictions-overview"></a><span data-ttu-id="d0771-103">予測の概要</span><span class="sxs-lookup"><span data-stu-id="d0771-103">Predictions overview</span></span>

<span data-ttu-id="d0771-104">Dynamics 365 Customer Insights には、AI や機械学習を活用してデータを予測するさまざまなオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d0771-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="d0771-105">標準モデル</span><span class="sxs-lookup"><span data-stu-id="d0771-105">Out-of-box models</span></span>

<span data-ttu-id="d0771-106">データの予測を開始する最も簡単な方法は、事前定義されたモデルであり、多くの場合、標準モデルと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d0771-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="d0771-107">特定のデータと構造があれば、インサイトをすばやく生成することができます。</span><span class="sxs-lookup"><span data-stu-id="d0771-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="d0771-108">現在、以下のモデルが使用可能です:</span><span class="sxs-lookup"><span data-stu-id="d0771-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="d0771-109">[顧客の生涯価値](predict-customer-lifetime-value.md): ビジネスとのやり取り全体を通じて、顧客の潜在的な売上を予測します。</span><span class="sxs-lookup"><span data-stu-id="d0771-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="d0771-110">[製品推奨](predict-product-recommendation.md): 購入行動や類似の購入パターンを持つ顧客に基づいて、予測製品推奨セットを提案します。</span><span class="sxs-lookup"><span data-stu-id="d0771-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="d0771-111">[サブスクリプション離反](predict-subscription-churn.md): 顧客が自社のサブスクリプション製品やサービスを使用しなくなるリスクがあるかどうかを予測します。</span><span class="sxs-lookup"><span data-stu-id="d0771-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="d0771-112">[トランザクション離反](predict-transactional-churn.md): 顧客が一定期間内に製品やサービスを購入しなくなるかどうかを予測します。</span><span class="sxs-lookup"><span data-stu-id="d0771-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="d0771-113">Azure Machine Learning 統合</span><span class="sxs-lookup"><span data-stu-id="d0771-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="d0771-114">組織が既に Azure Machine Learning の実験に基づく機械学習シナリオを使用している場合、Customer Insights のカスタム モデル機能はドットを関連付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d0771-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="d0771-115">インサイトを生成するデータの選択に役立つワークフローを作成し、結果を統合された顧客プロファイルにマップします。</span><span class="sxs-lookup"><span data-stu-id="d0771-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="d0771-116">詳細については、[カスタム機械学習モデル](custom-models.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0771-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="d0771-117">AI Builder の予測</span><span class="sxs-lookup"><span data-stu-id="d0771-117">AI Builder prediction</span></span>

<span data-ttu-id="d0771-118">データ セットが不完全で、一部の値が欠落している場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0771-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="d0771-119">Customer Insights は、顧客エンティティとセグメントの不足している値を予測するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d0771-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="d0771-120">詳細については、[予測を使用した部分データの完成](predictions.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0771-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
