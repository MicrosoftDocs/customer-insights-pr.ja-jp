---
title: Power Query コネクタを使用してデータを取り込む
description: Power Queryに基づくデータソース用のコネクタです。
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406173"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="5b807-103">Power Query データソースに接続する</span><span class="sxs-lookup"><span data-stu-id="5b807-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="5b807-104">Power Query では一連の広範なコネクターを搭載しており、データを取り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="5b807-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="5b807-105">これらコネクターの多くが Dynamics 365 Customer Insights でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5b807-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="5b807-106">Power Query コネクタに基づくデータ ソースの追加方法については、次のセクションで説明する手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b807-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="5b807-107">ただし、使用するコネクタによっては、異なる情報が必要になります。</span><span class="sxs-lookup"><span data-stu-id="5b807-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="5b807-108">それぞれのコネクタに関する詳細情報については、[Power Query コネクタについての参考資料](https://docs.microsoft.com/power-query/connectors/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b807-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="5b807-109">新しいデータ ソースの作成</span><span class="sxs-lookup"><span data-stu-id="5b807-109">Create a new data source</span></span>

1. <span data-ttu-id="5b807-110">対象者に関するインサイトで、**データ** > **データ ソース** に移動します。</span><span class="sxs-lookup"><span data-stu-id="5b807-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="5b807-111">**データソースの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b807-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="5b807-112">**データをインポート** する方法を選択し、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b807-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="5b807-113">データ ソースの **名前** を入力し、**次へ** を選択してデータ ソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="5b807-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="5b807-114">[使用可能なコネクタ](#available-power-query-data-sources) のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="5b807-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="5b807-115">この例では、**Text/CSV** コネクタを選択しています。</span><span class="sxs-lookup"><span data-stu-id="5b807-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="5b807-116">選択したコネクタの **接続設定** で必要な詳細を入力し、**次へ** を選択するとデータのプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b807-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="5b807-117">**データの変換** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b807-117">Select **Transform data**.</span></span> <span data-ttu-id="5b807-118">この手順では、データ ソースにエンティティを追加します。</span><span class="sxs-lookup"><span data-stu-id="5b807-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="5b807-119">エンティティとはデータセットを意味します。</span><span class="sxs-lookup"><span data-stu-id="5b807-119">Entities are datasets.</span></span> <span data-ttu-id="5b807-120">複数のデータセットを含むデータベースがある場合、各データセットは独自のエンティティです。</span><span class="sxs-lookup"><span data-stu-id="5b807-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="5b807-121">**Power Query - クエリの編集** ダイアログでは、データを確認したり、詳細化したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5b807-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="5b807-122">選択したデータ ソースで識別されたシステムが左側のペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b807-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5b807-123">![クエリの編集ダイアログ](media/data-manager-configure-edit-queries.png "クエリの編集ダイアログ")</span><span class="sxs-lookup"><span data-stu-id="5b807-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="5b807-124">また、データをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5b807-124">You can also transform your data.</span></span> <span data-ttu-id="5b807-125">編集または変換するエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="5b807-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="5b807-126">変換を適用するには、Power Query ウィンドウのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b807-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="5b807-127">それぞれの変換は、**適用された手順** 配下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b807-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="5b807-128">Power Query には、事前に構築された変換オプションが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="5b807-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="5b807-129">詳細については、[Power Query の変換](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b807-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="5b807-130">**クエリの編集** ダイアログで **データの取得** を選択することで、その他のエンティティをデータ ソースに追加できます。</span><span class="sxs-lookup"><span data-stu-id="5b807-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="5b807-131">次の変換を強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5b807-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="5b807-132">CSV ファイルからデータを取り込む場合、多くの場合、最初の行にヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b807-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="5b807-133">**テーブルの変換** に移動し、**最初の行をヘッダーとして使用する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b807-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="5b807-134">データ型が適切に設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5b807-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="5b807-135">Power Query ウィンドウの下部にある **保存** を選択して変換を保存します。</span><span class="sxs-lookup"><span data-stu-id="5b807-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="5b807-136">保存をすると、**データ** > **データ ソース** にデータソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b807-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="5b807-137">**データ ソース** ページに、新しいデータ ソースが **更新中** の状態で表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b807-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="5b807-138">利用可能な Power Query のデータソース</span><span class="sxs-lookup"><span data-stu-id="5b807-138">Available Power Query data sources</span></span>

<span data-ttu-id="5b807-139">Customer Insights にデータをインポートするために選択できるコネクタの最新のリストについては、[Power Query コネクタの参考資料](https://docs.microsoft.com/power-query/connectors/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b807-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="5b807-140">**Customer Insights (Dataflows)** 列にチェック マークが付いているコネクタは、Power Query に基づいた新しいデータ ソースを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5b807-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="5b807-141">特定のコネクタのドキュメントを確認し、その前提条件、制限、およびその他の詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="5b807-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="5b807-142">Power Query データソースの編集</span><span class="sxs-lookup"><span data-stu-id="5b807-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="5b807-143">アプリのプロセスの 1 つで (たとえば、*セグメント化*、*一致*、または *マージ*)、現在使用されているデータソースに変更を加えることができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5b807-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="5b807-144">**設定** ページを使用して、有効な各プロセスの進行状況を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="5b807-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="5b807-145">プロセスが完了すると、**データ ソース** ページに戻り、変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="5b807-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="5b807-146">対象者に関するインサイトで、**データ** > **データ ソース** に移動します。</span><span class="sxs-lookup"><span data-stu-id="5b807-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="5b807-147">変更するデータ ソースの横にある縦の省略記号を選択し、ドロップダウンメニューから **編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b807-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5b807-148">![オプションの編集](media/edit-option-data-sources.png "オプションの編集")</span><span class="sxs-lookup"><span data-stu-id="5b807-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="5b807-149">**Power Query - キューの編集** ダイアログで、[新しいデータソースの作成](#create-a-new-data-source)に記載されているように、変更と変換を適用します。</span><span class="sxs-lookup"><span data-stu-id="5b807-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="5b807-150">編集の完了後は、Power Query で **保存** を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="5b807-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
