---
title: 既存セグメントのセグメント インサイト
description: 既存のセグメントに関するインサイトを取得して、相違点と共通点を確認します。
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2856888d6ac64d5daabcc5a234f13bc6f88bb3df
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306080"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="e54d2-103">セグメント インサイト (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e54d2-103">Segment insights (preview)</span></span>

<span data-ttu-id="e54d2-104">既存セグメントに関する追加情報とインサイトを検出します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="e54d2-105">2 つのセグメントの違いや共通点を調査します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="e54d2-106">セグメントの重複</span><span class="sxs-lookup"><span data-stu-id="e54d2-106">Segment overlap</span></span>

<span data-ttu-id="e54d2-107">セグメントの重複分析は、2 つ以上のセグメントに共通する顧客とその数を示します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="e54d2-108">たとえば、頻繁に利用する顧客のセグメントが、サービスまたは製品に満足している顧客を含むセグメントとどのように重複しているかです。</span><span class="sxs-lookup"><span data-stu-id="e54d2-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="e54d2-109">また、特定の属性の重複がどのように変化するかを分析することもできます。</span><span class="sxs-lookup"><span data-stu-id="e54d2-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="e54d2-110">重複分析を実行する</span><span class="sxs-lookup"><span data-stu-id="e54d2-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="e54d2-111">**セグメント** に移動し、**インサイト (プレビュー)** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="e54d2-112">**新規** を選択し、**インサイトの種類を選択** ペインで **重複** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="e54d2-113">関心のあるセグメントを選択して、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="e54d2-114">オプションで、1 つ以上の関心のあるフィールドを選択して、すべての可能なフィールド値の重複を分析し、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="e54d2-115">重複分析の名前、オプションの表示名、および説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="e54d2-116">**保存** を選択して、分析を開始します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="e54d2-117">状態が更新中から成功に変わると、重複分析の準備が整います。</span><span class="sxs-lookup"><span data-stu-id="e54d2-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="e54d2-118">重複分析を表示して最適化する</span><span class="sxs-lookup"><span data-stu-id="e54d2-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="e54d2-119">分析が完了したら、**セグメント** > **インサイト (プレビュー)** でこのインサイトの詳細を見つけます。</span><span class="sxs-lookup"><span data-stu-id="e54d2-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="セグメント重複分析情報の詳細":::

<span data-ttu-id="e54d2-121">分析結果を表示するには、分析情報を選択してください:</span><span class="sxs-lookup"><span data-stu-id="e54d2-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="e54d2-122">分析用に選択されたセグメントと重複するメンバーの数。</span><span class="sxs-lookup"><span data-stu-id="e54d2-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="e54d2-123">1 つのセグメントに含まれているが、残りのセグメントには含まれていないメンバーの数。</span><span class="sxs-lookup"><span data-stu-id="e54d2-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="e54d2-124">重複分析の構成中にフィールドを選択した場合、対応するタブにそれらが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e54d2-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="e54d2-125">フィルター ドロップダウンを使用して、関心のある属性レベルを選択すると、下部のテーブルに対応するデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e54d2-125">You can use the filter dropdown to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="e54d2-126">セグメントの区別</span><span class="sxs-lookup"><span data-stu-id="e54d2-126">Segment differentiators</span></span>

<span data-ttu-id="e54d2-127">セグメントの差別化要因は、セグメントを他の顧客や他のセグメントと区別するものを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e54d2-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="e54d2-128">セグメントを選択するだけで、選択したセグメントを区別するプロファイル属性とメジャーがシステムによって識別されます。</span><span class="sxs-lookup"><span data-stu-id="e54d2-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="e54d2-129">差別化要因分析を実行する</span><span class="sxs-lookup"><span data-stu-id="e54d2-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="e54d2-130">**セグメント** に移動し、**インサイト (プレビュー)** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="e54d2-131">**新規** を選択し、**インサイトの種類を選択** ペインで **重複** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="e54d2-132">分析するセグメントを **プライマリ セグメント** として選択し、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="e54d2-133">**すべての顧客** または **セカンダリ セグメント** を選択し、プライマリ セグメントと比較して **次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="e54d2-134">必要に応じて、特定の属性に分析を集中させるために関心のある 1 つ以上のフィールドを選択し、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="e54d2-135">重複分析の名前、オプションの表示名、および説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="e54d2-136">**保存** を選択して、分析を開始します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="e54d2-137">状態が更新中から成功に変わると、重複分析の準備が整います。</span><span class="sxs-lookup"><span data-stu-id="e54d2-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="e54d2-138">差別化要因分析を表示して最適化する</span><span class="sxs-lookup"><span data-stu-id="e54d2-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="e54d2-139">分析が完了したら、**セグメント** > **インサイト (プレビュー)** でこのインサイトの詳細を見つけます。</span><span class="sxs-lookup"><span data-stu-id="e54d2-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="セグメント差別化要因分析情報の詳細":::

<span data-ttu-id="e54d2-141">分析結果を表示するには、分析情報を選択してください。</span><span class="sxs-lookup"><span data-stu-id="e54d2-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="e54d2-142">差別化要因分析には 2 つのタブがあります。</span><span class="sxs-lookup"><span data-stu-id="e54d2-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="e54d2-143">**属性** タブには、差別化要因と見なされるプロファイル属性が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e54d2-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="e54d2-144">**メジャー** タブには差別化要因が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e54d2-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="e54d2-145">各タブには、次の詳細が含まれます:</span><span class="sxs-lookup"><span data-stu-id="e54d2-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="e54d2-146">差異スコアでソートされた、差別化要因のランク付きリスト。</span><span class="sxs-lookup"><span data-stu-id="e54d2-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="e54d2-147">各差別化要因の **差異スコア**。</span><span class="sxs-lookup"><span data-stu-id="e54d2-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="e54d2-148">差異スコアは、2 つのセグメント間の属性の違いの程度を表します。</span><span class="sxs-lookup"><span data-stu-id="e54d2-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="e54d2-149">差異スコアが高いほど、2 つのセグメント間の属性の違いが大きくなります。</span><span class="sxs-lookup"><span data-stu-id="e54d2-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="e54d2-150">スコアを選択して、その属性の値の分布を示す **差異スコア** ペインを開きます。</span><span class="sxs-lookup"><span data-stu-id="e54d2-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="e54d2-151">セグメント インサイトの管理</span><span class="sxs-lookup"><span data-stu-id="e54d2-151">Manage segment insights</span></span>

<span data-ttu-id="e54d2-152">コマンド バーからのインサイトに次のオプションを使用できます:</span><span class="sxs-lookup"><span data-stu-id="e54d2-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="e54d2-153">**戻る** でインサイトのリストを返します</span><span class="sxs-lookup"><span data-stu-id="e54d2-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="e54d2-154">**最新の状態に更新** で分析を再実行します</span><span class="sxs-lookup"><span data-stu-id="e54d2-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="e54d2-155">**削除** でこのインサイトを削除します</span><span class="sxs-lookup"><span data-stu-id="e54d2-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]