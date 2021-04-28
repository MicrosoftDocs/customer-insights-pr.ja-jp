---
title: 顧客活動
description: 顧客活動を定義し、顧客のタイムラインで表示します。
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866413"
---
# <a name="customer-activities"></a><span data-ttu-id="f1739-103">顧客活動</span><span class="sxs-lookup"><span data-stu-id="f1739-103">Customer activities</span></span>

<span data-ttu-id="f1739-104">Dynamics 365 Customer Insights では、[さまざまなデータ ソース](data-sources.md) からの顧客活動を組み合わせて、活動を時系列で一覧表示するタイムラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1739-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="f1739-105">[顧客カード アドイン](customer-card-add-in.md) ソリューション、または Power BI ダッシュボードを使用して、Dynamics 365 アプリにタイムラインを含めます。</span><span class="sxs-lookup"><span data-stu-id="f1739-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="f1739-106">活動を定義する</span><span class="sxs-lookup"><span data-stu-id="f1739-106">Define an activity</span></span>

<span data-ttu-id="f1739-107">データ ソースには、複数のデータ ソースからのトランザクション データと活動データを持つエンティティを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f1739-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="f1739-108">これらのエンティティを識別し、顧客のタイムラインで表示するアクティビティを選択します。</span><span class="sxs-lookup"><span data-stu-id="f1739-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="f1739-109">対象となる活動 (複数可) を含むエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="f1739-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="f1739-110">エンティティには、顧客のタイムラインに含めるために少なくとも 1 つの **日付** 属性が必要で、**日付** フィールドなしではエンティティを追加できません。</span><span class="sxs-lookup"><span data-stu-id="f1739-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="f1739-111">このようなエンティティが見つからない場合は、**活動の追加** コントロールは無効になります。</span><span class="sxs-lookup"><span data-stu-id="f1739-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="f1739-112">対象者に関するインサイトで、**データ** > **活動** に移動します。</span><span class="sxs-lookup"><span data-stu-id="f1739-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="f1739-113">**活動の追加** を選択して、活動設定プロセスのガイド付きエクスペリエンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="f1739-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="f1739-114">**活動データ** の手順で、次のフィールドの値を設定します:</span><span class="sxs-lookup"><span data-stu-id="f1739-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="f1739-115">**活動名**: 活動の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1739-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="f1739-116">**エンティティ**: トランザクションデータ、つまり活動データを含むエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="f1739-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="f1739-117">**主キー** : レコードを一意に識別するフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="f1739-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="f1739-118">重複する値、空の値、または欠損した値を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="f1739-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="名前、エンティティ、および主キーを使用して活動データを設定する。":::

1. <span data-ttu-id="f1739-120">**次へ** を選択して、次の手順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f1739-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="f1739-121">**関連付け** の手順で、活動データを対応する顧客に接続するための詳細を構成します。</span><span class="sxs-lookup"><span data-stu-id="f1739-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="f1739-122">この手順では、エンティティ間の接続を視覚化します。</span><span class="sxs-lookup"><span data-stu-id="f1739-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="f1739-123">**第 1**: 別のエンティティとの関係を確立するために使用される活動エンティティの外部フィールド。</span><span class="sxs-lookup"><span data-stu-id="f1739-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="f1739-124">**第 2**: 活動エンティティが関係する、対応するソース顧客エンティティ。</span><span class="sxs-lookup"><span data-stu-id="f1739-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="f1739-125">データ統合プロセスで使用されるソース顧客エンティティにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="f1739-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="f1739-126">**第 3**: この活動エンティティと選択したソース顧客エンティティの間に関連がすでに存在する場合、関連付け名は読み取り専用モードになります。</span><span class="sxs-lookup"><span data-stu-id="f1739-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="f1739-127">そのような関係が存在しない場合は、このボックスに入力した名前で新しい関係が作成されます。</span><span class="sxs-lookup"><span data-stu-id="f1739-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="エンティティの関連付けを定義する。":::

1. <span data-ttu-id="f1739-129">**次へ** を選択して、次の手順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f1739-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="f1739-130">**活動の統合** の手順で、活動イベントと活動の開始時間を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1739-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="f1739-131">**必須フィールド**</span><span class="sxs-lookup"><span data-stu-id="f1739-131">**Required fields**</span></span>
      1. <span data-ttu-id="f1739-132">**イベント活動**: この活動のイベントであるフィールド</span><span class="sxs-lookup"><span data-stu-id="f1739-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="f1739-133">**タイムスタンプ**: 活動の開始時刻を表すフィールド。</span><span class="sxs-lookup"><span data-stu-id="f1739-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="f1739-134">**オプション フィールド**</span><span class="sxs-lookup"><span data-stu-id="f1739-134">**Optional fields**</span></span>
      1. <span data-ttu-id="f1739-135">**追加情報**: この活動に関連する情報を含むフィールド。</span><span class="sxs-lookup"><span data-stu-id="f1739-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="f1739-136">**アイコン**: この活動の種類を最もよく表すアイコン。</span><span class="sxs-lookup"><span data-stu-id="f1739-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="f1739-137">**Web アドレス**: この活動に関する情報を含む URL を持つフィールド。</span><span class="sxs-lookup"><span data-stu-id="f1739-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="f1739-138">たとえば、このアクティビティのソースとなるトランザクション システムです。</span><span class="sxs-lookup"><span data-stu-id="f1739-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="f1739-139">この URL は、データ ソースの任意のフィールドにすることも、Power Query 変換を使用して新たなフィールドとして構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1739-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="f1739-140">URL データは、*Unified Activity* エンティティに保存され、[API](apis.md) を使用してダウンストリームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1739-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Unified Activity エンティティで顧客活動データを指定する。":::

1. <span data-ttu-id="f1739-142">**次へ** を選択して、次の手順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f1739-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="f1739-143">**終了して確認** を選択して、活動の種類を **その他** に設定した状態で活動を保存できます。</span><span class="sxs-lookup"><span data-stu-id="f1739-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="f1739-144">**活動の種類** の手順で活動の種類を選択し、オプションで Customer Insights の他の領域で使用するために活動の種類の一部をセマンティックにマップするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f1739-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="f1739-145">現在、フィールドのマップに同意した後、*Subscription* & *SalesOrderLine* の活動の種類をセマンティックにマップできます。</span><span class="sxs-lookup"><span data-stu-id="f1739-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="f1739-146">活動の種類が新しい活動に関連しない場合は、カスタム活動の種類に *その他* または *新規作成* を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f1739-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="f1739-147">**次へ** を選択して、次の手順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f1739-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="f1739-148">**レビュー** の手順で、選択内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="f1739-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="f1739-149">前述のいずれかの手順に戻り、必要に応じて情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="f1739-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="活動に指定されたフィールドを確認する。":::
   
1. <span data-ttu-id="f1739-151">**活動を保存する** を選択して変更を適用し、**完了** を選択して、**データ** > **活動** に戻ります。</span><span class="sxs-lookup"><span data-stu-id="f1739-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="f1739-152">ここでは、タイムラインに表示するように設定されている活動を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f1739-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="f1739-153">**活動** ページで **実行** を選択し、活動を処理します。</span><span class="sxs-lookup"><span data-stu-id="f1739-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="f1739-154">タスク/プロセスには、[6 種類の状態](system.md#status-types) があります。</span><span class="sxs-lookup"><span data-stu-id="f1739-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f1739-155">さらに、ほとんどのプロセスは、[その他の下流プロセスに依存します](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="f1739-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f1739-156">プロセスのステータスを選択して、ジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f1739-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f1739-157">ジョブのタスクの 1 つについて **詳細の表示** を選択すると、処理時間、最終処理日、およびタスクに関連するすべてのエラーと警告などの追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1739-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="f1739-158">既存の活動の管理</span><span class="sxs-lookup"><span data-stu-id="f1739-158">Manage existing activities</span></span>

<span data-ttu-id="f1739-159">**データ** > **活動** で、保存したすべての活動を表示して管理できます。</span><span class="sxs-lookup"><span data-stu-id="f1739-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="f1739-160">各活動は、ソース、エンティティ、および活動の種類に関する詳細も含む行で表されます。</span><span class="sxs-lookup"><span data-stu-id="f1739-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="f1739-161">活動を選択すると、次のアクションが可能になります。</span><span class="sxs-lookup"><span data-stu-id="f1739-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="f1739-162">**編集**: レビューの手順で活動設定を開きます。</span><span class="sxs-lookup"><span data-stu-id="f1739-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="f1739-163">この手順から、現在の構成の一部またはすべてを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f1739-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="f1739-164">構成を変更した後、**活動を保存する** を選択し、**実行** を選択して変更を処理します。</span><span class="sxs-lookup"><span data-stu-id="f1739-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="f1739-165">**名前の変更**: 選択した活動に別の名前を入力するダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="f1739-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="f1739-166">**保存** を選択して変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="f1739-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="f1739-167">**削除**: 選択した活動の削除を確認するダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="f1739-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="f1739-168">活動を選択してから削除アイコンを選択することにより、一度に複数の活動を削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1739-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="f1739-169">**削除** を選択して、削除内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="f1739-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
