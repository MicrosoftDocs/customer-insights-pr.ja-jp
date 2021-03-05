---
title: 製品レコメンデーションの予測
description: 顧客が購入またはやり取りする可能性のある製品を予測します。
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270507"
---
# <a name="product-recommendation-prediction-preview"></a><span data-ttu-id="ed998-103">製品レコメンデーションの予測 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="ed998-103">Product recommendation prediction (preview)</span></span>

<span data-ttu-id="ed998-104">製品レコメンデーション モデルは、予測製品レコメンデーションのセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="ed998-104">The product recommendation model creates sets of predictive product recommendations.</span></span> <span data-ttu-id="ed998-105">レコメンデーションは、以前の購入行動と同様の購入パターンを持つ顧客に基づいています。</span><span class="sxs-lookup"><span data-stu-id="ed998-105">Recommendations are based on previous purchase behavior and customers with similar purchase patterns.</span></span> <span data-ttu-id="ed998-106">**インテリジェンス** > **予測** ページで、新しい製品レコメンデーション予測を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ed998-106">You can create new product recommendation predictions on the **Intelligence** > **Predictions** page.</span></span> <span data-ttu-id="ed998-107">作成済みの予測を確認するには、**自分の予測** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-107">Select **My predictions** to see other predictions that you've created.</span></span>

<span data-ttu-id="ed998-108">製品レコメンデーションは、現地の法律や規制、および顧客の期待の対象となる場合がありますが、モデルは特に考慮に入れるよう構築されていません。</span><span class="sxs-lookup"><span data-stu-id="ed998-108">Product recommendations may be subject to local laws and regulations as well as customer expectations, which the model is not built to specifically take into account.</span></span>  <span data-ttu-id="ed998-109">この予測機能のユーザーの場合、**レコメンデーションを顧客に提供する前に確認して**、適用される法律や規制を遵守し、推奨する対象である顧客の期待に沿うようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed998-109">As a user of this predictive capability, **you must review the recommendations prior to delivering them to your customers** to ensure you are complying with any applicable laws or regulations, as well as customer expectations for what you may recommend.</span></span> 

<span data-ttu-id="ed998-110">さらに、このモデルの出力は、製品 ID に基づいたレコメンデーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="ed998-110">Additionally, the output of this model will give you recommendations based on the product ID.</span></span> <span data-ttu-id="ed998-111">配信メカニズムでは、予測された製品 ID を取得し、それらを適切なコンテンツにマッピングして、ローカリゼーション、画像コンテンツ、およびその他のビジネス固有のコンテンツや動作を説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed998-111">Your delivery mechanism will need to take predicted product IDs and map them to appropriate content for your customers to account for localization, image content, and other business specific content or behavior.</span></span>

## <a name="sample-guide"></a><span data-ttu-id="ed998-112">サンプル ガイド</span><span class="sxs-lookup"><span data-stu-id="ed998-112">Sample Guide</span></span>

<span data-ttu-id="ed998-113">この機能を試すことに興味があるが、以下の要件を満たすためのデータがない場合は、[サンプル実装を作成する](sample-guide-predict-product-recommendation.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="ed998-113">If you're interested in trying this feature but don't have data to complete the requirements below, you can [create a sample implementation](sample-guide-predict-product-recommendation.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ed998-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="ed998-114">Prerequisites</span></span>

- <span data-ttu-id="ed998-115">少なくとも Customer Insights の[共同作成者権限](permissions.md) があること。</span><span class="sxs-lookup"><span data-stu-id="ed998-115">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="ed998-116">ビジネスのためのさまざまなタイプの製品と、顧客がそれらをどのように操作するかを理解するためのビジネス知識。</span><span class="sxs-lookup"><span data-stu-id="ed998-116">Business knowledge to understand different types of products for your business and how your customers interact with them.</span></span> <span data-ttu-id="ed998-117">以前に顧客が購入した製品または新製品のレコメンデーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ed998-117">We support recommending products that have been previously purchased by your customers or recommendations for new products.</span></span>
- <span data-ttu-id="ed998-118">トランザクション、購入、その履歴に関するデータ:</span><span class="sxs-lookup"><span data-stu-id="ed998-118">Data about transactions, purchases, and their history:</span></span>
    - <span data-ttu-id="ed998-119">購入またはトランザクションを区別するためのトランザクション識別子。</span><span class="sxs-lookup"><span data-stu-id="ed998-119">Transaction identifiers to distinguish purchases or transactions.</span></span>
    - <span data-ttu-id="ed998-120">トランザクションを顧客にマッピングするための顧客 ID。</span><span class="sxs-lookup"><span data-stu-id="ed998-120">Customer identifiers to map transactions to your customers.</span></span>
    - <span data-ttu-id="ed998-121">トランザクションが発生した日付を指定するトランザクション イベント日付。</span><span class="sxs-lookup"><span data-stu-id="ed998-121">Transaction event dates that specify dates the transaction occurred on.</span></span>
    - <span data-ttu-id="ed998-122">(オプション) トランザクションの製品 ID 情報。</span><span class="sxs-lookup"><span data-stu-id="ed998-122">(Optional) Product ID information for the transaction.</span></span>
    - <span data-ttu-id="ed998-123">(オプション) トランザクションが返品であるかどうか。</span><span class="sxs-lookup"><span data-stu-id="ed998-123">(Optional) If a transaction is a return or not.</span></span>
    - <span data-ttu-id="ed998-124">セマンティック データ スキーマには、次の情報が必要です:</span><span class="sxs-lookup"><span data-stu-id="ed998-124">The semantic data schema requires the following information:</span></span>
        - <span data-ttu-id="ed998-125">**トランザクション ID:** 購入またはトランザクションの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="ed998-125">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="ed998-126">**トランザクションの日付:** 購入またはトランザクションの日付。</span><span class="sxs-lookup"><span data-stu-id="ed998-126">**Transaction date:** The date the of the purchase or transaction.</span></span>
        - <span data-ttu-id="ed998-127">**トランザクションの値:** 購入またはトランザクションの数値。</span><span class="sxs-lookup"><span data-stu-id="ed998-127">**Value of the transaction:** The numerical value of the purchase or transaction.</span></span>
        - <span data-ttu-id="ed998-128">**一意の製品 ID:** データが品目レベルの場合に購入した製品またはサービスの ID。</span><span class="sxs-lookup"><span data-stu-id="ed998-128">**Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="ed998-129">(オプション) **購入または返品:** トランザクションが返品であったかどうかを識別する true/false フィールド。</span><span class="sxs-lookup"><span data-stu-id="ed998-129">(Optional) **Purchase or return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="ed998-130">**トランザクションの値** がマイナスの場合、この情報を使用して返品を推測します。</span><span class="sxs-lookup"><span data-stu-id="ed998-130">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>


## <a name="create-a-product-recommendation-prediction"></a><span data-ttu-id="ed998-131">製品レコメンデーション予測を作成する</span><span class="sxs-lookup"><span data-stu-id="ed998-131">Create a product recommendation prediction</span></span>

1. <span data-ttu-id="ed998-132">Customer Insights で、**インテリジェンス** > **予測** に移動します。</span><span class="sxs-lookup"><span data-stu-id="ed998-132">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="ed998-133">**製品レコメンデーション モデル (プレビュー)** タイルを選択して、**このモデルを使用** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-133">Select the **Product recommendations model (preview)** tile and select **Use this model**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ed998-134">![[このモデルを使用]ボタンを使用した製品レコメンデーション モデル タイル](media/product-recommendation-usethismodel.PNG "[このモデルを使用]ボタンを使用した製品レコメンデーション モデル タイル")</span><span class="sxs-lookup"><span data-stu-id="ed998-134">![Product Recommendation model tile with Use this model button](media/product-recommendation-usethismodel.PNG "Product Recommendation model tile with Use this model button")</span></span>

1. <span data-ttu-id="ed998-135">モデル要件に関する情報をレビューします。</span><span class="sxs-lookup"><span data-stu-id="ed998-135">Review the information about the model requirements.</span></span> <span data-ttu-id="ed998-136">必要なデータがある場合は、**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-136">If you have the required data, select **Get started**.</span></span>

### <a name="name-model"></a><span data-ttu-id="ed998-137">モデルに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="ed998-137">Name model</span></span>

1. <span data-ttu-id="ed998-138">モデルにはその他と区別できるような名前を付けてください。</span><span class="sxs-lookup"><span data-stu-id="ed998-138">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="ed998-139">スペースを入れずに、文字と数字のみを使用して出力エンティティの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ed998-139">Enter a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="ed998-140">この名前を、モデル エンティティが使用します。</span><span class="sxs-lookup"><span data-stu-id="ed998-140">That's the name that the model entity will use.</span></span> <span data-ttu-id="ed998-141">続いて、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-141">Then, select **Next**.</span></span>

### <a name="define-product-recommendation-configuration"></a><span data-ttu-id="ed998-142">製品レコメンデーション構成を定義する</span><span class="sxs-lookup"><span data-stu-id="ed998-142">Define product recommendation configuration</span></span>

1. <span data-ttu-id="ed998-143">顧客に推薦する **製品数** を設定します。</span><span class="sxs-lookup"><span data-stu-id="ed998-143">Set the **Number of products** you want to recommend to a customer.</span></span> <span data-ttu-id="ed998-144">この値は、配信方法がデータをどのように入力するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ed998-144">This value depends on how your delivery method fills data.</span></span> <span data-ttu-id="ed998-145">3 つの製品を推奨できる場合、それに応じてこの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="ed998-145">If you can recommend three products, set this value accordingly.</span></span>
   
   >[!TIP]
   > <span data-ttu-id="ed998-146">下書き状態の予測はいつでも、**保存して閉じる** を選択して保存できます。</span><span class="sxs-lookup"><span data-stu-id="ed998-146">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="ed998-147">ドラフト予測は **自分の予測** タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed998-147">You'll find the draft prediction in the **My predictions** tab.</span></span>

1. <span data-ttu-id="ed998-148">**顧客が最近購入した製品を提案する** かどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-148">Choose if you want to **Suggest products customers have recently purchased**.</span></span>

1. <span data-ttu-id="ed998-149">最近購入した商品を推奨 *しない* ことを選択した場合、**ウィンドウを見返す** を設定します。</span><span class="sxs-lookup"><span data-stu-id="ed998-149">If you've selected to *not* recommend recently purchased products, set the **Look back window**.</span></span> <span data-ttu-id="ed998-150">この設定は、モデルが製品をユーザーに再度推奨する前に考慮する概算時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed998-150">This setting specifies the time frame the model considers before recommending the product to the user again.</span></span> <span data-ttu-id="ed998-151">たとえば、顧客が 2 年ごとにラップトップを購入することを示します。</span><span class="sxs-lookup"><span data-stu-id="ed998-151">For example, indicate a customer purchases a laptop every 2 years.</span></span> <span data-ttu-id="ed998-152">このウィンドウでは、過去 2 年間の購入履歴が表示され、アイテムが見つかった場合、そのアイテムはレコメンデーションから除外されます。</span><span class="sxs-lookup"><span data-stu-id="ed998-152">This window will look at the purchase history for the last 2 years, and if they find an item, the item will be filtered from the recommendations.</span></span>

1. <span data-ttu-id="ed998-153">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-153">Select **Next**</span></span>

### <a name="add-required-data"></a><span data-ttu-id="ed998-154">必須データの追加</span><span class="sxs-lookup"><span data-stu-id="ed998-154">Add required data</span></span>

1. <span data-ttu-id="ed998-155">**購入履歴** に対して **データを追加** を選択し、[前提条件](#prerequisites)に記載されているように、トランザクション/購入履歴情報を提供するエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-155">Select **Add data** for **Customer transaction history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="ed998-156">セマンティック フィールドを購入履歴エンティティ内の属性にマップし、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="ed998-157">フィールドの説明については、[前提条件](#prerequisites)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed998-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ed998-158">![エンティティ リレーションシップを定義する](media/product-recommendation-purchasehistorymapping.PNG "選択した購入履歴エンティティのフィールドにマッピングされているセマンティック属性を示す購入履歴ページ")</span><span class="sxs-lookup"><span data-stu-id="ed998-158">![Define the entity relationship](media/product-recommendation-purchasehistorymapping.PNG "Purchase history page showing semantic attributes that are mapped to fields in the selected purchase history entity")</span></span>

1. <span data-ttu-id="ed998-159">フィールドに値が入力されていない場合は、購入履歴エンティティから *顧客* エンティティへの関係を構成します。</span><span class="sxs-lookup"><span data-stu-id="ed998-159">If the fields aren't filled in, configure the relationship from your purchase history entity to the *Customer* entity.</span></span>
    1. <span data-ttu-id="ed998-160">**購入履歴エンティティ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="ed998-161">購入履歴エンティティで顧客を識別する **フィールド** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="ed998-162">これは、*顧客* エンティティの主要な顧客 ID に関連している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed998-162">It needs to relate to the primary customer ID of your *Customer* entity.</span></span>
    1. <span data-ttu-id="ed998-163">主要な顧客エンティティと一致する **顧客エンティティ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="ed998-164">関係性を説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ed998-164">Enter a name that describes the relationship.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="ed998-165">![顧客との関係の作成を示す購入履歴ページ](media/model-purchase-join.png "顧客との関係の作成を示す購入履歴ページ")</span><span class="sxs-lookup"><span data-stu-id="ed998-165">![Purchase history page showing the creation of a relationship to customer](media/model-purchase-join.png "Purchase history page showing the creation of a relationship to customer")</span></span>

1. <span data-ttu-id="ed998-166">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-166">Select **Save**.</span></span>

1. <span data-ttu-id="ed998-167">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-167">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="ed998-168">スケジュールの設定と構成のレビュー</span><span class="sxs-lookup"><span data-stu-id="ed998-168">Set schedule and review configuration</span></span>

1. <span data-ttu-id="ed998-169">モデルの再トレーニングを実施する頻度を設定します。</span><span class="sxs-lookup"><span data-stu-id="ed998-169">Set a frequency to retrain your model.</span></span> <span data-ttu-id="ed998-170">この設定は、新たなデータが Customer Insights にインポートされる際に予測の精度を更新するために重要です。</span><span class="sxs-lookup"><span data-stu-id="ed998-170">This setting is important to update the accuracy of predictions as new data is imported into Customer Insights.</span></span> <span data-ttu-id="ed998-171">多くの企業は、月に1度再トレーニングして、予測の精度を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="ed998-171">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="ed998-172">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-172">Select **Next**.</span></span>

1. <span data-ttu-id="ed998-173">構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="ed998-173">Review the configuration.</span></span> <span data-ttu-id="ed998-174">表示された値の配下の **編集する** を選択して、予測の構成の任意の部分に戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="ed998-174">You can go back to any part of the prediction configuration by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="ed998-175">または、進行状況のインジケーターから構成のステップを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ed998-175">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="ed998-176">すべての値が正しく構成されている場合は、**保存して実行する** を選択して予測プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="ed998-176">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="ed998-177">**自分の予測** タブで、予測の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ed998-177">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="ed998-178">予測で使用されるデータの量によっては、プロセスの完了までに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed998-178">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="ed998-179">予測の状態と結果を確認する</span><span class="sxs-lookup"><span data-stu-id="ed998-179">Review a prediction status and results</span></span>

1. <span data-ttu-id="ed998-180">**インテリジェンス** > **予測** で **自分の予測** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="ed998-180">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ed998-181">![自分の予測ページを表示する](media/product-recommendation-mypredictions.PNG "自分の予測ページを表示する")</span><span class="sxs-lookup"><span data-stu-id="ed998-181">![View of the My Predictions page](media/product-recommendation-mypredictions.PNG "View of the My Predictions page")</span></span>

1. <span data-ttu-id="ed998-182">レビューする予測を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-182">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="ed998-183">**予測名 :** 作成時に入力された予測の名前。</span><span class="sxs-lookup"><span data-stu-id="ed998-183">**Prediction name:** The name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="ed998-184">**予測タイプ :** 予測に使用されるモデルのタイプ</span><span class="sxs-lookup"><span data-stu-id="ed998-184">**Prediction type:** The type of model used for the prediction</span></span>
   - <span data-ttu-id="ed998-185">**出力エンティティ :** 予測の出力を保存するエンティティの名前。</span><span class="sxs-lookup"><span data-stu-id="ed998-185">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="ed998-186">**データ** > **エンティティ** で、この名前を持つエンティティを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="ed998-186">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="ed998-187">**予測フィールド:** このフィールドは、一部の種類の予測に対してのみ入力され、解約予測では使用されません。</span><span class="sxs-lookup"><span data-stu-id="ed998-187">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="ed998-188">**状態 :** 実行された予測の現在の状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="ed998-188">**Status:** The current status of the prediction's run.</span></span>
        - <span data-ttu-id="ed998-189">**待機中 :** 予測は現在、他のプロセスの実行を待機しています。</span><span class="sxs-lookup"><span data-stu-id="ed998-189">**Queued:** The prediction is currently waiting for other processes to run.</span></span>
        - <span data-ttu-id="ed998-190">**更新中 :** 予測は現在、処理の「スコア」ステージを実行し、出力エンティティに連携される結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="ed998-190">**Refreshing:** The prediction is currently running the "score" stage of processing to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="ed998-191">**失敗 :** 予測は失敗しました。</span><span class="sxs-lookup"><span data-stu-id="ed998-191">**Failed:** the prediction has failed.</span></span> <span data-ttu-id="ed998-192">詳細については、 **ログ** を選択してください。</span><span class="sxs-lookup"><span data-stu-id="ed998-192">Select **Logs** for more details.</span></span>
        - <span data-ttu-id="ed998-193">**成功 :** 予測は成功しました。</span><span class="sxs-lookup"><span data-stu-id="ed998-193">**Succeeded:** the prediction has succeeded.</span></span> <span data-ttu-id="ed998-194">省略記号配下の **表示** を選択して予測を確認します</span><span class="sxs-lookup"><span data-stu-id="ed998-194">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="ed998-195">**編集日 :** 予測の構成が変更された日付。</span><span class="sxs-lookup"><span data-stu-id="ed998-195">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="ed998-196">**最終更新日 :** 予測結果が出力エンティティで更新された日付。</span><span class="sxs-lookup"><span data-stu-id="ed998-196">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="ed998-197">予測の横にある縦の省略記号を選択して、確認する結果の **表示** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-197">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ed998-198">![編集、更新、表示、ログ、お削除を含む予測の縦の省略記号メニューのオプションの表示](media/product-recommendation-verticalellipses.PNG "編集、更新、表示、ログ、お削除を含む予測の縦の省略記号メニューのオプションの表示")</span><span class="sxs-lookup"><span data-stu-id="ed998-198">![View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete](media/product-recommendation-verticalellipses.PNG "View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete")</span></span>

1. <span data-ttu-id="ed998-199">結果ページには、3つの主要なデータ セクションがあります。</span><span class="sxs-lookup"><span data-stu-id="ed998-199">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="ed998-200">**トレーニング モデルのパフォーマンス :** 使用可能なスコアは A、B、C です。</span><span class="sxs-lookup"><span data-stu-id="ed998-200">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="ed998-201">このスコアは予測のパフォーマンスを示し、出力エンティティに格納されている結果を使用するかどうかの決定に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ed998-201">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span>
        - <span data-ttu-id="ed998-202">スコアは次のルールに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="ed998-202">Scores are determined based on the following rules:</span></span>
            - <span data-ttu-id="ed998-203">**A** 「Success @ K」メトリックがベースラインより最低 10% 高い場合、モデルは **A** 品質とみなされます。</span><span class="sxs-lookup"><span data-stu-id="ed998-203">**A** The model will be considered **A** quality if the "Success @ K" metric is at least 10% more the baseline.</span></span> 
            - <span data-ttu-id="ed998-204">**B** 「Success @ K」メトリックがベースラインより 0～10% 高い場合、モデルは **B** 品質とみなされます。</span><span class="sxs-lookup"><span data-stu-id="ed998-204">**B** The model will be considered **B** quality if the "Success @ K" metric is 0 to 10% more than the baseline.</span></span>
            - <span data-ttu-id="ed998-205">**C** 「Success @ K」メトリックがベースラインより低い場合、モデルは **C** 品質とみなされます。</span><span class="sxs-lookup"><span data-stu-id="ed998-205">**C** The model will be considered **C** quality if the "Success @ K" metric is less than than the baseline.</span></span>
               
               > [!div class="mx-imgBorder"]
               > <span data-ttu-id="ed998-206">![モデルのパフォーマンス結果を表示する](media/product-recommendation-modelperformance.PNG "モデルのパフォーマンス結果を表示する")</span><span class="sxs-lookup"><span data-stu-id="ed998-206">![View of the model performance result](media/product-recommendation-modelperformance.PNG "View of the model performance result")</span></span>
            - <span data-ttu-id="ed998-207">**ベースライン**: モデルは、すべての顧客の購入数で最も推奨される製品を取得し、モデルによって識別された学習ルールを使用して、顧客向けの一連のレコメンデーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ed998-207">**Baseline**: The model takes the top most recommended products by purchase count across all customers, and uses learned rules identified by the model to create a set of recommendations for the customers.</span></span> <span data-ttu-id="ed998-208">次に、予測は、製品を購入した顧客の数によって計算された上位の製品と比較されます。</span><span class="sxs-lookup"><span data-stu-id="ed998-208">The predictions are then compared to the top products, as calculated by the number of customers that had purchased the product.</span></span> <span data-ttu-id="ed998-209">顧客が推奨製品に少なくとも 1 つの製品を持っていて、それが上位の購入製品にも見られた場合、それらはベースラインの一部と見なされます。</span><span class="sxs-lookup"><span data-stu-id="ed998-209">If a customer has at least one product in their recommended products that was also seen in the top purchased products, they're considered a part of the baseline.</span></span> <span data-ttu-id="ed998-210">合計 100 人の顧客のうち推奨製品を購入した顧客が 10 人いた場合、ベースラインは 10% になります。</span><span class="sxs-lookup"><span data-stu-id="ed998-210">If there were 10 of these customers that had a recommended product purchased out of 100 total customers, the baseline would be 10%.</span></span>
            - <span data-ttu-id="ed998-211">**Success @ K**: トランザクションの期間の検証セットを使用して、すべての顧客に対してレコメンデーションが作成され、トランザクションの検証セットと比較されます。</span><span class="sxs-lookup"><span data-stu-id="ed998-211">**Success @ K**: Using a validation set of time period of transactions, recommendations are created for all customers and compared against the validation set of transactions.</span></span> <span data-ttu-id="ed998-212">たとえば、12 か月の期間で、12 月はデータの検証セットとして確保される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed998-212">For example, in a 12 month period, month 12 might be set aside as a validation set of data.</span></span> <span data-ttu-id="ed998-213">モデルで、過去 11 か月から学んだことに基づいて、12 月に購入するものを少なくとも 1 つ予測する場合、顧客が「Success @K」メトリックを増やします。</span><span class="sxs-lookup"><span data-stu-id="ed998-213">If the model predicts at least one thing you would purchase in month 12 based on what it learned from the previous 11 months, the customer would increase the "Success @ K" metric.</span></span>
    
    1. <span data-ttu-id="ed998-214">**最も提案された製品 (集計あり):** 顧客のために予測された上位 5 つの製品。</span><span class="sxs-lookup"><span data-stu-id="ed998-214">**Most suggested products (with tally):** The top 5 products that were predicted for your customers.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="ed998-215">![最も推奨される上位 5 つの製品を示すグラフ](media/product-recommendation-topproducts.PNG "最も推奨される上位 5 つの製品を示すグラフ")</span><span class="sxs-lookup"><span data-stu-id="ed998-215">![Graph showing the top 5 most recommended products](media/product-recommendation-topproducts.PNG "Graph showing the top 5 most recommended products")</span></span>
    
    1. <span data-ttu-id="ed998-216">**信頼度の高い製品に関するレコメンデーション:** モデルが顧客によって購入される可能性が高いと考えている、顧客に提供されるレコメンデーションのサンプル。</span><span class="sxs-lookup"><span data-stu-id="ed998-216">**High-confidence product recommendations:** A sample of recommendations provided to your customers that the model believes are likely to be purchased by the customer.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="ed998-217">![個々の顧客の一部のセットに対する信頼性の高い提案を示すリスト](media/product-recommendation-highconfidence.PNG "個々の顧客の一部のセットに対する信頼性の高い提案を示すリスト")</span><span class="sxs-lookup"><span data-stu-id="ed998-217">![List showing high confidence suggestions for a select set of individual customers](media/product-recommendation-highconfidence.PNG "List showing high confidence suggestions for a select set of individual customers")</span></span>

## <a name="fix-a-failed-prediction"></a><span data-ttu-id="ed998-218">失敗した予測を修正する</span><span class="sxs-lookup"><span data-stu-id="ed998-218">Fix a failed prediction</span></span>

1. <span data-ttu-id="ed998-219">**インテリジェンス** > **予測** で **自分の予測** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="ed998-219">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="ed998-220">エラーログを表示する予測を選択して **ログ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-220">Select the prediction you would like to view error logs for and select **Logs**.</span></span>

1. <span data-ttu-id="ed998-221">すべてのエラーをレビューします。</span><span class="sxs-lookup"><span data-stu-id="ed998-221">Review all the errors.</span></span> <span data-ttu-id="ed998-222">発生するエラーにはいくつかの種類があり、どのような状態でエラーが発生したかを記載しています。</span><span class="sxs-lookup"><span data-stu-id="ed998-222">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="ed998-223">たとえば、正確に予測するための十分なデータがない、というエラーは、多くの場合で Customer Insights に追加のデータをロードすることで解決されます。</span><span class="sxs-lookup"><span data-stu-id="ed998-223">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="ed998-224">予測を更新する</span><span class="sxs-lookup"><span data-stu-id="ed998-224">Refresh a prediction</span></span>

<span data-ttu-id="ed998-225">予測は、設定で構成したものと同じ[スケジュール](system.md#schedule-tab)でデータを自動更新します。</span><span class="sxs-lookup"><span data-stu-id="ed998-225">Predictions automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span>

1. <span data-ttu-id="ed998-226">**インテリジェンス** > **予測** で **自分の予測** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="ed998-226">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="ed998-227">更新する予測の横に配置されている縦型の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-227">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="ed998-228">**更新** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-228">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="ed998-229">予測を削除する</span><span class="sxs-lookup"><span data-stu-id="ed998-229">Delete a prediction</span></span>

<span data-ttu-id="ed998-230">予測を削除すると、その出力エンティティも削除されます。</span><span class="sxs-lookup"><span data-stu-id="ed998-230">Deleting a prediction will also remove its output entity.</span></span>

1. <span data-ttu-id="ed998-231">**インテリジェンス** > **予測** で **自分の予測** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="ed998-231">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="ed998-232">削除する予測の横に配置されている縦型の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-232">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="ed998-233">**削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed998-233">Select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]