---
title: 対象者に関するインサイトのセグメント
description: セグメントの概要と、セグメントの作成および管理方法。
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a7fa6515bd6e79dedfb21aa0f0b8e24b873a6771
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034018"
---
# <a name="segments-overview"></a><span data-ttu-id="83d69-103">すべてのセグメントの概要</span><span class="sxs-lookup"><span data-stu-id="83d69-103">Segments overview</span></span>

<span data-ttu-id="83d69-104">セグメントでは、統計、トランザクション、または行動の属性に基づいて、顧客をグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="83d69-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="83d69-105">セグメントを使用すると、プロモーション キャンペーン、営業活動、顧客サポート アクションを対象にして、ビジネス目標を達成することができます。</span><span class="sxs-lookup"><span data-stu-id="83d69-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="83d69-106">セグメント定義のフィルターに一致する顧客プロファイルは、セグメントの *メンバー* として参照されます。</span><span class="sxs-lookup"><span data-stu-id="83d69-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="83d69-107">一部の [サービス制限](service-limits.md) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="83d69-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="83d69-108">新しいセグメントの作成</span><span class="sxs-lookup"><span data-stu-id="83d69-108">Create a new segment</span></span>

<span data-ttu-id="83d69-109">新しいセグメントを作成するには、複数の方法があります:</span><span class="sxs-lookup"><span data-stu-id="83d69-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="83d69-110">セグメント ビルダーを使用した複雑なセグメント: [空のセグメント](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="83d69-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="83d69-111">1 つの演算子の単純なセグメント: [クイック セグメント](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="83d69-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="83d69-112">AI を活用した類似顧客の検索方法: [類似顧客](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="83d69-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="83d69-113">メジャーまたは属性に基づく AI を活用した提案: [メジャーを改善するための提案されたセグメント](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="83d69-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="83d69-114">活動に基づく提案: [顧客活動に基づく提案されたセグメント](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="83d69-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="get-insights-on-existing-segments"></a><span data-ttu-id="83d69-115">既存セグメントに関するインサイトの取得</span><span class="sxs-lookup"><span data-stu-id="83d69-115">Get insights on existing segments</span></span>

<span data-ttu-id="83d69-116">[セグメント インサイト](segment-insights.md) を使用して、既存セグメントに関する追加情報を検出します。</span><span class="sxs-lookup"><span data-stu-id="83d69-116">Discover additional information around your existing segments with [Segment insights](segment-insights.md).</span></span> <span data-ttu-id="83d69-117">2 つのセグメントの違いや共通点を調査します。</span><span class="sxs-lookup"><span data-stu-id="83d69-117">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="find-similar-customers"></a><span data-ttu-id="83d69-118">類似する顧客を見つける</span><span class="sxs-lookup"><span data-stu-id="83d69-118">Find similar customers</span></span>

<span data-ttu-id="83d69-119">人工知能を使用して、選択したセグメントのメンバーに類似する顧客を検索します。</span><span class="sxs-lookup"><span data-stu-id="83d69-119">Find customers that are similar to the members of a selected segment with the help of artificial intelligence.</span></span> <span data-ttu-id="83d69-120">詳細については、[類似顧客](find-similar-customer-segments.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83d69-120">For more information, see [similar customers ](find-similar-customer-segments.md).</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="83d69-121">既存のセグメントを管理する</span><span class="sxs-lookup"><span data-stu-id="83d69-121">Manage existing segments</span></span>

<span data-ttu-id="83d69-122">**セグメント** ページに移動し、保存したすべてのセグメントを表示して管理します。</span><span class="sxs-lookup"><span data-stu-id="83d69-122">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="83d69-123">各セグメントは、セグメントに関する追加情報を含む行で表されます。</span><span class="sxs-lookup"><span data-stu-id="83d69-123">Each segment is represented by a row that includes additional information about the segment.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="83d69-124">![既存のセグメントを管理するオプション](media/segments-selected-segment.png "既存のセグメントを管理するオプション")</span><span class="sxs-lookup"><span data-stu-id="83d69-124">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="83d69-125">セグメントを選択すると、次のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="83d69-125">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="83d69-126">セグメント メンバーのプレビューなどメンバー数の傾向など、セグメントの詳細を **表示** します。</span><span class="sxs-lookup"><span data-stu-id="83d69-126">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="83d69-127">プロパティを変更するセグメントを **編集** します。</span><span class="sxs-lookup"><span data-stu-id="83d69-127">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="83d69-128">セグメントの **複製を作成** します。</span><span class="sxs-lookup"><span data-stu-id="83d69-128">**Create duplicate** of a segment.</span></span> <span data-ttu-id="83d69-129">プロパティをすぐに編集するか、単に複製を保存するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="83d69-129">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="83d69-130">最新のデータを含めるセグメントを **最新の情報に更新します**。</span><span class="sxs-lookup"><span data-stu-id="83d69-130">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="83d69-131">セグメントを **アクティブ化** または **非アクティブ化** します。</span><span class="sxs-lookup"><span data-stu-id="83d69-131">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="83d69-132">セグメントには、アクティブまたは非アクティブの 2 つの状態があります。</span><span class="sxs-lookup"><span data-stu-id="83d69-132">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="83d69-133">これらの状態は、セグメントを編集するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="83d69-133">These states come in handy when editing a segment.</span></span> <span data-ttu-id="83d69-134">非アクティブなセグメントの場合、セグメント定義は存在しますが、まだ顧客は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="83d69-134">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="83d69-135">セグメントをアクティブ化すると、その状態が '非アクティブ' から 'アクティブ' に変わり、セグメント定義に一致する顧客の検索が開始されます。</span><span class="sxs-lookup"><span data-stu-id="83d69-135">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="83d69-136">[スケジュールされた更新](system.md#schedule-tab) が構成されている場合、非アクティブなセグメントには **状態** が **スキップされた** としてリストされ、更新も試行されなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="83d69-136">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="83d69-137">非アクティブなセグメントがアクティブ化されると、これによって最新の情報に更新され、これはスケジュールされた更新に含まれます。</span><span class="sxs-lookup"><span data-stu-id="83d69-137">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="83d69-138">または、**アクティブ化/非アクティブ化** ドロップダウンで **後でスケジュール** 機能を使用して、特定のセグメントをアクティブ化および非アクティブ化する未来の日時を指定します。</span><span class="sxs-lookup"><span data-stu-id="83d69-138">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="83d69-139">セグメントの **名前を変更します**。</span><span class="sxs-lookup"><span data-stu-id="83d69-139">**Rename** the segment.</span></span>
- <span data-ttu-id="83d69-140">メンバーのリストを、CSV ファイル形式で **ダウンロード** します。</span><span class="sxs-lookup"><span data-stu-id="83d69-140">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="83d69-141">**追加先** オプションは、別のアプリケーションで処理するために、セグメント内の顧客 ID のリストを送信します。</span><span class="sxs-lookup"><span data-stu-id="83d69-141">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="83d69-142">セグメントを **削除** します。</span><span class="sxs-lookup"><span data-stu-id="83d69-142">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="83d69-143">セグメントを最新の情報に更新する</span><span class="sxs-lookup"><span data-stu-id="83d69-143">Refresh segments</span></span>

<span data-ttu-id="83d69-144">**セグメント** pページで **すべて更新** を選択すると、すべてのセグメントを一度に更新することができ、1つまたは複数のセグメントを選択してオプションから **更新** を選択すると、該当するセグメントを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="83d69-144">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="83d69-145">または、**管理者** > **システム** > **スケジュール** で定期的な更新を構成できます。</span><span class="sxs-lookup"><span data-stu-id="83d69-145">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="83d69-146">タスク/プロセスには、[6 種類の状態](system.md#status-types) があります。</span><span class="sxs-lookup"><span data-stu-id="83d69-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="83d69-147">さらに、ほとんどのプロセスは、[その他の下流プロセスに依存します](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="83d69-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="83d69-148">プロセスのステータスを選択して、ジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="83d69-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="83d69-149">ジョブのタスクの 1 つについて **詳細の表示** を選択すると、処理時間、最終処理日、およびタスクに関連するすべてのエラーと警告などの追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="83d69-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="83d69-150">処理履歴とセグメント メンバーの表示</span><span class="sxs-lookup"><span data-stu-id="83d69-150">View processing history and segment members</span></span>

<span data-ttu-id="83d69-151">セグメントの詳細を確認すると、セグメントに関する統合データを表示できます。</span><span class="sxs-lookup"><span data-stu-id="83d69-151">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="83d69-152">**セグメント** ページで、レビューするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="83d69-152">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="83d69-153">ページの上部には、メンバー数の変化を視覚化する傾向グラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="83d69-153">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="83d69-154">データ ポイントにカーソルを合わせると、特定の日付のメンバー数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="83d69-154">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="83d69-155">視覚化の概算時間を更新できます。</span><span class="sxs-lookup"><span data-stu-id="83d69-155">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="83d69-156">![時間の範囲のセグメント化](media/segment-time-range.png "時間の範囲のセグメント化")</span><span class="sxs-lookup"><span data-stu-id="83d69-156">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="83d69-157">下部には、セグメント メンバーのリストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="83d69-157">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="83d69-158">このリストに表示されるフィールドは、セグメントのエンティティの属性に基づいています。</span><span class="sxs-lookup"><span data-stu-id="83d69-158">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="83d69-159">このリストは、一致するセグメント メンバーのプレビューであり、セグメントの最初の 100 レコードが表示されるため、必要に応じてセグメントをすばやく評価し、定義をレビューできます。</span><span class="sxs-lookup"><span data-stu-id="83d69-159">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="83d69-160">一致するすべてのレコードを表示するには、[セグメントをエクスポートする](export-destinations.md) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="83d69-160">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
