---
title: Customer Insights からの他のサービスへの接続。
description: 他のサービスとデータを共有します。
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304978"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="1399f-103">接続 (プレビュー) の概要</span><span class="sxs-lookup"><span data-stu-id="1399f-103">Connections (preview) overview</span></span>

<span data-ttu-id="1399f-104">接続は、Customer Insights とのデータ共有を可能にするためのキーです。</span><span class="sxs-lookup"><span data-stu-id="1399f-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="1399f-105">各接続は、特定のサービスとのデータ共有を確立します。</span><span class="sxs-lookup"><span data-stu-id="1399f-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="1399f-106">接続は、[サード パーティ エンリッチメントを構成](enrichment-hub.md) し、[エクスポートを構成](export-destinations.md) するための基盤となります。</span><span class="sxs-lookup"><span data-stu-id="1399f-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="1399f-107">同じ接続を複数回使用できます。</span><span class="sxs-lookup"><span data-stu-id="1399f-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="1399f-108">たとえば、Dynamics 365 Marketing への 1 つの接続は複数のエクスポートで機能し、1 つの Leadspace 接続は複数のエンリッチメントに使用できます。</span><span class="sxs-lookup"><span data-stu-id="1399f-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="1399f-109">**管理** > **接続** に移動し、接続を作成および表示します。</span><span class="sxs-lookup"><span data-stu-id="1399f-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="1399f-110">**接続** タブには、すべてのアクティブな接続が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1399f-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="1399f-111">一覧には、各接続の行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1399f-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="1399f-112">**検出** タブにある各拡張性オプションの概要、説明、実行可能な操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="1399f-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="1399f-113">エクスポート</span><span class="sxs-lookup"><span data-stu-id="1399f-113">Exports</span></span>

<span data-ttu-id="1399f-114">管理者のみが新しい接続を構成できますが、既存の接続を使用する共同作成者にアクセスを許可できます。</span><span class="sxs-lookup"><span data-stu-id="1399f-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="1399f-115">管理者はデータの行き先を制御し、共同作成者はニーズに合ったペイロードと頻度を定義します。</span><span class="sxs-lookup"><span data-stu-id="1399f-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="1399f-116">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1399f-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="1399f-117">エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="1399f-117">Enrichments</span></span>

<span data-ttu-id="1399f-118">管理者のみが新しい接続を構成できますが、作成された接続は常に管理者と共同作成者の両方が使用できます。</span><span class="sxs-lookup"><span data-stu-id="1399f-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="1399f-119">管理者は資格情報を管理し、データ転送に同意します。</span><span class="sxs-lookup"><span data-stu-id="1399f-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="1399f-120">その後、接続は、管理者と共同作成者の両方がエンリッチメントに使用できます。</span><span class="sxs-lookup"><span data-stu-id="1399f-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="1399f-121">新しい接続を追加する</span><span class="sxs-lookup"><span data-stu-id="1399f-121">Add a new connection</span></span>

<span data-ttu-id="1399f-122">接続を追加するには、[管理者のアクセス許可](permissions.md) が必要です。</span><span class="sxs-lookup"><span data-stu-id="1399f-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="1399f-123">他の Microsoft サービスに接続する場合、両方のサービスが同じ組織内にあることが必要です。</span><span class="sxs-lookup"><span data-stu-id="1399f-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="1399f-124">**管理** > **接続 (プレビュー)** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1399f-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="1399f-125">**接続** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="1399f-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="1399f-126">新しい接続を作成するには、**つながりの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1399f-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="1399f-127">ドロップダウン メニューから、作成する接続の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="1399f-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="1399f-128">**接続の設定** ペインに、必要な詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="1399f-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="1399f-129">接続の **表示名** と種類は、接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="1399f-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="1399f-130">この接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1399f-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="1399f-131">正確なフィールドは、接続しているサービスによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1399f-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="1399f-132">特定の接続の種類の詳細については、対象サービスに関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1399f-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="1399f-133">接続を作成するには、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1399f-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="1399f-134">**検出** タブのタイルで、**設定** を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="1399f-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="1399f-135">共同作成者がエクスポートに接続を使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="1399f-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="1399f-136">エクスポート接続を設定または編集するときに、この特定の接続を使用して [エクスポート](export-destinations.md) を定義できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1399f-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="1399f-137">既定では、管理者ロールを持つユーザーが接続を利用できます。</span><span class="sxs-lookup"><span data-stu-id="1399f-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="1399f-138">この設定は、**この接続を使用できるユーザーを選択する** で変更でき、共同作成者ロールを持つユーザーはこの接続を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1399f-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="1399f-139">共同作成者は接続を表示または編集できません。</span><span class="sxs-lookup"><span data-stu-id="1399f-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="1399f-140">エクスポートを作成するときに、表示名と種類のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1399f-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="1399f-141">接続を共有することにより、共同作成者が接続を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1399f-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="1399f-142">共同作成者が、エクスポートを設定すると、共有接続が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1399f-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="1399f-143">この特定の接続を使用するすべてのエクスポートを管理できます。</span><span class="sxs-lookup"><span data-stu-id="1399f-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="1399f-144">共同作成者によって既に定義されているエクスポートを保持したまま、この設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1399f-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="1399f-145">接続の編集</span><span class="sxs-lookup"><span data-stu-id="1399f-145">Edit a connection</span></span>

1. <span data-ttu-id="1399f-146">**管理** > **接続 (プレビュー)** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1399f-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="1399f-147">**接続** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="1399f-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="1399f-148">編集する接続の垂直方向の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="1399f-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="1399f-149">**編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1399f-149">Select **Edit**.</span></span>

1. <span data-ttu-id="1399f-150">更新する値を変更し、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1399f-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="1399f-151">接続の削除</span><span class="sxs-lookup"><span data-stu-id="1399f-151">Remove a connection</span></span>

<span data-ttu-id="1399f-152">削除する接続がエンリッチメントまたはエクスポートで使用されている場合は、最初にそれらをデタッチまたは削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1399f-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="1399f-153">削除ダイアログでは、関連するエンリッチメントまたはエクスポートを説明します。</span><span class="sxs-lookup"><span data-stu-id="1399f-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="1399f-154">分離されたエンリッチメントとエクスポートは非アクティブになります。</span><span class="sxs-lookup"><span data-stu-id="1399f-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="1399f-155">それらを再度アクティブにするには、[エンリッチメント](enrichment-hub.md) または [エクスポート](export-destinations.md) ページで別の接続を追加します。</span><span class="sxs-lookup"><span data-stu-id="1399f-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="1399f-156">**管理** > **接続 (プレビュー)** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1399f-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="1399f-157">**接続** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="1399f-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="1399f-158">削除する接続の垂直方向の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="1399f-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="1399f-159">ドロップダウン メニューで **削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1399f-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="1399f-160">確認ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1399f-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="1399f-161">この接続を使用するエンリッチメントまたはエクスポートがある場合は、ボタンを選択して、接続を使用しているものを確認します。</span><span class="sxs-lookup"><span data-stu-id="1399f-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="1399f-162">**エクスポート:** 接続を削除できるように、エクスポートを削除するか接続解除するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1399f-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="1399f-163">エクスポートを接続解除するために、管理者は **接続解除** アクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1399f-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="1399f-164">このアクションは、個別および複数の選択されたエクスポートで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1399f-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="1399f-165">接続解除することで、エクスポート構成は保持されますが、別の接続が追加されるまで実行されません。</span><span class="sxs-lookup"><span data-stu-id="1399f-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="1399f-166">**エンリッチメント:** 接続を削除できるように、エンリッチメントを削除するか非アクティブ化するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1399f-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="1399f-167">接続に依存関係がなくなったら、**管理** > **接続** に戻り、再度接続の削除を試みます。</span><span class="sxs-lookup"><span data-stu-id="1399f-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="1399f-168">削除の実行を確定するには、**削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1399f-168">To confirm the deletion, select **Remove**.</span></span>

