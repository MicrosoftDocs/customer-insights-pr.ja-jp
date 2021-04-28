---
title: Customer Insights からデータをエクスポートする
description: エクスポートを管理してデータを共有します。
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896149"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="e8eb0-103">エクスポート (プレビュー) の概要</span><span class="sxs-lookup"><span data-stu-id="e8eb0-103">Exports (preview) overview</span></span>

<span data-ttu-id="e8eb0-104">**エクスポート** ページには、構成済みのすべてのエクスポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="e8eb0-105">エクスポートは、特定のデータをさまざまなアプリケーションと共有します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="e8eb0-106">顧客プロファイルまたはエンティティ、スキーマ、およびマッピングの詳細を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="e8eb0-107">各エクスポートには、[認証とアクセスを管理するために、管理者によって設定された接続](connections.md) が必要です。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e8eb0-108">2021 年 3 月まで、エクスポートでは、対応するサービスへの接続が自動的に作成されていました。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="e8eb0-109">エクスポートを作成する前に、[管理者が作成および共有する接続](connections.md) が必要になりました。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="e8eb0-110">**データ** > **エクスポート** に移動し、エクスポート ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="e8eb0-111">すべてのユーザー ロールには、構成済みのエクスポートを表示するアクセス権があります。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="e8eb0-112">コマンド バーの検索フィールドを使用して、名前、接続名、または接続の種類でエクスポートを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="e8eb0-113">新しいエクスポートの設定</span><span class="sxs-lookup"><span data-stu-id="e8eb0-113">Set up a new export</span></span>

<span data-ttu-id="e8eb0-114">エクスポートを設定または編集するには、使用可能な接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="e8eb0-115">接続は [ユーザー ロール](permissions.md) によって異なります:</span><span class="sxs-lookup"><span data-stu-id="e8eb0-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="e8eb0-116">管理者はすべての接続にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-116">Administrators have access to all connections.</span></span> <span data-ttu-id="e8eb0-117">また、エクスポートを設定するときに新しい接続を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="e8eb0-118">共同作成者は、特定の接続にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="e8eb0-119">接続の構成と共有を管理者に依存します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="e8eb0-120">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="e8eb0-121">ビューアーは、既存のエクスポートを表示することはできますが、作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="e8eb0-122">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e8eb0-123">**エクスポートの追加** を選択して、新しいエクスポート先を作成します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="e8eb0-124">**エクスポートの設定** ペインで、使用する接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="e8eb0-125">[接続](connections.md) は、管理者によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="e8eb0-126">必要な詳細を入力して **保存** 選択し、エクスポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="e8eb0-127">エクスポートの編集</span><span class="sxs-lookup"><span data-stu-id="e8eb0-127">Edit an export</span></span>

1. <span data-ttu-id="e8eb0-128">編集するエクスポート先の垂直方向の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="e8eb0-129">ドロップダウン メニューから **編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="e8eb0-130">更新する値を変更し、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="e8eb0-131">エクスポートとエクスポートの詳細の表示</span><span class="sxs-lookup"><span data-stu-id="e8eb0-131">View Exports and export details</span></span>

<span data-ttu-id="e8eb0-132">エクスポート先を作成した後、**データ** > **エクスポート** に表示さます。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="e8eb0-133">すべてのユーザーは、共有されているデータとその最新の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="e8eb0-134">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e8eb0-135">編集権限のないユーザーは、**編集** ではなく **ビュー** を選択して、エクスポートの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="e8eb0-136">このサイド ペインには、このエクスポートの設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="e8eb0-137">編集権限がないと、値を変更できません。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="e8eb0-138">**閉じる** を選択して、エクスポート ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="e8eb0-139">オンデマンドでエクスポートを実行</span><span class="sxs-lookup"><span data-stu-id="e8eb0-139">Run exports on demand</span></span>

<span data-ttu-id="e8eb0-140">エクスポートを構成した後、作業中の接続がある限り、[スケジュール更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="e8eb0-141">スケジュール更新を待たずにデータをエクスポートするには、**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="e8eb0-142">次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-142">You have two options:</span></span>

- <span data-ttu-id="e8eb0-143">すべてのエクスポートを実行するには、コマンドバーで **すべて実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="e8eb0-144">1 つのエクスポートを実行するには、リスト項目で省略記号 (...) を選択してから、**実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="e8eb0-145">エクスポートの削除</span><span class="sxs-lookup"><span data-stu-id="e8eb0-145">Remove an Export</span></span>

1. <span data-ttu-id="e8eb0-146">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e8eb0-147">削除するエクスポートの垂直方向の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="e8eb0-148">ドロップダウン メニューで **削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="e8eb0-149">確認画面で **削除** を選択して削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="e8eb0-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
