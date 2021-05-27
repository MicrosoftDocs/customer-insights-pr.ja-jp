---
title: エンティティとデータセット
description: エンティティ ページにデータを表示します。
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049400"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="a33db-103">対象者に関するインサイトのエンティティ</span><span class="sxs-lookup"><span data-stu-id="a33db-103">Entities in audience insights</span></span>

<span data-ttu-id="a33db-104">[データソースの構成](data-sources.md) 後、**エンティティ** ページに移動して、取り込んだデータの品質を評価します。</span><span class="sxs-lookup"><span data-stu-id="a33db-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="a33db-105">エンティティはデータセットと見なされます。</span><span class="sxs-lookup"><span data-stu-id="a33db-105">Entities are considered datasets.</span></span> <span data-ttu-id="a33db-106">Dynamics 365 Customer Insights の複数の機能は、これらのエンティティを中心に構築されています。</span><span class="sxs-lookup"><span data-stu-id="a33db-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="a33db-107">それらを綿密に確認すると、これらの機能の出力を検証するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a33db-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="a33db-108">**エンティティ** ページにはエンティティがリストされ、次のいくつかの列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a33db-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="a33db-109">**名前**: プロジェクトの名前です。</span><span class="sxs-lookup"><span data-stu-id="a33db-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="a33db-110">エンティティ名の横に警告記号が表示されている場合、そのエンティティのデータが正常にロードされていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a33db-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="a33db-111">**ソース**: エンティティを取得したデータ ソースのタイプ</span><span class="sxs-lookup"><span data-stu-id="a33db-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="a33db-112">**作成者** : エンティティを作成した人の名前</span><span class="sxs-lookup"><span data-stu-id="a33db-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="a33db-113">**作成した**：エンティティ作成の日付と時刻</span><span class="sxs-lookup"><span data-stu-id="a33db-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="a33db-114">**更新者** : エンティティを更新した人の名前</span><span class="sxs-lookup"><span data-stu-id="a33db-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="a33db-115">**最終更新日** : エンティティを最後に更新した日付と時刻</span><span class="sxs-lookup"><span data-stu-id="a33db-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="a33db-116">**最新情報に更新した日** : 最後に最新の情報に更新した日付と時刻</span><span class="sxs-lookup"><span data-stu-id="a33db-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="a33db-117">特定エンティティのデータを調べる</span><span class="sxs-lookup"><span data-stu-id="a33db-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="a33db-118">エンティティを選択して、そのエンティティに含まれるさまざまなフィールドとレコードを調べます。</span><span class="sxs-lookup"><span data-stu-id="a33db-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a33db-119">![エンティティを選択する](media/data-manager-entities-data.png "エンティティの選択")</span><span class="sxs-lookup"><span data-stu-id="a33db-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="a33db-120">**データ** タブには、エンティティの個々のレコードに関する詳細を一覧表示したテーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a33db-120">The **Data** tab shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a33db-121">![フィールド テーブル](media/data-manager-entities-fields.PNG "フィールド テーブル")</span><span class="sxs-lookup"><span data-stu-id="a33db-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="a33db-122">**属性** タブは既定で選択されており、フィールド名、データ型、種類など、選択したエンティティの詳細を確認するためのテーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a33db-122">The **Attributes** tab is selected by default and shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="a33db-123">**種類** 列は、Common Data Model に関連した種類を表示し、これはシステムによって自動識別されるか、ユーザーによって[手動でマッピング](map-entities.md) されます。</span><span class="sxs-lookup"><span data-stu-id="a33db-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="a33db-124">これらは、属性のデータ型とは異なるセマンティック型です。たとえば、フィールド *メール* の下には、データ型 *テキスト* がありますが、その (セマンティック型の) Common Data Model の種類は、*メール* または *メールアドレス* である場合があります。</span><span class="sxs-lookup"><span data-stu-id="a33db-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="a33db-125">両方のテーブルには、エンティティのデータのサンプルのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a33db-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="a33db-126">完全なデータセットを表示するには、**データ ソース** ページに移動して、エンティティを選択し、**編集** を選択して、その後[データ ソース](data-sources.md) で説明した通り、このエンティティのデータを Power Query エディターで表示します。</span><span class="sxs-lookup"><span data-stu-id="a33db-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="a33db-127">エンティティに取り込まれたデータの詳細については、**概要** 列は、データに適用可能なヌル、欠損値、一意の値、カウント、分布など、データの重要な特性を提供します。</span><span class="sxs-lookup"><span data-stu-id="a33db-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="a33db-128">グラフ アイコンを選択して、データの概要を表示します。</span><span class="sxs-lookup"><span data-stu-id="a33db-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a33db-129">![概要記号](media/data-manager-entities-summary.png "データ概要テーブル")</span><span class="sxs-lookup"><span data-stu-id="a33db-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="a33db-130">次の手順</span><span class="sxs-lookup"><span data-stu-id="a33db-130">Next step</span></span>

<span data-ttu-id="a33db-131">[統一](data-unification.md) トピックで、取り込んだデータを *マップ*、*一致*、そして *マージ* する方法をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a33db-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
