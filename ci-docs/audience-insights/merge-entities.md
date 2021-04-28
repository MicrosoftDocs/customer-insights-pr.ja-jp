---
title: データ統合でエンティティをマージする
description: エンティティをマージして、統合顧客プロファイルを作成します。
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4ad06a0baf57e612fc0e0214dfd23d28e7d2b6be
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896517"
---
# <a name="merge-entities"></a><span data-ttu-id="ca062-103">エンティティの結合</span><span class="sxs-lookup"><span data-stu-id="ca062-103">Merge entities</span></span>

<span data-ttu-id="ca062-104">マージ フェーズはデータ統合プロセスの最後のフェーズです。</span><span class="sxs-lookup"><span data-stu-id="ca062-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="ca062-105">その目的は、競合するデータを調整することです。</span><span class="sxs-lookup"><span data-stu-id="ca062-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="ca062-106">競合するデータの例としては、2 つのデータ セットで見つかったがそれぞれに少しずつ異なって表示される顧客名 ("Grant Marshall" と "Grant Marshal") や、形式が異なる電話番号 (617-803-091X と 617803091X) などがあります。</span><span class="sxs-lookup"><span data-stu-id="ca062-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="ca062-107">これらの競合するデータ ポイントのマージは、属性ごとに行われます。</span><span class="sxs-lookup"><span data-stu-id="ca062-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="ca062-108">[一致フェーズ](match-entities.md) が完了したら、**統合** ページで **マージ** タイルを選択して、マージ フェーズを開始できます。</span><span class="sxs-lookup"><span data-stu-id="ca062-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="ca062-109">システム レコメンデーションのレビュー</span><span class="sxs-lookup"><span data-stu-id="ca062-109">Review system recommendations</span></span>

<span data-ttu-id="ca062-110">**マージ** ページでは、統合された顧客プロファイル エンティティ (構成プロセスの結果) 内でマージする属性を選択および除外します。</span><span class="sxs-lookup"><span data-stu-id="ca062-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="ca062-111">一部の属性は、システムによって自動的にマージされます。</span><span class="sxs-lookup"><span data-stu-id="ca062-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="ca062-112">結合された属性の表示</span><span class="sxs-lookup"><span data-stu-id="ca062-112">View merged attributes</span></span>

<span data-ttu-id="ca062-113">自動的にマージされた属性の 1 つに含まれる属性を表示するには、そのマージされた属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca062-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="ca062-114">マージされた属性を構成する 2 つの属性は、マージされた属性の下の 2 つの新しい行に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca062-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca062-115">![マージされた属性の選択](media/configure-data-merge-profile-attributes.png "マージされた属性を選択する")</span><span class="sxs-lookup"><span data-stu-id="ca062-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="ca062-116">マージされた属性の分離</span><span class="sxs-lookup"><span data-stu-id="ca062-116">Separate merged attributes</span></span>

<span data-ttu-id="ca062-117">自動的にマージされた属性を分離またはマージ解除するには、**プロファイル属性** テーブルで属性を検索します。</span><span class="sxs-lookup"><span data-stu-id="ca062-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="ca062-118">省略記号 (...) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca062-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="ca062-119">ドロップダウン 一覧で、**フィールドの分離** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca062-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="ca062-120">マージされた属性の削除</span><span class="sxs-lookup"><span data-stu-id="ca062-120">Remove merged attributes</span></span>

<span data-ttu-id="ca062-121">最終的な顧客プロファイル エンティティから属性を除外するには、**プロファイル属性** テーブルで探します。</span><span class="sxs-lookup"><span data-stu-id="ca062-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="ca062-122">省略記号 (...) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca062-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="ca062-123">ドロップダウン 一覧で、**マージしない** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca062-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="ca062-124">属性は、**顧客レコードから削除済み** セクションに移動されます。</span><span class="sxs-lookup"><span data-stu-id="ca062-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="ca062-125">マージされた属性を手動で追加する</span><span class="sxs-lookup"><span data-stu-id="ca062-125">Manually add a merged attribute</span></span>

<span data-ttu-id="ca062-126">マージされた属性を追加するには、**マージ** ページに移動する。</span><span class="sxs-lookup"><span data-stu-id="ca062-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="ca062-127">**マージされた属性の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca062-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="ca062-128">**名前** を提供して、それを **マージ** ページ上で識別します。</span><span class="sxs-lookup"><span data-stu-id="ca062-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="ca062-129">オプションで、統合された顧客プロファイル エンティティに表示する **表示名** を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca062-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="ca062-130">**重複する属性を選択** を構成して、一致したエンティティからマージする属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca062-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="ca062-131">属性を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca062-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="ca062-132">**重要度でランク付け** を設定して、1 つの属性を他の属性よりも優先します。</span><span class="sxs-lookup"><span data-stu-id="ca062-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="ca062-133">たとえば、 *WebAccountCSV* エンティティが、*Full Names* 属性についての最も正確なデータを含む場合、このエンティティを *WebAccountCSV* を選択することで *ContactCSV* よりも優先させます。</span><span class="sxs-lookup"><span data-stu-id="ca062-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="ca062-134">結果として、*WebAccountCSV* は最優先に移動し、同時に *ContactCSV* は、*氏名* 属性の値をプルするときに 2 番目の優先順位に移動します。</span><span class="sxs-lookup"><span data-stu-id="ca062-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="ca062-135">マージを実行する</span><span class="sxs-lookup"><span data-stu-id="ca062-135">Run your merge</span></span>

<span data-ttu-id="ca062-136">手動で属性をマージする場合でも、システムに属性をマージさせる場合でも、いつでもマージを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ca062-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="ca062-137">**マージ** ページで **実行** を選択して、このプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="ca062-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca062-138">![データ マージの保存と実行](media/configure-data-merge-save-run.png "データ マージの保存と実行")</span><span class="sxs-lookup"><span data-stu-id="ca062-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="ca062-139">追加の変更を加えてステップを再実行するために、進行中のマージをキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="ca062-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="ca062-140">**更新中 ...** テキストを選択して、表示された横ウィンドウの下にある **ジョブをキャンセル** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca062-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="ca062-141">**更新中 ...** テキストの変更に **成功した** 後、マージにより、定義したポリシーに従ってデータの矛盾が解消されました。</span><span class="sxs-lookup"><span data-stu-id="ca062-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="ca062-142">マージされた属性とマージされていない属性は、統合プロファイル エンティティに含まれます。</span><span class="sxs-lookup"><span data-stu-id="ca062-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="ca062-143">除外された属性は、統合プロファイル エンティティに含まれません。</span><span class="sxs-lookup"><span data-stu-id="ca062-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="ca062-144">初めてマージを正常に実行したのでなければ、エンリッチメント、セグメンテーション、メジャーを含むすべてのダウンストリーム プロセスが自動的に再実行されます。</span><span class="sxs-lookup"><span data-stu-id="ca062-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="ca062-145">すべてのダウンストリーム プロセスが再実行された後、顧客プロファイルには、行った変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="ca062-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="ca062-146">タスク/プロセスには、[6 種類の状態](system.md#status-types) があります。</span><span class="sxs-lookup"><span data-stu-id="ca062-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ca062-147">さらに、ほとんどのプロセスは、[その他の下流プロセスに依存します](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="ca062-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ca062-148">プロセスのステータスを選択して、ジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ca062-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ca062-149">ジョブのタスクの 1 つについて **詳細の表示** を選択すると、処理時間、最終処理日、およびタスクに関連するすべてのエラーと警告などの追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca062-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="ca062-150">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ca062-150">Next Step</span></span>

<span data-ttu-id="ca062-151">[活動](activities.md)、[エンリッチメント](enrichment-hub.md)、または [関連付け](relationships.md) を設定して、顧客に関するより多くのインサイトを取得します。</span><span class="sxs-lookup"><span data-stu-id="ca062-151">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="ca062-152">活動、エンリッチメント、または関連付けをすでに設定している場合、またはセグメントを定義している場合、自動的に処理されて最新の顧客データが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca062-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]