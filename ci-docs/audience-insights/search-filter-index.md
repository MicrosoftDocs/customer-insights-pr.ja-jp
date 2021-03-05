---
title: 顧客プロファイルの検索とフィルター
description: 統一された顧客プロファイルに関する情報をすばやく検索し、指定された属性をフィルタ―します。
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270072"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="222a2-103">顧客プロファイル: 検索とフィルターのインデックス</span><span class="sxs-lookup"><span data-stu-id="222a2-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="222a2-104">顧客データを統合した結果は、顧客ベース全体に統一されたビューを提供する顧客プロファイル エンティティです。</span><span class="sxs-lookup"><span data-stu-id="222a2-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="222a2-105">迅速に [特定の顧客または顧客グループに関する情報を見つける](customer-profiles.md) には、**検索** と **フィルタ** 機能を **顧客** ページで構成できます。</span><span class="sxs-lookup"><span data-stu-id="222a2-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="222a2-106">ユーザーが検索とフィルタリングに使用できる **検索およびフィルター インデックス** ページを読んで、管理者がどのように属性を編集できるかを学んください。</span><span class="sxs-lookup"><span data-stu-id="222a2-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="222a2-107">![検索フィルター](media/search-filter.png "検索フィルター")</span><span class="sxs-lookup"><span data-stu-id="222a2-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="222a2-108">フィールドを追加して属性を指定する</span><span class="sxs-lookup"><span data-stu-id="222a2-108">Add fields and specify attributes</span></span>

<span data-ttu-id="222a2-109">検索可能な属性を管理者として初めて定義する場合、最初にインデックス付きフィールドを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="222a2-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="222a2-110">**顧客** ページでユーザーが顧客を検索してフィルタ―できるすべての属性を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="222a2-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="222a2-111">データ統合プロセス中に作成した Customer Profile エンティティに存在する属性のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="222a2-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="222a2-112">**顧客** ページを開き、**インデックスの検索とフィルター** を選択します。</span><span class="sxs-lookup"><span data-stu-id="222a2-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="222a2-113">**+ 追加** を選択して、インデックス フィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="222a2-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="222a2-114">インデックス付きフィールドとして追加するリスト内の属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="222a2-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="222a2-115">**追加** を選択することで属性をいつでも追加できます。</span><span class="sxs-lookup"><span data-stu-id="222a2-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="222a2-116">また、選択した属性を削除するには、**削除** 記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="222a2-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="222a2-117">インデックス付き顧客フィールドのテーブルの説明</span><span class="sxs-lookup"><span data-stu-id="222a2-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="222a2-118">次の情報は、このテーブルにあります。</span><span class="sxs-lookup"><span data-stu-id="222a2-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="222a2-119">**名前** : Customer Profile エンティティに表示される属性の名前を表します。</span><span class="sxs-lookup"><span data-stu-id="222a2-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="222a2-120">**データの種類** : データ型が文字列、数値、または日付のいずれであるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="222a2-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="222a2-121">**検索に含まれる** : **顧客** ページで **検索** フィールドを使用して、この属性を使用して顧客の検索に使用できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="222a2-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="222a2-122">**フィルターを追加** : この属性が **顧客** ページでフィルタ―を使用できる方法を定義するコントロール。</span><span class="sxs-lookup"><span data-stu-id="222a2-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="222a2-123">特定の属性のフィルタ―オプションの編集</span><span class="sxs-lookup"><span data-stu-id="222a2-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="222a2-124">**Customers** ページの **フィルタ―** メニューには、さまざまな数の属性レベル (たとえば、顧客をフィルターするためのさまざまな年齢グループ) を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="222a2-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="222a2-125"> **検索およびフィルタ― インデックス** ページで特定の属性に対して **フィルタ―の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="222a2-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="222a2-126">結果の数とそれらを整理する順序を定義できます。</span><span class="sxs-lookup"><span data-stu-id="222a2-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="222a2-127">属性のデータ型に応じて、次のウィンドウのいずれかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="222a2-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="222a2-128">文字列タイプの属性： **文字列フィルター オプション** ウィンドウで希望する結果の数と、それらの結果を整理する順序のポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="222a2-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="222a2-129">数値タイプの属性： **数値フィルター オプション** ウィンドウに含まれる間隔と、それらが整理される順序のポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="222a2-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="222a2-130">データタイプの属性： **データ フィルター オプション** ウィンドウに含まれる間隔と、それらを整理する順序のポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="222a2-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="222a2-131">**保存** を選択して変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="222a2-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="222a2-132">設定を適用する準備ができたら **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="222a2-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="222a2-133">次の手順</span><span class="sxs-lookup"><span data-stu-id="222a2-133">Next steps</span></span>

<span data-ttu-id="222a2-134">**顧客** ページに移動して、顧客プロファイルを検索するか、インデックス付きフィールドを使用してすべての顧客プロファイルのサブセットを表示します。</span><span class="sxs-lookup"><span data-stu-id="222a2-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]