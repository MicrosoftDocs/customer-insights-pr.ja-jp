---
title: 顧客活動
description: 顧客活動を定義し、顧客のタイムラインで表示します。
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267438"
---
# <a name="customer-activities"></a><span data-ttu-id="f57e0-103">顧客活動</span><span class="sxs-lookup"><span data-stu-id="f57e0-103">Customer activities</span></span>

<span data-ttu-id="f57e0-104">Dynamics 365 Customer Insights で [さまざまなデータ ソース](data-sources.md) からの顧客活動を組み合わせて、活動を時系列順に一覧表示する顧客のタイムラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="f57e0-105">[カスタマー カード アドイン](customer-card-add-in.md)、または Power BI ダッシュボードを介して、Dynamics 365 の顧客エンゲージメント アプリにタイムラインを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f57e0-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="f57e0-106">活動を定義する</span><span class="sxs-lookup"><span data-stu-id="f57e0-106">Define an activity</span></span>

<span data-ttu-id="f57e0-107">データソースには、複数のデータソースからのトランザクション データと活動データを持つエンティティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f57e0-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="f57e0-108">これらのエンティティを識別し、顧客のタイムラインで表示するアクティビティを選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="f57e0-109">対象となる活動 (複数可) を含むエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="f57e0-110">対象者に関するインサイトで、**データ** > **活動** に移動します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="f57e0-111">**活動の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f57e0-112">エンティティには、顧客のタイムラインに含めるために少なくとも 1 つの **日付** 属性が必要で、**日付** フィールドなしではエンティティを追加できません。</span><span class="sxs-lookup"><span data-stu-id="f57e0-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="f57e0-113">このようなエンティティが見つからない場合は、**活動の追加** コントロールは無効になります。</span><span class="sxs-lookup"><span data-stu-id="f57e0-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="f57e0-114">**活動の追加** ウィンドウで、次のフィールドの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="f57e0-115">**エンティティ** : トランザクションデータまたは活動データを含むエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="f57e0-116">**主キー** : レコードを一意に識別するフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="f57e0-117">重複する値、空の値、または欠損した値を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="f57e0-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="f57e0-118">**タイムスタンプ** : 活動の開始時間を表すフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="f57e0-119">**イベント** : 活動のイベントであるフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="f57e0-120">**Web アドレス** : このアクティビティに関する追加情報を提供する URL を表すフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="f57e0-121">たとえば、このアクティビティのソースとなるトランザクション システムです。</span><span class="sxs-lookup"><span data-stu-id="f57e0-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="f57e0-122">この URL は、データ ソースの任意のフィールドにすることも、Power Query 変換を使用して新たなフィールドとして構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="f57e0-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="f57e0-123">この URL データは、API を使用してダウン ストリームで使用できる 統合された活動エンティティに保存されます。</span><span class="sxs-lookup"><span data-stu-id="f57e0-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="f57e0-124">**詳細** : オプションで、追加の詳細のために追加されるフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="f57e0-125">**アイコン** : オプションで、この活動を表すアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="f57e0-126">**活動タイプ** : 活動の意味上の定義を最もよく表す Common Data Model への活動タイプの参照を定義します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="f57e0-127">**リレーションシップの設定** セクションで、活動データを対応する顧客に接続するために使用される詳細を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f57e0-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="f57e0-128">**活動エンティティ フィールド**: 別のエンティティとのリレーションシップを確立するために使用される活動エンティティでフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="f57e0-129">**顧客エンティティ**: 活動エンティティがリレーションシップになる対応するソース顧客エンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="f57e0-130">データ統合プロセスで使用されるソース顧客エンティティのみに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="f57e0-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="f57e0-131">**顧客エンティティ フィールド**: このフィールドには、マップ プロセスで選択されたソース顧客エンティティの主キーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f57e0-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="f57e0-132">ソース顧客エンティティのこの主キー フィールドは、アクティビティ エンティティとの関係を確立するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f57e0-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="f57e0-133">**名前**: このアクティビティ エンティティと選択したソース顧客エンティティの間に関係が既に存在する場合、関係名は読み取り専用モードになります。</span><span class="sxs-lookup"><span data-stu-id="f57e0-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="f57e0-134">そのような関係が存在しない場合、ここで指定された名前で新しい関係が作成されます。</span><span class="sxs-lookup"><span data-stu-id="f57e0-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f57e0-135">![エンティティ リレーションシップを定義する](media/activities-entities-define.png "エンティティ リレーションシップを定義する")</span><span class="sxs-lookup"><span data-stu-id="f57e0-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="f57e0-136">**保存** を選択して変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="f57e0-137">**活動** ページで、**実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="f57e0-138">タスク/プロセスには、[6 種類の状態](system.md#status-types) があります。</span><span class="sxs-lookup"><span data-stu-id="f57e0-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f57e0-139">さらに、ほとんどのプロセスは、[その他の下流プロセスに依存します](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="f57e0-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f57e0-140">プロセスのステータスを選択して、ジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f57e0-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f57e0-141">ジョブのタスクの 1 つについて **詳細の表示** を選択すると、処理時間、最終処理日、およびタスクに関連するすべてのエラーと警告などの追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f57e0-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="f57e0-142">活動の編集</span><span class="sxs-lookup"><span data-stu-id="f57e0-142">Edit an activity</span></span>

1. <span data-ttu-id="f57e0-143">対象者に関するインサイトで、**データ** > **活動** に移動します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="f57e0-144">編集する活動エンティティを選択して、**編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="f57e0-145">または、エンティティ行にカーソルを合わせて、**編集** アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="f57e0-146">**編集** アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f57e0-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="f57e0-147">**活動の編集** ウィンドウで、値を更新して **保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="f57e0-148">**活動** ページで、**実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="f57e0-149">活動の削除</span><span class="sxs-lookup"><span data-stu-id="f57e0-149">Delete an activity</span></span>

1. <span data-ttu-id="f57e0-150">対象者に関するインサイトで、**データ** > **活動** に移動します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="f57e0-151">削除する活動エンティティを選択して、**削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="f57e0-152">または、エンティティ行にカーソルを合わせて、**削除** アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="f57e0-153">さらに、一度に削除する複数のアクティビティ エンティティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f57e0-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f57e0-154">![エンティティ関係を編集または削除する](media/activities-entities-edit-delete.png "エンティティ関係を編集または削除する")</span><span class="sxs-lookup"><span data-stu-id="f57e0-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="f57e0-155">**削除** アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="f57e0-156">削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="f57e0-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]