---
title: 対象者に関するインサイトのシステム構成
description: Dynamics 365 Customer Insights 対象者に関するインサイト機能のシステム設定について説明します。
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: a9c9e258da49b8f452550794539962d48b856829
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267346"
---
# <a name="system-configuration"></a><span data-ttu-id="62c0c-103">システム構成</span><span class="sxs-lookup"><span data-stu-id="62c0c-103">System configuration</span></span>

<span data-ttu-id="62c0c-104">**システム** ページには次のタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="62c0c-104">The **System** page includes the following tabs:</span></span>
- [<span data-ttu-id="62c0c-105">ステータス</span><span class="sxs-lookup"><span data-stu-id="62c0c-105">Status</span></span>](#status-tab)
- [<span data-ttu-id="62c0c-106">スケジュール​​</span><span class="sxs-lookup"><span data-stu-id="62c0c-106">Schedule</span></span>](#schedule-tab)
- [<span data-ttu-id="62c0c-107">API の使用状況</span><span class="sxs-lookup"><span data-stu-id="62c0c-107">API usage</span></span>](#api-usage-tab)
- [<span data-ttu-id="62c0c-108">詳細</span><span class="sxs-lookup"><span data-stu-id="62c0c-108">About</span></span>](#about-tab)
- [<span data-ttu-id="62c0c-109">全般</span><span class="sxs-lookup"><span data-stu-id="62c0c-109">General</span></span>](#general-tab)

> [!div class="mx-imgBorder"]
> <span data-ttu-id="62c0c-110">![システム ページ](media/system-tabs.png "システム ページ")</span><span class="sxs-lookup"><span data-stu-id="62c0c-110">![System page](media/system-tabs.png "System page")</span></span>

## <a name="status-tab"></a><span data-ttu-id="62c0c-111">ステータス タブ</span><span class="sxs-lookup"><span data-stu-id="62c0c-111">Status tab</span></span>

<span data-ttu-id="62c0c-112">**ステータス タブ** では、データの取り込み、データのエクスポート、およびその他のいくつかの重要な製品プロセスの進行状況を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="62c0c-112">The **Status tab** lets you track the progress of data ingestion, data exports, and several other important product processes.</span></span> <span data-ttu-id="62c0c-113">このタブの情報を確認して、アクティブなプロセスの完全性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="62c0c-113">Review the information on this tab to ensure the completeness of active processes.</span></span>

<span data-ttu-id="62c0c-114">このタブには、さまざまなプロセスのステータスと処理情報を含むテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="62c0c-114">This tab includes tables with status and processing information for various processes.</span></span> <span data-ttu-id="62c0c-115">各テーブルは、タスクの **名前** とそれに対応するエンティティ、その最新の実行の **状態**、**最終更新** を追跡します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-115">Each table tracks the **Name** of the task and its corresponding entity, the **Status** of its most recent run, and when it was **Last updated**.</span></span>

<span data-ttu-id="62c0c-116">名前を選択すると、タスクが最後に実行した詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="62c0c-116">View the details of the tasks' last several runs by selecting its name.</span></span>

### <a name="status-types"></a><span data-ttu-id="62c0c-117">状態の種類</span><span class="sxs-lookup"><span data-stu-id="62c0c-117">Status types</span></span>

<span data-ttu-id="62c0c-118">タスクには、6 種類の状態があります。</span><span class="sxs-lookup"><span data-stu-id="62c0c-118">There are six types of status for tasks.</span></span> <span data-ttu-id="62c0c-119">次の状態タイプは、*一致*、*マージ*、*データ ソース*、*セグメント*、*対策*、*エンリッチメント*、*活動内容*、 *予測* ページ上でも表示されます。</span><span class="sxs-lookup"><span data-stu-id="62c0c-119">The following status types also show on the *Match*, *Merge*, *Data sources*, *Segments*, *Measures*, *Enrichment*, *Activities*, and *Predictions* pages:</span></span>

- <span data-ttu-id="62c0c-120">**処理:** タスクは進行中です。</span><span class="sxs-lookup"><span data-stu-id="62c0c-120">**Processing:** Task is in progress.</span></span> <span data-ttu-id="62c0c-121">ステータスは、完了または失敗に変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="62c0c-121">The status can change to Successful or Failure.</span></span>
- <span data-ttu-id="62c0c-122">**完了:** タスクは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="62c0c-122">**Successful:** Task completed successfully.</span></span>
- <span data-ttu-id="62c0c-123">**スキップ :** タスクがスキップされました。</span><span class="sxs-lookup"><span data-stu-id="62c0c-123">**Skipped:** Task got skipped.</span></span> <span data-ttu-id="62c0c-124">このタスクが依存している 1 つ以上のダウン ストリームプロセスが失敗しているか、スキップされました。</span><span class="sxs-lookup"><span data-stu-id="62c0c-124">One or more of the downstream processes this task depends on are failing or got skipped.</span></span>
- <span data-ttu-id="62c0c-125">**失敗:** タスクの処理に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="62c0c-125">**Failure:** Processing  of the task has failed.</span></span>
- <span data-ttu-id="62c0c-126">**キャンセル:** 処理が完了する前にユーザーによってキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="62c0c-126">**Canceled:** Processing was canceled by the user before it finished.</span></span>
- <span data-ttu-id="62c0c-127">**キュー登録済み:** 処理はキューに入っており、すべての上流タスクが完了すると開始されます。</span><span class="sxs-lookup"><span data-stu-id="62c0c-127">**Queued:** Processing is queued and will start once all the upstream tasks are completed.</span></span> <span data-ttu-id="62c0c-128">詳細については、[更新ポリシー](#refresh-policies) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62c0c-128">For more information, see [Refresh policies](#refresh-policies).</span></span>

### <a name="refresh-policies"></a><span data-ttu-id="62c0c-129">更新ポリシー</span><span class="sxs-lookup"><span data-stu-id="62c0c-129">Refresh policies</span></span>

<span data-ttu-id="62c0c-130">このリストには、主要プロセスごとの更新ポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="62c0c-130">This list shows the refresh policies for each of the main processes:</span></span>

- <span data-ttu-id="62c0c-131">**データソース:** [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-131">**Data sources:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="62c0c-132">その他のプロセスには依存しません。</span><span class="sxs-lookup"><span data-stu-id="62c0c-132">Doesn't depend on any other process.</span></span> <span data-ttu-id="62c0c-133">一致は、このプロセスが正常に完了するかどうかに依存します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-133">Match depends on the successful completion of this process.</span></span>
- <span data-ttu-id="62c0c-134">**一致:** [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-134">**Match:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="62c0c-135">一致の定義で使用されるデータソースの処理に依存します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-135">Depends on the processing of the data sources used in the match definition.</span></span> <span data-ttu-id="62c0c-136">マージは、このプロセスが正常に完了するかどうかに依存します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-136">Merge depends on the successful completion of this process.</span></span>
- <span data-ttu-id="62c0c-137">**マージ:** [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-137">**Merge**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="62c0c-138">一致プロセスが正常に完了するかどうかに依存します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-138">Depends on the completion of the match process.</span></span> <span data-ttu-id="62c0c-139">セグメント、メジャー、エンリッチメント、検索、活動、予測、およびデータ準備は、このプロセスが正常に完了するかどうかに依存します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-139">Segments, measures, enrichment, search, activities, predictions, and data preparation depend on the successful completion of this process.</span></span>
- <span data-ttu-id="62c0c-140">**セグメント**: 手動 (単回更新)、および [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-140">**Segments**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="62c0c-141">マージに依存します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-141">Depends on Merge.</span></span> <span data-ttu-id="62c0c-142">インサイトはその処理に依存します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-142">Insights depend on its processing.</span></span>
- <span data-ttu-id="62c0c-143">**メジャー**: 手動 (単回更新) 、および [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-143">**Measures**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="62c0c-144">マージに依存します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-144">Depends on Merge.</span></span>
- <span data-ttu-id="62c0c-145">**メジャー**: 手動 (単回更新)、および [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-145">**Activities**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="62c0c-146">マージに依存します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-146">Depends on Merge.</span></span>
- <span data-ttu-id="62c0c-147">**エンリッチメント**: 手動 (単回更新)、および [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-147">**Enrichment**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="62c0c-148">マージに依存します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-148">Depends on Merge.</span></span>
- <span data-ttu-id="62c0c-149">**検索**: 手動 (単回更新)、および [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-149">**Search**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="62c0c-150">マージに依存します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-150">Depends on Merge.</span></span>
- <span data-ttu-id="62c0c-151">**データ準備**: [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-151">**Data preparation**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="62c0c-152">マージに依存します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-152">Depends on Merge.</span></span>
- <span data-ttu-id="62c0c-153">**インサイト**: 手動 (単回更新)、および [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-153">**Insights**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="62c0c-154">セグメントに依存します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-154">Depends on Segments.</span></span>

<span data-ttu-id="62c0c-155">タスクのステータスを選択して、そこにあったジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="62c0c-155">Select the status of a task to see the progress details of the entire job it was in.</span></span> <span data-ttu-id="62c0c-156">上記の更新ポリシーは、**スキップした** または **待機中** のタスクに対処するために何ができるかを理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="62c0c-156">The refresh policies above can help to understand what you can do to address a **Skipped** or **Queued** task.</span></span>

## <a name="schedule-tab"></a><span data-ttu-id="62c0c-157">スケジュール​​ タブ</span><span class="sxs-lookup"><span data-stu-id="62c0c-157">Schedule tab</span></span>

<span data-ttu-id="62c0c-158">**スケジュール** タブを使用して、[取り込まれたデータ ソース](data-sources.md) すべての自動更新をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="62c0c-158">Use the **Schedule** tab to schedule automatic refreshes of all your [ingested data sources](data-sources.md).</span></span> <span data-ttu-id="62c0c-159">自動更新により、データソースの更新が統一された顧客プロファイルに確実に反映されます。</span><span class="sxs-lookup"><span data-stu-id="62c0c-159">Automatic refreshes help ensure that updates from your data sources are reflected in your unified customer profiles.</span></span>

1. <span data-ttu-id="62c0c-160">対象者に関するインサイトで、**管理** > **システム** に移動し、**スケジュール** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-160">In audience insights, go to **Admin** > **System** and select the **Schedule** tab.</span></span>

2. <span data-ttu-id="62c0c-161">スケジュールされた更新の規定の状態は **オフ** です。</span><span class="sxs-lookup"><span data-stu-id="62c0c-161">The default state for the scheduled refresh is **Off**.</span></span> <span data-ttu-id="62c0c-162">スケジュールされた更新を有効にするには、画面上部のトグルを **ON** に変更します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-162">To enable scheduled refreshes, change the toggle at the top of the screen to **On**.</span></span>

3. <span data-ttu-id="62c0c-163">**毎週** の更新(デフォルト) か **毎日** の更新を選択します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-163">Choose between **Weekly** (default) and **Daily** refreshes.</span></span> <span data-ttu-id="62c0c-164">毎週更新をスケジュールする場合は、更新を実行する日を 1 日以上選択します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-164">If you intend to schedule weekly refreshes, select one or more days on which you want to run the refresh.</span></span>

4. <span data-ttu-id="62c0c-165">**タイム ゾーン** を設定し、続いて **時間** ドロップダウンで更新のタイミングを設定します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-165">Set your **Time zone**, then use the **Time** dropdown to set your refresh timing.</span></span> <span data-ttu-id="62c0c-166">終了したら、**設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-166">When you're finished, select **Set**.</span></span> <span data-ttu-id="62c0c-167">1 日に複数の更新をスケジュールする場合は、**別の時間を追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-167">If you'd like to schedule multiple refreshes in a single day, select **Add another time**.</span></span>

5. <span data-ttu-id="62c0c-168">**保存** を選択して変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-168">Select **Save** to apply your changes.</span></span>

## <a name="about-tab"></a><span data-ttu-id="62c0c-169">タブについて</span><span class="sxs-lookup"><span data-stu-id="62c0c-169">About tab</span></span>

<span data-ttu-id="62c0c-170">**情報** タブには組織の **表示名**、アクティブな **環境 ID**、**領域**、**セッション ID** が含まれます。</span><span class="sxs-lookup"><span data-stu-id="62c0c-170">The **About** tab contains your organization's **Display name**, the active **Environment ID**, the **Region**, and your **Session ID**.</span></span> <span data-ttu-id="62c0c-171">複数の作業環境がある場合は、それぞれに簡単に識別できる表示名を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="62c0c-171">If you have more than one work environment, you should give each an easily identifiable display name.</span></span>

## <a name="general-tab"></a><span data-ttu-id="62c0c-172">[全般] タブ</span><span class="sxs-lookup"><span data-stu-id="62c0c-172">General tab</span></span>

<span data-ttu-id="62c0c-173">**全般** タブには、**言語** そして **国/地域の形式** の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="62c0c-173">There are two options on the **General** tab, **Language** and **Country/Region format**.</span></span>

<span data-ttu-id="62c0c-174">アプリは、[複数の言語をサポートしています](supported-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="62c0c-174">The app [supports a number of languages](supported-languages.md).</span></span> <span data-ttu-id="62c0c-175">優先する言語を変更するには、ドロップダウンから **言語** を選択します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-175">To change your preferred language, choose a **Language** from the dropdown.</span></span>

<span data-ttu-id="62c0c-176">日付、時刻、数値の優先フォーマットを変更するには、**国/地域の形式** ドロップダウンを使用します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-176">To change your preferred formatting for dates, time, and numbers, use the **Country/Region format** dropdown.</span></span> <span data-ttu-id="62c0c-177">このフィールドの下にフォーマット プレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="62c0c-177">A formatting preview is displayed under this field.</span></span> <span data-ttu-id="62c0c-178">新しい言語を選択すると、システムは自動的に選択を提案します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-178">The system will automatically suggest a selection when you choose a new language.</span></span>

<span data-ttu-id="62c0c-179">**保存** を選択し、選択したものを確認します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-179">Select **Save** to confirm your selections.</span></span>

## <a name="api-usage-tab"></a><span data-ttu-id="62c0c-180">API の使用率タブ</span><span class="sxs-lookup"><span data-stu-id="62c0c-180">API usage tab</span></span>

<span data-ttu-id="62c0c-181">リアルタイム API の使用に関する詳細を検索し、特定の概算時間で発生したイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-181">Find details about the real-time API usage and see which events happened in a given time frame.</span></span> <span data-ttu-id="62c0c-182">**概算時間を選択します** ドロップダウン メニューで概算時間を選択します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-182">You choose the time frame in the **Select a time frame** drop-down menu.</span></span> 

<span data-ttu-id="62c0c-183">**API の使用** には、3 つのセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="62c0c-183">The **API usage** contains three sections:</span></span> 
- <span data-ttu-id="62c0c-184">**API 呼び出し** - 選択した概算時間での API への呼び出しのs集計数を視覚化するグラフ。</span><span class="sxs-lookup"><span data-stu-id="62c0c-184">**API calls** - a chart that visualizes the aggregated number of calls to the API in the selected time frame.</span></span>

- <span data-ttu-id="62c0c-185">**データ転送** - 選択した概算時間で API を介して転送されたデータの量を示すグラフ。</span><span class="sxs-lookup"><span data-stu-id="62c0c-185">**Data transfer** - a chart that shows the amount of data that was transferred through the API in the selected time frame.</span></span>

-  <span data-ttu-id="62c0c-186">**操作** - 使用可能な各 API 操作の行と操作の使用法に関する詳細を含むテーブル。</span><span class="sxs-lookup"><span data-stu-id="62c0c-186">**Operations** - a table with rows for each available API operation and details about the usage of the operations.</span></span> <span data-ttu-id="62c0c-187">[API リファレンス](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)に移動する操作名を選択できます。</span><span class="sxs-lookup"><span data-stu-id="62c0c-187">You can select an operation name to go to [the API reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

   <span data-ttu-id="62c0c-188">[リアルタイムのデータ インジェスト](real-time-data-ingestion.md)を使用する操作には、リアルタイムの API 使用状況を表示するための双眼鏡記号の付いたボタンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="62c0c-188">Operations which use [real-time data ingestion](real-time-data-ingestion.md) contain a button with a binocular symbol to view real-time API usage.</span></span> <span data-ttu-id="62c0c-189">ボタンを選択して、現在の環境でリアルタイム API の使用状況の詳細を含むサイド ペインを開きます。</span><span class="sxs-lookup"><span data-stu-id="62c0c-189">Select the button to open a side pane containing usage details for the real-time API usage in the current environment.</span></span>   
   <span data-ttu-id="62c0c-190">**リアルタイム API の使用** ペインで **グループ化の基準** ボックスを使って、リアルタイムのインタラクションを最適に表示する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="62c0c-190">Use the **Group by** box in the **Real-time API usage** pane to choose how to best present your real-time interactions.</span></span> <span data-ttu-id="62c0c-191">API メソッド、エンティティー修飾名 (取り込んだエンティティー)、作成者 (イベントのソース)、結果 (成功または失敗)、またはエラー コード別にデータをグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="62c0c-191">You can group the data by API method, entity qualified name (ingested entity), created by (source of the event), result (success or failure) or error codes.</span></span> <span data-ttu-id="62c0c-192">データは履歴グラフおよびテーブルとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="62c0c-192">The data is available as a history chart and as a table.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]