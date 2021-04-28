---
title: トランザクション解約予測
description: 顧客が製品やサービスを購入しなくなるリスクがあるかどうかを予測します。
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 43fcd37f8dd71e2890334a4cc53d49dae97d63c6
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906862"
---
# <a name="transactional-churn-prediction-preview"></a><span data-ttu-id="4925d-103">トランザクション解約予測 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="4925d-103">Transactional churn prediction (preview)</span></span>

<span data-ttu-id="4925d-104">トランザクション解約予測は、顧客が特定の時間枠内に製品またはサービスを購入しなくなるかどうかを予測するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4925d-104">Transactional churn prediction helps predict if a customer will no longer purchase your products or services in a given time window.</span></span> <span data-ttu-id="4925d-105">**インテリジェンス** > **予測** で新しい解約予測を作成できます。</span><span class="sxs-lookup"><span data-stu-id="4925d-105">You can create new churn predictions on **Intelligence** > **Predictions**.</span></span> <span data-ttu-id="4925d-106">作成済みの予測を確認するには、**自分の予測** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-106">Select **My predictions** to see other predictions that you've created.</span></span>

> [!TIP]
> <span data-ttu-id="4925d-107">サンプル データを使用して、トランザクション解約予測のチュートリアルを試してみてください: [トランザクション解約予測サンプル ガイド](sample-guide-predict-transactional-churn.md)。</span><span class="sxs-lookup"><span data-stu-id="4925d-107">Try the tutorial for a translactional churn prediction using sample data: [Transactional churn prediction (preview) sample guide](sample-guide-predict-transactional-churn.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4925d-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="4925d-108">Prerequisites</span></span>

- <span data-ttu-id="4925d-109">少なくとも Customer Insights の[共同作成者権限](permissions.md) があること。</span><span class="sxs-lookup"><span data-stu-id="4925d-109">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="4925d-110">ビジネスにとっての解約の意味を理解するためのビジネス知識。</span><span class="sxs-lookup"><span data-stu-id="4925d-110">Business knowledge to understand what churn means for your business.</span></span> <span data-ttu-id="4925d-111">時間ベースの解約定義をサポートします。つまり、顧客は購入がない期間の後に解約したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="4925d-111">We support time-based churn definitions, meaning a customer is considered to have churned after a period of no purchases.</span></span>
- <span data-ttu-id="4925d-112">トランザクション/購入とその履歴に関するデータ:</span><span class="sxs-lookup"><span data-stu-id="4925d-112">Data about your transactions/purchases and their history:</span></span>
    - <span data-ttu-id="4925d-113">購入/トランザクションを区別するためのトランザクション識別子。</span><span class="sxs-lookup"><span data-stu-id="4925d-113">Transaction identifiers to distinguish purchases/transactions.</span></span>
    - <span data-ttu-id="4925d-114">トランザクションを顧客に一致させるための顧客 ID。</span><span class="sxs-lookup"><span data-stu-id="4925d-114">Customer identifiers to match transactions to your customers.</span></span>
    - <span data-ttu-id="4925d-115">トランザクションが発生した日付を定義するトランザクション イベントの日付。</span><span class="sxs-lookup"><span data-stu-id="4925d-115">Transaction event dates, which define the dates the transaction occurred on.</span></span>
    - <span data-ttu-id="4925d-116">購入/トランザクションのセマンティック データ スキーマには、次の情報が必要です:</span><span class="sxs-lookup"><span data-stu-id="4925d-116">The semantic data schema for purchases/transactions requires the following information:</span></span>
        - <span data-ttu-id="4925d-117">**トランザクション ID:** 購入またはトランザクションの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="4925d-117">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="4925d-118">**トランザクションの日付:** 購入またはトランザクションの日付。</span><span class="sxs-lookup"><span data-stu-id="4925d-118">**Transaction Date:** The date of the purchase or transaction.</span></span>
        - <span data-ttu-id="4925d-119">**トランザクションの値:** トランザクション/品目の通貨/数値。</span><span class="sxs-lookup"><span data-stu-id="4925d-119">**Value of the transaction:** The currency/numerical value amount of the transaction/item.</span></span>
        - <span data-ttu-id="4925d-120">(オプション) **一意の製品 ID:** データが品目レベルの場合に購入した製品またはサービスの ID。</span><span class="sxs-lookup"><span data-stu-id="4925d-120">(Optional) **Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="4925d-121">(オプション) **このトランザクションが返品であったかどうか:** トランザクションが返品であったかどうかを識別する true/false フィールド。</span><span class="sxs-lookup"><span data-stu-id="4925d-121">(Optional) **Whether this transaction was a return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="4925d-122">**トランザクションの値** がマイナスの場合、この情報を使用して返品を推測します。</span><span class="sxs-lookup"><span data-stu-id="4925d-122">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>
- <span data-ttu-id="4925d-123">(オプション) 顧客活動に関するデータ:</span><span class="sxs-lookup"><span data-stu-id="4925d-123">(Optional) Data about customer activities:</span></span>
    - <span data-ttu-id="4925d-124">同じタイプのアクティビティを区別するアクティビティの識別子。</span><span class="sxs-lookup"><span data-stu-id="4925d-124">Activity identifiers to distinguish activities of the same type.</span></span>
    - <span data-ttu-id="4925d-125">アクティビティを顧客にマッピングする顧客の識別子。</span><span class="sxs-lookup"><span data-stu-id="4925d-125">Customer identifiers to map activities to your customers.</span></span>
    - <span data-ttu-id="4925d-126">アクティビティの名前と日付を含むアクティビティ情報。</span><span class="sxs-lookup"><span data-stu-id="4925d-126">Activity information containing the name and date of the activity.</span></span>
    - <span data-ttu-id="4925d-127">顧客活動の意味論的データ スキーマには次のものが含まれます :</span><span class="sxs-lookup"><span data-stu-id="4925d-127">The semantic data schema for customer activities includes:</span></span>
        - <span data-ttu-id="4925d-128">**主キー :** アクティビティの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="4925d-128">**Primary key:** A unique identifier for an activity.</span></span> <span data-ttu-id="4925d-129">たとえば、Web サイトへのアクセスや、顧客が製品のサンプルを試したことを示す使用記録などです。</span><span class="sxs-lookup"><span data-stu-id="4925d-129">For example, a website visit or a usage record showing the customer tried a sample of your product.</span></span>
        - <span data-ttu-id="4925d-130">**タイムスタンプ :** 主キーで識別されるイベントの日時。</span><span class="sxs-lookup"><span data-stu-id="4925d-130">**Timestamp:** The date and time of the event identified by the primary key.</span></span>
        - <span data-ttu-id="4925d-131">**イベント :** 使用するイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="4925d-131">**Event:** The name of the event you want to use.</span></span> <span data-ttu-id="4925d-132">たとえば、食料品店の "UserAction" というフィールドは、顧客が使用するクーポンである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4925d-132">For example, a field called "UserAction" in a grocery store might be a coupon use by the customer.</span></span>
        - <span data-ttu-id="4925d-133">**詳細 :** イベントの詳細情報。</span><span class="sxs-lookup"><span data-stu-id="4925d-133">**Details:** Detailed information about the event.</span></span> <span data-ttu-id="4925d-134">たとえば、食料品店の "CouponValue" というフィールドは、クーポンの通貨値である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4925d-134">For example, a field called "CouponValue" in a grocery store might be the currency value of the coupon.</span></span>
- <span data-ttu-id="4925d-135">推奨されるデータ特性:</span><span class="sxs-lookup"><span data-stu-id="4925d-135">Suggested data characteristics:</span></span>
    - <span data-ttu-id="4925d-136">十分な履歴データ: 選択した時間枠の少なくとも 2 倍のトランザクション データ。</span><span class="sxs-lookup"><span data-stu-id="4925d-136">Sufficient historical data: Transaction data for at least double the selected time window.</span></span> <span data-ttu-id="4925d-137">2 - 3 年分のサブスクリプションデータが望ましい。</span><span class="sxs-lookup"><span data-stu-id="4925d-137">Preferably, two to three years of subscription data.</span></span> 
    - <span data-ttu-id="4925d-138">顧客ごとの複数の購入: 顧客ごとに少なくとも 2 つのトランザクションが理想的です。</span><span class="sxs-lookup"><span data-stu-id="4925d-138">Multiple purchases per customer: Ideally at least two transactions per customer.</span></span>
    - <span data-ttu-id="4925d-139">顧客数: 少なくとも 10 人の顧客プロファイル、1,000 人を超える一意の顧客が望ましい。</span><span class="sxs-lookup"><span data-stu-id="4925d-139">Number of customers: At least 10 customer profiles, preferably more than 1,000 unique customers.</span></span> <span data-ttu-id="4925d-140">モデルは、顧客が 10 人未満で、履歴データが不十分な場合に失敗します。</span><span class="sxs-lookup"><span data-stu-id="4925d-140">The model will fail with fewer than 10 customers and insufficient historical data.</span></span>
    - <span data-ttu-id="4925d-141">データの完全性: 提供されたエンティティのデータ フィールドで不足値の 20% 未満。</span><span class="sxs-lookup"><span data-stu-id="4925d-141">Data completeness: Less than 20% of missing values in the data field of the entity provided.</span></span>

> [!NOTE]
> <span data-ttu-id="4925d-142">顧客の購入頻度が高いビジネス (数週間ごと) の場合は、より短い予測ウィンドウと離反定義を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4925d-142">For a business with high customer purchase frequency (every few weeks) it's recommended to select a shorter prediction window and churn definition.</span></span> <span data-ttu-id="4925d-143">購入頻度が低い (数か月ごとまたは年に 1 回) 場合は、より長い予測ウィンドウと離反定義を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-143">For low purchase frequency (every few months or once a year), choose a longer prediction window and churn definition.</span></span>

## <a name="create-a-transactional-churn-prediction"></a><span data-ttu-id="4925d-144">トランザクション解約予測の作成</span><span class="sxs-lookup"><span data-stu-id="4925d-144">Create a transactional churn prediction</span></span>

1. <span data-ttu-id="4925d-145">Customer Insights で、**インテリジェンス** > **予測** に移動します。</span><span class="sxs-lookup"><span data-stu-id="4925d-145">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="4925d-146">**顧客離反モデル (プレビュー)** タイルを選択して、**このモデルを使用** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-146">Select the **Customer churn model (preview)** tile and select **Use this model**.</span></span>
   
1. <span data-ttu-id="4925d-147">**顧客離反モデル** ペインで、**トランザクション** を選択して、**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-147">In the **Customer churn model** pane, choose **Transactional** and select **Get started**.</span></span>

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="顧客離反モデル ペインで選択されたトランザクション オプションのスクリーンショット。":::

### <a name="name-model"></a><span data-ttu-id="4925d-149">モデルに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="4925d-149">Name model</span></span>

1. <span data-ttu-id="4925d-150">モデルにはその他と区別できるような名前を付けてください。</span><span class="sxs-lookup"><span data-stu-id="4925d-150">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="4925d-151">出力エンティティの名前には、スペースを含まない文字と数字のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="4925d-151">Provide a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="4925d-152">この名前を、モデル エンティティが使用します。</span><span class="sxs-lookup"><span data-stu-id="4925d-152">That's the name that the model entity will use.</span></span> 

1. <span data-ttu-id="4925d-153">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-153">Select **Next**.</span></span>

### <a name="define-customer-churn"></a><span data-ttu-id="4925d-154">顧客離反の定義</span><span class="sxs-lookup"><span data-stu-id="4925d-154">Define customer churn</span></span>

1. <span data-ttu-id="4925d-155">**次の解約の可能性がある顧客を特定する** フィールドで、解約を予測する期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="4925d-155">Set a window of days to predict churn for in the **Identify customers who may churn in the next** field.</span></span> <span data-ttu-id="4925d-156">たとえば、今後 90 日間の顧客の解約リスクを予測して、マーケティング保持の取り組みに合わせます。</span><span class="sxs-lookup"><span data-stu-id="4925d-156">For example, predict the risk of churn for your customers over the next 90 days to align to your marketing retention efforts.</span></span> <span data-ttu-id="4925d-157">解約リスクを長い期間または短い期間で予測すると、解約リスク プロファイルの要因に対処することがより困難になる可能性がありますが、それは特定のビジネス要件によって異なります。</span><span class="sxs-lookup"><span data-stu-id="4925d-157">Predicting churn risk for a longer or shorter period of time can make it more difficult to address the factors in your churn risk profile, but it depends on your specific business requirements.</span></span> 
   >[!TIP]
   > <span data-ttu-id="4925d-158">下書き状態の予測はいつでも、**保存して閉じる** を選択して保存できます。</span><span class="sxs-lookup"><span data-stu-id="4925d-158">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="4925d-159">予測ドラフトは **自分の予測** タブをで続きを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="4925d-159">You'll find the draft prediction in the **My predictions** tab to continue.</span></span>

1. <span data-ttu-id="4925d-160">**顧客が購入していない場合に解約する日数** フィールドに、解約を定義する日数を入力します。</span><span class="sxs-lookup"><span data-stu-id="4925d-160">Enter the number of days to define churn in the **A customer has churned if they've made no purchases in:** field.</span></span> <span data-ttu-id="4925d-161">たとえば、顧客が過去 30 日間に一度も購入していない場合、ビジネスに対して解約されたと見なされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4925d-161">For example, if a customer has made no purchases in the last 30 days, they might be considered as churned for your business.</span></span> 

1. <span data-ttu-id="4925d-162">**次へ** を選んで続行します。</span><span class="sxs-lookup"><span data-stu-id="4925d-162">Select **Next** to continue</span></span>

### <a name="add-required-data"></a><span data-ttu-id="4925d-163">必須データを追加する</span><span class="sxs-lookup"><span data-stu-id="4925d-163">Add required data</span></span>

1. <span data-ttu-id="4925d-164">**購入履歴** の **データを追加** を選択し、[前提条件](#prerequisites) に記載されているように、トランザクション/購入履歴情報を提供するエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-164">Select **Add data** for **Purchase history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="4925d-165">セマンティック フィールドを購入履歴エンティティ内の属性にマップし、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-165">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="4925d-166">フィールドの説明については、[前提条件](#prerequisites)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4925d-166">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="購入エンティティのセマンティック フィールドをマップします。":::

1. <span data-ttu-id="4925d-168">以下のフィールドが入力されていない場合は、購入履歴エンティティから顧客エンティティへの関係を構成します。</span><span class="sxs-lookup"><span data-stu-id="4925d-168">If the fields below aren't populated, configure the relationship from your purchase history entity to the Customer entity.</span></span>
    1. <span data-ttu-id="4925d-169">**購入履歴エンティティ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-169">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="4925d-170">購入履歴エンティティで顧客を識別する **フィールド** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-170">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="4925d-171">これは、顧客エンティティの主要な顧客 ID に関連している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4925d-171">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="4925d-172">主要な顧客エンティティと一致する **顧客エンティティ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-172">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="4925d-173">関係性を説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4925d-173">Enter a name that describes the relationship.</span></span>

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="顧客との関係の作成を示す購入履歴ページ。":::
   
1. <span data-ttu-id="4925d-175">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-175">Select **Next**.</span></span>

1. <span data-ttu-id="4925d-176">必要に応じて、**顧客活動** の **データの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-176">Optionally, select **Add data** for **Customer activities**.</span></span> <span data-ttu-id="4925d-177">前提条件に記載されているように、顧客活動情報を提供するエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-177">Choose the entity that provides the customer activity information as described in the prerequisites.</span></span>

1. <span data-ttu-id="4925d-178">セマンティック フィールドを顧客活動エンティティ内の属性にマップし、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-178">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span> <span data-ttu-id="4925d-179">フィールドの説明については、[前提条件](#prerequisites)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4925d-179">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="トランザクション データの顧客フィールドをマッピングします。":::

1. <span data-ttu-id="4925d-181">構成した顧客活動のタイプに一致する活動タイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-181">Select an activity type that matches to the type of customer activity you're configuring.</span></span> <span data-ttu-id="4925d-182">**新規作成** を作成して、利用可能な活動の種類を選択するか、新しい種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="4925d-182">Select **Create new** and choose an available activity type or create a new type.</span></span>

1. <span data-ttu-id="4925d-183">顧客アクティビティのエンティティと顧客エンティティの関係を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4925d-183">You'll need to configure the relationship from your customer activity entity to the Customer entity.</span></span>
    1. <span data-ttu-id="4925d-184">顧客活動テーブルで顧客を識別する フィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-184">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="4925d-185">これは、顧客エンティティのプライマリ 顧客 ID に直接関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="4925d-185">It can be directly related to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="4925d-186">主要な顧客エンティティと一致する顧客エンティティを選択します</span><span class="sxs-lookup"><span data-stu-id="4925d-186">Select the Customer entity that matches your primary Customer entity</span></span>
    1. <span data-ttu-id="4925d-187">関係性を説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4925d-187">Enter a name that describes the relationship.</span></span>

1. <span data-ttu-id="4925d-188">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-188">Select **Save**.</span></span>

1. <span data-ttu-id="4925d-189">他にも顧客活動がある場合は、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4925d-189">If you have any other customer activities you would like to include, repeat the steps above.</span></span>

1. <span data-ttu-id="4925d-190">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-190">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="4925d-191">スケジュールを設定して構成を確認する</span><span class="sxs-lookup"><span data-stu-id="4925d-191">Set schedule and review configuration</span></span>

1. <span data-ttu-id="4925d-192">モデルの再トレーニングを実施する頻度を設定します。</span><span class="sxs-lookup"><span data-stu-id="4925d-192">Set a frequency to retrain your model.</span></span> <span data-ttu-id="4925d-193">この設定は、新しいデータが取り込まれるときに、予測の精度を更新するために重要です。</span><span class="sxs-lookup"><span data-stu-id="4925d-193">This setting is important to update the accuracy of predictions as new data is ingested.</span></span> <span data-ttu-id="4925d-194">多くの企業は、月に1度再トレーニングして、予測の精度を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="4925d-194">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="4925d-195">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-195">Select **Next**.</span></span>

1. <span data-ttu-id="4925d-196">予測の構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="4925d-196">Review the configuration of the prediction.</span></span> <span data-ttu-id="4925d-197">表示された値の下で **編集** を選択すると、前の手順に戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="4925d-197">You can go back to prior steps by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="4925d-198">または、進行状況のインジケーターから構成のステップを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4925d-198">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="4925d-199">すべての値が正しく構成されている場合は、**保存して実行する** を選択して予測プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="4925d-199">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="4925d-200">**自分の予測** タブで、予測の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4925d-200">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="4925d-201">予測で使用されるデータの量によっては、プロセスの完了までに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4925d-201">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="4925d-202">予測の状態と結果を確認する</span><span class="sxs-lookup"><span data-stu-id="4925d-202">Review a prediction status and results</span></span>

1. <span data-ttu-id="4925d-203">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-203">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="4925d-204">レビューする予測を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-204">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="4925d-205">**予測名:** 作成時に提供された予測の名前。</span><span class="sxs-lookup"><span data-stu-id="4925d-205">**Prediction name:** Name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="4925d-206">**予測の種類:** 予測に使用されるモデルのタ種類</span><span class="sxs-lookup"><span data-stu-id="4925d-206">**Prediction type:** Type of model used for the prediction</span></span>
   - <span data-ttu-id="4925d-207">**出力エンティティ :** 予測の出力を保存するエンティティの名前。</span><span class="sxs-lookup"><span data-stu-id="4925d-207">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="4925d-208">**データ** > **エンティティ** で、この名前を持つエンティティを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="4925d-208">You can find an entity with this name on **Data** > **Entities**.</span></span>    
     <span data-ttu-id="4925d-209">出力エンティティでは、*ChurnScore* は離反の予測確率であり、*IsChurn* は *ChurnScore* に基づく 0.5 のしきい値を持つバイナリ ラベルです。</span><span class="sxs-lookup"><span data-stu-id="4925d-209">In the output entity, *ChurnScore* is the predicted probability of churn and *IsChurn* is a binary label based on *ChurnScore* with 0.5 threshold.</span></span> <span data-ttu-id="4925d-210">既定のしきい値は、ユーザーのシナリオでは機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="4925d-210">The default threshold might not work for your scenario.</span></span> <span data-ttu-id="4925d-211">任意のしきい値で [新しいセグメントを作成](segments.md#create-a-new-segment) します。</span><span class="sxs-lookup"><span data-stu-id="4925d-211">[Create a new segment](segments.md#create-a-new-segment) with your preferred threshold.</span></span>
     <span data-ttu-id="4925d-212">すべての顧客が必ずしもアクティブな顧客であるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="4925d-212">Not all customers are necessarily active customers.</span></span> <span data-ttu-id="4925d-213">中には、長い間活動をしておらず、離反定義に基づいて、すでに離反していると考えられる顧客もいます。</span><span class="sxs-lookup"><span data-stu-id="4925d-213">Some of them may not have had any activity for a long time and are considered as churned already, based on you churn definition.</span></span> <span data-ttu-id="4925d-214">すでに離反している顧客の離反リスクを予測することは、関心のある対象者ではないため役に立ちません。</span><span class="sxs-lookup"><span data-stu-id="4925d-214">Predicting the churn risk for customers who already churned isn't useful because the are not the audience of interest.</span></span>
   - <span data-ttu-id="4925d-215">**予測フィールド:** このフィールドは、一部の種類の予測に対してのみ入力され、解約予測では使用されません。</span><span class="sxs-lookup"><span data-stu-id="4925d-215">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="4925d-216">**状態:** 予測実行の状態。</span><span class="sxs-lookup"><span data-stu-id="4925d-216">**Status:** Status of the prediction run.</span></span>
        - <span data-ttu-id="4925d-217">**キュー:** 予測は、他のプロセスが実行されるのを待っています。</span><span class="sxs-lookup"><span data-stu-id="4925d-217">**Queued:** Prediction is waiting for other processes to run.</span></span>
        - <span data-ttu-id="4925d-218">**更新:** 予測は現在、実行されており、出力エンティティに流れ込む結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="4925d-218">**Refreshing:** Prediction is currently running to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="4925d-219">**失敗:** 予測の実行に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="4925d-219">**Failed:** Prediction run has failed.</span></span> <span data-ttu-id="4925d-220">詳細については、[ログを確認](#troubleshoot-a-failed-prediction) します。</span><span class="sxs-lookup"><span data-stu-id="4925d-220">[Review the logs](#troubleshoot-a-failed-prediction) for more details.</span></span>
        - <span data-ttu-id="4925d-221">**成功:** 予測は成功しました。</span><span class="sxs-lookup"><span data-stu-id="4925d-221">**Succeeded:** Prediction has succeeded.</span></span> <span data-ttu-id="4925d-222">省略記号配下の **表示** を選択して予測を確認します</span><span class="sxs-lookup"><span data-stu-id="4925d-222">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="4925d-223">**編集日 :** 予測の構成が変更された日付。</span><span class="sxs-lookup"><span data-stu-id="4925d-223">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="4925d-224">**最終更新日 :** 予測結果が出力エンティティで更新された日付。</span><span class="sxs-lookup"><span data-stu-id="4925d-224">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="4925d-225">予測の横にある縦の省略記号を選択して、確認する結果の **表示** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-225">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>

   :::image type="content" source="media/model-subs-view.PNG" alt-text="コントロールを表示して、予測の結果を確認します。":::   

1. <span data-ttu-id="4925d-227">結果ページには、3つの主要なデータ セクションがあります。</span><span class="sxs-lookup"><span data-stu-id="4925d-227">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="4925d-228">**トレーニング モデルのパフォーマンス :** 使用可能なスコアは A、B、C です。</span><span class="sxs-lookup"><span data-stu-id="4925d-228">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="4925d-229">このスコアは予測のパフォーマンスを示し、出力エンティティに格納されている結果を使用するかどうかの決定に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4925d-229">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="4925d-230">スコアは次のルールに基づいて決定されます :</span><span class="sxs-lookup"><span data-stu-id="4925d-230">Scores are determined based on the following rules:</span></span>
         
         - <span data-ttu-id="4925d-231">**A** モデルが予測全体の少なくとも 50% を正確に予測した場合、および解約した顧客の正確な予測の割合がベースライン率より少なくとも 10% 大きい場合。</span><span class="sxs-lookup"><span data-stu-id="4925d-231">**A** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is greater than the baseline rate by at least 10%.</span></span>
            
         - <span data-ttu-id="4925d-232">**B** モデルが予測全体の少なくとも 50% を正確に予測した場合、および解約した顧客の正確な予測の割合がベースラインより最大 10% 大きい場合。</span><span class="sxs-lookup"><span data-stu-id="4925d-232">**B** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is up to 10% greater than the baseline.</span></span>
            
         - <span data-ttu-id="4925d-233">**C** モデルが予測全体の 50% 未満を正確に予測した場合、または解約した顧客の正確な予測の割合がベースラインより少ない場合。</span><span class="sxs-lookup"><span data-stu-id="4925d-233">**C** when the model accurately predicted less 50% of the total predictions, or when the percentage of accurate predictions for customers who churned is less than the baseline.</span></span>
               
         - <span data-ttu-id="4925d-234">**ベースライン** は、モデルの予測時間枠の入力 (たとえば、1 年) を取得し、モデルは、1 か月以下に達するまで 2 で割ることにより、さまざまな時間の割合を作成します。</span><span class="sxs-lookup"><span data-stu-id="4925d-234">**Baseline** takes the prediction time window input for the model (for example, one year) and the model creates different fractions of time by dividing it by 2 until it reaches one month or less.</span></span> <span data-ttu-id="4925d-235">これらの割合を使用して、この期間に購入していない顧客向けのビジネス ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="4925d-235">It uses these fractions to create a business rule for customers who have not purchased in this time frame.</span></span> <span data-ttu-id="4925d-236">これらの顧客は解約されたと見なされます。</span><span class="sxs-lookup"><span data-stu-id="4925d-236">These customers are considered as churned.</span></span> <span data-ttu-id="4925d-237">誰が解約するかを予測する最も高い能力を持つ時間ベースのビジネス ルールが、ベースライン モデルとして選択されます。</span><span class="sxs-lookup"><span data-stu-id="4925d-237">The time-based business rule with the highest ability to predict who is likely to churn is chosen as baseline model.</span></span>
            
    1. <span data-ttu-id="4925d-238">**解約の可能性 (顧客数) :** 解約の予測リスクに基づく顧客のグループ。</span><span class="sxs-lookup"><span data-stu-id="4925d-238">**Likelihood to churn (number of customers):** Groups of customers based on their predicted risk of churn.</span></span> <span data-ttu-id="4925d-239">このデータは、解約のリスクが高い顧客のセグメントを作成する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4925d-239">This data can help you later if you want to create a segment of customers with high churn risk.</span></span> <span data-ttu-id="4925d-240">このようなセグメントは、セグメント メンバーの停止がどこにあるべきかを理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4925d-240">Such segments help to understand where your cutoff should be for segment membership.</span></span>
       
    1. <span data-ttu-id="4925d-241">**最も影響力のある要因 :** 予測を作成する際には、様々な要素が考慮されています。</span><span class="sxs-lookup"><span data-stu-id="4925d-241">**Most influential factors:** There are many factors that are taken into account when creating your prediction.</span></span> <span data-ttu-id="4925d-242">各因子には、モデルが作成する集計された予測に対して計算された重要度があります。</span><span class="sxs-lookup"><span data-stu-id="4925d-242">Each of the factors has its importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="4925d-243">これらの要素を使用して、予測の結果を検証することができます。</span><span class="sxs-lookup"><span data-stu-id="4925d-243">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="4925d-244">あるいは、この情報を後で使用して、顧客の解約リスクに影響を与える[セグメントを作成する](segments.md)こともできます。</span><span class="sxs-lookup"><span data-stu-id="4925d-244">Or you can use this information later to [create segments](segments.md) that could help influence churn risk for customers.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="4925d-245">失敗した予測のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4925d-245">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="4925d-246">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-246">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="4925d-247">エラー ログを表示する予測の横にある縦の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-247">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="4925d-248">**ログ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-248">Select **Logs**.</span></span>

1. <span data-ttu-id="4925d-249">すべてのエラーをレビューします。</span><span class="sxs-lookup"><span data-stu-id="4925d-249">Review all the errors.</span></span> <span data-ttu-id="4925d-250">発生するエラーにはいくつかの種類があり、どのような状態でエラーが発生したかを記載しています。</span><span class="sxs-lookup"><span data-stu-id="4925d-250">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="4925d-251">たとえば、正確に予測するための十分なデータがない、というエラーは、多くの場合で Customer Insights に追加のデータをロードすることで解決されます。</span><span class="sxs-lookup"><span data-stu-id="4925d-251">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="4925d-252">予測を更新する</span><span class="sxs-lookup"><span data-stu-id="4925d-252">Refresh a prediction</span></span>

<span data-ttu-id="4925d-253">予測は、設定で構成されているとおり、同一の[データ更新スケジュール](system.md#schedule-tab)に基づいて自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="4925d-253">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="4925d-254">手動で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="4925d-254">You can refresh them manually too.</span></span>

1. <span data-ttu-id="4925d-255">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-255">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="4925d-256">更新する予測の横に配置されている縦型の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-256">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="4925d-257">**最新の情報に更新** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-257">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="4925d-258">予測を削除する</span><span class="sxs-lookup"><span data-stu-id="4925d-258">Delete a prediction</span></span>

<span data-ttu-id="4925d-259">予測を削除すると、その出力エンティティも削除されます。</span><span class="sxs-lookup"><span data-stu-id="4925d-259">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="4925d-260">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-260">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="4925d-261">削除する予測の横に配置されている縦型の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-261">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="4925d-262">**削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4925d-262">Select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
