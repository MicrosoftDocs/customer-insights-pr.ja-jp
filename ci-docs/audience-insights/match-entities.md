---
title: データ統合のためにエンティティを照合する
description: データを照合して、統合顧客プロファイルを作成します。
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2eb84c44aa530346a73ba720106734d705a45f23
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595570"
---
# <a name="match-entities"></a><span data-ttu-id="fd8b7-103">エンティティを一致させる</span><span class="sxs-lookup"><span data-stu-id="fd8b7-103">Match entities</span></span>

<span data-ttu-id="fd8b7-104">一致フェーズでは、データセットを統合して顧客プロファイルデータセットを統合する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-104">The match phase specifies how to combine your datasets into a unified customer profile dataset.</span></span> <span data-ttu-id="fd8b7-105">データ統合プロセスの [マップ ステップ](map-entities.md) を完了後、エンティティを照合する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-105">After completing the [map step](map-entities.md) in the data unification process, you're ready to match your entities.</span></span> <span data-ttu-id="fd8b7-106">一致フェーズには少なくとも 2 つのマッピングされたエンティティ が必要です。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-106">The match phase requires at least two mapped entities.</span></span>

<span data-ttu-id="fd8b7-107">照合ページは、次の 3 つのセクションで構成されます:</span><span class="sxs-lookup"><span data-stu-id="fd8b7-107">The match page consists of three sections:</span></span> 
- <span data-ttu-id="fd8b7-108">一致するレコードの数を要約する重要な指標</span><span class="sxs-lookup"><span data-stu-id="fd8b7-108">Key metrics that summarize the number of matched records</span></span>
- <span data-ttu-id="fd8b7-109">エンティティ間照合の照合順序とルール</span><span class="sxs-lookup"><span data-stu-id="fd8b7-109">Match order and rules for cross-entity matching</span></span>
- <span data-ttu-id="fd8b7-110">照合エンティティの重複排除ルール</span><span class="sxs-lookup"><span data-stu-id="fd8b7-110">Rules for deduplication of match entities</span></span>

## <a name="specify-the-match-order"></a><span data-ttu-id="fd8b7-111">一致順を指定します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-111">Specify the match order</span></span>

<span data-ttu-id="fd8b7-112">**データ** > **統一する** > **一致** に移動してから、**順序の設定** を設定して照合フェーズを開始します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-112">Go to **Data** > **Unify** > **Match** and select **Set order** to start the match phase.</span></span>

<span data-ttu-id="fd8b7-113">各照合では、2 つ以上のエンティティを単一の連結エンティティに統合します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-113">Each match unifies two or more entities into a single, consolidated entity.</span></span> <span data-ttu-id="fd8b7-114">同時に、一意の顧客レコードを保持します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-114">At the same time, it keeps the unique customer records.</span></span> <span data-ttu-id="fd8b7-115">たとえば、次の 2 つのエンティティを選択しました: 主エンティティとして **eCommerce:eCommerceContacts** と 2番目のエンティティとして **LoyaltyScheme:loyCustomers**。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-115">For example, we selected two entities: **eCommerce:eCommerceContacts** as the primary entity and **LoyaltyScheme:loyCustomers** as second entity.</span></span> <span data-ttu-id="fd8b7-116">エンティティの順序は、システムがレコードの照合を試みる順序を指定します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-116">The order of the entities specifies in which order the system will try to match the records.</span></span>

:::image type="content" source="media/match-page.png" alt-text="データ統合プロセスの統合領域にある照合ページのスクリーンショット。":::
  
<span data-ttu-id="fd8b7-118">主エンティティ *eCommerce:eCommerceContacts* は、次のエンティティ *LoyaltyScheme:loyCustomers* と一致します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-118">The primary entity *eCommerce:eCommerceContacts* is matched with the next entity *LoyaltyScheme:loyCustomers*.</span></span> <span data-ttu-id="fd8b7-119">2 つ以上のエンティティがある場合、最初の照合ステップの結果であるデータセットは、次のエンティティと一致します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-119">The dataset that results from the first match step is matched with the following entity if you have more than two entities.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd8b7-120">主エンティティとして選択したエンティティは、統合プロファイル データセットの基盤として機能します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-120">The entity that you choose as your primary entity will serve as the basis for your unified profiles dataset.</span></span> <span data-ttu-id="fd8b7-121">一致フェーズで選択された追加のエンティティは、このエンティティに追加されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-121">Additional entities that are selected during the match phase will be added to this entity.</span></span> <span data-ttu-id="fd8b7-122">これは、統合されたエンティティに、このエンティティに含まれる *すべて* のデータが、含まれるという意味ではありません。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-122">This doesn't mean that the unified entity will include *all* of the data included in this entity.</span></span>
>
> <span data-ttu-id="fd8b7-123">エンティティの階層を選択する際に役立つ 2 つの考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-123">There are two considerations that can help you choose the hierarchy of your entities:</span></span>
>
> - <span data-ttu-id="fd8b7-124">主エンティティとして、顧客に関する最も完全で信頼性の高いプロファイル データを持つエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-124">Choose the entity with the most complete and reliable profile data about your customers as primary entity.</span></span>
> - <span data-ttu-id="fd8b7-125">他のエンティティと共通のいくつかの属性 (例えば、名前、電話番号、電子メール アドレス) を持つエンティティを主エンティティとして選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-125">Choose the entity that hast several attributes in common with other entities (for example, name, phone number, or email address) as primary entity.</span></span>

<span data-ttu-id="fd8b7-126">照合順序を指定すると、定義された照合ペアが **データ** > **統合** > **照合** の **一致したレコードの詳細** セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-126">After specifying the match order, you'll see the defined match pairs in the **Matched records details** section on **Data** > **Unify** > **Match**.</span></span> <span data-ttu-id="fd8b7-127">照合プロセスが完了するまで、重要な指標は空になります。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-127">The key metrics will be empty until the match process completes.</span></span>

## <a name="define-rules-for-match-pairs"></a><span data-ttu-id="fd8b7-128">照合ペアのルールを定義する</span><span class="sxs-lookup"><span data-stu-id="fd8b7-128">Define rules for match pairs</span></span>

<span data-ttu-id="fd8b7-129">一致ルールは、エンティティの特定のペアが一致するロジックを指定します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-129">Match rules specify the logic by which a specific pair of entities will be matched.</span></span>

<span data-ttu-id="fd8b7-130">エンティティ名の横にある **ルールが必要です** 警告は、照合ペアに照合ルールが定義されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-130">The **Needs rules** warning next to an entity name suggests that no match rule is defined for a match pair.</span></span> 

:::image type="content" source="media/match-rule-add.png" alt-text="ルールを追加するコントロールが強調表示された一致したレコードの詳細セクションのスクリーンショット。":::

1. <span data-ttu-id="fd8b7-132">**一致したレコードの詳細** セクションのエンティティの下にある **ルールの追加** を選択して、照合ルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-132">Select **Add rules** under an entity in the **Matched records details** section to define match rules.</span></span>

1. <span data-ttu-id="fd8b7-133">**ルールの作成** ペインで、ルールの条件を構成します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-133">In the **Create rule** pane, configure the conditions for the rule.</span></span>

   :::image type="content" source="media/match-rule-conditions.png" alt-text="開かれた条件付き照合ルールのスクリーンショット。":::

   - <span data-ttu-id="fd8b7-135">**エンティティ/フィールド (最初の行)**: 関連エンティティと属性を選択して、顧客に固有である可能性が高いレコード プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-135">**Entity/Field (first row)**: Choose a related entity and an attribute to specify a record property that is likely unique to a customer.</span></span> <span data-ttu-id="fd8b7-136">たとえば、電話番号や電子メール アドレスなどです。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-136">For example, a phone number or email address.</span></span> <span data-ttu-id="fd8b7-137">アクティビティ タイプの属性による照合は避けてください。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-137">Avoid matching by activity-type attributes.</span></span> <span data-ttu-id="fd8b7-138">たとえば、購入 ID は、他のレコードの種類では一致しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-138">For example, a purchase ID will likely find no match in other record types.</span></span>

   - <span data-ttu-id="fd8b7-139">**エンティティ/フィールド (2行目)**: 最初の行で指定されたエンティティの属性に関連する属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-139">**Entity/Field (second row)**: Choose an attribute that relates to the attribute of the entity specified in the first row.</span></span>

   - <span data-ttu-id="fd8b7-140">**正規化**: 選択された属性について、次の正規化オプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-140">**Normalize**: Select from following normalization options for the selected attributes.</span></span> 
     - <span data-ttu-id="fd8b7-141">空白: すべてのスペースを削除します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-141">Whitespace: Removes all spaces.</span></span> <span data-ttu-id="fd8b7-142">*Hello   World* は、*HelloWorld* になります。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-142">*Hello   World* becomes *HelloWorld*.</span></span>
     - <span data-ttu-id="fd8b7-143">記号: すべての記号と特殊文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-143">Symbols: Removes all symbols and special characters.</span></span> <span data-ttu-id="fd8b7-144">*Head&Shoulder* は *HeadShoulder* になります。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-144">*Head&Shoulder* becomes *HeadShoulder*.</span></span>
     - <span data-ttu-id="fd8b7-145">テキストを小文字に: すべての文字を小文字に変換します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-145">Text to lower case: Converts all character to lower case.</span></span> <span data-ttu-id="fd8b7-146">*ALL CAPS and Title Case* は *all caps and title case* になります。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-146">*ALL CAPS and Title Case* becomes *all caps and title case*.</span></span>
     - <span data-ttu-id="fd8b7-147">Unicode から ASCII へ: Unicode 表記を ASCII 文字に変換します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-147">Unicode to ASCII: Converts unicode notation to ASCII characters.</span></span> <span data-ttu-id="fd8b7-148">*/u00B2* は *2* になります。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-148">*/u00B2* becomes *2*.</span></span>
     - <span data-ttu-id="fd8b7-149">数字: ローマ数字などの他の数字システムをアラビア数字に変換します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-149">Numerals: Converts other numeral systems, such as Roman numerals, to Arabic numerals.</span></span> <span data-ttu-id="fd8b7-150">*VIII* は *8* になります。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-150">*VIII* becomes *8*.</span></span>
     - <span data-ttu-id="fd8b7-151">セマンティックの種類: 名前、役職、電話番号、住所などを標準化します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-151">Semantic types: Standardizes names, titles, phone numbers, addresses, etc.</span></span> 

   - <span data-ttu-id="fd8b7-152">**精度**: この条件に適用する精度のレベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-152">**Precision**: Set the level of precision to apply for this condition.</span></span> 
     - <span data-ttu-id="fd8b7-153">**基本**: *低*、*中*、*高*、*完全一致* から選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-153">**Basic**: Choose from *Low*, *Medium*, *High*, and *Exact*.</span></span> <span data-ttu-id="fd8b7-154">**完全** を選択して、100％ に一致するレコードのみを一致させます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-154">Select **Exact** to only match records that that match 100 percent.</span></span> <span data-ttu-id="fd8b7-155">その他のレベルの 1 つを選択して、100％ 同一ではないレコードに一致させます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-155">Select one of the other levels to match records that aren't 100 percent identical.</span></span>
     - <span data-ttu-id="fd8b7-156">**カスタム**: レコードが一致する必要がある割合を設定します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-156">**Custom**: Set a percentage that records need to match.</span></span> <span data-ttu-id="fd8b7-157">システムは、このしきい値を超えるレコードのみを照合します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-157">The system will only match records passing this threshold.</span></span>

1. <span data-ttu-id="fd8b7-158">**名前** にルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-158">Provide a **Name** for the rule.</span></span>

1. <span data-ttu-id="fd8b7-159">[さらに条件を追加](#add-conditions-to-a-rule) するか、 **完了** を選択して、ルールの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-159">[Add more conditions](#add-conditions-to-a-rule) or select **Done** to finalize the rule.</span></span>

1. <span data-ttu-id="fd8b7-160">オプションで、[ルールをさらに追加](#add-rules-to-a-match-pair) します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-160">Optionally, [add more rules](#add-rules-to-a-match-pair).</span></span>

1. <span data-ttu-id="fd8b7-161">**保存** を選択して変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-161">Select **Save** to apply your changes.</span></span>

### <a name="add-conditions-to-a-rule"></a><span data-ttu-id="fd8b7-162">ルールに条件を追加する</span><span class="sxs-lookup"><span data-stu-id="fd8b7-162">Add conditions to a rule</span></span>

<span data-ttu-id="fd8b7-163">属性が複数の条件を満たす場合にのみエンティティを照合するには、照合ルールにさらに条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-163">To match entities only if attributes meet multiple conditions, add more conditions to a match rule.</span></span> <span data-ttu-id="fd8b7-164">条件は論理 AND 演算子で接続されるため、すべての条件が満たされた場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-164">Conditions are connected with a logical AND operator and thus only executed if all conditions are met.</span></span>

1. <span data-ttu-id="fd8b7-165">**データ** > **統合** > **照合** に移動し、条件を追加するルールで **編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-165">Go to **Data** > **Unify** > **Match** and select **Edit** on the rule you want to add conditions to.</span></span>

1. <span data-ttu-id="fd8b7-166">**ルールを編集** ウィンドウで、**条件を追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-166">In the **Edit rule** pane, select **Add condition**.</span></span>

1. <span data-ttu-id="fd8b7-167">**完了** を選択して、ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-167">Select **Done** so save the rule.</span></span>

### <a name="add-rules-to-a-match-pair"></a><span data-ttu-id="fd8b7-168">照合ペアにルールを追加する</span><span class="sxs-lookup"><span data-stu-id="fd8b7-168">Add rules to a match pair</span></span>

<span data-ttu-id="fd8b7-169">照合ルールは条件セットを表します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-169">Match rules represent sets of conditions.</span></span> <span data-ttu-id="fd8b7-170">複数の属性に基づく条件によってエンティティを照合するには、ルールをさらに追加します</span><span class="sxs-lookup"><span data-stu-id="fd8b7-170">To match entities by conditions based on multiple attributes, add more rules</span></span>

1.  <span data-ttu-id="fd8b7-171">**データ** > **統合** > **照合** に移動し、ルールを追加するエンティティで **ルールの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-171">Go to **Data** > **Unify** > **Match** and select **Add rule** on the entity you want to add rules to.</span></span>

2. <span data-ttu-id="fd8b7-172">[照合ペアのルールを定義する](#define-rules-for-match-pairs) の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-172">Follow the steps in [Define rules for match pairs](#define-rules-for-match-pairs).</span></span>

> [!NOTE]
> <span data-ttu-id="fd8b7-173">ルールの順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-173">The order of rules matters.</span></span> <span data-ttu-id="fd8b7-174">照合アルゴリズムでは、最初のルールに基づいて照合を試み、最初のルールで一致するものがなかった場合に限り、2 番目のルールに進みます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-174">The matching algorithm tries to match on the basis of your first rule and continues to the second rule only if no matches were identified with the first rule.</span></span>

## <a name="define-deduplication-on-a-match-entity"></a><span data-ttu-id="fd8b7-175">照合エンティティで重複排除を定義する</span><span class="sxs-lookup"><span data-stu-id="fd8b7-175">Define deduplication on a match entity</span></span>

<span data-ttu-id="fd8b7-176">[エンティティ間の照合ルール](#define-rules-for-match-pairs) に加えて、重複排除ルールを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-176">In addition to [cross-entity match rules](#define-rules-for-match-pairs), you can also specify deduplications rules.</span></span> <span data-ttu-id="fd8b7-177">*重複排除* は、レコードを照合するときの別のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-177">*Deduplication* is another process when matching records.</span></span> <span data-ttu-id="fd8b7-178">重複レコードを識別し、1 つのレコードにマージします。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-178">It identifies duplicate records and merges them into one record.</span></span> <span data-ttu-id="fd8b7-179">ソース レコードは、代替 ID でマージされたレコードにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-179">Source records get linked to the merged record with alternate IDs.</span></span>

<span data-ttu-id="fd8b7-180">重複排除したレコードは、エンティティ間の照合プロセスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-180">Deduplicated records will be used in the cross-entity matching process.</span></span> <span data-ttu-id="fd8b7-181">重複排除は個々のエンティティで発生し、照合ペアで使用されるすべてのエンティティで構成できます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-181">Deduplication happens on individual entities and can be configured every entity used in match pairs.</span></span>

<span data-ttu-id="fd8b7-182">重複排除ルールの指定は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-182">Specifying deduplication rules isn't mandatory.</span></span> <span data-ttu-id="fd8b7-183">そのようなルールが構成されていない場合は、システム定義ルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-183">If no such rules are configured, the system-defined rules are applied.</span></span> <span data-ttu-id="fd8b7-184">エンティティ データをエンティティ間照合に渡してパフォーマンスを向上させる前に、すべてのレコードを 1 つのレコードに結合します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-184">They combine all records into a single record before passing the entity data to cross-entity matching for enhanced performance.</span></span>

### <a name="add-deduplication-rules"></a><span data-ttu-id="fd8b7-185">重複排除ルールの追加</span><span class="sxs-lookup"><span data-stu-id="fd8b7-185">Add deduplication rules</span></span>

1. <span data-ttu-id="fd8b7-186">**データ** > **統合** > **照合** に移動します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-186">Go to **Data** > **Unify** > **Match**.</span></span>

1. <span data-ttu-id="fd8b7-187">**マージした重複** セクションで、**エンティティの設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-187">In the **Merged duplicates** section, select **Set entities**.</span></span> <span data-ttu-id="fd8b7-188">重複排除ルールがすでに作成されている場合は、**編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-188">In case deduplication rules are already created, select **Edit**.</span></span>

1. <span data-ttu-id="fd8b7-189">**基本設定をマージする** ペイン、重複排除を実行するエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-189">In the **Merge preferences** pane, choose the entities you want to run deduplication on.</span></span>

1. <span data-ttu-id="fd8b7-190">重複レコードを結合する方法を指定し、次の 3 つのオプションのいずれかを選択します:</span><span class="sxs-lookup"><span data-stu-id="fd8b7-190">Specify how to combine the duplicate records and choose one of three options:</span></span>
   - <span data-ttu-id="fd8b7-191">**最も多く入力された**: 最も多くの属性フィールドが入力されたレコードを勝者レコードとして識別します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-191">**Most filled**: Identifies the record with most populated attribute fields as the winner record.</span></span> <span data-ttu-id="fd8b7-192">これは既定のマージ オプションです。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-192">It's the default merge option.</span></span>
   - <span data-ttu-id="fd8b7-193">**最も新しい**: 最新性に基づいて勝者レコードを識別します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-193">**Most recent**: Identifies the winner record based on the most recency.</span></span> <span data-ttu-id="fd8b7-194">最新性を定義するには、日付または数値フィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-194">Requires a date or a numeric field to define the recency.</span></span>
   - <span data-ttu-id="fd8b7-195">**最も古い**: 最も古いレコードに基づいて勝者レコードを識別します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-195">**Least recent**: Identifies the winner record based on the least recency.</span></span> <span data-ttu-id="fd8b7-196">最新性を定義するには、日付または数値フィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-196">Requires a date or a numeric field to define the recency.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd8b7-197">![重複排除ルール ステップ 1](media/match-selfconflation.png "重複排除ルール ステップ 1")</span><span class="sxs-lookup"><span data-stu-id="fd8b7-197">![Deduplication rules step 1](media/match-selfconflation.png "Deduplication rules step 1")</span></span>
 
1. <span data-ttu-id="fd8b7-198">エンティティを選択して、マージの基本設定を設定したら、**ルールの追加** を選択して、エンティティ レベルで重複排除ルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-198">Once the entities are selected and their merge preference is set, select **Add rule** to define the deduplication rules at an entity level.</span></span>
   - <span data-ttu-id="fd8b7-199">**フィールドを選択** は、そのエンティティから使用可能なすべてのフィールドを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-199">**Select field** lists all the available fields from that entity.</span></span> <span data-ttu-id="fd8b7-200">重複をチェックするフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-200">Choose the field you want to check for duplicates.</span></span> <span data-ttu-id="fd8b7-201">各顧客に固有である可能性が高いフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-201">Choose fields that are likely unique for every single customer.</span></span> <span data-ttu-id="fd8b7-202">たとえば、電子メール アドレス、または名前、都市、電話番号の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-202">For example, an email address, or the combination of name, city, and phone number.</span></span>
   - <span data-ttu-id="fd8b7-203">正規化と精度の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-203">Specify the normalization and precision settings.</span></span>
   - <span data-ttu-id="fd8b7-204">**条件の追加** を選択して、さらに条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-204">Define more conditions by selecting **Add condition**.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd8b7-205">![重複排除ルール ステップ 2](media/match-selfconflation-rules.png "重複排除ルール ステップ 2")</span><span class="sxs-lookup"><span data-stu-id="fd8b7-205">![Deduplication rules step 2](media/match-selfconflation-rules.png "Deduplication rules step 2")</span></span>

  <span data-ttu-id="fd8b7-206">エンティティに対して複数の重複排除ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-206">You can create multiple deduplication rules for an entity.</span></span> 

1. <span data-ttu-id="fd8b7-207">照合プロセスを実行すると、重複排除ルールで定義された条件に基づいてレコードがグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-207">Running the match process now groups the records based on the conditions defined in the deduplication rules.</span></span> <span data-ttu-id="fd8b7-208">レコードをグループ化した後、マージ ポリシーを適用して、勝者レコードを識別します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-208">After grouping the records, the merge policy is applied to identify the winner record.</span></span>

1. <span data-ttu-id="fd8b7-209">次にこの勝者レコードが、非勝者レコード (たとえば、代替 ID) とともに、エンティティ間の照合に渡され、一致の品質が向上します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-209">This winner record is then passed on to the cross-entity matching, along with the non-winner records (for example, alternate IDs) to improve the matching quality.</span></span>

1. <span data-ttu-id="fd8b7-210">定義されたカスタム照合ルールは、重複排除ルールを上書きします。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-210">Any custom match rules defined overwrite deduplication rules.</span></span> <span data-ttu-id="fd8b7-211">重複排除ルールが一致するレコードを識別し、カスタム照合ルールがそれらのレコードと照合しないように設定されている場合、これら 2 つのレコードの照合は行われません。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-211">If a deduplication rule identifies matching records, and a custom match rule is set to never match those records, then these two records won't be matched.</span></span>

1. <span data-ttu-id="fd8b7-212">[照合プロセスを実行](#run-the-match-process) すると、重複排除の統計が重要な指標タイルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-212">After [running the match process](#run-the-match-process), you will see the deduplication stats in the key metrics tiles.</span></span>

### <a name="deduplication-output-as-an-entity"></a><span data-ttu-id="fd8b7-213">エンティティとしての重複排除出力</span><span class="sxs-lookup"><span data-stu-id="fd8b7-213">Deduplication output as an entity</span></span>

<span data-ttu-id="fd8b7-214">重複排除プロセスでは、照合ペアからエンティティごとに新しいエンティティを作成して、重複排除されたレコードを識別します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-214">The deduplication process creates a new entity for every entity from the match pairs to identify the deduplicated records.</span></span> <span data-ttu-id="fd8b7-215">これらのエンティティは、**エンティティ** ページの **システム** セクションに **ConflationMatchPairs:CustomerInsights** とともに、**Deduplication_DataSource_Entity** という名前で表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-215">These entities can be found along with the **ConflationMatchPairs:CustomerInsights** in the **System** section in the **Entities** page, with the name **Deduplication_DataSource_Entity**.</span></span>

<span data-ttu-id="fd8b7-216">重複排除出力エンティティには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-216">A deduplication output entity contains the following information:</span></span>
- <span data-ttu-id="fd8b7-217">ID/キー</span><span class="sxs-lookup"><span data-stu-id="fd8b7-217">IDs / Keys</span></span>
  - <span data-ttu-id="fd8b7-218">主キーフィールドとその代替 ID フィールド。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-218">Primary key field and its alternate IDs field.</span></span> <span data-ttu-id="fd8b7-219">代替 ID フィールドは、レコードに対して識別されたすべての代替 ID で構成されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-219">Alternate IDs field consists of all the alternate IDs identified for a record.</span></span>
  - <span data-ttu-id="fd8b7-220">Deduplication_GroupId フィールドには、指定された重複排除フィールドに基づいてすべての類似レコードをグループ化するエンティティ内で識別されたグループまたはクラスターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-220">Deduplication_GroupId field shows the group or cluster identified within an entity that groups all the similar records based on the specified deduplication fields.</span></span> <span data-ttu-id="fd8b7-221">これは、システム処理の目的で使用されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-221">It's used for system processing purposes.</span></span> <span data-ttu-id="fd8b7-222">手動の重複排除ルールが指定されておらず、システム定義の重複排除ルールが適用されている場合、このフィールドが重複排除出力エンティティに表示されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-222">If there are no manual deduplication rules specified and system defined deduplication rules apply, you may not find this field in the deduplication output entity.</span></span>
  - <span data-ttu-id="fd8b7-223">Deduplication_WinnerId: このフィールドには、識別されたグループまたはクラスターからの勝者 ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-223">Deduplication_WinnerId: This field contains the winner ID from the identified groups or clusters.</span></span> <span data-ttu-id="fd8b7-224">Deduplication_WinnerId がレコードの主キー値と同じである場合、そのレコードが勝者レコードであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-224">If the Deduplication_WinnerId is same as the Primary key value for a record, it means that the record is the winner record.</span></span>
- <span data-ttu-id="fd8b7-225">重複排除ルールを定義するために使用されるフィールド。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-225">Fields used to define the deduplication rules.</span></span>
- <span data-ttu-id="fd8b7-226">[ルール] フィールドと [スコア] フィールドは、どの重複排除ルールが適用され、照合アルゴリズムによってスコアが返されことを示します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-226">Rule and Score fields to denote which of the deduplication rules got applied and the score returned by the matching algorithm.</span></span>
   
## <a name="run-the-match-process"></a><span data-ttu-id="fd8b7-227">照合プロセスを実行する</span><span class="sxs-lookup"><span data-stu-id="fd8b7-227">Run the match process</span></span>

<span data-ttu-id="fd8b7-228">エンティティ間の照合ルールや重複排除ルールなど、構成された照合ルールを使用して、照合プロセスを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-228">With configured match rules, including cross-entity matching and deduplication rules, you can run the match process.</span></span> 

<span data-ttu-id="fd8b7-229">**データ** > **統合** > **照合** に移動し、**実行** を選択して、プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-229">Go to **Data** > **Unify** > **Match** and select **Run** to start the process.</span></span> <span data-ttu-id="fd8b7-230">照合アルゴリズムは完了するまでに時間がかかり、完了するまで構成を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-230">The matching algorithm takes some time to complete and you can't change the configuration until it completes.</span></span> <span data-ttu-id="fd8b7-231">変更するには、実行をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-231">To make changes, you can cancel the run.</span></span> <span data-ttu-id="fd8b7-232">ジョブの状態を選択し、**ジョブの取り消し** を **プロセス詳細** ペインで選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-232">Select the status of the job and select **Cancel job** on the **Progress details** pane.</span></span>

<span data-ttu-id="fd8b7-233">成功した実行結果である、統合した顧客プロファイル エンティティは、**エンティティ** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-233">You'll find the result of a successful run, the unified customer profile entity, on the **Entities** page.</span></span> <span data-ttu-id="fd8b7-234">統合された顧客エンティティは、**プロファイル** セクションで **顧客** と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-234">Your unified customer entity is called **Customers** in the **Profiles** section.</span></span> <span data-ttu-id="fd8b7-235">最初に成功した照合の実行は、統合 *Customer* エンティティを作成します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-235">The first successful match run creates the unified *Customer* entity.</span></span> <span data-ttu-id="fd8b7-236">後続のすべての照合実行では、そのエンティティが展開されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-236">All subsequent match runs expand that entity.</span></span>

> [!TIP]
> <span data-ttu-id="fd8b7-237">タスク/プロセスには、[6 種類の状態](system.md#status-types) があります。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-237">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="fd8b7-238">さらに、ほとんどのプロセスは、[その他の下流プロセスに依存します](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-238">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="fd8b7-239">プロセスのステータスを選択して、ジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-239">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="fd8b7-240">ジョブのタスクの 1 つについて **詳細の表示** を選択すると、処理時間、最終処理日、およびタスクに関連するすべてのエラーと警告などの追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-240">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="review-and-validate-your-matches"></a><span data-ttu-id="fd8b7-241">一致のレビューと検証</span><span class="sxs-lookup"><span data-stu-id="fd8b7-241">Review and validate your matches</span></span>

<span data-ttu-id="fd8b7-242">**データ** > **統合** > **照合** に移動し、照合ペアの品質を評価し、必要に応じて改善します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-242">Go to **Data** > **Unify** > **Match** to evaluate the quality of your match pairs and refine them if necessary.</span></span>

<span data-ttu-id="fd8b7-243">ページ上部のタイルには、一致したレコードと重複レコードの数を集計した重要な指標が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-243">The tiles on top of the page show key metrics, summarizing the number of matched records and duplicates.</span></span>

:::image type="content" source="media/match-KPIs.png" alt-text="数値と詳細が示された照合ページ上の重要な指標のトリミングされたスクリーンショット。":::

- <span data-ttu-id="fd8b7-245">**一意のソース レコード** は、前回の照合実行で処理された個々のソース レコードの数を示します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-245">**Unique source records** shows the number of individual source records that were processed in last match run.</span></span>
- <span data-ttu-id="fd8b7-246">**一致するレコードと一致しないレコード** は、照合ルールの処理後に残っている一意のレコードの数を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-246">**Matched and non-matched records** highlights how many unique records remain after processing the match rules.</span></span>
- <span data-ttu-id="fd8b7-247">**一致するレコードのみ** は、すべての照合ペアの一致数を示します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-247">**Matched records only** shows the number of matches across all of your match pairs.</span></span>

<span data-ttu-id="fd8b7-248">**一致したレコードの詳細** テーブルで、各照合ペアの結果とそのルールを評価できます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-248">You can assess the results of each match pair and its rules in the **Matched records details** table.</span></span> <span data-ttu-id="fd8b7-249">照合ペアから取得したレコード数と、一致に成功したレコードの割合を比較します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-249">Compare the number of records that came from a match pair against the percentage of successfully matched records.</span></span>

<span data-ttu-id="fd8b7-250">照合ペアのルールを確認して、ルール レベルで一致に成功したレコードの割合を確認します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-250">Review the rules of a match pair to see the percentage of successfully matched records at the rule level.</span></span> <span data-ttu-id="fd8b7-251">省略記号 (...) を選択してから、**一致プレビュー** を選択し、これらすべてのレコードをルール レベルで表示します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-251">Select the ellipsis (...) and then select **Match preview** to view all these records on the rule level.</span></span> <span data-ttu-id="fd8b7-252">いくつかのレコードを調べて、それらが正しく一致していることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-252">We recommend that you take a look at some records to validate that they were matched correctly.</span></span>

<span data-ttu-id="fd8b7-253">条件でさまざまな精度のしきい値を試して、最適な値を見つけてください。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-253">Try different precision thresholds on conditions to find the optimal value.</span></span>

  1. <span data-ttu-id="fd8b7-254">試行するルールの省略記号 (...) を選択し、**編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-254">Select the ellipsis (...) for the rule that you want to experiment with and select **Edit**.</span></span>

  2. <span data-ttu-id="fd8b7-255">修正する条件の精度の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-255">Change the precisions values in the conditions you want to revise.</span></span>

  3. <span data-ttu-id="fd8b7-256">**プレビュー** を選択し、選択した条件に対して一致するレコードと一致しないレコードの数を表示します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-256">Select **Preview** so see the number of matched and unmatched records for the selected condition.</span></span>

## <a name="manage-match-rules"></a><span data-ttu-id="fd8b7-257">照合ルールの管理</span><span class="sxs-lookup"><span data-stu-id="fd8b7-257">Manage match rules</span></span>

<span data-ttu-id="fd8b7-258">ほとんどの照合パラメーターを再構成および微調整できます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-258">You can reconfigure and fine-tune most of the match parameters.</span></span>

:::image type="content" source="media/match-rules-management.png" alt-text="照合ルール オプションを含むドロップダウン メニューのスクリーンショット。":::

- <span data-ttu-id="fd8b7-260">複数のルールを定義した場合、**ルールの順序を変更** します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-260">**Change the order of your rules** if you defined multiple rules.</span></span> <span data-ttu-id="fd8b7-261">**上に移動** と **下に移動** オプションを選択するか、ドラッグ アンド ドロップで照合ルールを並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-261">You can reorder the match rules by selecting the **Move Up** and **Move Down** options or by drag and drop.</span></span>

- <span data-ttu-id="fd8b7-262">**編集** を選択して **ルール条件を変更** し、別のフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-262">**Change rule conditions** by selecting **Edit** and choose different fields.</span></span>

- <span data-ttu-id="fd8b7-263">**ルールを非アクティブ化する** は、照合ルールを保持しながら、照合プロセスから除外します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-263">**Deactivate a rule** to retain a match rule while excluding it from the matching process.</span></span>

- <span data-ttu-id="fd8b7-264">照合ルールを定義後、変更を加えて同様のルールを作成する場合は、**ルールを複製** して、**複製** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-264">**Duplicate your rules** if you've defined a match rule and would like to create a similar rule with modifications, select **Duplicate**.</span></span>

- <span data-ttu-id="fd8b7-265">**ルールを削除** するには、**削除** シンボルを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-265">**Delete a rule** by selecting the **Delete** symbol.</span></span>

## <a name="specify-custom-match-conditions"></a><span data-ttu-id="fd8b7-266">カスタム照合条件の指定</span><span class="sxs-lookup"><span data-stu-id="fd8b7-266">Specify custom match conditions</span></span>

<span data-ttu-id="fd8b7-267">特定のレコードが常に照合する、または全く照合すべき条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-267">You can specify conditions that certain records should always match or never match.</span></span> <span data-ttu-id="fd8b7-268">これらのルールをアップロードして、標準の照合プロセスを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-268">These rules can be uploaded to override the standard match process.</span></span> <span data-ttu-id="fd8b7-269">たとえば、レコードに John Doe I と John Doe II がある場合、システムはそれらを 1 人の人物として照合する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-269">For example, if there are John Doe I and John Doe II in our records, the system might match them as one person.</span></span> <span data-ttu-id="fd8b7-270">カスタム照合ルールでは、プロファイルが別の人を参照するように指定できます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-270">Custom match rules let you specify that their profiles refer to different people.</span></span> 

1. <span data-ttu-id="fd8b7-271">**データ** > **統合** > **照合** に移動し、**カスタム照合** を **一致したレコードの詳細** セクションで選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-271">Go to **Data** > **Unify** > **Match** and select **Custom match** in the **Matched records details** section.</span></span>

  :::image type="content" source="media/custom-match-create.png" alt-text="カスタム照合コントロールが強調表示された照合ルール セクションのスクリーンショット。":::

1. <span data-ttu-id="fd8b7-273">カスタム照合ルールが設定されていない場合は、詳細を含む新しい **カスタム照合** ペインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-273">If you have no custom match rules set, you'll see a new **Custom match** pane with more details.</span></span>

1. <span data-ttu-id="fd8b7-274">**テンプレートに記入する** を選択して、どのエンティティのどのレコードが常に一致するか、または一致しないかを指定できるテンプレート ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-274">Select **Fill in the template** to get a template file that can specify which records from which entities should always match or never match.</span></span> <span data-ttu-id="fd8b7-275">2 つの異なるファイルの「常に一致する」レコードと「全く一致しない」レコードを別々に入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-275">You'll need to separately fill in the "always match" records and "never match" records in two different files.</span></span>

1. <span data-ttu-id="fd8b7-276">テンプレートには、カスタム一致で使用されるエンティティとエンティティの主キーの値を指定するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-276">The template contains fields to specify the entity and the entity primary key values to be used in the custom match.</span></span> <span data-ttu-id="fd8b7-277">たとえば、*Sales* エンティティの主キー *12345* を *Contact* エンティティの主キー *34567* と常に一致させる場合は、テンプレートに次のように入力します:</span><span class="sxs-lookup"><span data-stu-id="fd8b7-277">For example, if you want primary key *12345* from *Sales* entity to always match with primary key *34567* from *Contact* entity, fill in the template:</span></span>
    - <span data-ttu-id="fd8b7-278">Entity1: Sales</span><span class="sxs-lookup"><span data-stu-id="fd8b7-278">Entity1: Sales</span></span>
    - <span data-ttu-id="fd8b7-279">Entity1Key: 12345</span><span class="sxs-lookup"><span data-stu-id="fd8b7-279">Entity1Key: 12345</span></span>
    - <span data-ttu-id="fd8b7-280">Entity2: Contact</span><span class="sxs-lookup"><span data-stu-id="fd8b7-280">Entity2: Contact</span></span>
    - <span data-ttu-id="fd8b7-281">Entity2Key: 34567</span><span class="sxs-lookup"><span data-stu-id="fd8b7-281">Entity2Key: 34567</span></span>

   <span data-ttu-id="fd8b7-282">同じテンプレート ファイルで、複数のエンティティからカスタム一致レコードを指定できます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-282">The same template file can specify custom match records from multiple entities.</span></span>
   
   <span data-ttu-id="fd8b7-283">エンティティの重複排除にカスタム照合を指定する場合は、Entity1 とEntity2 の両方と同じエンティティを指定し、異なる主キー値を設定します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-283">If you want to specify custom matching for deduplication on an entity, provide the same entity as both Entity1 and Entity2 and set the different primary key values.</span></span>

1. <span data-ttu-id="fd8b7-284">適用するすべてのオーバーライドを追加したら、テンプレート ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-284">After adding all the overrides you want to apply, save the template file.</span></span>

1. <span data-ttu-id="fd8b7-285">**データ** > **データ ソース** に移動し、テンプレート ファイルを新しいエンティティとして取り込みます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-285">Go to **Data** > **Data sources** and ingest the template files as new entities.</span></span> <span data-ttu-id="fd8b7-286">取り込んだ後、それらを使用して一致構成を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-286">Once ingested, you can use them to specify the Match configuration.</span></span>

1. <span data-ttu-id="fd8b7-287">ファイルをアップロードした後、エンティティが利用可能になったら、**カスタム一致** オプションをもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-287">After uploading the files and entities are available, select the **Custom match** option again.</span></span> <span data-ttu-id="fd8b7-288">含めるエンティティを指定するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-288">You'll see options to specify the entities you want to include.</span></span> <span data-ttu-id="fd8b7-289">ドロップダウン メニューから必要なエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-289">Select the required entities from the drop-down menu.</span></span>

   :::image type="content" source="media/custom-match-overrides.png" alt-text="カスタム照合シナリオに対する上書きを選択するダイアログのスクリーンショット。":::

1. <span data-ttu-id="fd8b7-291">**常に一致** と **一致しない** に使用するエンティティを選択して、**完了** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-291">Select the entities you want to use for **Always match** and **Never match**, select **Done**.</span></span>

1. <span data-ttu-id="fd8b7-292">**照合** ページで **保存** を選択し、カスタム照合構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-292">Select **Save** on the **Match** page to apply the custom match configuration.</span></span>

1. <span data-ttu-id="fd8b7-293">**照合** ページで **実行** を選択し、照合プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-293">Select **Run** on the **Match** page to start the matching process.</span></span> <span data-ttu-id="fd8b7-294">他の指定された照合ルールは、カスタム照合構成によって上書きされます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-294">Other specified match rules are overridden by the custom match configuration.</span></span>

> [!TIP]
> <span data-ttu-id="fd8b7-295">**データ** > **エンティティ** に移動し、**ConflationMatchPair** エンティティを確認して、上書きが適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-295">Go to **Data** > **Entities** and review the **ConflationMatchPair** entity to confirm that the overrides are applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="fd8b7-296">次のステップ</span><span class="sxs-lookup"><span data-stu-id="fd8b7-296">Next step</span></span>

<span data-ttu-id="fd8b7-297">1 つ以上の一致ペアの一致プロセスを完了した後、データの矛盾の可能性がある場合は [**マージ**](merge-entities.md) トピックを読んで解決することができます。</span><span class="sxs-lookup"><span data-stu-id="fd8b7-297">After completing the match process for at least one match pair, you may resolve possible contradictions in your data by going through the [**Merge**](merge-entities.md) topic.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
