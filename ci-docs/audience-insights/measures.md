---
title: メジャーの作成および編集
description: 特定の事業分野のパフォーマンスを分析および反映するために、顧客関連型メジャーを定義します。
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406192"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="39748-103">メジャーの定義と管理</span><span class="sxs-lookup"><span data-stu-id="39748-103">Define and manage measures</span></span>

<span data-ttu-id="39748-104">**メジャー** は、特定の事業分野のパフォーマンスと正常性を反映する主要業績評価指標 (KPI) を表します。</span><span class="sxs-lookup"><span data-stu-id="39748-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="39748-105">対象者に関するインサイトは、メジャーを手動でコーディングまたは検証する必要のないクエリ ビルダーを使用して、さまざまなタイプのメジャーを構築するための直感的なエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="39748-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="39748-106">**ホーム** ページでビジネス指標を追跡できます。**顧客カード** で特定の顧客向けの対策を参照して、メジャーを使用して、**セグメント** ページで顧客セグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="39748-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="39748-107">メジャーを作成する</span><span class="sxs-lookup"><span data-stu-id="39748-107">Create a measure</span></span>

<span data-ttu-id="39748-108">このセクションでは、ゼロからメジャーを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="39748-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="39748-109">顧客エンティティを介して接続された複数のデータ ソースのデータを使用してメジャーを構築できます。</span><span class="sxs-lookup"><span data-stu-id="39748-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="39748-110">一部の [サービス制限](service-limits.md) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="39748-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="39748-111">対象者に関するインサイトで、**メジャー** に移動します。</span><span class="sxs-lookup"><span data-stu-id="39748-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="39748-112">**新規メジャー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39748-112">Select **New measure**.</span></span>

3. <span data-ttu-id="39748-113">メジャーの **種類** を選択します :</span><span class="sxs-lookup"><span data-stu-id="39748-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="39748-114">**顧客属性** : 顧客のスコア、値、または状態を反映する顧客ごとの単一フィールド。</span><span class="sxs-lookup"><span data-stu-id="39748-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="39748-115">顧客属性は、**Customer_Measure** と呼ばれる新しいシステム生成エンティティで属性として作成されます。</span><span class="sxs-lookup"><span data-stu-id="39748-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="39748-116">**顧客メジャー**: 選択したディメンション別の内訳を含む顧客行動に関するインサイト。</span><span class="sxs-lookup"><span data-stu-id="39748-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="39748-117">新しいエンティティが、各メジャーのために、潜在的に顧客ごとに複数のレコードで生成されます。</span><span class="sxs-lookup"><span data-stu-id="39748-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="39748-118">**ビジネス メジャー** : ビジネスの業務パフォーマンスと正常性を追跡します。</span><span class="sxs-lookup"><span data-stu-id="39748-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="39748-119">ビジネス メジャーには 2 つの異なる出力があります : **ホーム** ページ上で表示される数値での出力、または **エンティティ** ページ上にある新しいエンティティです。</span><span class="sxs-lookup"><span data-stu-id="39748-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="39748-120">**名前** とオプションで **表示名** を提供して、次に **次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39748-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="39748-121">**エンティティ** セクションで、ドロップダウン リストから最初のエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="39748-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="39748-122">この時点で、メジャー定義の一部として追加のエンティティが必要かどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39748-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="39748-123">![メジャー定義](media/measure-definition.png "メジャー定義")</span><span class="sxs-lookup"><span data-stu-id="39748-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="39748-124">もっとエンティティを追加するには、**エンティティを追加** を選択して、メジャーに使用するエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="39748-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="39748-125">開始エンティティとのリレーションシップを持つエンティティのみを選択します。</span><span class="sxs-lookup"><span data-stu-id="39748-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="39748-126">リレーションシップを定義することについての詳細は、[リレーションシップ](relationships.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39748-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="39748-127">オプションで、変数を構成できます。</span><span class="sxs-lookup"><span data-stu-id="39748-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="39748-128">**変数** セクションで、**新しい変数** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39748-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="39748-129">変数は、選択した各レコードで行われる計算です。</span><span class="sxs-lookup"><span data-stu-id="39748-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="39748-130">たとえば、各顧客のレコードの販売時点 (POS) とオンライン販売を合計します。</span><span class="sxs-lookup"><span data-stu-id="39748-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="39748-131">変数の **名前** を提供します。</span><span class="sxs-lookup"><span data-stu-id="39748-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="39748-132">**表現** 領域で、計算を開始するフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="39748-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="39748-133">**式** 領域に式を入力し、同時に計算に含めるフィールドをさらに選択します。</span><span class="sxs-lookup"><span data-stu-id="39748-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="39748-134">現時点で算術式のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="39748-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="39748-135">さらに、変数計算は、異なる [エンティティ パス](relationships.md) からのエンティティをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="39748-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="39748-136">**完了** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39748-136">Select **Done**.</span></span>

11. <span data-ttu-id="39748-137">**メジャー定義** セクションでは、選択したエンティティと計算された変数を新しいメジャー エンティティまたは属性に集約する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="39748-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="39748-138">**新しいディメンション** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39748-138">Select **New dimension**.</span></span> <span data-ttu-id="39748-139">ディメンションは関数による *グループ* として考えることができます。</span><span class="sxs-lookup"><span data-stu-id="39748-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="39748-140">メジャー エンティティまたは属性のデータ出力は、定義されたすべてのディメンションによってグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="39748-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="39748-141">![集約サイクルの選択](media/measures-businessreport-measure-definition2.png "集約サイクルの選択")</span><span class="sxs-lookup"><span data-stu-id="39748-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="39748-142">ディメンションの定義の一部として、次の情報を選択または入力します。</span><span class="sxs-lookup"><span data-stu-id="39748-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="39748-143">**エンティティ** : メジャー エンティティを定義する場合、少なくとも 1 つの属性を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="39748-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="39748-144">メジャー属性を定義する場合、デフォルトで 1 つの属性のみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="39748-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="39748-145">この選択は、その属性を含むエンティティの選択に関するものです。</span><span class="sxs-lookup"><span data-stu-id="39748-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="39748-146">**フィールド** : メジャー エンティティまたは属性に含める特定の属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="39748-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="39748-147">**バケット** : データを日単位、月単位、または年単位で集約するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="39748-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="39748-148">これは、日付タイプ属性を選択した場合にのみ必須です。</span><span class="sxs-lookup"><span data-stu-id="39748-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="39748-149">**次として** : 新規フィールドの名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="39748-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="39748-150">**表示名**: フィールドの表示名を定義します。</span><span class="sxs-lookup"><span data-stu-id="39748-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="39748-151">ビジネス メジャーは単一番号のエンティティとして保存され、さらにディメンションを追加しない限り、**ホーム** ページ上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="39748-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="39748-152">さらにディメンションを追加すると、メジャーは **ホーム** ページ上に表示 *されません*。</span><span class="sxs-lookup"><span data-stu-id="39748-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="39748-153">オプションで、集計関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="39748-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="39748-154">集計を作成すると、メジャー エンティティまたは属性内に新しい値が作成されます。</span><span class="sxs-lookup"><span data-stu-id="39748-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="39748-155">サポートされる集約関数は次のとおりです。**分**、**最大**、**平均**、**中央値**、**合計**、**一意のカウント**、**最初** (ディメンション値の最初のレコードを撮る)、および **最終** (ディメンション値に追加された最後のレコードを取る)。</span><span class="sxs-lookup"><span data-stu-id="39748-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="39748-156">**保存** を選択して、メジャーに変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="39748-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="39748-157">メジャーの管理</span><span class="sxs-lookup"><span data-stu-id="39748-157">Manage your measures</span></span>

<span data-ttu-id="39748-158">少なくとも 1 つのメジャーを作成すると、**メジャー** ページにメジャーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39748-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="39748-159">メジャー タイプ、作成者、作成日時、最終編集日時、ステータス (メジャーがアクティブか、非アクティブか、失敗)、および最終更新日時に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39748-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="39748-160">リストからメジャーを選択すると、その出力のプレビューを表示できます。</span><span class="sxs-lookup"><span data-stu-id="39748-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="39748-161">すべてのメジャーを同時に更新するには、特定のメジャーを選択せずに **すべて更新** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39748-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="39748-162">![単一のメジャーを管理するためのアクション](media/measure-actions.png "単一のメジャーを管理するためのアクション")</span><span class="sxs-lookup"><span data-stu-id="39748-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="39748-163">または、リストからメジャーを選択し、次のいずれかのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="39748-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="39748-164">メジャー名を選択して詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="39748-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="39748-165">メジャーの構成を **編集** します。</span><span class="sxs-lookup"><span data-stu-id="39748-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="39748-166">メジャーの **名前を変更** します。</span><span class="sxs-lookup"><span data-stu-id="39748-166">**Rename** the measure.</span></span>
- <span data-ttu-id="39748-167">メジャーを **削除** します。</span><span class="sxs-lookup"><span data-stu-id="39748-167">**Delete** the measure.</span></span>
- <span data-ttu-id="39748-168">省略記号 (...) を、その後 **更新** を選択してメジャーの更新プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="39748-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="39748-169">省略記号 (...)、その後 **ダウンロード** を選択して、メジャーの .CSV ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="39748-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="39748-170">タスク/プロセスには、[6 種類の状態](system.md#status-types) があります。</span><span class="sxs-lookup"><span data-stu-id="39748-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="39748-171">さらに、ほとんどのプロセスは、[その他の下流プロセスに依存します](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="39748-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="39748-172">プロセスのステータスを選択して、ジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="39748-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="39748-173">ジョブのタスクの 1 つについて **詳細の表示** を選択すると、処理時間、最終処理日、およびタスクに関連するすべてのエラーと警告などの追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39748-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="39748-174">次のステップ</span><span class="sxs-lookup"><span data-stu-id="39748-174">Next step</span></span>

<span data-ttu-id="39748-175">既存のメジャーを使用して、**セグメント** ページで最初の顧客セグメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="39748-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="39748-176">詳細については、[セグメント](segments.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39748-176">For more information, see [Segments](segments.md).</span></span>
