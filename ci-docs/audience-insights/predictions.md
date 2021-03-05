---
title: 予測を使用して部分データを完成させる
description: 予測を使用して、不完全な顧客データを入力します。
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268278"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="98087-103">予測で部分データを完成させる</span><span class="sxs-lookup"><span data-stu-id="98087-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="98087-104">予測により、予測値を簡単に作成して、顧客の理解を深めることができます。</span><span class="sxs-lookup"><span data-stu-id="98087-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="98087-105">**インテリジェンス** > **予測** ページで、**自分の予測** を選択して、対象者に関するインサイトの他の部分で構成した予測を表示し、さらにカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="98087-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="98087-106">環境でAzure Data Lake Gen 2 保存スペースを使用している場合、この機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="98087-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="98087-107">予測機能は自動化された手段を使用してデータを評価し、そのデータに基づいて予測を行うため、プロファイリングの方法として使用できる機能があります。この用語は一般データ保護規則 ("GDPR") で定義されています。</span><span class="sxs-lookup"><span data-stu-id="98087-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="98087-108">顧客がこの機能を使用してデータを処理する場合、GDPR またはその他の法律または規制が適用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="98087-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="98087-109">お客様は、予測を含む Dynamics 365 Customer Insights の使用が、プライバシー、個人データ、生体認証データ、データ保護、通信の秘密保持に関連する法律を含む、適用されるすべての法律および規制に準拠していることを確認する責任があります。</span><span class="sxs-lookup"><span data-stu-id="98087-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="98087-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="98087-110">Prerequisites</span></span>

<span data-ttu-id="98087-111">組織で予測機能を使用するには、次の前提条件を満たす必要があります:</span><span class="sxs-lookup"><span data-stu-id="98087-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="98087-112">組織には、[Common Data Service で設定された](https://docs.microsoft.com/ai-builder/build-model#prerequisites) インスタンスがあり、Customer Insights と同じ組織にあります。</span><span class="sxs-lookup"><span data-stu-id="98087-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="98087-113">ご使用の環境は、Common Data Service インスタンスに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="98087-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="98087-114">[新しい環境を作成する](manage-environments.md) 場合は、**環境の作成** ダイアログで設定して、**詳細** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="98087-115">既に環境を作成している場合は、その設定に移動して **詳細** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="98087-116">いずれの場合も、**予測の使用** セクションで、環境を関連付ける Common Data Service インスタンス URLを入力します。</span><span class="sxs-lookup"><span data-stu-id="98087-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="98087-117">顧客エンティティで予測を作成する</span><span class="sxs-lookup"><span data-stu-id="98087-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="98087-118">対象者に関するインサイトで、**データ** > **エンティティ** に移動します。</span><span class="sxs-lookup"><span data-stu-id="98087-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="98087-119">**顧客** エンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="98087-120">**顧客: CustomerInsights** エンティティで、**フィールド** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="98087-121">値を予測する属性名を見つけてから、**概要** 列で **概要** アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="98087-122">![概要アイコン](media/intelligence-overviewicon.png "概要アイコン")</span><span class="sxs-lookup"><span data-stu-id="98087-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="98087-123">属性の欠損値の割合が高い場合は、**欠損値を予測** を選択して、予測を続行します。</span><span class="sxs-lookup"><span data-stu-id="98087-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="98087-124">![欠損値の予測ボタンが表示された概要ステータス](media/intelligence-overviewpredictmissingvalues.png "欠損値の予測ボタンが表示された概要ステータス")</span><span class="sxs-lookup"><span data-stu-id="98087-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="98087-125">予測結果に **表示名** と **出力エンティティ名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="98087-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="98087-126">オプションの事前設定リストには、予測カテゴリに値をマッピングできる場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="98087-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="98087-127">この場合、予測の True/False またはバイナリの性質にマップされるため、カテゴリ オプションは 0 または 1 のみです。</span><span class="sxs-lookup"><span data-stu-id="98087-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="98087-128">カテゴリ列で、最終予測で "0" に分類するフィールド値を "0" にマップし、最終予測で "1" に分類する項目を "1" にマップします。</span><span class="sxs-lookup"><span data-stu-id="98087-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="98087-129">![カテゴリにマップされたフィールド値を示す例](media/intelligence-categorymapping.png "カテゴリにマップされたフィールド値を示す例")</span><span class="sxs-lookup"><span data-stu-id="98087-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="98087-130">**完了** を選択すると、予測が処理されます。</span><span class="sxs-lookup"><span data-stu-id="98087-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="98087-131">データのサイズと複雑さによっては、処理に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="98087-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="98087-132">結果は作成した予測の **出力エンティティ名** に基づいて、新しいエンティティで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="98087-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="98087-133">セグメントの作成中に予測を作成する</span><span class="sxs-lookup"><span data-stu-id="98087-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="98087-134">セグメントを作成するときに、選択した特定の属性の欠損値を予測することもできます。</span><span class="sxs-lookup"><span data-stu-id="98087-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="98087-135">具体的には、統合された顧客エンティティまたはCustomer_Measureエンティティに基づいてセグメントをすばやく作成する場合です。</span><span class="sxs-lookup"><span data-stu-id="98087-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="98087-136">このフローの一部として、顧客満足度、または購入金額など、セグメントの基礎となる特定の属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="98087-137">セグメントの作成時に、システムはこの属性の欠損値を予測する方法を提案します。</span><span class="sxs-lookup"><span data-stu-id="98087-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="98087-138">対象者に関するインサイトで、**セグメント** に移動し、**プロファイル** タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="98087-139">セグメントを作成する **フィールド** を選択して、**オペレーター** を選択して、次に **レビュー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="98087-140">**名前** と **表示名** をセグメントに提供します。</span><span class="sxs-lookup"><span data-stu-id="98087-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="98087-141">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-141">Select **Save**.</span></span>

5. <span data-ttu-id="98087-142">作成したセグメントのソース フィールドに不完全なデータがある場合、欠損値の予測を選択できます。</span><span class="sxs-lookup"><span data-stu-id="98087-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="98087-143">![予測ボタン](media/segments-predictoption.png "予測ボタン")</span><span class="sxs-lookup"><span data-stu-id="98087-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="98087-144">予測結果に **表示名** と **出力エンティティ名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="98087-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="98087-145">**完了** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-145">Select **Done**.</span></span> <span data-ttu-id="98087-146">予測は、**出力エンティティ名** に指定した名前の新しいエンティティですぐに生成されます。</span><span class="sxs-lookup"><span data-stu-id="98087-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="98087-147">予測の表示</span><span class="sxs-lookup"><span data-stu-id="98087-147">View a prediction</span></span>

1. <span data-ttu-id="98087-148">対象者に関するインサイトで、**インテリジェンス** > **予測** > **自分の予測** に移動します。</span><span class="sxs-lookup"><span data-stu-id="98087-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="98087-149">レビューする予測を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="98087-150"> **アクション** 列で省略記号を選択し、**表示** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="98087-151">予測のビューに多数のデータ ポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="98087-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="98087-152">![予測ページ](media/intelligence-predictionsviewpage.png "予測ページ")</span><span class="sxs-lookup"><span data-stu-id="98087-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="98087-153">**予測値** は、フィールド値からカテゴリへのマッピング段階で作成したマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="98087-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="98087-154">これらは、特定のカテゴリにマップされたデータセット内の値です。</span><span class="sxs-lookup"><span data-stu-id="98087-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="98087-155">-**トップ インフルエンサー** は、特定のカテゴリにマップされるフィールド値の予測の信頼性に最も影響を与えた可能性があるデータセット内の要因です。</span><span class="sxs-lookup"><span data-stu-id="98087-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="98087-156">**パフォーマンス** は、予測がどのように行われているかを示します。</span><span class="sxs-lookup"><span data-stu-id="98087-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="98087-157">リンクを選択して詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="98087-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="98087-158">**プレビュー** は、予測からの出力データセットのサンプルと、0 が不確実で 1 が確実である予測値の尤度または信頼度を示します。</span><span class="sxs-lookup"><span data-stu-id="98087-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="98087-159">予測を更新する</span><span class="sxs-lookup"><span data-stu-id="98087-159">Update a prediction</span></span>

1. <span data-ttu-id="98087-160">対象者に関するインサイトで、**インテリジェンス** > **予測** > **自分の予測** に移動します。</span><span class="sxs-lookup"><span data-stu-id="98087-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="98087-161">更新したい予測を選択して、**更新** アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="98087-162">予測は処理がスケジュールされます。</span><span class="sxs-lookup"><span data-stu-id="98087-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="98087-163">最後に更新された時刻は、**予測** ページの **更新済み** 列に更新されます。</span><span class="sxs-lookup"><span data-stu-id="98087-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="98087-164">予測の編集</span><span class="sxs-lookup"><span data-stu-id="98087-164">Edit a prediction</span></span>

<span data-ttu-id="98087-165">予測を作成したら、AI Builder でモデルをカスタマイズして、モデルの有効性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="98087-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="98087-166">対象者に関するインサイトで、**インテリジェンス** > **予測** > **自分の予測** に移動します。</span><span class="sxs-lookup"><span data-stu-id="98087-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="98087-167">編集する予測を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="98087-168"> **アクション** 列で省略記号を選択し、**表示** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="98087-169">**AI Builder でカスタマイズ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="98087-170">AI Builder でモデルを更新します。</span><span class="sxs-lookup"><span data-stu-id="98087-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="98087-171">[AI Builder でのモデルの管理に関する詳細](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models)。</span><span class="sxs-lookup"><span data-stu-id="98087-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="98087-172">予測の次の実行では、作成した更新済みモデルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="98087-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="98087-173">AI Builder で作成された新しいモデルは、モデルが上記のエクスペリエンスから作成されていない限り、対象者に関するインサイトに表示されません。</span><span class="sxs-lookup"><span data-stu-id="98087-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="98087-174">予測の削除</span><span class="sxs-lookup"><span data-stu-id="98087-174">Remove a prediction</span></span>

1. <span data-ttu-id="98087-175">対象者に関するインサイトで、**インテリジェンス** > **予測** > **自分の予測** に移動します。</span><span class="sxs-lookup"><span data-stu-id="98087-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="98087-176">削除する予測を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="98087-177"> **アクション** 列で省略記号を選択し、**削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="98087-178">削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="98087-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="98087-179">トラブルシューティング​​</span><span class="sxs-lookup"><span data-stu-id="98087-179">Troubleshooting</span></span>

<span data-ttu-id="98087-180">エラーが原因で Common Data Service の添付プロセスを完了できない場合は、プロセスを手動で完了できます。</span><span class="sxs-lookup"><span data-stu-id="98087-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="98087-181">添付プロセスで発生する可能性のある既知の問題が 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="98087-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="98087-182">顧客カード アドイン ソリューションがインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="98087-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="98087-183">指示を完了して、[ソリューションをインストールして構成します](customer-card-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="98087-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="98087-184">アプリのアクセス許可は付与されていません。</span><span class="sxs-lookup"><span data-stu-id="98087-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="98087-185">[https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="98087-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="98087-186">**環境** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="98087-187">アクセス許可を追加したい環境の横にある省略記号を選択して、**設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="98087-188">**ユーザー + アクセス権限** を展開して、**ユーザー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="98087-189">**+ 新規** を選択して、**ユーザー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="98087-190">**アプリケーション ユーザー** を選択して、まだ選択されていない場合は、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="98087-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="98087-191">**ユーザー名:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="98087-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="98087-192">**アプリケーション ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="98087-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="98087-193">**名:** 顧客</span><span class="sxs-lookup"><span data-stu-id="98087-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="98087-194">**姓:** インサイト</span><span class="sxs-lookup"><span data-stu-id="98087-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="98087-195">**メインのメール:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="98087-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="98087-196">**保存して閉じる** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="98087-197">作成したユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="98087-198">上部メニューバーから、**ロールの管理** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="98087-199">**システム管理者** を選択して、次に **OK** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98087-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]