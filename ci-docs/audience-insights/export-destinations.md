---
title: Customer Insights からデータをエクスポートする
description: エクスポートを管理してデータを共有します。
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253046"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="76151-103">エクスポート (プレビュー) の概要</span><span class="sxs-lookup"><span data-stu-id="76151-103">Exports (preview) overview</span></span>

<span data-ttu-id="76151-104">**エクスポート** ページには、構成済みのすべてのエクスポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="76151-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="76151-105">エクスポートは、特定のデータをさまざまなアプリケーションと共有します。</span><span class="sxs-lookup"><span data-stu-id="76151-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="76151-106">顧客プロファイルまたはエンティティ、スキーマ、およびマッピングの詳細を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="76151-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="76151-107">各エクスポートには、[認証とアクセスを管理するために、管理者によって設定された接続](connections.md) が必要です。</span><span class="sxs-lookup"><span data-stu-id="76151-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="76151-108">**データ** > **エクスポート** に移動し、エクスポート ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="76151-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="76151-109">すべてのユーザー ロールには、構成済みのエクスポートを表示するアクセス権があります。</span><span class="sxs-lookup"><span data-stu-id="76151-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="76151-110">コマンド バーの検索フィールドを使用して、名前、接続名、または接続の種類でエクスポートを検索します。</span><span class="sxs-lookup"><span data-stu-id="76151-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="76151-111">新しいエクスポートの設定</span><span class="sxs-lookup"><span data-stu-id="76151-111">Set up a new export</span></span>

<span data-ttu-id="76151-112">エクスポートを設定または編集するには、使用可能な接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="76151-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="76151-113">接続は [ユーザー ロール](permissions.md) によって異なります:</span><span class="sxs-lookup"><span data-stu-id="76151-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="76151-114">管理者はすべての接続にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="76151-114">Administrators have access to all connections.</span></span> <span data-ttu-id="76151-115">また、エクスポートを設定するときに新しい接続を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="76151-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="76151-116">共同作成者は、特定の接続にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="76151-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="76151-117">接続の構成と共有を管理者に依存します。</span><span class="sxs-lookup"><span data-stu-id="76151-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="76151-118">エクスポートの一覧には、共同作成者がエクスポートを編集できるか、表示のみできるかが **アクセス許可** 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="76151-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="76151-119">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76151-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="76151-120">ビューアーは、既存のエクスポートを表示することはできますが、作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="76151-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="76151-121">新しいエクスポートの定義</span><span class="sxs-lookup"><span data-stu-id="76151-121">Define a new export</span></span>

1. <span data-ttu-id="76151-122">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="76151-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="76151-123">**エクスポートの追加** を選択し、新しいエクスポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="76151-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="76151-124">**エクスポートの設定** ペインで、使用する接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="76151-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="76151-125">[接続](connections.md) は、管理者によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="76151-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="76151-126">必要な詳細を入力して **保存** 選択し、エクスポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="76151-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="76151-127">既存のエクスポートに基づく新しいエクスポートの定義</span><span class="sxs-lookup"><span data-stu-id="76151-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="76151-128">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="76151-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="76151-129">エクスポートの一覧で、複製するエクスポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="76151-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="76151-130">コマンド バーで **複製の作成** を選択して、選択したエクスポートの詳細が表示された **エクスポートの設定** ペインを開きます。</span><span class="sxs-lookup"><span data-stu-id="76151-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="76151-131">エクスポートを確認して調整し、**保存** を選択て、新しいエクスポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="76151-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="76151-132">エクスポートの編集</span><span class="sxs-lookup"><span data-stu-id="76151-132">Edit an export</span></span>

1. <span data-ttu-id="76151-133">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="76151-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="76151-134">エクスポートの一覧で、編集するエクスポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="76151-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="76151-135">コマンド バーで、**編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="76151-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="76151-136">更新する値を変更し、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="76151-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="76151-137">エクスポートとエクスポートの詳細の表示</span><span class="sxs-lookup"><span data-stu-id="76151-137">View exports and export details</span></span>

<span data-ttu-id="76151-138">エクスポート先を作成した後、**データ** > **エクスポート** に表示さます。</span><span class="sxs-lookup"><span data-stu-id="76151-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="76151-139">すべてのユーザーは、共有されているデータとその最新の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="76151-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="76151-140">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="76151-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="76151-141">編集権限のないユーザーは、**編集** ではなく **ビュー** を選択して、エクスポートの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="76151-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="76151-142">サイド ペインには、エクスポートの構成が表示されます。</span><span class="sxs-lookup"><span data-stu-id="76151-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="76151-143">編集権限がないと、値を変更できません。</span><span class="sxs-lookup"><span data-stu-id="76151-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="76151-144">**閉じる** を選択して、エクスポート ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="76151-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="76151-145">エクスポートのスケジュールと実行</span><span class="sxs-lookup"><span data-stu-id="76151-145">Schedule and run exports</span></span>

<span data-ttu-id="76151-146">構成する各エクスポートには、更新スケジュールがあります。</span><span class="sxs-lookup"><span data-stu-id="76151-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="76151-147">更新中に、システムはエクスポートに含める新しいデータまたは更新されたデータを検索します。</span><span class="sxs-lookup"><span data-stu-id="76151-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="76151-148">既定では、エクスポートはすべての [スケジュールされたシステム更新](system.md#schedule-tab) の一部として実行されます。</span><span class="sxs-lookup"><span data-stu-id="76151-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="76151-149">更新スケジュールをカスタマイズするか、オフにしてエクスポートを手動で実行できます。</span><span class="sxs-lookup"><span data-stu-id="76151-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="76151-150">エクスポートのスケジュールは、環境の状態によって異なります。</span><span class="sxs-lookup"><span data-stu-id="76151-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="76151-151">スケジュールされたエクスポートを開始するときに、進行中の [依存関係](system.md#refresh-policies) に更新がある場合、システムは最初に依存関係を完了してから、エクスポートを実行します。</span><span class="sxs-lookup"><span data-stu-id="76151-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="76151-152">エクスポートが最後に更新された日時を列 **最終更新** で確認できます。</span><span class="sxs-lookup"><span data-stu-id="76151-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="76151-153">エクスポートのスケジュール</span><span class="sxs-lookup"><span data-stu-id="76151-153">Schedule exports</span></span>

<span data-ttu-id="76151-154">個々のエクスポートまたは複数のエクスポートのカスタム更新スケジュールを一度に定義できます。</span><span class="sxs-lookup"><span data-stu-id="76151-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="76151-155">現在定義されているスケジュールは、エクスポート リストの **スケジュール** 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="76151-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="76151-156">スケジュールを変更するアクセス許可は、[エクスポートを編集および定義する](export-destinations.md#set-up-a-new-export) 許可と同じです。</span><span class="sxs-lookup"><span data-stu-id="76151-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="76151-157">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="76151-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="76151-158">スケジュールするエクスポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="76151-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="76151-159">コマンド バーで、**スケジュール** を選択します。</span><span class="sxs-lookup"><span data-stu-id="76151-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="76151-160">**エクスポートのスケジュール** ペインで、**スケジュールの実行** を **オン** に設定して、エクスポートを自動的に実行します。</span><span class="sxs-lookup"><span data-stu-id="76151-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="76151-161">手動で更新するには、**オフ** に設定します。</span><span class="sxs-lookup"><span data-stu-id="76151-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="76151-162">自動的に更新されたエクスポートの場合は、**繰り返し** 値を選択し、その詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="76151-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="76151-163">定義された時間は、繰り返しのすべてのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="76151-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="76151-164">これは、エクスポートの更新を開始する時間です。</span><span class="sxs-lookup"><span data-stu-id="76151-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="76151-165">**保存** を選択して、変更を適用してアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="76151-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="76151-166">複数のエクスポートのスケジュールを編集する場合は、**スケジュールの保持または上書き** で選択する必要があります:</span><span class="sxs-lookup"><span data-stu-id="76151-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="76151-167">**スケジュールを個別に保持**: 選択したエクスポートに対して以前に定義したスケジュールを保持し、無効化または有効化のみを行います。</span><span class="sxs-lookup"><span data-stu-id="76151-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="76151-168">**選択したすべてのエクスポートの新しいスケジュールを定義**: 選択したエクスポートの既存のスケジュールを上書きします。</span><span class="sxs-lookup"><span data-stu-id="76151-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="76151-169">オンデマンドでエクスポートを実行</span><span class="sxs-lookup"><span data-stu-id="76151-169">Run exports on demand</span></span>

<span data-ttu-id="76151-170">スケジュール更新を待たずにデータをエクスポートするには、**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="76151-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="76151-171">すべてのエクスポートを実行するには、コマンドバーで **すべて実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="76151-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="76151-172">このアクションは、アクティブなスケジュールを持つエクスポートのみを実行します。</span><span class="sxs-lookup"><span data-stu-id="76151-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="76151-173">単一のエクスポートを実行するには、一覧で選択し、コマンド バーの **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="76151-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="76151-174">これが、アクティブなスケジュールなしでエクスポートを実行する方法です。</span><span class="sxs-lookup"><span data-stu-id="76151-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="76151-175">エクスポートの削除</span><span class="sxs-lookup"><span data-stu-id="76151-175">Remove an Export</span></span>

1. <span data-ttu-id="76151-176">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="76151-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="76151-177">削除するエクスポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="76151-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="76151-178">コマンド バーで、**削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="76151-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="76151-179">確認画面で **削除** を選択して削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="76151-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
