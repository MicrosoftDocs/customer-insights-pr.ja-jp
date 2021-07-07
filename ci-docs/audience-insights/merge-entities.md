---
title: データ統合でエンティティをマージする
description: エンティティをマージして、統合顧客プロファイルを作成します。
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305649"
---
# <a name="merge-entities"></a><span data-ttu-id="c60db-103">エンティティの結合</span><span class="sxs-lookup"><span data-stu-id="c60db-103">Merge entities</span></span>

<span data-ttu-id="c60db-104">マージ フェーズはデータ統合プロセスの最後のフェーズです。</span><span class="sxs-lookup"><span data-stu-id="c60db-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="c60db-105">その目的は、競合するデータを調整することです。</span><span class="sxs-lookup"><span data-stu-id="c60db-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="c60db-106">競合するデータの例としては、2 つのデータ セットで見つかったがそれぞれに少しずつ異なって表示される顧客名 ("Grant Marshall" と "Grant Marshal") や、形式が異なる電話番号 (617-803-091X と 617803091X) などがあります。</span><span class="sxs-lookup"><span data-stu-id="c60db-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="c60db-107">これらの競合するデータ ポイントのマージは、属性ごとに行われます。</span><span class="sxs-lookup"><span data-stu-id="c60db-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="統合された顧客プロファイルを定義するマージされたフィールドを持つテーブルを表示するデータ統合プロセスのマージ ページ。":::

<span data-ttu-id="c60db-109">[一致フェーズ](match-entities.md) が完了したら、**統合** ページで **マージ** タイルを選択して、マージ フェーズを開始できます。</span><span class="sxs-lookup"><span data-stu-id="c60db-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="c60db-110">システム レコメンデーションのレビュー</span><span class="sxs-lookup"><span data-stu-id="c60db-110">Review system recommendations</span></span>

<span data-ttu-id="c60db-111">**データ** > **統合** > **マージ** で、統合された顧客プロファイル エンティティ内でマージする属性を選択して除外します。</span><span class="sxs-lookup"><span data-stu-id="c60db-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="c60db-112">統合された顧客プロファイルは、データ統合プロセスの結果です。</span><span class="sxs-lookup"><span data-stu-id="c60db-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="c60db-113">一部の属性は、システムによって自動的にマージされます。</span><span class="sxs-lookup"><span data-stu-id="c60db-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="c60db-114">自動的にマージされた属性の 1 つに含まれる属性を表示するには、そのマージされた属性をテーブルの **顧客フィールド** タブで選択します。</span><span class="sxs-lookup"><span data-stu-id="c60db-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="c60db-115">マージされた属性を構成する属性は、マージされた属性の下の 2 つの新しい行に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c60db-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="c60db-116">マージされたフィールドの分離、名前変更、除外、および編集</span><span class="sxs-lookup"><span data-stu-id="c60db-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="c60db-117">システムがマージされた属性を処理する方法を変更して、統合された顧客プロファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="c60db-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="c60db-118">**詳細表示** を選択して、変更する項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="c60db-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="マージされた属性を管理するための詳細表示ドロップダウン メニューのオプション。":::

<span data-ttu-id="c60db-120">詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c60db-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="c60db-121">マージされたフィールドの分離</span><span class="sxs-lookup"><span data-stu-id="c60db-121">Separate merged fields</span></span>

<span data-ttu-id="c60db-122">マージされたフィールドを分離するには、テーブルで属性を見つけます。</span><span class="sxs-lookup"><span data-stu-id="c60db-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="c60db-123">分離されたフィールドは、統合された顧客プロファイルの個別のデータ ポイントとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="c60db-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="c60db-124">マージされたフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="c60db-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="c60db-125">**詳細表示** を選択し、**フィールドの分離** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c60db-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="c60db-126">分離を確認します。</span><span class="sxs-lookup"><span data-stu-id="c60db-126">Confirm the separation.</span></span>

1. <span data-ttu-id="c60db-127">**保存** と **実行** を選択し、変更を処理します。</span><span class="sxs-lookup"><span data-stu-id="c60db-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="c60db-128">マージされたフィールドの名前を変更</span><span class="sxs-lookup"><span data-stu-id="c60db-128">Rename merged fields</span></span>

<span data-ttu-id="c60db-129">マージされた属性の表示名を変更します。</span><span class="sxs-lookup"><span data-stu-id="c60db-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="c60db-130">出力エンティティの名前は変更できません。</span><span class="sxs-lookup"><span data-stu-id="c60db-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="c60db-131">マージされたフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="c60db-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="c60db-132">**詳細表示** を選択し、**名前の変更** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c60db-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="c60db-133">変更した表示名を確認します。</span><span class="sxs-lookup"><span data-stu-id="c60db-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="c60db-134">**保存** と **実行** を選択し、変更を処理します。</span><span class="sxs-lookup"><span data-stu-id="c60db-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="c60db-135">マージされたフィールドの除外</span><span class="sxs-lookup"><span data-stu-id="c60db-135">Exclude merged fields</span></span>

<span data-ttu-id="c60db-136">統合された顧客プロファイルから属性を除外します。</span><span class="sxs-lookup"><span data-stu-id="c60db-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="c60db-137">フィールドがセグメントなどの他のプロセスで使用されている場合は、顧客プロファイルから除外する前に、これらのプロセスから削除します。</span><span class="sxs-lookup"><span data-stu-id="c60db-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="c60db-138">マージされたフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="c60db-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="c60db-139">**詳細表示** を選択し、**除外** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c60db-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="c60db-140">除外を確認します。</span><span class="sxs-lookup"><span data-stu-id="c60db-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="c60db-141">**保存** と **実行** を選択し、変更を処理します。</span><span class="sxs-lookup"><span data-stu-id="c60db-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="c60db-142">**マージ** ページで **除外されたフィールド** を選択して、除外したすべてのフィールドのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="c60db-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="c60db-143">このペインでは、除外されたフィールドを再び追加できます。</span><span class="sxs-lookup"><span data-stu-id="c60db-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="c60db-144">フィールドを手動で結合</span><span class="sxs-lookup"><span data-stu-id="c60db-144">Manually combine fields</span></span>

<span data-ttu-id="c60db-145">マージされた属性を手動で指定します。</span><span class="sxs-lookup"><span data-stu-id="c60db-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="c60db-146">**マージ** ページで **フィールドの結合** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c60db-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="c60db-147">**名前** と **出力フィールド名** を指定します。</span><span class="sxs-lookup"><span data-stu-id="c60db-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="c60db-148">フィールドを選択して追加します。</span><span class="sxs-lookup"><span data-stu-id="c60db-148">Choose a field to add.</span></span> <span data-ttu-id="c60db-149">**フィールドの追加** を選択して、さらにフィールドを結合します。</span><span class="sxs-lookup"><span data-stu-id="c60db-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="c60db-150">除外を確認します。</span><span class="sxs-lookup"><span data-stu-id="c60db-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="c60db-151">**保存** と **実行** を選択し、変更を処理します。</span><span class="sxs-lookup"><span data-stu-id="c60db-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="c60db-152">フィールドの順序の変更</span><span class="sxs-lookup"><span data-stu-id="c60db-152">Change the order of fields</span></span>

<span data-ttu-id="c60db-153">一部のエンティティには、他のエンティティよりも多くの詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c60db-153">Some entities contain more details than others.</span></span> <span data-ttu-id="c60db-154">エンティティにフィールドに関する最新データが含まれている場合、値をマージするときに他のエンティティより優先することができます。</span><span class="sxs-lookup"><span data-stu-id="c60db-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="c60db-155">マージされたフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="c60db-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="c60db-156">**詳細表示** を選択し、**編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c60db-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="c60db-157">**フィールドの結合** ペインで、**上/下へ移動** を選択し順序を設定するか、目的の位置にドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="c60db-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="c60db-158">変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="c60db-158">Confirm the change.</span></span>

1. <span data-ttu-id="c60db-159">**保存** と **実行** を選択し、変更を処理します。</span><span class="sxs-lookup"><span data-stu-id="c60db-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="c60db-160">マージを実行する</span><span class="sxs-lookup"><span data-stu-id="c60db-160">Run your merge</span></span>

<span data-ttu-id="c60db-161">手動で属性をマージする場合でも、システムに属性をマージさせる場合でも、いつでもマージを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c60db-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="c60db-162">**マージ** ページで **実行** を選択して、このプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="c60db-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c60db-163">![データ マージの保存と実行](media/configure-data-merge-save-run.png "データ マージの保存と実行")</span><span class="sxs-lookup"><span data-stu-id="c60db-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="c60db-164">**マージのみ実行** は、統合された顧客エンティティに反映された出力のみを表示する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="c60db-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="c60db-165">ダウンストリーム プロセスは [更新スケジュールで定義](system.md#schedule-tab) されたように更新されます。</span><span class="sxs-lookup"><span data-stu-id="c60db-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="c60db-166">**マージおよびダウンストリーム プロセスの実行** を選択して、変更内容でシステムを更新します。</span><span class="sxs-lookup"><span data-stu-id="c60db-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="c60db-167">エンリッチメント、セグメント、メジャーを含むすべてのプロセスが自動的に再実行されます。</span><span class="sxs-lookup"><span data-stu-id="c60db-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="c60db-168">すべてのダウンストリーム プロセスが完了すると、顧客プロファイルに変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="c60db-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="c60db-169">さらに変更を加えてステップを再実行するには、進行中のマージをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="c60db-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="c60db-170">**更新中 ...** テキストを選択して、表示された横ウィンドウの下にある **ジョブをキャンセル** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c60db-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="c60db-171">タスク/プロセスには、[6 種類の状態](system.md#status-types) があります。</span><span class="sxs-lookup"><span data-stu-id="c60db-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c60db-172">さらに、ほとんどのプロセスは、[その他の下流プロセスに依存します](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="c60db-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c60db-173">プロセスのステータスを選択して、ジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c60db-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c60db-174">ジョブのタスクの 1 つについて **詳細の表示** を選択すると、処理時間、最終処理日、およびタスクに関連するすべてのエラーと警告などの追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c60db-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="c60db-175">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c60db-175">Next Step</span></span>

<span data-ttu-id="c60db-176">[活動](activities.md)、[エンリッチメント](enrichment-hub.md)、または [関連付け](relationships.md) を設定して、顧客に関するより多くのインサイトを取得します。</span><span class="sxs-lookup"><span data-stu-id="c60db-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="c60db-177">アクティビティ、エンリッチメント、またはセグメントをすでに構成している場合、最新の顧客データを使用するように自動的に処理されます。</span><span class="sxs-lookup"><span data-stu-id="c60db-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
