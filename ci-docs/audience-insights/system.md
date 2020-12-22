---
title: 対象者に関するインサイトのシステム構成
description: Dynamics 365 Customer Insights 対象者に関するインサイト機能のシステム設定について説明します。
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406193"
---
# <a name="system-configuration"></a><span data-ttu-id="79392-103">システム構成</span><span class="sxs-lookup"><span data-stu-id="79392-103">System configuration</span></span>

<span data-ttu-id="79392-104">**システム** ページには 4つ のタブがあります: **状態**、**スケジュール**、**詳細**、**全般**。</span><span class="sxs-lookup"><span data-stu-id="79392-104">The **System** page includes four tabs: **Status**, **Schedule**, **About**, and **General**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79392-105">![システム ページ](media/system-tabs.png "システム ページ")</span><span class="sxs-lookup"><span data-stu-id="79392-105">![System page](media/system-tabs.png "System page")</span></span>

## <a name="status-tab"></a><span data-ttu-id="79392-106">ステータス タブ</span><span class="sxs-lookup"><span data-stu-id="79392-106">Status tab</span></span>

<span data-ttu-id="79392-107">**状態タブ** では、データ インジェストの進行状況といくつかの重要な製品プロセスの進行状況を追跡します。</span><span class="sxs-lookup"><span data-stu-id="79392-107">The **Status tab** lets you track the progress of data ingestion, data exports, and several important product processes.</span></span> <span data-ttu-id="79392-108">このタブの情報を確認して、アクティブなプロセスの完全性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="79392-108">Review the information on this tab to ensure the completeness of active processes.</span></span>

<span data-ttu-id="79392-109">このタブには、**データソース**、**システム プロセス**、**データの準備** のステータス テーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="79392-109">This tab includes status tables for **Data sources**, **System processes**, and **Data preparation**.</span></span> <span data-ttu-id="79392-110">各テーブルは、タスクの **名前** とそれに対応するエンティティ、その最新の実行の **状態**、**最終更新** を追跡します。</span><span class="sxs-lookup"><span data-stu-id="79392-110">Each table tracks the **Name** of the task and its corresponding entity, the **Status** of its most recent run, and when it was **Last updated**.</span></span>

<span data-ttu-id="79392-111">名前を選択すると、タスクが最後に実行した詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="79392-111">View the details of the tasks' last several runs by selecting its name.</span></span>

### <a name="status-types"></a><span data-ttu-id="79392-112">状態の種類</span><span class="sxs-lookup"><span data-stu-id="79392-112">Status types</span></span>

<span data-ttu-id="79392-113">タスクには、6 種類の状態があります。</span><span class="sxs-lookup"><span data-stu-id="79392-113">There are six types of status for tasks.</span></span> <span data-ttu-id="79392-114">次の状態タイプは、*一致*、*マージ*、*データ ソース*、*セグメント*、*対策*、*エンリッチメント*、*活動内容*、 *予測* ページ上でも表示されます。</span><span class="sxs-lookup"><span data-stu-id="79392-114">The following status types also show on the *Match*, *Merge*, *Data sources*, *Segments*, *Measures*, *Enrichment*, *Activities*, and *Predictions* pages:</span></span>

- <span data-ttu-id="79392-115">**処理:** タスクは進行中です。</span><span class="sxs-lookup"><span data-stu-id="79392-115">**Processing:** Task is in progress.</span></span> <span data-ttu-id="79392-116">ステータスは、完了または失敗に変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79392-116">The status can change to Successful or Failure.</span></span>
- <span data-ttu-id="79392-117">**完了:** タスクは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="79392-117">**Successful:** Task completed successfully.</span></span>
- <span data-ttu-id="79392-118">**スキップ :** タスクがスキップされました。</span><span class="sxs-lookup"><span data-stu-id="79392-118">**Skipped:** Task got skipped.</span></span> <span data-ttu-id="79392-119">このタスクが依存している 1 つ以上のダウン ストリームプロセスが失敗しているか、スキップされました。</span><span class="sxs-lookup"><span data-stu-id="79392-119">One or more of the downstream processes this task depends on are failing or got skipped.</span></span>
- <span data-ttu-id="79392-120">**失敗:** タスクの処理に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="79392-120">**Failure:** Processing  of the task has failed.</span></span>
- <span data-ttu-id="79392-121">**キャンセル:** 処理が完了する前にユーザーによってキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="79392-121">**Canceled:** Processing was canceled by the user before it finished.</span></span>
- <span data-ttu-id="79392-122">**待機中:** 処理はキューに入っており、すべてのダウンストリーム タスクが完了すると開始されます。</span><span class="sxs-lookup"><span data-stu-id="79392-122">**Queued:** Processing is queued and will start once all the downstream tasks are completed.</span></span> <span data-ttu-id="79392-123">詳細については、[更新ポリシー](#refresh-policies) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79392-123">For more information, see [Refresh policies](#refresh-policies).</span></span>

### <a name="refresh-policies"></a><span data-ttu-id="79392-124">更新ポリシー</span><span class="sxs-lookup"><span data-stu-id="79392-124">Refresh policies</span></span>

<span data-ttu-id="79392-125">このリストには、主要プロセスごとの更新ポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79392-125">This list shows the refresh policies for each of the main processes:</span></span>

- <span data-ttu-id="79392-126">**データソース:** [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="79392-126">**Data sources:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="79392-127">その他のプロセスには依存しません。</span><span class="sxs-lookup"><span data-stu-id="79392-127">Doesn't depend on any other process.</span></span> <span data-ttu-id="79392-128">一致は、このプロセスが正常に完了するかどうかに依存します。</span><span class="sxs-lookup"><span data-stu-id="79392-128">Match depends on the successful completion of this process.</span></span>
- <span data-ttu-id="79392-129">**一致:** [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="79392-129">**Match:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="79392-130">一致の定義で使用されるデータソースの処理に依存します。</span><span class="sxs-lookup"><span data-stu-id="79392-130">Depends on the processing of the data sources used in the match definition.</span></span> <span data-ttu-id="79392-131">マージは、このプロセスが正常に完了するかどうかに依存します。</span><span class="sxs-lookup"><span data-stu-id="79392-131">Merge depends on the successful completion of this process.</span></span>
- <span data-ttu-id="79392-132">**マージ:** [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="79392-132">**Merge**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="79392-133">一致プロセスが正常に完了するかどうかに依存します。</span><span class="sxs-lookup"><span data-stu-id="79392-133">Depends on the completion of the match process.</span></span> <span data-ttu-id="79392-134">セグメント、メジャー、エンリッチメント、検索、活動、予測、およびデータ準備は、このプロセスが正常に完了するかどうかに依存します。</span><span class="sxs-lookup"><span data-stu-id="79392-134">Segments, measures, enrichment, search, activities, predictions, and data preparation depend on the successful completion of this process.</span></span>
- <span data-ttu-id="79392-135">**セグメント**: 手動 (単回更新)、および [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="79392-135">**Segments**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="79392-136">マージに依存します。</span><span class="sxs-lookup"><span data-stu-id="79392-136">Depends on Merge.</span></span> <span data-ttu-id="79392-137">インサイトはその処理に依存します。</span><span class="sxs-lookup"><span data-stu-id="79392-137">Insights depend on its processing.</span></span>
- <span data-ttu-id="79392-138">**メジャー**: 手動 (単回更新) 、および [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="79392-138">**Measures**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="79392-139">マージに依存します。</span><span class="sxs-lookup"><span data-stu-id="79392-139">Depends on Merge.</span></span>
- <span data-ttu-id="79392-140">**メジャー**: 手動 (単回更新)、および [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="79392-140">**Activities**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="79392-141">マージに依存します。</span><span class="sxs-lookup"><span data-stu-id="79392-141">Depends on Merge.</span></span>
- <span data-ttu-id="79392-142">**エンリッチメント**: 手動 (単回更新)、および [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="79392-142">**Enrichment**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="79392-143">マージに依存します。</span><span class="sxs-lookup"><span data-stu-id="79392-143">Depends on Merge.</span></span>
- <span data-ttu-id="79392-144">**検索**: 手動 (単回更新)、および [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="79392-144">**Search**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="79392-145">マージに依存します。</span><span class="sxs-lookup"><span data-stu-id="79392-145">Depends on Merge.</span></span>
- <span data-ttu-id="79392-146">**データ準備**: [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="79392-146">**Data preparation**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="79392-147">マージに依存します。</span><span class="sxs-lookup"><span data-stu-id="79392-147">Depends on Merge.</span></span>
- <span data-ttu-id="79392-148">**インサイト**: 手動 (単回更新)、および [構成済みスケジュール](#schedule-tab) に従って実行します。</span><span class="sxs-lookup"><span data-stu-id="79392-148">**Insights**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="79392-149">セグメントに依存します。</span><span class="sxs-lookup"><span data-stu-id="79392-149">Depends on Segments.</span></span>

<span data-ttu-id="79392-150">タスクのステータスを選択して、そこにあったジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="79392-150">Select the status of a task to see the progress details of the entire job it was in.</span></span> <span data-ttu-id="79392-151">上記の更新ポリシーは、**スキップした** または **待機中** のタスクに対処するために何ができるかを理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="79392-151">The refresh policies above can help to understand what you can do to address a **Skipped** or **Queued** task.</span></span>

## <a name="schedule-tab"></a><span data-ttu-id="79392-152">スケジュール​​ タブ</span><span class="sxs-lookup"><span data-stu-id="79392-152">Schedule tab</span></span>

<span data-ttu-id="79392-153">**スケジュール** タブを使用して、[取り込まれたデータ ソース](data-sources.md) すべての自動更新をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="79392-153">Use the **Schedule** tab to schedule automatic refreshes of all your [ingested data sources](data-sources.md).</span></span> <span data-ttu-id="79392-154">自動更新により、データソースの更新が統一された顧客プロファイルに確実に反映されます。</span><span class="sxs-lookup"><span data-stu-id="79392-154">Automatic refreshes help ensure that updates from your data sources are reflected in your unified customer profiles.</span></span>

1. <span data-ttu-id="79392-155">対象者に関するインサイトで、**管理** > **システム** に移動し、**スケジュール** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="79392-155">In audience insights, go to **Admin** > **System** and select the **Schedule** tab.</span></span>

2. <span data-ttu-id="79392-156">スケジュールされた更新の規定の状態は **オフ** です。</span><span class="sxs-lookup"><span data-stu-id="79392-156">The default state for the scheduled refresh is **Off**.</span></span> <span data-ttu-id="79392-157">スケジュールされた更新を有効にするには、画面上部のトグルを **ON** に変更します。</span><span class="sxs-lookup"><span data-stu-id="79392-157">To enable scheduled refreshes, change the toggle at the top of the screen to **On**.</span></span>

3. <span data-ttu-id="79392-158">**毎週** の更新(デフォルト) か **毎日** の更新を選択します。</span><span class="sxs-lookup"><span data-stu-id="79392-158">Choose between **Weekly** (default) and **Daily** refreshes.</span></span> <span data-ttu-id="79392-159">毎週更新をスケジュールする場合は、更新を実行する日を 1 日以上選択します。</span><span class="sxs-lookup"><span data-stu-id="79392-159">If you intend to schedule weekly refreshes, select one or more days on which you want to run the refresh.</span></span>

4. <span data-ttu-id="79392-160">**タイム ゾーン** を設定し、続いて **時間** ドロップダウンで更新のタイミングを設定します。</span><span class="sxs-lookup"><span data-stu-id="79392-160">Set your **Time zone**, then use the **Time** dropdown to set your refresh timing.</span></span> <span data-ttu-id="79392-161">終了したら、**設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="79392-161">When you're finished, select **Set**.</span></span> <span data-ttu-id="79392-162">1 日に複数の更新をスケジュールする場合は、**別の時間を追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="79392-162">If you'd like to schedule multiple refreshes in a single day, select **Add another time**.</span></span>

5. <span data-ttu-id="79392-163">**保存** を選択して変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="79392-163">Select **Save** to apply your changes.</span></span>

## <a name="about-tab"></a><span data-ttu-id="79392-164">タブについて</span><span class="sxs-lookup"><span data-stu-id="79392-164">About tab</span></span>

<span data-ttu-id="79392-165">**情報** タブには組織の **表示名**、アクティブな **環境 ID**、**領域**、**セッション ID** が含まれます。</span><span class="sxs-lookup"><span data-stu-id="79392-165">The **About** tab contains your organization's **Display name**, the active **Environment ID**, the **Region**, and your **Session ID**.</span></span> <span data-ttu-id="79392-166">複数の作業環境がある場合は、それぞれに簡単に識別できる表示名を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="79392-166">If you have more than one work environment, you should give each an easily identifiable display name.</span></span>

## <a name="general-tab"></a><span data-ttu-id="79392-167">[全般] タブ</span><span class="sxs-lookup"><span data-stu-id="79392-167">General tab</span></span>

<span data-ttu-id="79392-168">**全般** タブには、**言語** そして **国/地域の形式** の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="79392-168">There are two options on the **General** tab, **Language** and **Country/Region format**.</span></span>

<span data-ttu-id="79392-169">アプリは、[複数の言語をサポートしています](supported-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="79392-169">The app [supports a number of languages](supported-languages.md).</span></span> <span data-ttu-id="79392-170">優先する言語を変更するには、ドロップダウンから **言語** を選択します。</span><span class="sxs-lookup"><span data-stu-id="79392-170">To change your preferred language, choose a **Language** from the dropdown.</span></span>

<span data-ttu-id="79392-171">日付、時刻、数値の優先フォーマットを変更するには、**国/地域の形式** ドロップダウンを使用します。</span><span class="sxs-lookup"><span data-stu-id="79392-171">To change your preferred formatting for dates, time, and numbers, use the **Country/Region format** dropdown.</span></span> <span data-ttu-id="79392-172">このフィールドの下にフォーマット プレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79392-172">A formatting preview is displayed under this field.</span></span> <span data-ttu-id="79392-173">新しい言語を選択すると、システムは自動的に選択を提案します。</span><span class="sxs-lookup"><span data-stu-id="79392-173">The system will automatically suggest a selection when you choose a new language.</span></span>

<span data-ttu-id="79392-174">**保存** を選択し、選択したものを確認します。</span><span class="sxs-lookup"><span data-stu-id="79392-174">Select **Save** to confirm your selections.</span></span>

## <a name="api-usage-tab"></a><span data-ttu-id="79392-175">API の使用率タブ</span><span class="sxs-lookup"><span data-stu-id="79392-175">API usage tab</span></span>

<span data-ttu-id="79392-176">リアルタイム API の使用状況の詳細情報を確認し、特定の時間範囲でどのイベントが発生したかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="79392-176">Find details about the real-time API usage and see which events happened in a given time range.</span></span> <span data-ttu-id="79392-177">詳細については、[リアルタイム ワークフロー インジェスト](real-time-data-ingestion.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79392-177">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>
