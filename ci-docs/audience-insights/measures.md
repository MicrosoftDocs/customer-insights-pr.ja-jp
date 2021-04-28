---
title: メジャーを作成および管理する
description: メジャーを定義して、ビジネスのパフォーマンスを分析して反映させます。
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a94a32a04f2a8beb661c27271fe96f23d998722
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887946"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="3926a-103">メジャーの定義と管理</span><span class="sxs-lookup"><span data-stu-id="3926a-103">Define and manage measures</span></span>

<span data-ttu-id="3926a-104">メジャーは、顧客の行動とビジネス パフォーマンスをよりよく理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3926a-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="3926a-105">[統合されたプロファイル](data-unification.md) から関連する値を確認します。</span><span class="sxs-lookup"><span data-stu-id="3926a-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="3926a-106">たとえば、ビジネスでは、*顧客あたりの合計支出* を表示して、個々の顧客の購入履歴を把握したり、*会社の総売上高* を測定して、ビジネス全体の集計レベルの収益を把握したりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3926a-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="3926a-107">メジャーは、さまざまな演算子と単純なマッピング オプションを備えたデータ クエリ プラットフォームであるメジャー ビルダーを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="3926a-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="3926a-108">データをフィルタリングし、結果をグループ化し、[エンティティ関連パス](relationships.md)を検出して、出力をプレビューします。</span><span class="sxs-lookup"><span data-stu-id="3926a-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="3926a-109">メジャー ビルダーを使用して、顧客データを照会し、インサイトを抽出することによりビジネス アクティビティを計画します。</span><span class="sxs-lookup"><span data-stu-id="3926a-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="3926a-110">たとえば、*顧客あたりの総支出* と *顧客あたりのトータル リターン* のメジャーを作成することにより、支出は多いが収益が高い顧客のグループを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3926a-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="3926a-111">[セグメントを作成](segments.md)して、次善の行動を推進できます。</span><span class="sxs-lookup"><span data-stu-id="3926a-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="3926a-112">独自のメジャーをゼロから構築する</span><span class="sxs-lookup"><span data-stu-id="3926a-112">Build your own measure from scratch</span></span>

<span data-ttu-id="3926a-113">このセクションでは、新しいメジャーを最初から作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3926a-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="3926a-114">顧客エンティティに接続するように設定された関係を持つデータ エンティティからのデータ属性を使用してメジャーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3926a-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="3926a-115">対象者に関するインサイトで、**メジャー** に移動します。</span><span class="sxs-lookup"><span data-stu-id="3926a-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="3926a-116">**新規** を選択して、**独自に構築する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="3926a-117">**名前の編集** を選択して、メジャーの **名前** を提供します。</span><span class="sxs-lookup"><span data-stu-id="3926a-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="3926a-118">新しいメジャー構成に、たとえば、CustomerID と 1 つの計算の 2 つのフィールドしかない場合、出力は、Customer_Measure と呼ばれるシステム生成エンティティに新しい列として追加されます。</span><span class="sxs-lookup"><span data-stu-id="3926a-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="3926a-119">また、統一された顧客プロファイルでメジャーの値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3926a-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="3926a-120">他のメジャーは、独自のエンティティを生成します。</span><span class="sxs-lookup"><span data-stu-id="3926a-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="3926a-121">構成領域で、**関数の選択** ドロップダウン メニューから集計関数を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="3926a-122">集計関数は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3926a-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="3926a-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="3926a-123">**Sum**</span></span>
   - <span data-ttu-id="3926a-124">**平均**</span><span class="sxs-lookup"><span data-stu-id="3926a-124">**Average**</span></span>
   - <span data-ttu-id="3926a-125">**回数**</span><span class="sxs-lookup"><span data-stu-id="3926a-125">**Count**</span></span>
   - <span data-ttu-id="3926a-126">**一意の件数**</span><span class="sxs-lookup"><span data-stu-id="3926a-126">**Count Unique**</span></span>
   - <span data-ttu-id="3926a-127">**最高**</span><span class="sxs-lookup"><span data-stu-id="3926a-127">**Max**</span></span>
   - <span data-ttu-id="3926a-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="3926a-128">**Min**</span></span>
   - <span data-ttu-id="3926a-129">**最初**: データ レコードの最初の値を取得します</span><span class="sxs-lookup"><span data-stu-id="3926a-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="3926a-130">**最終**: データ レコードに追加された最後の値を取得します</span><span class="sxs-lookup"><span data-stu-id="3926a-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="メジャー計算の演算子。":::

1. <span data-ttu-id="3926a-132">**属性の追加** を選択して、このメジャーを作成するために必要なデータを選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="3926a-133">**属性** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="3926a-134">データ エンティティ: 測定する属性を含むエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="3926a-135">データ属性: メジャーを計算するために集計関数で使用する属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="3926a-136">一度に選択できる属性は 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="3926a-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="3926a-137">**対策** タブを選択することにより、既存のメジャーからデータ属性を選択することもできます。または、エンティティまたはメジャー名を検索できます。</span><span class="sxs-lookup"><span data-stu-id="3926a-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="3926a-138">**追加** を選択して、選択した属性をメジャーに追加します。</span><span class="sxs-lookup"><span data-stu-id="3926a-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="計算に使用する属性を選択します。":::

1. <span data-ttu-id="3926a-140">より複雑なメジャーを作成するには、属性を追加するか、メジャー関数で数学演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="3926a-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="数学演算子を使用して複雑なメジャーを作成します。":::

1. <span data-ttu-id="3926a-142">フィルターを追加するには、構成領域で **フィルター** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="3926a-143">**フィルター** ペインの **属性の追加** セクションで、フィルターの作成に使用する属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="3926a-144">フィルター演算子を設定して、選択したすべての属性のフィルターを定義します。</span><span class="sxs-lookup"><span data-stu-id="3926a-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="3926a-145">**適用** を選択して、フィルタ＝をメジャーに追加します。</span><span class="sxs-lookup"><span data-stu-id="3926a-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="3926a-146">ディメンションを追加するには、構成領域で **ディメンション** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="3926a-147">ディメンションは、メジャー出力エンティティの列として表示されます。</span><span class="sxs-lookup"><span data-stu-id="3926a-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="3926a-148">**ディメンションの編集** を選択して、メジャー値をグループ化するデータ属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="3926a-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="3926a-149">たとえば、都市や性別。</span><span class="sxs-lookup"><span data-stu-id="3926a-149">For example, city or gender.</span></span> <span data-ttu-id="3926a-150">既定では、*顧客レベル メジャー* を作成するのに *CustomerID* ディメンションが選択されます。</span><span class="sxs-lookup"><span data-stu-id="3926a-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="3926a-151">*ビジネスレベル メジャー* を作成する場合、既定ディメンションを削除できます。</span><span class="sxs-lookup"><span data-stu-id="3926a-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="3926a-152">**完了** を選択して、ディメンションをメジャーに追加します。</span><span class="sxs-lookup"><span data-stu-id="3926a-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="3926a-153">たとえば、*null* を *0* に置き換えるなど、整数で置き換える必要がある値がデータにある場合は、**ルール** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="3926a-154">ルールを構成し、置換として整数のみを選択していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3926a-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="3926a-155">マッピングしたデータ エンティティと *Customer* エンティティの間に複数のパスがある場合、識別された [エンティティ関連パス](relationships.md) の 1 つを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3926a-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="3926a-156">メジャー結果は、選択したパスによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3926a-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="3926a-157">**データ設定** を選択し、メジャーを識別するために使用するエンティティ パスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="3926a-158">*Customer* エンティティへのパスが 1 つしかない場合、このコントロールは表示されません。</span><span class="sxs-lookup"><span data-stu-id="3926a-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="3926a-159">**完了** を選択して、選択肢を適用します。</span><span class="sxs-lookup"><span data-stu-id="3926a-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="メジャーのエンティティ パスを選択します。":::

1. <span data-ttu-id="3926a-161">メジャーの計算をさらに追加するには、**新しい計算** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="3926a-162">新しい計算には、同じエンティティ パス上のエンティティのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3926a-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="3926a-163">メジャー出力エンティティの列として、より多くの計算が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3926a-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="3926a-164">計算で **...** を選択して、メジャーからの計算を **複製**、**名前変更**、または **削除** を行います。</span><span class="sxs-lookup"><span data-stu-id="3926a-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="3926a-165">**プレビュー** エリアには、フィルターやディメンションなど、メジャー出力エンティティのデータ スキーマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3926a-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="3926a-166">プレビューは、構成の変更に動的に反応します。</span><span class="sxs-lookup"><span data-stu-id="3926a-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="3926a-167">**実行** を選択して、構成されたメジャーの結果を計算します。</span><span class="sxs-lookup"><span data-stu-id="3926a-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="3926a-168">現在の構成を保持し、後でメジャーを実行する場合、**保存して閉じる** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="3926a-169">**メジャー** に移動して、リストで新たに作成されたメジャーを確認します。</span><span class="sxs-lookup"><span data-stu-id="3926a-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="3926a-170">テンプレートを使用してメジャーを作成する</span><span class="sxs-lookup"><span data-stu-id="3926a-170">Use a template to build a measure</span></span>

<span data-ttu-id="3926a-171">一般的に使用されるメジャーの定義済みテンプレートを使用して、それらを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3926a-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="3926a-172">テンプレートの詳細な説明とガイド付きのエクスペリエンスは、効率的なメジャーの作成に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3926a-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="3926a-173">テンプレートは、*Unified Activity* エンティティからマップされたデータに基づいて構築されます。</span><span class="sxs-lookup"><span data-stu-id="3926a-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="3926a-174">したがって、テンプレートからメジャーを作成する前に、[顧客活動](activities.md) を構成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3926a-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="3926a-175">使用できるメジャー テンプレート:</span><span class="sxs-lookup"><span data-stu-id="3926a-175">Available measure templates:</span></span> 
- <span data-ttu-id="3926a-176">平均取引値 (ATV)</span><span class="sxs-lookup"><span data-stu-id="3926a-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="3926a-177">合計取引値</span><span class="sxs-lookup"><span data-stu-id="3926a-177">Total transaction value</span></span>
- <span data-ttu-id="3926a-178">日別平均売上</span><span class="sxs-lookup"><span data-stu-id="3926a-178">Average daily revenue</span></span>
- <span data-ttu-id="3926a-179">年別平均売上</span><span class="sxs-lookup"><span data-stu-id="3926a-179">Average yearly revenue</span></span>
- <span data-ttu-id="3926a-180">取引回数</span><span class="sxs-lookup"><span data-stu-id="3926a-180">Transaction count</span></span>
- <span data-ttu-id="3926a-181">獲得したロイヤルティ ポイント</span><span class="sxs-lookup"><span data-stu-id="3926a-181">Loyalty points earned</span></span>
- <span data-ttu-id="3926a-182">引き換え済みのロイヤルティ ポイント</span><span class="sxs-lookup"><span data-stu-id="3926a-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="3926a-183">ロイヤルティ ポイントの残高</span><span class="sxs-lookup"><span data-stu-id="3926a-183">Loyalty points balance</span></span>
- <span data-ttu-id="3926a-184">アクティブな顧客ライフスパン</span><span class="sxs-lookup"><span data-stu-id="3926a-184">Active customer lifespan</span></span>
- <span data-ttu-id="3926a-185">ロイヤルティ メンバーシップの期間</span><span class="sxs-lookup"><span data-stu-id="3926a-185">Loyalty membership duration</span></span>
- <span data-ttu-id="3926a-186">最後の購入以降の時間</span><span class="sxs-lookup"><span data-stu-id="3926a-186">Time since last purchase</span></span>

<span data-ttu-id="3926a-187">次の手順では、テンプレートを使用して新しいメジャーを作成する手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="3926a-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="3926a-188">対象者に関するインサイトで、**メジャー** に移動します。</span><span class="sxs-lookup"><span data-stu-id="3926a-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="3926a-189">**新規** を選択し、**テンプレートを選択** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="テンプレートを強調表示して新しいメジャーを作成するときのドロップダウン メニューのスクリーンショット。":::

1. <span data-ttu-id="3926a-191">ニーズに最適なテンプレートを検索し、**テンプレートを選択** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="3926a-192">すべてのデータが揃っている場合、必要なデータを確認して、**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="3926a-193">**名前の編集** ペインで、メジャーと出力エンティティの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="3926a-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="3926a-194">**完了** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-194">Select **Done**.</span></span>

1. <span data-ttu-id="3926a-195">**期間の設定** セクションで、使用するデータの概算時間を定義します。</span><span class="sxs-lookup"><span data-stu-id="3926a-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="3926a-196">**すべての時間** を選択して、新しいメジャーでデータ セット全体をカバーするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="3926a-197">または、メジャーを **特定の期間** に集中させる場合です。</span><span class="sxs-lookup"><span data-stu-id="3926a-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="テンプレートからメジャーを構成するときの期間セクションを示すスクリーンショット。":::

1. <span data-ttu-id="3926a-199">次のセクションで、**データの追加** を選択し、活動を選択して、*Unified Activity* エンティティから対応するデータをマップします。</span><span class="sxs-lookup"><span data-stu-id="3926a-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="3926a-200">ステップ 1/2: **活動の種類** の下にある、使用するエンティティの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="3926a-201">**活動** でマップするエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="3926a-202">ステップ 2/2: 計算式に必要なコンポーネントの *Unified Activity* エンティティから属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="3926a-203">たとえば、平均取引値の場合は、取引値を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="3926a-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="3926a-204">**活動のタイムスタンプ** で、活動の日時を表す属性を Unified Activity エンティティから選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="3926a-205">データ マッピングが成功すると、状態が **完了** と表示され、マップされた活動と属性の名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3926a-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="完了したメジャー テンプレート構成のスクリーンショット。":::

1. <span data-ttu-id="3926a-207">**実行** を選択してメジャーの結果を計算できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3926a-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="3926a-208">後で調整するには、**下書きの保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="3926a-209">メジャーの管理</span><span class="sxs-lookup"><span data-stu-id="3926a-209">Manage your measures</span></span>

<span data-ttu-id="3926a-210">メジャーのリストは、**メジャー** ページにあります。</span><span class="sxs-lookup"><span data-stu-id="3926a-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="3926a-211">メジャー タイプ、作成者、作成日、ステータス、および状態に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3926a-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="3926a-212">リストからメジャーを選択すると、出力をプレビューして .CSV ファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="3926a-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="3926a-213">すべてのメジャーを同時に更新するには、特定のメジャーを選択せずに **すべて更新** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3926a-214">![単一のメジャーを管理するためのアクション](media/measure-actions.png "単一のメジャーを管理するためのアクション")</span><span class="sxs-lookup"><span data-stu-id="3926a-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="3926a-215">次のオプションのリストからメジャーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3926a-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="3926a-216">メジャー名を選択して詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="3926a-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="3926a-217">メジャーの構成を **編集** します。</span><span class="sxs-lookup"><span data-stu-id="3926a-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="3926a-218">最新のデータに基づいて、メジャーを **更新** します。</span><span class="sxs-lookup"><span data-stu-id="3926a-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="3926a-219">メジャーの **名前を変更** します。</span><span class="sxs-lookup"><span data-stu-id="3926a-219">**Rename** the measure.</span></span>
- <span data-ttu-id="3926a-220">メジャーを **削除** します。</span><span class="sxs-lookup"><span data-stu-id="3926a-220">**Delete** the measure.</span></span>
- <span data-ttu-id="3926a-221">**アクティブ化** または **非アクティブ化** します。</span><span class="sxs-lookup"><span data-stu-id="3926a-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="3926a-222">非アクティブなメジャーは、[スケジュールされた更新](system.md#schedule-tab)中に更新されません。</span><span class="sxs-lookup"><span data-stu-id="3926a-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="3926a-223">タスク/プロセスには、[6 種類の状態](system.md#status-types) があります。</span><span class="sxs-lookup"><span data-stu-id="3926a-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3926a-224">さらに、ほとんどのプロセスは、[その他の下流プロセスに依存します](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="3926a-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3926a-225">プロセスのステータスを選択して、ジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3926a-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3926a-226">ジョブのタスクの 1 つについて **詳細の表示** を選択すると、処理時間、最終処理日、およびタスクに関連するすべてのエラーと警告などの追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3926a-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="3926a-227">次のステップ</span><span class="sxs-lookup"><span data-stu-id="3926a-227">Next step</span></span>

<span data-ttu-id="3926a-228">既存のメジャーを使用して[顧客セグメント](segments.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="3926a-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]