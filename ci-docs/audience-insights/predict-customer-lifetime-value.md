---
title: 顧客の生涯価値 (CLV) の予測
description: 将来のアクティブな顧客の潜在的な収益を予測します。
ms.date: 02/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 835a9f3371a8c1b1a10d5c6901c03e1df5379d3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595814"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a><span data-ttu-id="77662-103">顧客の生涯価値 (CLV) の予測 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="77662-103">Customer lifetime value (CLV) prediction (Preview)</span></span>

<span data-ttu-id="77662-104">個々のアクティブな顧客が定義済みの将来の期間を通じてビジネスにもたらす潜在的な価値 (収益) を予測します。</span><span class="sxs-lookup"><span data-stu-id="77662-104">Predict potential value (revenue) that individual active customers will bring in to your business through a defined future time period.</span></span> <span data-ttu-id="77662-105">この機能は、さまざまな目標を達成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="77662-105">This feature can help you achieve various goals:</span></span> 
- <span data-ttu-id="77662-106">価値の高い顧客を特定し、このインサイトを処理します</span><span class="sxs-lookup"><span data-stu-id="77662-106">Identify high-value customers and process this insight</span></span>
- <span data-ttu-id="77662-107">潜在的な価値に基づいて戦略的な顧客セグメントを作成し、ターゲットを絞った営業、マーケティング、およびサポートの取り組みでパーソナライズされたキャンペーンを実行します</span><span class="sxs-lookup"><span data-stu-id="77662-107">Create strategical customer segments based on their potential value to run personalized campaigns with targeted sales, marketing, and support efforts</span></span>
- <span data-ttu-id="77662-108">顧客価値を高める機能に焦点を当てて製品開発をガイドします</span><span class="sxs-lookup"><span data-stu-id="77662-108">Guide product development by focusing on features tht increase customer value</span></span>
- <span data-ttu-id="77662-109">営業またはマーケティング戦略を最適化し、顧客アウトリーチのためにより正確に予算を割り当てます</span><span class="sxs-lookup"><span data-stu-id="77662-109">Optimize sales or marketing strategy and allocate budget more accurately for customer outreach</span></span>
- <span data-ttu-id="77662-110">ロイヤルティ プログラムまたはリワード プログラムを通じて、価値の高い顧客を特定して報酬を提供します</span><span class="sxs-lookup"><span data-stu-id="77662-110">Recognize and reward high-value customers through loyalty or rewards programs</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="77662-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="77662-111">Prerequisites</span></span>

<span data-ttu-id="77662-112">始める前に、CLV がビジネスにとって何を意味するかを考えてください。</span><span class="sxs-lookup"><span data-stu-id="77662-112">Before getting started, reflect what CLV means for your business.</span></span> <span data-ttu-id="77662-113">現在、トランザクション ベースの CLV 予測をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="77662-113">Currently, we support transaction-based CLV prediction.</span></span> <span data-ttu-id="77662-114">顧客の予測値は、ビジネス トランザクションの履歴に基づいています。</span><span class="sxs-lookup"><span data-stu-id="77662-114">The predicted value of a customer is based on history of business transactions.</span></span> <span data-ttu-id="77662-115">予測を作成するには、少なくとも[共同作成者](permissions.md)アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="77662-115">To create the prediction, you need at least [Contributor](permissions.md) permissions.</span></span>

<span data-ttu-id="77662-116">CLV モデルの構成と実行にはそれほど時間がかからないため、さまざまな入力設定で複数のモデルを作成し、モデルの結果を比較して、ビジネス ニーズに最適なモデル シナリオを確認することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="77662-116">Since configuring and running a CLV model doesn't take much time, consider creating several models with varying input preferences and compare model results to see which model scenario best fits your business needs.</span></span>

###  <a name="data-requirements"></a><span data-ttu-id="77662-117">データ要件</span><span class="sxs-lookup"><span data-stu-id="77662-117">Data requirements</span></span>

<span data-ttu-id="77662-118">次のデータが必要です。オプションとしてマークされている場合、モデルのパフォーマンスを向上させるために推奨されます。</span><span class="sxs-lookup"><span data-stu-id="77662-118">The following data is required, and where marked optional, recommended for increased model performance.</span></span> <span data-ttu-id="77662-119">モデルが処理できるデータが多いほど、予測がより正確になります。</span><span class="sxs-lookup"><span data-stu-id="77662-119">The more data the model can process, the more accurate the prediction will be.</span></span> <span data-ttu-id="77662-120">したがって、可能な場合は、より多くの顧客活動データを取り込むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="77662-120">Therefore, we encourage you to ingest more customer activity data, if available.</span></span>

- <span data-ttu-id="77662-121">顧客識別子: トランザクションを個々の顧客に照合するための一意識別子</span><span class="sxs-lookup"><span data-stu-id="77662-121">Customer Identifier: Unique identifier to match transactions to an individual customer</span></span>

- <span data-ttu-id="77662-122">トランザクション履歴: 以下のセマンティック データ スキーマを含む履歴トランザクション ログ</span><span class="sxs-lookup"><span data-stu-id="77662-122">Transaction History: Historical transactions log with below semantic data schema</span></span>
    - <span data-ttu-id="77662-123">トランザクション ID: 各トランザクションの一意識別子</span><span class="sxs-lookup"><span data-stu-id="77662-123">Transaction ID: Unique identifier of each transaction</span></span>
    - <span data-ttu-id="77662-124">取引日: 日付、できれば各トランザクションのタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="77662-124">Transaction date: Date, preferably a time stamp of each transaction</span></span>
    - <span data-ttu-id="77662-125">トランザクション金額: 各トランザクションの金銭的価値 (売上や利益率など)</span><span class="sxs-lookup"><span data-stu-id="77662-125">Transaction amount: Monetary value (for example, revenue or profit margin) of each transaction</span></span>
    - <span data-ttu-id="77662-126">返品に割り当てられたラベル (オプション): トランザクションが返品であるかどうかを示すブール値</span><span class="sxs-lookup"><span data-stu-id="77662-126">Label assigned to returns (optional): Boolean value signifying whether the transaction is a return</span></span> 
    - <span data-ttu-id="77662-127">製品 ID (オプション): トランザクションに関係する製品の製品 ID</span><span class="sxs-lookup"><span data-stu-id="77662-127">Product ID (optional): Product ID of product involved in the transaction</span></span>

- <span data-ttu-id="77662-128">たとえば、追加データ (オプション)</span><span class="sxs-lookup"><span data-stu-id="77662-128">Additional data (optional), for example</span></span>
    - <span data-ttu-id="77662-129">Web アクティビティ: Web サイトの訪問履歴、メール履歴</span><span class="sxs-lookup"><span data-stu-id="77662-129">Web activities: website visit history, email history</span></span>
    - <span data-ttu-id="77662-130">ロイヤルティ活動: ロイヤルティ リワード ポイントの発生と引き換え履歴</span><span class="sxs-lookup"><span data-stu-id="77662-130">Loyalty activities: loyalty reward points accrual and redemption history</span></span>
    - <span data-ttu-id="77662-131">顧客サービス ログ、サービス コール、苦情、または返品履歴</span><span class="sxs-lookup"><span data-stu-id="77662-131">Customer service log, service call, complaint, or return history</span></span>
- <span data-ttu-id="77662-132">顧客活動に関するデータ (オプション):</span><span class="sxs-lookup"><span data-stu-id="77662-132">Data about customer activities (optional):</span></span>
    - <span data-ttu-id="77662-133">同じ種類の活動を区別する活動識別子</span><span class="sxs-lookup"><span data-stu-id="77662-133">Activity identifiers to distinguish activities of the same type</span></span>
    - <span data-ttu-id="77662-134">活動を顧客にマッピングする顧客識別子</span><span class="sxs-lookup"><span data-stu-id="77662-134">Customer identifiers to map activities to your customers</span></span>
    - <span data-ttu-id="77662-135">活動の名前と日付を含む活動情報</span><span class="sxs-lookup"><span data-stu-id="77662-135">Activity information containing the name and date of the activity</span></span>
    - <span data-ttu-id="77662-136">活動のセマンティック データ スキーマには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="77662-136">The semantic data schema for activities includes:</span></span> 
        - <span data-ttu-id="77662-137">主キー: 活動の一意識別子</span><span class="sxs-lookup"><span data-stu-id="77662-137">Primary key: A unique identifier for an activity</span></span>
        - <span data-ttu-id="77662-138">タイムスタンプ: 主キーで識別される、イベントの日時</span><span class="sxs-lookup"><span data-stu-id="77662-138">Timestamp: The date and time of the event identified by the primary key</span></span>
        - <span data-ttu-id="77662-139">イベント (活動名): 使用したいイベントの名前</span><span class="sxs-lookup"><span data-stu-id="77662-139">Event (activity name):  The name of event you want to use</span></span>
        - <span data-ttu-id="77662-140">詳細 (金額または値): 顧客活動に関する詳細</span><span class="sxs-lookup"><span data-stu-id="77662-140">Details (amount or value): Details about the customer activity</span></span>

## <a name="create-a-customer-lifetime-value-prediction"></a><span data-ttu-id="77662-141">顧客の生涯価値の予測を作成する</span><span class="sxs-lookup"><span data-stu-id="77662-141">Create a Customer Lifetime Value prediction</span></span>

1. <span data-ttu-id="77662-142">対象者に関するインサイトで、**インテリジェンス** > **予測** に移動します。</span><span class="sxs-lookup"><span data-stu-id="77662-142">In audience insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="77662-143">**顧客生涯価値** タイルを選択して、**モデルを使用する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-143">Select the **Customer lifetime value** tile and select **Use model**.</span></span> 

1. <span data-ttu-id="77662-144">**顧客生涯価値 (プレビュー)** ペインで、**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-144">In the **Customer lifetime value (preview)** pane, select **Get started**.</span></span>

1. <span data-ttu-id="77662-145">他のモデルまたはエンティティと区別するための **このモデルに名前を付ける** と **出力エンティティ名**。</span><span class="sxs-lookup"><span data-stu-id="77662-145">**Name this model** and the **Output entity name** to distinguish them from other models or entities.</span></span>

1. <span data-ttu-id="77662-146">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-146">Select **Next**.</span></span>

### <a name="define-model-preferences"></a><span data-ttu-id="77662-147">モデルの基本設定を定義する</span><span class="sxs-lookup"><span data-stu-id="77662-147">Define model preferences</span></span>

1. <span data-ttu-id="77662-148">**予測期間** を設定して、CLV を予測する期間を定義します。</span><span class="sxs-lookup"><span data-stu-id="77662-148">Set a **Prediction time period** to define how far into the future you want to predict the CLV.</span></span>    
   <span data-ttu-id="77662-149">既定では、単位は月に設定されています。</span><span class="sxs-lookup"><span data-stu-id="77662-149">By default, the unit is set as months.</span></span> <span data-ttu-id="77662-150">さらに将来の期間を延長するには、年に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="77662-150">You can change it to years to look further in the future.</span></span>

   > [!TIP]
   > <span data-ttu-id="77662-151">設定した期間の CLV を正確に予測するには、同等の期間の履歴データが必要です。</span><span class="sxs-lookup"><span data-stu-id="77662-151">To accurately predict CLV for the time period you set, you need a comparable period of historical data.</span></span> <span data-ttu-id="77662-152">たとえば、今後 12 か月の予測を行う場合は、少なくとも 18〜24 か月の履歴データを用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="77662-152">For example, if you want to predict for the next 12 months, it is recommended that you have at least 18 – 24 months of historical data.</span></span>

1. <span data-ttu-id="77662-153">**アクティブな顧客** がビジネスにとってどのような意味を持つかを指定します。</span><span class="sxs-lookup"><span data-stu-id="77662-153">Specify what **Active customers** mean for your business.</span></span> <span data-ttu-id="77662-154">顧客をアクティブと見なすには、少なくとも 1 件のトランザクションが必要である概算時間を設定します。</span><span class="sxs-lookup"><span data-stu-id="77662-154">Set the time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="77662-155">このモデルは、アクティブな顧客の CLV のみを予測します。</span><span class="sxs-lookup"><span data-stu-id="77662-155">The model will only predict CLV for active customers.</span></span> 
   - <span data-ttu-id="77662-156">**モデルで購入間隔を計算する (推奨)**: モデルはデータを分析し、過去の購入に基づいて期間を決定します。</span><span class="sxs-lookup"><span data-stu-id="77662-156">**Let model calculate purchase interval (recommended)**: The model analyzes your data and determines a time period based on historical purchases.</span></span>
   - <span data-ttu-id="77662-157">**間隔を手動で設定する**: アクティブな顧客の特定のビジネス定義がある場合、このオプションを選択し、それに応じて期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="77662-157">**Set interval manually**: If you have a specific business definition of an active customer, choose this option and set the time period accordingly.</span></span>

1. <span data-ttu-id="77662-158">**価値の高い顧客** のパーセンタイルを定義して、モデルがビジネス定義に適合する結果を提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="77662-158">Define percentile of **High-value customer** to enable the model to provide results that fit your business definition.</span></span>
    - <span data-ttu-id="77662-159">**モデル計算 (推奨)**: モデルはデータを分析し、顧客のトランザクション履歴に基づいて、ビジネスにとって価値の高い顧客が何かを判断します。</span><span class="sxs-lookup"><span data-stu-id="77662-159">**Model calculation (recommended)**: The model analyzes your data and determines what a high value customer might be for your business based on your customers’ transaction history.</span></span> <span data-ttu-id="77662-160">このモデルは、ヒューリスティック ルール (80/20 ルールまたはパレートの法則に触発された) を使用して、価値の高い顧客の割合を見つけます。</span><span class="sxs-lookup"><span data-stu-id="77662-160">The model uses a heuristic rule (inspired by the 80/20 rule or pareto principle) to find the proportion of high-value customers.</span></span> <span data-ttu-id="77662-161">過去の期間にビジネスの累積収益の 80% に貢献した顧客の割合は、価値の高い顧客と見なされます。</span><span class="sxs-lookup"><span data-stu-id="77662-161">The percentage of customers that contributed to 80% cumulative revenue for your business in the historical period are considered high-value customers.</span></span> <span data-ttu-id="77662-162">通常、30〜40% 未満の顧客は 80% の累積収益に貢献しています。</span><span class="sxs-lookup"><span data-stu-id="77662-162">Typically, less than 30-40% customers contribute to 80% cumulative revenue.</span></span> <span data-ttu-id="77662-163">ただし、この数はビジネスや業界によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="77662-163">However, this number might vary depending on your business and industry.</span></span>    
    - <span data-ttu-id="77662-164">**アクティブな顧客 (上位 %)**: ビジネスにとって価値の高い顧客を、最もアクティブな有料顧客のパーセンタイルとして定義します。</span><span class="sxs-lookup"><span data-stu-id="77662-164">**Percent of top active customers**: Define high-value customers for your business as a percentile of top active paying customers.</span></span> <span data-ttu-id="77662-165">たとえば、このオプションを使用して、価値の高い顧客を将来の有料顧客の上位 20% として定義できます。</span><span class="sxs-lookup"><span data-stu-id="77662-165">For example, you can use this option to define high-value customers as top 20% of future paying customers.</span></span>

    <span data-ttu-id="77662-166">ビジネスが別の方法で価値の高い顧客を定義している場合、[ぜひお知らせください](https://go.microsoft.com/fwlink/?linkid=2074172)。</span><span class="sxs-lookup"><span data-stu-id="77662-166">If your business defines high value customers in a different way, [let us know as we would love to hear](https://go.microsoft.com/fwlink/?linkid=2074172).</span></span>

1. <span data-ttu-id="77662-167">**次へ** を選択して、次のステップに進みます。</span><span class="sxs-lookup"><span data-stu-id="77662-167">Select **Next** to proceed to the next step.</span></span>

### <a name="add-required-data"></a><span data-ttu-id="77662-168">必須データの追加</span><span class="sxs-lookup"><span data-stu-id="77662-168">Add required data</span></span>

1. <span data-ttu-id="77662-169">**必須データ** ステップで、**顧客購入履歴** に対して **データを追加** を選択し、[前提条件](#prerequisites)に記載されているように、トランザクション/購入履歴情報を提供するエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-169">In the **Required data** step, select **Add data** for **Customer transaction history** and choose the entity that provides the transaction history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="77662-170">セマンティック フィールドを購入履歴エンティティ内の属性にマップし、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-170">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span>

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="必要なデータに対してデータ属性をマッピングするための構成ステップの画像。":::
 
1. <span data-ttu-id="77662-172">以下のフィールドが入力されていない場合は、購入履歴エンティティから *顧客* エンティティへの関係を構成して、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-172">If the fields below aren't populated, configure the relationship from your purchase history entity to the *Customer* entity and select **Save**.</span></span>
    1. <span data-ttu-id="77662-173">トランザクション履歴エンティティ を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-173">Select the transaction history entity.</span></span>
    1. <span data-ttu-id="77662-174">購入履歴エンティティで顧客を識別するフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-174">Select the field that identifies a customer in the purchase history entity.</span></span> <span data-ttu-id="77662-175">これは、顧客エンティティの主要な顧客 ID に関連している必要があります。</span><span class="sxs-lookup"><span data-stu-id="77662-175">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="77662-176">主要な顧客エンティティに一致するエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-176">Select the entity that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="77662-177">関係性を説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="77662-177">Enter a name that describes the relationship.</span></span>

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="顧客エンティティとの関係を定義するための構成ステップの画像。":::

1. <span data-ttu-id="77662-179">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-179">Select **Next**.</span></span>

### <a name="add-optional-data"></a><span data-ttu-id="77662-180">オプション データを追加する</span><span class="sxs-lookup"><span data-stu-id="77662-180">Add optional data</span></span>

<span data-ttu-id="77662-181">主要な顧客と対話を反映するデータ (Web、顧客サービス、イベント ログなど) は、トランザクション レコードにコンテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="77662-181">Data reflecting key customer interactions (like web, customer service, and event logs) adds context to transaction records.</span></span> <span data-ttu-id="77662-182">顧客活動データのパターンが多いほど、予測の精度を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="77662-182">More patterns found in your customer activity data can improve the accuracy of the predictions.</span></span> 

1. <span data-ttu-id="77662-183">**追加データ (オプション)** ステップで、**データを追加する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-183">In the **Additional data (optional)** step, select **Add data**.</span></span> <span data-ttu-id="77662-184">[前提条件](#prerequisites)に記載されているように、顧客活動情報を提供するエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-184">Choose the customer activity entity that provides the customer activity information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="77662-185">セマンティック フィールドを顧客活動エンティティ内の属性にマップし、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-185">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span>

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="追加データに対してフィールドをマッピングするための構成ステップの画像。":::

1. <span data-ttu-id="77662-187">追加する顧客活動の種類に一致する活動の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-187">Select an activity type that matches the type of customer activity you're adding.</span></span> <span data-ttu-id="77662-188">既存の活動の種類から選択するか、新しい活動の種類を追加します。</span><span class="sxs-lookup"><span data-stu-id="77662-188">Choose from existing activity types or add a new activity type.</span></span>

1. <span data-ttu-id="77662-189">顧客活動エンティティから *顧客* エンティティへの関係を構成します。</span><span class="sxs-lookup"><span data-stu-id="77662-189">Configure the relationship from your customer activity entity to the *Customer* entity.</span></span>
    
    1. <span data-ttu-id="77662-190">顧客活動テーブルで顧客を識別する フィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-190">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="77662-191">これは、*顧客* エンティティのプライマリ 顧客 ID に直接関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="77662-191">It can be directly related to the primary customer ID of your *Customer* entity.</span></span>
    1. <span data-ttu-id="77662-192">主要な *顧客* エンティティと一致する *顧客* エンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-192">Select the *Customer* entity that matches your primary *Customer* entity.</span></span>
    1. <span data-ttu-id="77662-193">関係性を説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="77662-193">Enter a name that describes the relationship.</span></span>

   :::image type="content" source="media/clv-additional-data.png" alt-text="データを追加し、入力された例を使用して活動を構成するための構成フローのステップの画像。":::

1. <span data-ttu-id="77662-195">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-195">Select **Save**.</span></span>    
    <span data-ttu-id="77662-196">含めたい他の顧客活動がある場合は、さらにデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="77662-196">Add more data if there are other customer activities you want to include.</span></span>

1. <span data-ttu-id="77662-197">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-197">Select **Next**.</span></span>

### <a name="set-update-schedule"></a><span data-ttu-id="77662-198">スケジュールの更新を設定する</span><span class="sxs-lookup"><span data-stu-id="77662-198">Set update schedule</span></span>

1. <span data-ttu-id="77662-199">**データ更新スケジュール** ステップで、最新のデータに基づいてモデルを再トレーニングする頻度を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-199">In the **Data update schedule** step, choose the frequency to retrain your model based on the latest data.</span></span> <span data-ttu-id="77662-200">この設定は、新しいデータが対象者に関するインサイトに取り込まれるときに、予測の精度を更新するために重要です。</span><span class="sxs-lookup"><span data-stu-id="77662-200">This setting is important to update the accuracy of predictions as new data is ingested in audience insights.</span></span> <span data-ttu-id="77662-201">多くの企業は、月に1度再トレーニングして、予測の精度を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="77662-201">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="77662-202">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-202">Select **Next**.</span></span>


### <a name="review-and-run-the-model-configuration"></a><span data-ttu-id="77662-203">モデル構成を確認して実行します</span><span class="sxs-lookup"><span data-stu-id="77662-203">Review and run the model configuration</span></span>

1. <span data-ttu-id="77662-204">**モデルの詳細を確認します** ステップで、予測の構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="77662-204">In the **Review your model details** step, validate the configuration of the prediction.</span></span> <span data-ttu-id="77662-205">表示された値の配下の **編集する** を選択して、予測の構成の任意の部分に戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="77662-205">You can go back to any part of the prediction configuration by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="77662-206">進行状況のインジケーターから構成ステップを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="77662-206">You can also select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="77662-207">すべての値が正しく構成されている場合は、**保存して実行** を選択して、モデルの実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="77662-207">If all values are configured correctly, select **Save and run** to start running the model.</span></span> <span data-ttu-id="77662-208">**自分の予測** タブで、予測プロセスのステータスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="77662-208">On the **My predictions** tab, you can see the status of the prediction process.</span></span> <span data-ttu-id="77662-209">予測で使用されるデータの量によっては、プロセスの完了までに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="77662-209">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-prediction-status-and-results"></a><span data-ttu-id="77662-210">予測の状態と結果のレビュー</span><span class="sxs-lookup"><span data-stu-id="77662-210">Review prediction status and results</span></span>

### <a name="review-prediction-status"></a><span data-ttu-id="77662-211">予測ステータスをレビューする</span><span class="sxs-lookup"><span data-stu-id="77662-211">Review prediction status</span></span>

1.  <span data-ttu-id="77662-212">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-212">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2.  <span data-ttu-id="77662-213">レビューする予測を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-213">Select the prediction you want to review.</span></span>

- <span data-ttu-id="77662-214">**予測名**: 作成時に提供された予測の名前。</span><span class="sxs-lookup"><span data-stu-id="77662-214">**Prediction name**: Name of the prediction provided when creating it.</span></span>
- <span data-ttu-id="77662-215">**予測の種類**: 予測に使用されるモデルの種類</span><span class="sxs-lookup"><span data-stu-id="77662-215">**Prediction type**: Type of model used for the prediction</span></span>
- <span data-ttu-id="77662-216">**出力エンティティ**: 予測の結果を保管するエンティティの名前。</span><span class="sxs-lookup"><span data-stu-id="77662-216">**Output entity**: Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="77662-217">**データ** > **エンティティ** に移動して、この名前のエンティティを検索します。</span><span class="sxs-lookup"><span data-stu-id="77662-217">Go to **Data** > **Entities** to find the entity with this name.</span></span>
- <span data-ttu-id="77662-218">**予測フィールド**: このフィールドは、一部の種類の予測に対してのみ入力され、顧客の生涯価値では使用されません。</span><span class="sxs-lookup"><span data-stu-id="77662-218">**Predicted field**: This field is populated only for some types of predictions, and isn't used in customer lifetime value prediction.</span></span>
- <span data-ttu-id="77662-219">**状態**: 予測実行の状態。</span><span class="sxs-lookup"><span data-stu-id="77662-219">**Status**: Status of the prediction run.</span></span>
    - <span data-ttu-id="77662-220">**キュー**: 予測は、他のプロセスが完了されるのを待っています。</span><span class="sxs-lookup"><span data-stu-id="77662-220">**Queued**: Prediction is waiting for other processes to complete.</span></span>
    - <span data-ttu-id="77662-221">**更新**: 予測は現在、実行されており、出力エンティティに流れ込む結果を作成します。</span><span class="sxs-lookup"><span data-stu-id="77662-221">**Refreshing**: Prediction is currently running to create results that will flow into the output entity.</span></span>
    - <span data-ttu-id="77662-222">**失敗**: 予測の実行に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="77662-222">**Failed**: Prediction run has failed.</span></span> <span data-ttu-id="77662-223">詳細については、[ログを確認](#troubleshoot-a-failed-prediction) します。</span><span class="sxs-lookup"><span data-stu-id="77662-223">[Review the logs](#troubleshoot-a-failed-prediction) for more details.</span></span>
    - <span data-ttu-id="77662-224">**成功**: 予測は成功しました。</span><span class="sxs-lookup"><span data-stu-id="77662-224">**Succeeded**: Prediction has succeeded.</span></span> <span data-ttu-id="77662-225">縦の省略記号の下で **表示** を選択して、予測の結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="77662-225">Select **View** under the vertical ellipses to review the prediction results.</span></span>
- <span data-ttu-id="77662-226">**編集日**: 予測の構成が変更された日付。</span><span class="sxs-lookup"><span data-stu-id="77662-226">**Edited**: The date the configuration for the prediction was changed.</span></span>
- <span data-ttu-id="77662-227">**最終更新日**: 予測結果が出力エンティティで更新された日付。</span><span class="sxs-lookup"><span data-stu-id="77662-227">**Last refreshed**: The date the prediction refreshed results in the output entity.</span></span>


### <a name="review-prediction-results"></a><span data-ttu-id="77662-228">予測の結果をレビューする</span><span class="sxs-lookup"><span data-stu-id="77662-228">Review prediction results</span></span>

1. <span data-ttu-id="77662-229">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-229">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="77662-230">結果をレビューする予測を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-230">Select the prediction you want to review results for.</span></span>

<span data-ttu-id="77662-231">結果ページには、3 つの主要なデータ セクションがあります。</span><span class="sxs-lookup"><span data-stu-id="77662-231">There are three primary sections of data within the results page.</span></span>

- <span data-ttu-id="77662-232">**トレーニング モデルのパフォーマンス**: A、B、または C が可能なグレードです。</span><span class="sxs-lookup"><span data-stu-id="77662-232">**Training model performance**: A, B, or C are possible grades.</span></span> <span data-ttu-id="77662-233">このグレードは、予測のパフォーマンスを示し、出力エンティティに保管されている結果を使用するかどうかを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="77662-233">This grade indicates the performance of the prediction and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="77662-234">**このスコアの詳細** を選択して、基礎となるモデルのパフォーマンス メトリックと、最終的なモデルのパフォーマンス グレードがどのように導き出されたかの理解を深めます。</span><span class="sxs-lookup"><span data-stu-id="77662-234">Select **Learn about this score** to better understand the underlying model performance metrics and how the final model performance grade was derived.</span></span>
  
  :::image type="content" source="media/clv-model-score.png" alt-text="グレード A のモデル スコア情報ボックスの画像。":::

  <span data-ttu-id="77662-236">予測の構成中に提供された価値の高い顧客の定義を使用して、システムは、ベースライン モデルと比較して価値の高い顧客を予測する際に AI モデルがどのように機能したかを評価します。</span><span class="sxs-lookup"><span data-stu-id="77662-236">Using the definition of high value customers provided while configuring the prediction, the system assess how the AI model performed in predicting the high value customers as compared to a baseline model.</span></span>    

  <span data-ttu-id="77662-237">グレードは次のルールに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="77662-237">Grades are determined based on the following rules:</span></span>
  - <span data-ttu-id="77662-238">モデルが価値の高い顧客を正確に予測した割合が、ベースライン モデルより少なくとも 5% 高い場合は A。</span><span class="sxs-lookup"><span data-stu-id="77662-238">A when the model accurately predicted at least 5% more high-value customers as compared to the baseline model.</span></span>
  - <span data-ttu-id="77662-239">モデルが価値の高い顧客を正確に予測した割合が、ベースライン モデルより 0～5% 高い場合は B。</span><span class="sxs-lookup"><span data-stu-id="77662-239">B when the model accurately predicted between 0-5% more high-value customers as compared to the baseline model.</span></span>
  - <span data-ttu-id="77662-240">モデルが価値の高い顧客を正確に予測した率がベースライン モデルより低い場合は C。</span><span class="sxs-lookup"><span data-stu-id="77662-240">C when the model accurately predicted fewer high-value customers as compared to the baseline model.</span></span>

  <span data-ttu-id="77662-241">**モデルの評価** ペインには、AI モデルのパフォーマンスとベースライン モデルに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="77662-241">The **Model rating** pane shows further details about the AI model performance and the baseline model.</span></span> <span data-ttu-id="77662-242">ベースライン モデルは、非 AI ベースのアプローチを使用して、主に顧客による過去の購入に基づいて顧客生涯価値を計算します。</span><span class="sxs-lookup"><span data-stu-id="77662-242">The baseline model uses a non-AI based approach to calculate customer lifetime value based primarily on historical purchases made by customers.</span></span>     
  <span data-ttu-id="77662-243">ベースライン モデルによる CLV の計算に使用される標準式:</span><span class="sxs-lookup"><span data-stu-id="77662-243">The standard formula used to calculate CLV by the baseline model:</span></span>    

  <span data-ttu-id="77662-244">*各顧客の CLV =アクティブな顧客ウィンドウで顧客が行った平均月間購入 x CLV 予測期間の月数 x すべての顧客の全体的な保持率*</span><span class="sxs-lookup"><span data-stu-id="77662-244">*CLV for each customer = Average monthly purchase made by the customer in the active customer window \* Number of months in the CLV prediction period \* Overall retention rate of all customers*</span></span>

  <span data-ttu-id="77662-245">AI モデルは、2 つのモデルパフォーマンス メトリックに基づいてベースライン モデルと比較されます。</span><span class="sxs-lookup"><span data-stu-id="77662-245">The AI model is compared to the baseline model based on two model performance metrics.</span></span>
  
  - <span data-ttu-id="77662-246">**価値の高い顧客の予測を行う際の成功率**</span><span class="sxs-lookup"><span data-stu-id="77662-246">**Success rate in predicting high-value customers**</span></span>

    <span data-ttu-id="77662-247">AI モデルを使用して、ベースライン モデルと比較したときの、価値の高い顧客を予測する際の違いを確認してください。</span><span class="sxs-lookup"><span data-stu-id="77662-247">See the difference in predicting high-value customers using the AI model compared to the baseline model.</span></span> <span data-ttu-id="77662-248">たとえば、成功率 84% は、トレーニング データ内のすべての価値の高い顧客のうち、AI モデルが 84% を正確にキャプチャできたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="77662-248">For example, 84% success rate means that out of all the high-value customers in the training data, the AI model was able to accurately capture 84%.</span></span> <span data-ttu-id="77662-249">次に、この成功率をベースライン モデルの成功率と比較して、相対的な変化を報告します。</span><span class="sxs-lookup"><span data-stu-id="77662-249">We then compare this success rate with the success rate of the baseline model to report the relative change.</span></span> <span data-ttu-id="77662-250">この値は、モデルにグレードを割り当てるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="77662-250">This value is used to assign a grade to the model.</span></span>

  - <span data-ttu-id="77662-251">**エラー指標**</span><span class="sxs-lookup"><span data-stu-id="77662-251">**Error metrics**</span></span>
    
    <span data-ttu-id="77662-252">別のメトリックを使用すると、将来の値を予測する際のエラーの観点からモデルの全体的なパフォーマンスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="77662-252">Another metric lets you review the overall performance of the model in terms of error in predicting future values.</span></span> <span data-ttu-id="77662-253">このエラーを評価するために、全体的な二乗平均平方根誤差 (RMSE) メトリックを使用します。</span><span class="sxs-lookup"><span data-stu-id="77662-253">We use the overall Root Mean Squared Error (RMSE) metric to assess this error.</span></span> <span data-ttu-id="77662-254">RMSE は、定量的データを予測する際のモデルの誤差を測定するための標準的な方法です。</span><span class="sxs-lookup"><span data-stu-id="77662-254">RMSE is a standard way to measure the error of a model in predicting quantitative data.</span></span> <span data-ttu-id="77662-255">AI モデルの RMSE がベースライン モデルの RMSE と比較され、相対的な差異が報告されます。</span><span class="sxs-lookup"><span data-stu-id="77662-255">The AI model’s RMSE is compared to the RMSE of the baseline model and the relative difference is reported.</span></span>

  <span data-ttu-id="77662-256">AI モデルは、顧客がビジネスにもたらす価値に応じて、顧客の正確なランキングを優先します。</span><span class="sxs-lookup"><span data-stu-id="77662-256">The AI model prioritizes the accurate ranking of customers according to the value they bring to your business.</span></span> <span data-ttu-id="77662-257">したがって、価値の高い顧客を予測する成功率のみを使用して、最終的なモデルのグレードを導き出します。</span><span class="sxs-lookup"><span data-stu-id="77662-257">So only the success rate of predicting high-value customers is used to derive the final model grade.</span></span> <span data-ttu-id="77662-258">RMSE メトリックは、外れ値に敏感です。</span><span class="sxs-lookup"><span data-stu-id="77662-258">The RMSE metric is sensitive to outliers.</span></span> <span data-ttu-id="77662-259">購入額が非常に高い顧客の割合が少ないシナリオでは、全体的な RMSE メトリックがモデルのパフォーマンスの全体像を示していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="77662-259">In scenarios where you have a small percentage of customers with extraordinarily high purchase values, the overall RMSE metric might not give the full picture of the model performance.</span></span>   

- <span data-ttu-id="77662-260">**パーセンタイルごとの顧客の値**: 価値の高い顧客の定義を使用して、顧客は CLV 予測に基づいて価値の低い顧客と価値の高い顧客にグループ化され、グラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="77662-260">**Value of customers by percentile**: Using your definition of high-value customers, customers are grouped into low-value and high-value, based on their CLV predictions, and shown in a chart.</span></span> <span data-ttu-id="77662-261">ヒストグラムのバーにカーソルを合わせると、各グループの顧客数とそのグループの平均 CLV を確認できます。</span><span class="sxs-lookup"><span data-stu-id="77662-261">By hovering over the bars in the histogram, you can see the number of customers in each group and the average CLV of that group.</span></span> <span data-ttu-id="77662-262">このデータは、CLV 予測に基づいて[顧客のセグメントを作成する](segments.md)際に有用です。</span><span class="sxs-lookup"><span data-stu-id="77662-262">This data can help if you want to [create segments of customers](segments.md) based on their CLV predictions.</span></span>

- <span data-ttu-id="77662-263">**最も影響力の大きい係数**: AI モデルに提供された入力データに基づいて CLV 予測を作成する際には、さまざまな係数が考慮されます。</span><span class="sxs-lookup"><span data-stu-id="77662-263">**Most influential factors**: Various factors are considered when creating your CLV prediction based on the input data provided to the AI model.</span></span> <span data-ttu-id="77662-264">各要素の重要度は、モデルが作成する集約された予測に対して計算されます。</span><span class="sxs-lookup"><span data-stu-id="77662-264">Each of the factors has their importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="77662-265">これらの係数を使用すると、予測結果を検証するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="77662-265">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="77662-266">これらの係数が、すべての顧客の CLV の予測に貢献した最も影響の大きい係数について提供するインサイトも増加します。</span><span class="sxs-lookup"><span data-stu-id="77662-266">These factors also provide more insight about the most influential factors that contributed towards predicting CLV across all your customers.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="77662-267">予測を更新する</span><span class="sxs-lookup"><span data-stu-id="77662-267">Refresh a prediction</span></span>

<span data-ttu-id="77662-268">予測は、設定で構成したものと同じ[スケジュール](system.md#schedule-tab)でデータを自動更新します。</span><span class="sxs-lookup"><span data-stu-id="77662-268">Predictions automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="77662-269">手動で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="77662-269">You can refresh them manually too.</span></span>

1. <span data-ttu-id="77662-270">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-270">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2. <span data-ttu-id="77662-271">更新する予測の横に配置されている縦型の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-271">Select the vertical ellipses next to the prediction you want to refresh.</span></span>
3. <span data-ttu-id="77662-272">**最新の情報に更新** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-272">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="77662-273">予測を削除する</span><span class="sxs-lookup"><span data-stu-id="77662-273">Delete a prediction</span></span>

<span data-ttu-id="77662-274">予測を削除すると、その出力エンティティも削除されます。</span><span class="sxs-lookup"><span data-stu-id="77662-274">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="77662-275">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-275">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2. <span data-ttu-id="77662-276">削除する予測の横に配置されている縦型の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-276">Select the vertical ellipses next to the prediction you want to delete.</span></span>
3. <span data-ttu-id="77662-277">**削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-277">Select **Delete**.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="77662-278">失敗した予測のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="77662-278">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="77662-279">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-279">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>
2. <span data-ttu-id="77662-280">エラー ログを表示する予測の横にある縦の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-280">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>
3. <span data-ttu-id="77662-281">**ログ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77662-281">Select **Logs**.</span></span>
4. <span data-ttu-id="77662-282">すべてのエラーをレビューします。</span><span class="sxs-lookup"><span data-stu-id="77662-282">Review all the errors.</span></span> <span data-ttu-id="77662-283">発生するエラーにはいくつかの種類があり、どのような状態でエラーが発生したかを記載しています。</span><span class="sxs-lookup"><span data-stu-id="77662-283">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="77662-284">たとえば、正確に予測するのに十分なデータがないというエラーは、通常、対象者インサイトに追加データをロードすることで解決されます。</span><span class="sxs-lookup"><span data-stu-id="77662-284">For example, an error that there's not enough data to accurately predict is typically resolved by loading more data into audience insights.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]