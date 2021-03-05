---
title: AI で類似する顧客を見つける
description: 人工知能を活用して類似した顧客セグメントを見つけます。
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: b9b2e7fa862b595c6a364a7208e42295b4f9df83
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268876"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="3aca1-103">類似した顧客 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="3aca1-103">Similar Customers (preview)</span></span>

<span data-ttu-id="3aca1-104">この機能を使用すると、人工知能を使用して顧客ベース内で類似した顧客を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="3aca1-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="3aca1-105">この機能を使用するには、少なくとも1つのセグメントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3aca1-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="3aca1-106">既存のセグメントの基準を拡張することで、そのセグメントに類似した顧客を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="3aca1-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="3aca1-107">*類似した顧客を見つける* は、は、データを評価し、そのデータに基づいて予測を行う自動化された手法を使用しているため、一般データ保護規則 (GDPR) で定義されているプロファイリングの手法として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3aca1-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="3aca1-108">顧客がこの機能を使用してデータを処理する場合、GDPR またはその他の法律または規制が適用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3aca1-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="3aca1-109">お客様は、予測を含む Dynamics 365 Customer Insights の使用が、プライバシー、個人データ、生体認証データ、データ保護、通信の秘密保持に関連する法律を含む、適用されるすべての法律および規制に準拠していることを確認する責任があります。</span><span class="sxs-lookup"><span data-stu-id="3aca1-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="3aca1-110">類似した顧客を見つける</span><span class="sxs-lookup"><span data-stu-id="3aca1-110">Finding similar customers</span></span>

1. <span data-ttu-id="3aca1-111">対象者に関するインサイトで **セグメント** に移動し、新しいセグメントのベースにするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="3aca1-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="3aca1-112">ご利用の *ソース セグメント* が最適でしょう。</span><span class="sxs-lookup"><span data-stu-id="3aca1-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="3aca1-113">アクションバーで、**類似の顧客を見つける** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3aca1-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="3aca1-114">新たなセグメントの推奨名を確認し、必要に応じて変更します。</span><span class="sxs-lookup"><span data-stu-id="3aca1-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="3aca1-115">新たなセグメントを定義するフィールドを確認します。</span><span class="sxs-lookup"><span data-stu-id="3aca1-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="3aca1-116">これらのフィールドは、システムがソース セグメントに類似する顧客を見つけようとする基準の定義を行います。</span><span class="sxs-lookup"><span data-stu-id="3aca1-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="3aca1-117">システムは既定で推奨フィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="3aca1-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="3aca1-118">モデルのパフォーマンスを大きく低下させる可能性があるフィールドは、自動的に除外されます。</span><span class="sxs-lookup"><span data-stu-id="3aca1-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="3aca1-119">次のデータ型のフィールドです : StringType、BooleanType、CharType、LongType、IntType、DoubleType、FloatType、ShortType</span><span class="sxs-lookup"><span data-stu-id="3aca1-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="3aca1-120">カーディナリティ (フィールド内の要素数) が2未満、または30を超えるフィールド</span><span class="sxs-lookup"><span data-stu-id="3aca1-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="3aca1-121">新たなセグメントで **すべての顧客**  を含めるか、 **特定の既存セグメント** の顧客のみを含めるかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3aca1-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="3aca1-122">ソースセグメントの顧客を除外するには、**ソース セグメント内の全員を除外する** チェックボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3aca1-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="3aca1-123">既定では、システムはターゲットの対象ユーザーの全体の 20％ のみを出力に含めることを推奨しています。</span><span class="sxs-lookup"><span data-stu-id="3aca1-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="3aca1-124">必要に応じてこのしきい値を編集してください。</span><span class="sxs-lookup"><span data-stu-id="3aca1-124">Edit this threshold as needed.</span></span> <span data-ttu-id="3aca1-125">しきい値を大きくすると、精度が低下します。</span><span class="sxs-lookup"><span data-stu-id="3aca1-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="3aca1-126">ページの下部で **実行** を選択し、データセットを分析する二項分類タスク (機械学習のメソッド) を開始します。</span><span class="sxs-lookup"><span data-stu-id="3aca1-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="3aca1-127">類似するセグメントを表示する</span><span class="sxs-lookup"><span data-stu-id="3aca1-127">View the similar segment</span></span>

<span data-ttu-id="3aca1-128">類似するセグメントを処理した後、新たなセグメントが **セグメント** ページにリスト表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aca1-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3aca1-129">![類似する顧客のセグメント](media/expanded-segment.png "類似する顧客のセグメント")</span><span class="sxs-lookup"><span data-stu-id="3aca1-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="3aca1-130">アクションバーで **表示** を選択して、セグメントの詳細を開きます。</span><span class="sxs-lookup"><span data-stu-id="3aca1-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="3aca1-131">このビューには、[類似性スコア](#about-similarity-scores)の結果の分布に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3aca1-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="3aca1-132">類似性スコアの値は、**セグメント メンバーのプレビュー** にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aca1-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="3aca1-133">類似するセグメントの出力を使用する</span><span class="sxs-lookup"><span data-stu-id="3aca1-133">Use the output of a similar segment</span></span>

<span data-ttu-id="3aca1-134">他のセグメントと同じように、[類似するのセグメントの出力](segments.md)を使って作業することができます。</span><span class="sxs-lookup"><span data-stu-id="3aca1-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="3aca1-135">たとえば、セグメントのエクスポート、またはメジャーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3aca1-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="3aca1-136">類似するセグメントを更新して編集する</span><span class="sxs-lookup"><span data-stu-id="3aca1-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="3aca1-137">類似するセグメントを更新するには、**セグメント** ページで選択し、アクション バーで **更新** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3aca1-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="3aca1-138">類似するセグメントを編集すると、データが再処理されます。</span><span class="sxs-lookup"><span data-stu-id="3aca1-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="3aca1-139">既に作成されているセグメントは、更新されたデータに基づいて更新されます。</span><span class="sxs-lookup"><span data-stu-id="3aca1-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="3aca1-140">類似するセグメントを編集するには、**セグメント** ページで選択し、アクション バーで **編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3aca1-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="3aca1-141">変更を適用後は、**実行** を選択して処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="3aca1-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="3aca1-142">類似したセグメントの削除</span><span class="sxs-lookup"><span data-stu-id="3aca1-142">Delete a similar segment</span></span>

<span data-ttu-id="3aca1-143">類似したセグメントを編集するには、**セグメント** ページで選択し、アクション バーで **削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3aca1-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="3aca1-144">続いて、削除の確認をします。</span><span class="sxs-lookup"><span data-stu-id="3aca1-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="3aca1-145">類似性スコアについて</span><span class="sxs-lookup"><span data-stu-id="3aca1-145">About similarity scores</span></span>

<span data-ttu-id="3aca1-146">二項分類の機械学習モデルは、類似するセグメントの顧客に対してスコアを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3aca1-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="3aca1-147">このスコアは、ソース セグメント内の顧客との類似性に基づいています。</span><span class="sxs-lookup"><span data-stu-id="3aca1-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="3aca1-148">0.55 未満の類似性スコアは、システムがソース セグメントの顧客と *類似していない* と分類した顧客です</span><span class="sxs-lookup"><span data-stu-id="3aca1-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="3aca1-149">0.55 ～ 0.7 の間の類似性スコアは、 *やや類似している* と分類されます</span><span class="sxs-lookup"><span data-stu-id="3aca1-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="3aca1-150">0.7 ～ 0.85 の間の類似性スコアは、 *類似している* と分類されます</span><span class="sxs-lookup"><span data-stu-id="3aca1-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="3aca1-151">0.85 ～ 1 の間の類似性スコアは、*とても類似している* と分類されます</span><span class="sxs-lookup"><span data-stu-id="3aca1-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="3aca1-152">類似性スコアが 0.4 未満の顧客はモデルの出力対象となりません。</span><span class="sxs-lookup"><span data-stu-id="3aca1-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="3aca1-153">システムは、これらソース セグメントと十分に類似していると見なしません。</span><span class="sxs-lookup"><span data-stu-id="3aca1-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]