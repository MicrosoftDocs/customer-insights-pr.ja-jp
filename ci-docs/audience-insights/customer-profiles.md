---
title: 顧客プロファイルの表示
description: 統合顧客データの結合ビューを取得します。
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 13308c2f40cda0d7e813b4d94ab47d53b5ce2115
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653896"
---
# <a name="customer-profiles"></a><span data-ttu-id="1ec4d-103">顧客プロファイル</span><span class="sxs-lookup"><span data-stu-id="1ec4d-103">Customer profiles</span></span>

<span data-ttu-id="1ec4d-104">**顧客** ページには、[すべてのデータ ソース](data-sources.md) から収集されたプロファイル データに基づいて、顧客の結合ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="1ec4d-105">[統合された顧客エンティティを作成](data-unification.md) した後、顧客プロファイルを利用できます。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="1ec4d-106">データ統合プロセスを完了して、顧客のより豊富なビューを取得してください。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="1ec4d-107">このページでは、顧客を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="1ec4d-108">顧客は個人でも組織でも構いません (プレビュー)。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="1ec4d-109">各顧客または組織のプロファイルはタイルで表されます。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="1ec4d-110">特定の顧客または組織に関する追加情報を表示するには、タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="1ec4d-111">ページの下部にある改ページ コントロールを使用して、その他のレコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="1ec4d-112">![B2C 顧客プロファイル](media/profiles-customers.png "B2C 顧客プロファイル")</span><span class="sxs-lookup"><span data-stu-id="1ec4d-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="1ec4d-113">組織 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="1ec4d-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="1ec4d-114">![B2B 顧客プロファイル](media/profile-customers-b2b.png "B2B 顧客プロファイル")</span><span class="sxs-lookup"><span data-stu-id="1ec4d-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="1ec4d-115">ナビゲーションで **顧客** を選択してもタイルが表示されない場合は、**検索 & フィルタ―インデックス** で管理者が [少なくとも 1 つの検索可能な属性を定義する](search-filter-index.md) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="1ec4d-116">顧客の検索</span><span class="sxs-lookup"><span data-stu-id="1ec4d-116">Search for customers</span></span>

<span data-ttu-id="1ec4d-117">検索ボックスに名前またはその他の属性を入力して、顧客を検索します。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="1ec4d-118">検索は、データ統合プロセス中に作成された顧客プロファイルエンティティ内でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="1ec4d-119">管理者として、**インデックスの検索とフィルター** ページを使用して検索可能な属性を設定できます。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="1ec4d-120">詳細については、[検索とフィルターインデックスの管理](search-filter-index.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="1ec4d-121">顧客のフィルタ―</span><span class="sxs-lookup"><span data-stu-id="1ec4d-121">Filter customers</span></span>

<span data-ttu-id="1ec4d-122">Customer Profile エンティティ フィールドで顧客をフィルタリングできます。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="1ec4d-123">検索と同様に、管理者は **インデックスの検索とフィルター** ページを使用して、最初にフィールドをフィルター可能として定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="1ec4d-124">**顧客** ページで、**フィルター** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="1ec4d-125">顧客をフィルタ―する属性の隣にあるボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="1ec4d-126">![顧客プロファイル](media/profiles-customers3.png "顧客プロファイル")</span><span class="sxs-lookup"><span data-stu-id="1ec4d-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="1ec4d-127">**顧客** ページで **フィルターをクリア** を選択して、フィルターを削除します。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="1ec4d-128">顧客詳細ページ</span><span class="sxs-lookup"><span data-stu-id="1ec4d-128">Customer details page</span></span>

<span data-ttu-id="1ec4d-129">顧客タイルのいずれかを選択して、**顧客詳細ページ** を開きます。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="1ec4d-130">このビューには、選択した顧客の統合された情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="1ec4d-131">次の顧客の詳細が含まれます:</span><span class="sxs-lookup"><span data-stu-id="1ec4d-131">Customer details include:</span></span>

-   <span data-ttu-id="1ec4d-132">**顧客プロファイル タイル:** このタイルには、統合顧客プロファイル エンティティのさまざまな値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="1ec4d-133">これらの詳細には、電子メールアドレス、名前、都市などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="1ec4d-134">**潜在的な関心、潜在的なブランド:** ファースト パーティのエンリッチメントを設定したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="1ec4d-135">これは、この顧客に類似するプロファイルを持つ顧客が持つ可能性のあるブランドに対する潜在的な関心と親近感を表します。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="1ec4d-136">詳細については、[ブランドと興味のアフィニティで顧客プロファイルを強化する](enrichment-microsoft-graph.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="1ec4d-137">**メジャー:** 特定種類のメジャー (顧客属性メジャー) を 1 つ以上構成したかどうかを表示します。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="1ec4d-138">これには、個々の顧客レベルの顧客に関する計算された KPI が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="1ec4d-139">詳細については、[メジャーの定義および管理](measures.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="1ec4d-140">**活動のタイムライン:** 活動を構成したかどうかを表示します。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="1ec4d-141">タイムライン ビューには、最新の活動から始めて、この顧客の時系列に並べ替えられた活動が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="1ec4d-142">詳細については、[顧客アクティビティ](activities.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="1ec4d-143">**顧客に戻る** を選択して、顧客検索ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1ec4d-144">次の手順</span><span class="sxs-lookup"><span data-stu-id="1ec4d-144">Next steps</span></span>

<span data-ttu-id="1ec4d-145">[データソースをさらに追加する](data-sources.md) または [顧客セグメントを作成する](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="1ec4d-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>
