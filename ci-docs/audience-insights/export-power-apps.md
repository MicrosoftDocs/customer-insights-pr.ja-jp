---
title: Power Apps コネクタ
description: Power Apps と Power Automate に接続します。
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598161"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="ceb7c-103">Microsoft Power Appsコネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="ceb7c-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="ceb7c-104">統合された顧客プロファイルを Power Apps でパーソナライズされたアプリに取り込みます。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="ceb7c-105">Power Apps と Dynamics 365 Customer Insights の接続</span><span class="sxs-lookup"><span data-stu-id="ceb7c-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="ceb7c-106">Customer Insights は、多くの [Power Apps でデータの利用可能なソース](/powerapps/maker/canvas-apps/working-with-data-sources) のうちの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="ceb7c-107">Power Apps ドキュメントを参照して、[アプリにデータ接続を追加する](/powerapps/maker/canvas-apps/add-data-connection) 方法を学んでください。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="ceb7c-108">また、[Power Apps が委任を使用し、キャンバス アプリで大規模なデータセットを処理する方法](/powerapps/maker/canvas-apps/delegation-overview) を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="ceb7c-109">使用可能なエンティティ</span><span class="sxs-lookup"><span data-stu-id="ceb7c-109">Available entities</span></span>

<span data-ttu-id="ceb7c-110">Customer Insights をデータ接続として追加した後、Power Apps で次のエンティティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="ceb7c-111">顧客: [統合された顧客プロファイル](customer-profiles.md) からのデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="ceb7c-112">統合された活動: アプリに[活動タイムライン](activities.md)を表示します。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="ceb7c-113">制限</span><span class="sxs-lookup"><span data-stu-id="ceb7c-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="ceb7c-114">取得可能なエンティティ</span><span class="sxs-lookup"><span data-stu-id="ceb7c-114">Retrievable entities</span></span>

<span data-ttu-id="ceb7c-115">取得できるのは Power Apps コネクタを介した **顧客**、**UnifiedActivity**、**セグメント** エンティティのみです。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="ceb7c-116">その他のエンティティは、基礎となるコネクタが Power Automate のトリガーを介してサポートしているため、表示されています。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="ceb7c-117">委任</span><span class="sxs-lookup"><span data-stu-id="ceb7c-117">Delegation</span></span>

<span data-ttu-id="ceb7c-118">委任は、Customer エンティティと UnifiedActivity エンティティで動作します。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="ceb7c-119">**顧客** エンティティへの委任: このエンティティに委任を使用するには、[インデックスの検索およびフィルター処理](search-filter-index.md) でフィールドにインデックスを付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="ceb7c-120">**UnifiedActivity** の委任 : このエンティティに対する委任は、フィールド **ActivityId** と **CustomerId** に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="ceb7c-121">委任の詳細については、[Power Apps で委任可能な機能と操作](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="ceb7c-122">ギャラリー コントロールの例</span><span class="sxs-lookup"><span data-stu-id="ceb7c-122">Example gallery control</span></span>

<span data-ttu-id="ceb7c-123">たとえば、顧客プロファイルを [ギャラリー コントロール](/powerapps/maker/canvas-apps/add-gallery) に追加します。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="ceb7c-124">**ギャラリー** コントロールを、構築しているアプリに追加します。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ceb7c-125">![ギャラリー要素を追加する](media/connector-powerapps9.png "ギャラリー要素を追加する")</span><span class="sxs-lookup"><span data-stu-id="ceb7c-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="ceb7c-126">**顧客** をアイテムのデータ ソースとして選択します。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ceb7c-127">![データ ソースを選択](media/choose-datasource-powerapps.png "データ ソースを選択")</span><span class="sxs-lookup"><span data-stu-id="ceb7c-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="ceb7c-128">右側のデータパネルを変更して、ギャラリーに表示する顧客エンティティのフィールドを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ceb7c-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="ceb7c-129">選択した顧客のフィールドをギャラリーに表示する場合は、次のラベルのテキスト プロパティを入力します : **{Name_of_the_gallery}。選択済み。{property_name}**</span><span class="sxs-lookup"><span data-stu-id="ceb7c-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="ceb7c-130">例 : Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="ceb7c-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="ceb7c-131">顧客の統合されたタイムラインを表示するには、ギャラリー要素を追加し、次の項目プロパティを追加します : **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="ceb7c-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="ceb7c-132">例 : Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="ceb7c-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]