---
title: トランザクション解約予測
description: 顧客が製品やサービスを購入しなくなるリスクがあるかどうかを予測します。
ms.date: 11/12/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f3cbbf99a6cecba2aab2cf85428d53e5df8346e4
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644409"
---
# <a name="transactional-churn-prediction-preview"></a><span data-ttu-id="fbd41-103">トランザクション解約予測 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="fbd41-103">Transactional churn prediction (preview)</span></span>

<span data-ttu-id="fbd41-104">トランザクション解約予測は、顧客が特定の時間枠内に製品またはサービスを購入しなくなるかどうかを予測するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-104">Transactional churn prediction helps predict if a customer will no longer purchase your products or services in a given time window.</span></span> <span data-ttu-id="fbd41-105">**インテリジェンス** > **予測** で新しい解約予測を作成できます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-105">You can create new churn predictions on **Intelligence** > **Predictions**.</span></span> <span data-ttu-id="fbd41-106">作成済みの予測を確認するには、**自分の予測** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-106">Select **My predictions** to see other predictions that you've created.</span></span>

> [!TIP]
> <span data-ttu-id="fbd41-107">サンプル データを使用して、トランザクション解約予測のチュートリアルを試してみてください: [トランザクション解約予測サンプル ガイド](sample-guide-predict-transactional-churn.md)。</span><span class="sxs-lookup"><span data-stu-id="fbd41-107">Try the tutorial for a translactional churn prediction using sample data: [Transactional churn prediction (preview) sample guide](sample-guide-predict-transactional-churn.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fbd41-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="fbd41-108">Prerequisites</span></span>

- <span data-ttu-id="fbd41-109">少なくとも Customer Insights の[共同作成者権限](permissions.md) があること。</span><span class="sxs-lookup"><span data-stu-id="fbd41-109">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="fbd41-110">ビジネスにとっての解約の意味を理解するためのビジネス知識。</span><span class="sxs-lookup"><span data-stu-id="fbd41-110">Business knowledge to understand what churn means for your business.</span></span> <span data-ttu-id="fbd41-111">時間ベースの解約定義をサポートします。つまり、顧客は購入がない期間の後に解約したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-111">We support time-based churn definitions, meaning a customer is considered to have churned after a period of no purchases.</span></span>
- <span data-ttu-id="fbd41-112">トランザクション/購入とその履歴に関するデータ:</span><span class="sxs-lookup"><span data-stu-id="fbd41-112">Data about your transactions/purchases and their history:</span></span>
    - <span data-ttu-id="fbd41-113">購入/トランザクションを区別するためのトランザクション識別子。</span><span class="sxs-lookup"><span data-stu-id="fbd41-113">Transaction identifiers to distinguish purchases/transactions.</span></span>
    - <span data-ttu-id="fbd41-114">トランザクションを顧客に一致させるための顧客 ID。</span><span class="sxs-lookup"><span data-stu-id="fbd41-114">Customer identifiers to match transactions to your customers.</span></span>
    - <span data-ttu-id="fbd41-115">トランザクションが発生した日付を定義するトランザクション イベントの日付。</span><span class="sxs-lookup"><span data-stu-id="fbd41-115">Transaction event dates, which define the dates the transaction occurred on.</span></span>
    - <span data-ttu-id="fbd41-116">購入/トランザクションのセマンティック データ スキーマには、次の情報が必要です:</span><span class="sxs-lookup"><span data-stu-id="fbd41-116">The semantic data schema for purchases/transactions requires the following information:</span></span>
        - <span data-ttu-id="fbd41-117">**トランザクション ID:** 購入またはトランザクションの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="fbd41-117">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="fbd41-118">**トランザクションの日付:** 購入またはトランザクションの日付。</span><span class="sxs-lookup"><span data-stu-id="fbd41-118">**Transaction Date:** The date of the purchase or transaction.</span></span>
        - <span data-ttu-id="fbd41-119">**トランザクションの値:** トランザクション/品目の通貨/数値。</span><span class="sxs-lookup"><span data-stu-id="fbd41-119">**Value of the transaction:** The currency/numerical value amount of the transaction/item.</span></span>
        - <span data-ttu-id="fbd41-120">(オプション) **一意の製品 ID:** データが品目レベルの場合に購入した製品またはサービスの ID。</span><span class="sxs-lookup"><span data-stu-id="fbd41-120">(Optional) **Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="fbd41-121">(オプション) **このトランザクションが返品であったかどうか:** トランザクションが返品であったかどうかを識別する true/false フィールド。</span><span class="sxs-lookup"><span data-stu-id="fbd41-121">(Optional) **Whether this transaction was a return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="fbd41-122">**トランザクションの値** がマイナスの場合、この情報を使用して返品を推測します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-122">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>
- <span data-ttu-id="fbd41-123">(オプション) 顧客活動に関するデータ:</span><span class="sxs-lookup"><span data-stu-id="fbd41-123">(Optional) Data about customer activities:</span></span>
    - <span data-ttu-id="fbd41-124">同じタイプのアクティビティを区別するアクティビティの識別子。</span><span class="sxs-lookup"><span data-stu-id="fbd41-124">Activity identifiers to distinguish activities of the same type.</span></span>
    - <span data-ttu-id="fbd41-125">アクティビティを顧客にマッピングする顧客の識別子。</span><span class="sxs-lookup"><span data-stu-id="fbd41-125">Customer identifiers to map activities to your customers.</span></span>
    - <span data-ttu-id="fbd41-126">アクティビティの名前と日付を含むアクティビティ情報。</span><span class="sxs-lookup"><span data-stu-id="fbd41-126">Activity information containing the name and date of the activity.</span></span>
    - <span data-ttu-id="fbd41-127">顧客活動の意味論的データ スキーマには次のものが含まれます :</span><span class="sxs-lookup"><span data-stu-id="fbd41-127">The semantic data schema for customer activities includes:</span></span>
        - <span data-ttu-id="fbd41-128">**主キー :** アクティビティの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="fbd41-128">**Primary key:** A unique identifier for an activity.</span></span> <span data-ttu-id="fbd41-129">たとえば、Web サイトへのアクセスや、顧客が製品のサンプルを試したことを示す使用記録などです。</span><span class="sxs-lookup"><span data-stu-id="fbd41-129">For example, a website visit or a usage record showing the customer tried a sample of your product.</span></span>
        - <span data-ttu-id="fbd41-130">**タイムスタンプ :** 主キーで識別されるイベントの日時。</span><span class="sxs-lookup"><span data-stu-id="fbd41-130">**Timestamp:** The date and time of the event identified by the primary key.</span></span>
        - <span data-ttu-id="fbd41-131">**イベント :** 使用するイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="fbd41-131">**Event:** The name of the event you want to use.</span></span> <span data-ttu-id="fbd41-132">たとえば、食料品店の "UserAction" というフィールドは、顧客が使用するクーポンである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fbd41-132">For example, a field called "UserAction" in a grocery store might be a coupon use by the customer.</span></span>
        - <span data-ttu-id="fbd41-133">**詳細 :** イベントの詳細情報。</span><span class="sxs-lookup"><span data-stu-id="fbd41-133">**Details:** Detailed information about the event.</span></span> <span data-ttu-id="fbd41-134">たとえば、食料品店の "CouponValue" というフィールドは、クーポンの通貨値である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fbd41-134">For example, a field called "CouponValue" in a grocery store might be the currency value of the coupon.</span></span>

## <a name="create-a-transactional-churn-prediction"></a><span data-ttu-id="fbd41-135">トランザクション解約予測の作成</span><span class="sxs-lookup"><span data-stu-id="fbd41-135">Create a transactional churn prediction</span></span>

1. <span data-ttu-id="fbd41-136">Customer Insights で、**インテリジェンス** > **予測** に移動します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-136">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="fbd41-137">**顧客離反モデル (プレビュー)** タイルを選択して、**このモデルを使用** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-137">Select the **Customer churn model (preview)** tile and select **Use this model**.</span></span>
   
1. <span data-ttu-id="fbd41-138">**顧客離反モデル** ペインで、**トランザクション** を選択して、**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-138">In the **Customer churn model** pane, choose **Transactional** and select **Get started**.</span></span>

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="顧客離反モデル ペインで選択されたトランザクション オプションのスクリーンショット。":::

### <a name="name-model"></a><span data-ttu-id="fbd41-140">モデルに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="fbd41-140">Name model</span></span>

1. <span data-ttu-id="fbd41-141">モデルにはその他と区別できるような名前を付けてください。</span><span class="sxs-lookup"><span data-stu-id="fbd41-141">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="fbd41-142">出力エンティティの名前には、スペースを含まない文字と数字のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="fbd41-142">Provide a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="fbd41-143">この名前を、モデル エンティティが使用します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-143">That's the name that the model entity will use.</span></span> 

1. <span data-ttu-id="fbd41-144">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-144">Select **Next**.</span></span>

### <a name="define-customer-churn"></a><span data-ttu-id="fbd41-145">顧客離反の定義</span><span class="sxs-lookup"><span data-stu-id="fbd41-145">Define customer churn</span></span>

1. <span data-ttu-id="fbd41-146">**次の解約の可能性がある顧客を特定する** フィールドで、解約を予測する期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-146">Set a window of days to predict churn for in the **Identify customers who may churn in the next** field.</span></span> <span data-ttu-id="fbd41-147">たとえば、今後 90 日間の顧客の解約リスクを予測して、マーケティング保持の取り組みに合わせます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-147">For example, predict the risk of churn for your customers over the next 90 days to align to your marketing retention efforts.</span></span> <span data-ttu-id="fbd41-148">解約リスクを長い期間または短い期間で予測すると、解約リスク プロファイルの要因に対処することがより困難になる可能性がありますが、それは特定のビジネス要件によって異なります。</span><span class="sxs-lookup"><span data-stu-id="fbd41-148">Predicting churn risk for a longer or shorter period of time can make it more difficult to address the factors in your churn risk profile, but it depends on your specific business requirements.</span></span> 
   >[!TIP]
   > <span data-ttu-id="fbd41-149">下書き状態の予測はいつでも、**保存して閉じる** を選択して保存できます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-149">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="fbd41-150">予測ドラフトは **自分の予測** タブをで続きを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-150">You'll find the draft prediction in the **My predictions** tab to continue.</span></span>

1. <span data-ttu-id="fbd41-151">**顧客が購入していない場合に解約する日数** フィールドに、解約を定義する日数を入力します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-151">Enter the number of days to define churn in the **A customer has churned if they've made no purchases in:** field.</span></span> <span data-ttu-id="fbd41-152">たとえば、顧客が過去 30 日間に一度も購入していない場合、ビジネスに対して解約されたと見なされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fbd41-152">For example, if a customer has made no purchases in the last 30 days, they might be considered as churned for your business.</span></span> 

1. <span data-ttu-id="fbd41-153">**次へ** を選んで続行します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-153">Select **Next** to continue</span></span>

### <a name="add-required-data"></a><span data-ttu-id="fbd41-154">必須データを追加する</span><span class="sxs-lookup"><span data-stu-id="fbd41-154">Add required data</span></span>

1. <span data-ttu-id="fbd41-155">**購入履歴** の **データを追加** を選択し、[前提条件](#prerequisites) に記載されているように、トランザクション/購入履歴情報を提供するエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-155">Select **Add data** for **Purchase history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="fbd41-156">セマンティック フィールドを購入履歴エンティティ内の属性にマップし、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="fbd41-157">フィールドの説明については、[前提条件](#prerequisites)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbd41-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="購入エンティティのセマンティック フィールドをマップします。":::

1. <span data-ttu-id="fbd41-159">以下のフィールドが入力されていない場合は、購入履歴エンティティから顧客エンティティへの関係を構成します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-159">If the fields below aren't populated, configure the relationship from your purchase history entity to the Customer entity.</span></span>
    1. <span data-ttu-id="fbd41-160">**購入履歴エンティティ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="fbd41-161">購入履歴エンティティで顧客を識別する **フィールド** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="fbd41-162">これは、顧客エンティティの主要な顧客 ID に関連している必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbd41-162">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="fbd41-163">主要な顧客エンティティと一致する **顧客エンティティ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="fbd41-164">関係性を説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-164">Enter a name that describes the relationship.</span></span>

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="顧客との関係の作成を示す購入履歴ページ。":::
   
1. <span data-ttu-id="fbd41-166">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-166">Select **Next**.</span></span>

1. <span data-ttu-id="fbd41-167">必要に応じて、**顧客活動** の **データの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-167">Optionally, select **Add data** for **Customer activities**.</span></span> <span data-ttu-id="fbd41-168">前提条件に記載されているように、顧客活動情報を提供するエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-168">Choose the entity that provides the customer activity information as described in the prerequisites.</span></span>

1. <span data-ttu-id="fbd41-169">セマンティック フィールドを顧客活動エンティティ内の属性にマップし、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-169">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span> <span data-ttu-id="fbd41-170">フィールドの説明については、[前提条件](#prerequisites)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbd41-170">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="fbd41-171">構成した顧客活動のタイプに一致する活動タイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-171">Select an activity type that matches to the type of customer activity you're configuring.</span></span> <span data-ttu-id="fbd41-172">**新規作成** を作成して、利用可能な活動の種類を選択するか、新しい種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-172">Select **Create new** and choose an available activity type or create a new type.</span></span>

1. <span data-ttu-id="fbd41-173">顧客アクティビティのエンティティと顧客エンティティの関係を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbd41-173">You'll need to configure the relationship from your customer activity entity to the Customer entity.</span></span>
    1. <span data-ttu-id="fbd41-174">顧客活動テーブルで顧客を識別する フィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-174">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="fbd41-175">これは、顧客エンティティのプライマリ 顧客 ID に直接関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-175">It can be directly related to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="fbd41-176">主要な顧客エンティティと一致する顧客エンティティを選択します</span><span class="sxs-lookup"><span data-stu-id="fbd41-176">Select the Customer entity that matches your primary Customer entity</span></span>
    1. <span data-ttu-id="fbd41-177">関係性を説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-177">Enter a name that describes the relationship.</span></span>

1. <span data-ttu-id="fbd41-178">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-178">Select **Save**.</span></span>

1. <span data-ttu-id="fbd41-179">他にも顧客活動がある場合は、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-179">If you have any other customer activities you would like to include, repeat the steps above.</span></span>

1. <span data-ttu-id="fbd41-180">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-180">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="fbd41-181">スケジュールを設定して構成を確認する</span><span class="sxs-lookup"><span data-stu-id="fbd41-181">Set schedule and review configuration</span></span>

1. <span data-ttu-id="fbd41-182">モデルの再トレーニングを実施する頻度を設定します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-182">Set a frequency to retrain your model.</span></span> <span data-ttu-id="fbd41-183">この設定は、新しいデータが取り込まれるときに、予測の精度を更新するために重要です。</span><span class="sxs-lookup"><span data-stu-id="fbd41-183">This setting is important to update the accuracy of predictions as new data is ingested.</span></span> <span data-ttu-id="fbd41-184">多くの企業は、月に1度再トレーニングして、予測の精度を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-184">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="fbd41-185">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-185">Select **Next**.</span></span>

1. <span data-ttu-id="fbd41-186">予測の構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-186">Review the configuration of the prediction.</span></span> <span data-ttu-id="fbd41-187">表示された値の下で **編集** を選択すると、前の手順に戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-187">You can go back to prior steps by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="fbd41-188">または、進行状況のインジケーターから構成のステップを選択できます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-188">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="fbd41-189">すべての値が正しく構成されている場合は、**保存して実行する** を選択して予測プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-189">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="fbd41-190">**自分の予測** タブで、予測の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-190">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="fbd41-191">予測で使用されるデータの量によっては、プロセスの完了までに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fbd41-191">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="fbd41-192">予測の状態と結果を確認する</span><span class="sxs-lookup"><span data-stu-id="fbd41-192">Review a prediction status and results</span></span>

1. <span data-ttu-id="fbd41-193">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-193">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="fbd41-194">レビューする予測を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-194">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="fbd41-195">**予測名:** 作成時に提供された予測の名前。</span><span class="sxs-lookup"><span data-stu-id="fbd41-195">**Prediction name:** Name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="fbd41-196">**予測の種類:** 予測に使用されるモデルのタ種類</span><span class="sxs-lookup"><span data-stu-id="fbd41-196">**Prediction type:** Type of model used for the prediction</span></span>
   - <span data-ttu-id="fbd41-197">**出力エンティティ :** 予測の出力を保存するエンティティの名前。</span><span class="sxs-lookup"><span data-stu-id="fbd41-197">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="fbd41-198">**データ** > **エンティティ** で、この名前を持つエンティティを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-198">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="fbd41-199">**予測フィールド:** このフィールドは、一部の種類の予測に対してのみ入力され、解約予測では使用されません。</span><span class="sxs-lookup"><span data-stu-id="fbd41-199">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="fbd41-200">**状態:** 予測実行の状態。</span><span class="sxs-lookup"><span data-stu-id="fbd41-200">**Status:** Status of the prediction run.</span></span>
        - <span data-ttu-id="fbd41-201">**キュー:** 予測は、他のプロセスが実行されるのを待っています。</span><span class="sxs-lookup"><span data-stu-id="fbd41-201">**Queued:** Prediction is waiting for other processes to run.</span></span>
        - <span data-ttu-id="fbd41-202">**更新:** 予測は現在、実行されており、出力エンティティに流れ込む結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-202">**Refreshing:** Prediction is currently running to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="fbd41-203">**失敗:** 予測の実行に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="fbd41-203">**Failed:** Prediction run has failed.</span></span> <span data-ttu-id="fbd41-204">詳細については、[ログを確認](#troubleshoot-a-failed-prediction) します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-204">[Review the logs](#troubleshoot-a-failed-prediction) for more details.</span></span>
        - <span data-ttu-id="fbd41-205">**成功:** 予測は成功しました。</span><span class="sxs-lookup"><span data-stu-id="fbd41-205">**Succeeded:** Prediction has succeeded.</span></span> <span data-ttu-id="fbd41-206">省略記号配下の **表示** を選択して予測を確認します</span><span class="sxs-lookup"><span data-stu-id="fbd41-206">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="fbd41-207">**編集日 :** 予測の構成が変更された日付。</span><span class="sxs-lookup"><span data-stu-id="fbd41-207">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="fbd41-208">**最終更新日 :** 予測結果が出力エンティティで更新された日付。</span><span class="sxs-lookup"><span data-stu-id="fbd41-208">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="fbd41-209">予測の横にある縦の省略記号を選択して、確認する結果の **表示** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-209">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>

   :::image type="content" source="media/model-subs-view.PNG" alt-text="コントロールを表示して、予測の結果を確認します。":::   

1. <span data-ttu-id="fbd41-211">結果ページには、3つの主要なデータ セクションがあります。</span><span class="sxs-lookup"><span data-stu-id="fbd41-211">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="fbd41-212">**トレーニング モデルのパフォーマンス :** 使用可能なスコアは A、B、C です。</span><span class="sxs-lookup"><span data-stu-id="fbd41-212">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="fbd41-213">このスコアは予測のパフォーマンスを示し、出力エンティティに格納されている結果を使用するかどうかの決定に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-213">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="fbd41-214">スコアは次のルールに基づいて決定されます :</span><span class="sxs-lookup"><span data-stu-id="fbd41-214">Scores are determined based on the following rules:</span></span>
         
         - <span data-ttu-id="fbd41-215">**A** モデルが予測全体の少なくとも 50% を正確に予測した場合、および解約した顧客の正確な予測の割合がベースライン率より少なくとも 10% 大きい場合。</span><span class="sxs-lookup"><span data-stu-id="fbd41-215">**A** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is greater than the baseline rate by at least 10%.</span></span>
            
         - <span data-ttu-id="fbd41-216">**B** モデルが予測全体の少なくとも 50% を正確に予測した場合、および解約した顧客の正確な予測の割合がベースラインより最大 10% 大きい場合。</span><span class="sxs-lookup"><span data-stu-id="fbd41-216">**B** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is up to 10% greater than the baseline.</span></span>
            
         - <span data-ttu-id="fbd41-217">**C** モデルが予測全体の 50% 未満を正確に予測した場合、または解約した顧客の正確な予測の割合がベースラインより少ない場合。</span><span class="sxs-lookup"><span data-stu-id="fbd41-217">**C** when the model accurately predicted less 50% of the total predictions, or when the percentage of accurate predictions for customers who churned is less than the baseline.</span></span>
               
         - <span data-ttu-id="fbd41-218">**ベースライン** は、モデルの予測時間枠の入力 (たとえば、1 年) を取得し、モデルは、1 か月以下に達するまで 2 で割ることにより、さまざまな時間の割合を作成します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-218">**Baseline** takes the prediction time window input for the model (for example, one year) and the model creates different fractions of time by dividing it by 2 until it reaches one month or less.</span></span> <span data-ttu-id="fbd41-219">これらの割合を使用して、この期間に購入していない顧客向けのビジネス ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-219">It uses these fractions to create a business rule for customers who have not purchased in this time frame.</span></span> <span data-ttu-id="fbd41-220">これらの顧客は解約されたと見なされます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-220">These customers are considered as churned.</span></span> <span data-ttu-id="fbd41-221">誰が解約するかを予測する最も高い能力を持つ時間ベースのビジネス ルールが、ベースライン モデルとして選択されます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-221">The time-based business rule with the highest ability to predict who is likely to churn is chosen as baseline model.</span></span>
            
    1. <span data-ttu-id="fbd41-222">**解約の可能性 (顧客数) :** 解約の予測リスクに基づく顧客のグループ。</span><span class="sxs-lookup"><span data-stu-id="fbd41-222">**Likelihood to churn (number of customers):** Groups of customers based on their predicted risk of churn.</span></span> <span data-ttu-id="fbd41-223">このデータは、解約のリスクが高い顧客のセグメントを作成する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-223">This data can help you later if you want to create a segment of customers with high churn risk.</span></span> <span data-ttu-id="fbd41-224">このようなセグメントは、セグメント メンバーの停止がどこにあるべきかを理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-224">Such segments help to understand where your cutoff should be for segment membership.</span></span>
       
    1. <span data-ttu-id="fbd41-225">**最も影響力のある要因 :** 予測を作成する際には、様々な要素が考慮されています。</span><span class="sxs-lookup"><span data-stu-id="fbd41-225">**Most influential factors:** There are many factors that are taken into account when creating your prediction.</span></span> <span data-ttu-id="fbd41-226">各因子には、モデルが作成する集計された予測に対して計算された重要度があります。</span><span class="sxs-lookup"><span data-stu-id="fbd41-226">Each of the factors has its importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="fbd41-227">これらの要素を使用して、予測の結果を検証することができます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-227">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="fbd41-228">あるいは、この情報を後で使用して、顧客の解約リスクに影響を与える[セグメントを作成する](segments.md)こともできます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-228">Or you can use this information later to [create segments](segments.md) that could help influence churn risk for customers.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="fbd41-229">失敗した予測のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="fbd41-229">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="fbd41-230">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-230">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="fbd41-231">エラー ログを表示する予測の横にある縦の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-231">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="fbd41-232">**ログ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-232">Select **Logs**.</span></span>

1. <span data-ttu-id="fbd41-233">すべてのエラーをレビューします。</span><span class="sxs-lookup"><span data-stu-id="fbd41-233">Review all the errors.</span></span> <span data-ttu-id="fbd41-234">発生するエラーにはいくつかの種類があり、どのような状態でエラーが発生したかを記載しています。</span><span class="sxs-lookup"><span data-stu-id="fbd41-234">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="fbd41-235">たとえば、正確に予測するための十分なデータがない、というエラーは、多くの場合で Customer Insights に追加のデータをロードすることで解決されます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-235">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="fbd41-236">予測を更新する</span><span class="sxs-lookup"><span data-stu-id="fbd41-236">Refresh a prediction</span></span>

<span data-ttu-id="fbd41-237">予測は、設定で構成されているとおり、同一の[データ更新スケジュール](system.md#schedule-tab)に基づいて自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-237">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="fbd41-238">手動で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-238">You can refresh them manually too.</span></span>

1. <span data-ttu-id="fbd41-239">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-239">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="fbd41-240">更新する予測の横に配置されている縦型の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-240">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="fbd41-241">**最新の情報に更新** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-241">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="fbd41-242">予測を削除する</span><span class="sxs-lookup"><span data-stu-id="fbd41-242">Delete a prediction</span></span>

<span data-ttu-id="fbd41-243">予測を削除すると、その出力エンティティも削除されます。</span><span class="sxs-lookup"><span data-stu-id="fbd41-243">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="fbd41-244">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-244">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="fbd41-245">削除する予測の横に配置されている縦型の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-245">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="fbd41-246">**削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbd41-246">Select **Delete**.</span></span>
