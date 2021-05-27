---
title: Customer Insights からデータをエクスポートする
description: エクスポートを管理してデータを共有します。
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016620"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="70a94-103">エクスポート (プレビュー) の概要</span><span class="sxs-lookup"><span data-stu-id="70a94-103">Exports (preview) overview</span></span>

<span data-ttu-id="70a94-104">**エクスポート** ページには、構成済みのすべてのエクスポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="70a94-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="70a94-105">エクスポートは、特定のデータをさまざまなアプリケーションと共有します。</span><span class="sxs-lookup"><span data-stu-id="70a94-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="70a94-106">顧客プロファイルまたはエンティティ、スキーマ、およびマッピングの詳細を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="70a94-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="70a94-107">各エクスポートには、[認証とアクセスを管理するために、管理者によって設定された接続](connections.md) が必要です。</span><span class="sxs-lookup"><span data-stu-id="70a94-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="70a94-108">**データ** > **エクスポート** に移動し、エクスポート ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="70a94-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="70a94-109">すべてのユーザー ロールには、構成済みのエクスポートを表示するアクセス権があります。</span><span class="sxs-lookup"><span data-stu-id="70a94-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="70a94-110">コマンド バーの検索フィールドを使用して、名前、接続名、または接続の種類でエクスポートを検索します。</span><span class="sxs-lookup"><span data-stu-id="70a94-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="70a94-111">新しいエクスポートの設定</span><span class="sxs-lookup"><span data-stu-id="70a94-111">Set up a new export</span></span>

<span data-ttu-id="70a94-112">エクスポートを設定または編集するには、使用可能な接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="70a94-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="70a94-113">接続は [ユーザー ロール](permissions.md) によって異なります:</span><span class="sxs-lookup"><span data-stu-id="70a94-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="70a94-114">管理者はすべての接続にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="70a94-114">Administrators have access to all connections.</span></span> <span data-ttu-id="70a94-115">また、エクスポートを設定するときに新しい接続を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="70a94-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="70a94-116">共同作成者は、特定の接続にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="70a94-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="70a94-117">接続の構成と共有を管理者に依存します。</span><span class="sxs-lookup"><span data-stu-id="70a94-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="70a94-118">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a94-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="70a94-119">ビューアーは、既存のエクスポートを表示することはできますが、作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="70a94-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="70a94-120">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="70a94-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="70a94-121">**エクスポートの追加** を選択して、新しいエクスポート先を作成します。</span><span class="sxs-lookup"><span data-stu-id="70a94-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="70a94-122">**エクスポートの設定** ペインで、使用する接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="70a94-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="70a94-123">[接続](connections.md) は、管理者によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="70a94-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="70a94-124">必要な詳細を入力して **保存** 選択し、エクスポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="70a94-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="70a94-125">エクスポートの編集</span><span class="sxs-lookup"><span data-stu-id="70a94-125">Edit an export</span></span>

1. <span data-ttu-id="70a94-126">編集するエクスポート先の垂直方向の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="70a94-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="70a94-127">ドロップダウン メニューから **編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70a94-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="70a94-128">更新する値を変更し、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70a94-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="70a94-129">エクスポートとエクスポートの詳細の表示</span><span class="sxs-lookup"><span data-stu-id="70a94-129">View Exports and export details</span></span>

<span data-ttu-id="70a94-130">エクスポート先を作成した後、**データ** > **エクスポート** に表示さます。</span><span class="sxs-lookup"><span data-stu-id="70a94-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="70a94-131">すべてのユーザーは、共有されているデータとその最新の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="70a94-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="70a94-132">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="70a94-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="70a94-133">編集権限のないユーザーは、**編集** ではなく **ビュー** を選択して、エクスポートの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="70a94-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="70a94-134">このサイド ペインには、このエクスポートの設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70a94-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="70a94-135">編集権限がないと、値を変更できません。</span><span class="sxs-lookup"><span data-stu-id="70a94-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="70a94-136">**閉じる** を選択して、エクスポート ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="70a94-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="70a94-137">オンデマンドでエクスポートを実行</span><span class="sxs-lookup"><span data-stu-id="70a94-137">Run exports on demand</span></span>

<span data-ttu-id="70a94-138">エクスポートを構成した後、作業中の接続がある限り、[スケジュール更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="70a94-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="70a94-139">スケジュール更新を待たずにデータをエクスポートするには、**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="70a94-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="70a94-140">次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="70a94-140">You have two options:</span></span>

- <span data-ttu-id="70a94-141">すべてのエクスポートを実行するには、コマンドバーで **すべて実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70a94-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="70a94-142">1 つのエクスポートを実行するには、リスト項目で省略記号 (...) を選択してから、**実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70a94-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="70a94-143">エクスポートの削除</span><span class="sxs-lookup"><span data-stu-id="70a94-143">Remove an Export</span></span>

1. <span data-ttu-id="70a94-144">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="70a94-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="70a94-145">削除するエクスポートの垂直方向の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="70a94-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="70a94-146">ドロップダウン メニューで **削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70a94-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="70a94-147">確認画面で **削除** を選択して削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="70a94-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
