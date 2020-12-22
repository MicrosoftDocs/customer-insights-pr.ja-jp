---
title: データ統合のためにエンティティを照合する
description: データを照合して、統合顧客プロファイルを作成します。
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406190"
---
# <a name="match-entities"></a><span data-ttu-id="0cad4-103">エンティティを一致させる</span><span class="sxs-lookup"><span data-stu-id="0cad4-103">Match entities</span></span>

<span data-ttu-id="0cad4-104">一致フェーズが完了すると、エンティティを一致させる準備が整います。</span><span class="sxs-lookup"><span data-stu-id="0cad4-104">After completing the map phase, you're ready to match your entities.</span></span> <span data-ttu-id="0cad4-105">一致フェーズでは、データセットを統合して顧客プロファイルデータセットを統合する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-105">The match phase specifies how to combine your datasets into a unified customer profile dataset.</span></span> <span data-ttu-id="0cad4-106">一致フェーズには少なくとも [2 つのマッピングされたエンティティ](map-entities.md) が必要です。</span><span class="sxs-lookup"><span data-stu-id="0cad4-106">The match phase requires at least [two mapped entities](map-entities.md).</span></span>

## <a name="specify-the-match-order"></a><span data-ttu-id="0cad4-107">一致順を指定します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-107">Specify the match order</span></span>

<span data-ttu-id="0cad4-108">**統合** > **一致** へ移動して、**順序を設定** を選択して一致フェーズを開始します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-108">Go to **Unify** > **Match** and select **Set order** to start the match phase.</span></span>

<span data-ttu-id="0cad4-109">各一致により、2 つ以上のエンティティが単一のエンティティに統合され、一意の顧客レコードがそれぞれ保持されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-109">Each match unifies two or more entities into a single entity, while persisting each unique customer record.</span></span> <span data-ttu-id="0cad4-110">次の例では、3 つの例を選択しました : **ContactCSV: TestData** を **主** エンティティとして、**WebAccountCSV: TestData** を **エンティティ 2** として、そして **CallRecordSmall: TestData** を **エンティティ 3** としてです。</span><span class="sxs-lookup"><span data-stu-id="0cad4-110">In the following example, we selected three entities: **ContactCSV: TestData** as the **Primary** entity, **WebAccountCSV: TestData** as **Entity 2**, and **CallRecordSmall: TestData** as **Entity 3**.</span></span> <span data-ttu-id="0cad4-111">上の図では、選択は一致順序がどのように実行されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="0cad4-111">The diagram above the selections illustrates how the match order will be executed.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0cad4-112">![データの一致順序を編集する](media/configure-data-match-order-edit-page.png "データの一致順序を編集する")</span><span class="sxs-lookup"><span data-stu-id="0cad4-112">![Edit the data match order](media/configure-data-match-order-edit-page.png "Edit the data match order")</span></span>
  
<span data-ttu-id="0cad4-113">**主** エンティティが、**エンティティ 2** と一致する。</span><span class="sxs-lookup"><span data-stu-id="0cad4-113">The **Primary** entity is matched with **Entity 2**.</span></span> <span data-ttu-id="0cad4-114">最初の一致からの結果となるデータセットは **エンティティ 3** です。</span><span class="sxs-lookup"><span data-stu-id="0cad4-114">The dataset that results from the first match is matched with **Entity 3**.</span></span>
<span data-ttu-id="0cad4-115">この例では、2 つの一致のみを選択しましたが、システムはさらに多くの一致をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-115">In this example, we only selected two matches, but the system can support more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0cad4-116">**主** エンティティとして選択したエンティティは、統合マスター データセットの基盤として機能します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-116">The entity that you choose as your **Primary** entity will serve as the basis for your unified master dataset.</span></span> <span data-ttu-id="0cad4-117">一致フェーズで選択された追加のエンティティは、このエンティティに追加されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-117">Additional entities that are selected during the match phase will be added to this entity.</span></span> <span data-ttu-id="0cad4-118">同時に、これは統合されたエンティティがこのエンティティに含まれるデータの *すべて* が含まれることは意味しません。</span><span class="sxs-lookup"><span data-stu-id="0cad4-118">At the same time, this doesn't mean that the unified entity will include *all* of the data included in this entity.</span></span>
>
> <span data-ttu-id="0cad4-119">エンティティの階層を選択する際に役立つ 2 つの考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="0cad4-119">There are two considerations that can help you choose the hierarchy of your entities:</span></span>
>
> - <span data-ttu-id="0cad4-120">顧客に関する最も完全で信頼性の高いデータを持つことを検討しているエンティティは何ですか？</span><span class="sxs-lookup"><span data-stu-id="0cad4-120">What entity do you consider having the most complete and reliable data about your customers?</span></span>
> - <span data-ttu-id="0cad4-121">今特定したエンティティには、その他のエンティティ (名前、電話番号、メールアドレスなど) でも共有される属性がありますか？</span><span class="sxs-lookup"><span data-stu-id="0cad4-121">Does the entity that you just identified have attributes that are also shared by other entities (for example, name, phone number, or email address)?</span></span> <span data-ttu-id="0cad4-122">そうでない場合は、2 番目に信頼性の高いエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-122">If not, choose your second most reliable entity.</span></span>

<span data-ttu-id="0cad4-123">**完了** を選択して、一致順を保存します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-123">Select **Done** to save your match order.</span></span>

## <a name="define-rules-for-your-first-match-pair"></a><span data-ttu-id="0cad4-124">最初の一致ペアのルールを定義する</span><span class="sxs-lookup"><span data-stu-id="0cad4-124">Define rules for your first match pair</span></span>

<span data-ttu-id="0cad4-125">一致順序を指定した後、**一致** ページで定義された一致が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-125">After specifying the match order, you'll see the defined matches on the **Match** page.</span></span> <span data-ttu-id="0cad4-126">画面上部のタイルには、一致順序を実行するまで空欄です。</span><span class="sxs-lookup"><span data-stu-id="0cad4-126">The tiles at the top of the screen will be empty until you run your match order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0cad4-127">![ルールを定義する](media/configure-data-match-need-rules.png "ルールを定義する")</span><span class="sxs-lookup"><span data-stu-id="0cad4-127">![Define rules](media/configure-data-match-need-rules.png "Define rules")</span></span>

<span data-ttu-id="0cad4-128">**ルールが必要** 警告は、一致ペアに対して一致ルールが定義されていないことを示唆しています。</span><span class="sxs-lookup"><span data-stu-id="0cad4-128">The **Needs Rules** warning suggests that no match rule is defined for a match pair.</span></span> <span data-ttu-id="0cad4-129">一致ルールは、エンティティの特定のペアが一致するロジックを指定します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-129">Match rules specify the logic by which a specific pair of entities will be matched.</span></span>

1. <span data-ttu-id="0cad4-130">最初のルールを定義するには、一致テーブル (1) で対応する一致行を選択することで **ルール定義** ウィンドウを開いてから、**新しいルールを作成** (2) を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-130">To define your first rule, open the **Rule Definition** pane by selecting the corresponding match row in the matches table (1) and then selecting **Create new rule** (2).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0cad4-131">![新規ルールの作成](media/configure-data-match-new-rule2.png "新規ルールの作成")</span><span class="sxs-lookup"><span data-stu-id="0cad4-131">![Create new rule](media/configure-data-match-new-rule2.png "Create new rule")</span></span>

2. <span data-ttu-id="0cad4-132">**ルールを編集** ウィンドウで、そのルールの条件を構成します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-132">In the **Edit Rule** pane, configure the conditions for that rule.</span></span> <span data-ttu-id="0cad4-133">各条件は、必須の選択を含む 2 つの行で表されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-133">Each condition is represented by two rows that include mandatory selections.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0cad4-134">![新規ルール ウィンドウ](media/configure-data-match-new-rule-condition.png "新規ルール ウィンドウ")</span><span class="sxs-lookup"><span data-stu-id="0cad4-134">![New rule pane](media/configure-data-match-new-rule-condition.png "New rule pane")</span></span>

   <span data-ttu-id="0cad4-135">エンティティ/フィールド (最初) - 最初の一致ペア エンティティからの一致に使用される属性。</span><span class="sxs-lookup"><span data-stu-id="0cad4-135">Entity/Field (first) - An attribute that will be used for matching from the first match pair entity.</span></span> <span data-ttu-id="0cad4-136">例には、電話番号またはメールアドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-136">Examples could include a phone number or email address.</span></span> <span data-ttu-id="0cad4-137">顧客に固有である可能性が高い属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-137">Choose an attribute that is likely to be unique to the customer.</span></span>

   > [!TIP]
   > <span data-ttu-id="0cad4-138">活動の種類の属性に基づいた一致は避けます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-138">Avoid matching on the basis of activity-type attributes.</span></span> <span data-ttu-id="0cad4-139">言い換えれば、属性が活動であると思われる場合、一致基準としては不十分な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0cad4-139">In other words, if an attribute seems to be an activity, then it might be a poor criteria to match by.</span></span>  

   <span data-ttu-id="0cad4-140">エンティティ/フィールド (2 番目) - 2 番目の一致ペア エンティティからの一致に使用される属性。</span><span class="sxs-lookup"><span data-stu-id="0cad4-140">Entity/Field (Second) - An attribute that will be used for matching from the second match pair entity.</span></span>

   <span data-ttu-id="0cad4-141">正規化 - **正規化の方法** : 選択した属性に対してさまざまな正規化オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0cad4-141">Normalize - **Normalization method**: Various normalization options are available for the selected attributes.</span></span> <span data-ttu-id="0cad4-142">たとえば、句読点の削除またはスペースの削除</span><span class="sxs-lookup"><span data-stu-id="0cad4-142">For example, removing punctuation or removing spaces</span></span>

   <span data-ttu-id="0cad4-143">組織名の正規化 (プレビュー) では、**種類 (電話、名前、組織)** を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-143">For Organization name normalization (Preview), you can also select **Type (Phone, Name, Organization)**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0cad4-144">![正規化-B2B](media/match-normalization-b2b.png "正規化-B2B")</span><span class="sxs-lookup"><span data-stu-id="0cad4-144">![Normalization-B2B](media/match-normalization-b2b.png "Normalization-B2B")</span></span>

   <span data-ttu-id="0cad4-145">精度レベル - この条件に使用される精度のレベル。</span><span class="sxs-lookup"><span data-stu-id="0cad4-145">Precision level - The level of precision that will be used for this condition.</span></span> <span data-ttu-id="0cad4-146">一致条件の精度レベルの設定には、**ベーシック** そして **カスタム** の 2 つのタイプがあります。</span><span class="sxs-lookup"><span data-stu-id="0cad4-146">Setting a precision level for a match condition can have two types: **Basic** and **Custom**.</span></span>  
   - <span data-ttu-id="0cad4-147">基本 : 低、中、高、および完全から選択する 4 つのオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-147">Basic: Provides you with four options to select from: Low, Medium, High, and Exact.</span></span> <span data-ttu-id="0cad4-148">**完全** を選択して、100％ に一致するレコードのみを一致させます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-148">Select **Exact** to only match records that that match 100 percent.</span></span> <span data-ttu-id="0cad4-149">その他のレベルの 1 つを選択して、100％ 同一ではないレコードに一致させます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-149">Select one of the other levels to match records that aren't 100 percent identical.</span></span>
   - <span data-ttu-id="0cad4-150">カスタム : スライダーを使用して、レコードが一致する必要があるカスタムパーセンテージを定義するか、**カスタム** フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-150">Custom: Use the slider to define the custom percentage that records need to match or enter a value in the **Custom** field.</span></span> <span data-ttu-id="0cad4-151">システムは、このしきい値を通過したレコードのみを照合一致ペアとして照合します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-151">The system will only match records passing this threshold as conflated match pairs.</span></span> <span data-ttu-id="0cad4-152">スライダーの値は 0 から 1 の間になります。</span><span class="sxs-lookup"><span data-stu-id="0cad4-152">Values on the slider are between 0 and 1.</span></span> <span data-ttu-id="0cad4-153">0.64 は 64％ を表します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-153">So 0.64 represents 64 percent.</span></span>

3. <span data-ttu-id="0cad4-154">**完了** を選択してルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-154">Select **Done** to save the rule.</span></span>

### <a name="add-multiple-conditions"></a><span data-ttu-id="0cad4-155">複数の条件を追加する</span><span class="sxs-lookup"><span data-stu-id="0cad4-155">Add multiple conditions</span></span>

<span data-ttu-id="0cad4-156">複数の条件が満たされた場合にのみエンティティを一致させるには、AND 演算子でリンクされている条件をさらに追加します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-156">To match your entities only if multiple conditions are met, add more conditions that are linked through an AND operator.</span></span>

1. <span data-ttu-id="0cad4-157">**ルールを編集** ウィンドウで、**条件を追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-157">In the **Edit rule** pane, select **Add condition**.</span></span> <span data-ttu-id="0cad4-158">既存の条件の横にある削除ボタンを選択して、条件を削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-158">You can also delete conditions by selecting the remove button next to an existing condition.</span></span>

2. <span data-ttu-id="0cad4-159">**完了** を選択して、ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-159">Select **Done** so save the rule.</span></span>

## <a name="add-multiple-rules"></a><span data-ttu-id="0cad4-160">複数のルールを追加する</span><span class="sxs-lookup"><span data-stu-id="0cad4-160">Add multiple rules</span></span>

<span data-ttu-id="0cad4-161">各条件は属性の単一のペアに適用されますが、ルールは条件のセットを表します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-161">Each condition applies to a single pair of attributes, while rules represent sets of conditions.</span></span> <span data-ttu-id="0cad4-162">エンティティをさまざまな属性セットに一致させるために、ルールを追加できます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-162">To have your entities matched by different sets of attributes, you can add more rules.</span></span>

1. <span data-ttu-id="0cad4-163">対象者に関するインサイトで、**データ** > **統合** > **照合** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-163">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

2. <span data-ttu-id="0cad4-164">更新するエンティティを選択し、**ルールを追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-164">Select the entity you want to update and select **Add rules**.</span></span>

3. <span data-ttu-id="0cad4-165">[最初の一致ペアのルールを定義する](#define-rules-for-your-first-match-pair) で概略された手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="0cad4-165">Follow the procedure as outlined in [Define rules for your first match pair](#define-rules-for-your-first-match-pair).</span></span>

> [!NOTE]
> <span data-ttu-id="0cad4-166">ルールの順序が重要です。</span><span class="sxs-lookup"><span data-stu-id="0cad4-166">The rule order matters.</span></span> <span data-ttu-id="0cad4-167">一致アルゴリズムは、最初のルールに基づいて一致を試み、最初のルールで一致が識別されなかった場合にのみ 2 番目のルールに進みます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-167">The matching algorithm tries to match on the basis of your first rule and continues to the second rule only if no matches were identified under the first rule.</span></span>

## <a name="define-deduplication-on-a-match-entity"></a><span data-ttu-id="0cad4-168">照合エンティティで重複排除を定義する</span><span class="sxs-lookup"><span data-stu-id="0cad4-168">Define deduplication on a match entity</span></span>

<span data-ttu-id="0cad4-169">上記のセクションで概説したように、エンティティ間の照合ルールを指定するだけでなく、重複排除ルールも指定できます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-169">Along with specifying cross entity matching rules as outlined in the above sections, you can also specify deduplications rules.</span></span> <span data-ttu-id="0cad4-170">*重複排除* はプロセスです。</span><span class="sxs-lookup"><span data-stu-id="0cad4-170">*Deduplication* is a process.</span></span> <span data-ttu-id="0cad4-171">重複するレコードを識別し、それらを 1 つのレコードにマージして、すべてのソース レコードをこのマージされたレコードに、マージされたレコードとは別の ID でリンクします。</span><span class="sxs-lookup"><span data-stu-id="0cad4-171">It identifies duplicate records, merges them into one record, and links all the source records to this merged record with alternate IDs to the merged record.</span></span>

<span data-ttu-id="0cad4-172">重複排除したレコードが識別された後、そのレコードはエンティティ間の照合プロセスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-172">After a deduplicated record is identified, that record will be used in the cross-entity matching process.</span></span> <span data-ttu-id="0cad4-173">重複排除はエンティティ レベルで実装され、照合プロセスで使用されるすべてのエンティティに適用できます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-173">Deduplication is implemented at the entity level and can be applied to every entity used in the Match process.</span></span>

### <a name="add-deduplication-rules"></a><span data-ttu-id="0cad4-174">重複排除ルールの追加</span><span class="sxs-lookup"><span data-stu-id="0cad4-174">Add deduplication rules</span></span>

1. <span data-ttu-id="0cad4-175">対象者に関するインサイトで、**データ** > **統合** > **照合** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-175">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

1. <span data-ttu-id="0cad4-176">**マージした重複** セクションで、**エンティティの設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-176">In the **Merged duplicates** section, select **Set entities**.</span></span>

1. <span data-ttu-id="0cad4-177">**基本設定をマージする** セクションで、重複排除を適用するエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-177">In the **Merge preferences** section, select the entities you want to apply deduplication to.</span></span>

1. <span data-ttu-id="0cad4-178">重複レコードをマージする方法を指定し、次の 3 つのマージ オプションのいずれかを選択します:</span><span class="sxs-lookup"><span data-stu-id="0cad4-178">Specify how to merge the duplicate records and choose one of three merge options:</span></span>
   - <span data-ttu-id="0cad4-179">*最も多く入力された*: 最も多く入力された属性を持つレコードを勝者レコードとして識別します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-179">*Most filled*: Identifies the record with most filled attributes as the winner record.</span></span> <span data-ttu-id="0cad4-180">これは既定のマージ オプションです。</span><span class="sxs-lookup"><span data-stu-id="0cad4-180">This is the default merge option.</span></span>
   - <span data-ttu-id="0cad4-181">*最も新しい*: 最新性に基づいて勝者レコードを識別します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-181">*Most recent*: Identifies the winner record based on the most recency.</span></span> <span data-ttu-id="0cad4-182">最新性を定義するには、日付または数値フィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="0cad4-182">Requires a date or a numeric field to define the recency.</span></span>
   - <span data-ttu-id="0cad4-183">*最も古い*: 最も古いレコードに基づいて勝者レコードを識別します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-183">*Least recent*: Identifies the winner record based on the least recency.</span></span> <span data-ttu-id="0cad4-184">最新性を定義するには、日付または数値フィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="0cad4-184">Requires a date or a numeric field to define the recency.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0cad4-185">![重複排除ルール ステップ 1](media/match-selfconflation.png "重複排除ルール ステップ 1")</span><span class="sxs-lookup"><span data-stu-id="0cad4-185">![Deduplication rules step 1](media/match-selfconflation.png "Deduplication rules step 1")</span></span>
 
1. <span data-ttu-id="0cad4-186">エンティティを選択して、マージの基本設定を設定したら、**新しいルールの作成** を選択して、エンティティ レベルで重複排除ルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-186">Once the entities are selected and their merge preference is set, select **Create new rule** to define the deduplication rules at an entity level.</span></span>
   - <span data-ttu-id="0cad4-187">**フィールドの選択** には、ソース データを重複排除するエンティティから使用可能なすべてのフィールドが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-187">**Select field** lists all the available fields from that entity you want to deduplicate source data on.</span></span>
   - <span data-ttu-id="0cad4-188">エンティティ間の照合で指定されたのと同様の方法で、正規化と精度の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-188">Specify the normalization and precision settings in similar way as specified in the cross entity matching.</span></span>
   - <span data-ttu-id="0cad4-189">**条件の追加** を選択して、追加の条件を定義できます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-189">You can define additional conditions by selecting **Add condition**.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0cad4-190">![重複排除ルール ステップ 2](media/match-selfconflation-rules.png "重複排除ルール ステップ 2")</span><span class="sxs-lookup"><span data-stu-id="0cad4-190">![Deduplication rules step 2](media/match-selfconflation-rules.png "Deduplication rules step 2")</span></span>

  <span data-ttu-id="0cad4-191">エンティティに対して複数の重複排除ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-191">You can create multiple deduplication rules for an entity.</span></span> 

1. <span data-ttu-id="0cad4-192">照合プロセスを実行すると、重複排除ルールで定義された条件に基づいてレコードがグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-192">Running the match process now groups the records based on the conditions defined in the deduplication rules.</span></span> <span data-ttu-id="0cad4-193">レコードをグループ化した後、マージ ポリシーを適用して、勝者レコードを識別します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-193">After grouping the records, the merge policy is applied to identify the winner record.</span></span>

1. <span data-ttu-id="0cad4-194">次に、この勝者レコードは、エンティティ間の照合に渡されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-194">This winner record is then passed on to the cross-entity matching.</span></span>

1. <span data-ttu-id="0cad4-195">「常に照合する」および「照合しない」に対して定義されたカスタム照合ルールは、重複排除ルールに優先します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-195">Any custom match rules defined for always match and never match overrule deduplication rules.</span></span> <span data-ttu-id="0cad4-196">重複排除ルールが一致するレコードを識別し、カスタム照合ルールがそれらのレコードと照合しないように設定されている場合、これら 2 つのレコードの照合は行われません。</span><span class="sxs-lookup"><span data-stu-id="0cad4-196">If a deduplication rule identifies matching records, and a custom match rule is set to never match those records, then these two records won't be matched.</span></span>

1. <span data-ttu-id="0cad4-197">照合プロセスを実行すると、重複排除の統計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-197">After running the match process, you will see the deduplication stats.</span></span>
   
> [!NOTE]
> <span data-ttu-id="0cad4-198">重複排除ルールの指定は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="0cad4-198">Specifying deduplication rules isn't mandatory.</span></span> <span data-ttu-id="0cad4-199">そのようなルールが構成されていない場合は、システム定義ルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-199">If no such rules are configured, the system-defined rules are applied.</span></span> <span data-ttu-id="0cad4-200">パフォーマンスとシステムの健全性を向上させるために、エンティティ データをエンティティ間の照合に渡す前に、主キーと照合ルールのフィールドの同じ値の組み合わせ (完全一致) を共有するすべてのレコードを 1 つのレコードにまとめます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-200">They collapse all records that share the same value combination (exact match) from primary key and the fields in the matching rules into a single record before passing the entity data to cross-entity matching for enhanced performance and system sanity.</span></span>

## <a name="run-your-match-order"></a><span data-ttu-id="0cad4-201">一致オーダーを実行する</span><span class="sxs-lookup"><span data-stu-id="0cad4-201">Run your match order</span></span>

<span data-ttu-id="0cad4-202">エンティティ間の照合や重複排除ルールなどの照合ルールを定義した後、照合順序を実行できます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-202">After defining the match rules, including cross-entity matching and deduplication rules, you can run the match order.</span></span> <span data-ttu-id="0cad4-203">**一致** ページで、**実行** を選択してこのプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-203">On the **Match** page, select **Run** to start the process.</span></span> <span data-ttu-id="0cad4-204">一致アルゴリズムは完了に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0cad4-204">The matching algorithm might take some time to complete.</span></span> <span data-ttu-id="0cad4-205">一致プロセスが完了するまで、**一致** ページでプロパティを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0cad4-205">You can't change properties on the **Match** page until the match process completes.</span></span> <span data-ttu-id="0cad4-206">**エンティティ** ページでで作成された統一された顧客プロファイルエンティティが見つかります。</span><span class="sxs-lookup"><span data-stu-id="0cad4-206">You'll find the unified customer profile entity that was created on the **Entities** page.</span></span> <span data-ttu-id="0cad4-207">統一された顧客エンティティは、**ConflationMatchPairs : CustomerInsights** と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-207">Your unified customer entity is called **ConflationMatchPairs:CustomerInsights**.</span></span>

<span data-ttu-id="0cad4-208">追加の変更を加えてステップを再実行するために、進行中の一致をキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-208">To make additional changes and rerun the step, you can cancel a match in progress.</span></span> <span data-ttu-id="0cad4-209">**更新中 ...** テキストを選択して、表示された横ウィンドウの下にある **ジョブをキャンセル** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-209">Select the **Refreshing ...** text and select **Cancel job** at the bottom of the side pane that appears.</span></span>

<span data-ttu-id="0cad4-210">一致プロセスが完了すると、**更新中 ...** テキストは、**完了** に代わり、ページのすべての機能を再び使用できます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-210">When the match process is complete, the **Refreshing ...** text will change to **Successful** and you can use all functionality of the page again.</span></span>

<span data-ttu-id="0cad4-211">最初の一致プロセスにより、統一されたマスター エンティティが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-211">The first match process results in the creation of a unified master entity.</span></span> <span data-ttu-id="0cad4-212">後続のすべての一致実行により、そのエンティティが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-212">All subsequent match runs result in the expansion of that entity.</span></span>

> [!TIP]
> <span data-ttu-id="0cad4-213">タスク/プロセスには、[6 種類の状態](system.md#status-types) があります。</span><span class="sxs-lookup"><span data-stu-id="0cad4-213">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="0cad4-214">さらに、ほとんどのプロセスは、[その他の下流プロセスに依存します](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="0cad4-214">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="0cad4-215">プロセスのステータスを選択して、ジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-215">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="0cad4-216">ジョブのタスクの 1 つについて **詳細の表示** を選択すると、処理時間、最終処理日、およびタスクに関連するすべてのエラーと警告などの追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-216">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="review-and-validate-your-matches"></a><span data-ttu-id="0cad4-217">一致のレビューと検証</span><span class="sxs-lookup"><span data-stu-id="0cad4-217">Review and validate your matches</span></span>

<span data-ttu-id="0cad4-218">一致ペアの品質を評価し、調整します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-218">Evaluate the quality of your match pairs and refine it:</span></span>

- <span data-ttu-id="0cad4-219">**一致** ページには、データに関する最初のインサイトを示す 2 つのタイルがあります。</span><span class="sxs-lookup"><span data-stu-id="0cad4-219">On the **Match** page, you'll find two tiles showing initial insights about your data.</span></span>

  - <span data-ttu-id="0cad4-220">**一意の顧客** : システムが識別した一意のプロファイルの数を示します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-220">**Unique customers**: shows the number of unique profiles that the system identified.</span></span>
  - <span data-ttu-id="0cad4-221">**一致したレコード** : すべての一致ペアにわたる一致の数を示します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-221">**Matched records**: shows the number of matches across all of your match pairs.</span></span>

- <span data-ttu-id="0cad4-222">**一致順** テーブルでは、この一致ペア エンティティからのレコードの数を、正常に一致したレコードの割合と比較することにより、各一致ペアの結果を評価できます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-222">In the **Match order** table, you can assess the results of each match pair by comparing the number of records that came from this match-pair entity against the percentage of successfully matched records.</span></span>

- <span data-ttu-id="0cad4-223">**一致順** テーブルのエンティティの **ルール** セクションで、一致順表では、ルールレベルで正常に一致したレコードの割合がわかります。</span><span class="sxs-lookup"><span data-stu-id="0cad4-223">In the **Rules** section of an entity in the **Match order** table, you'll find the percentage of successfully matched records at the rule level.</span></span> <span data-ttu-id="0cad4-224">ルールの横にあるテーブル シンボルを選択することで、ルール レベルでこれらすべてのレコードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-224">By selecting the table symbol next to a rule, you can view all these records on the rule level.</span></span> <span data-ttu-id="0cad4-225">レコードのサブセットをレビューして、それらが正しく一致したことを検証することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0cad4-225">We recommend that you review a subset of the records to validate that they were matched correctly.</span></span>

- <span data-ttu-id="0cad4-226">条件に応じてさまざまな精度のしきい値を試して、最適な値を特定します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-226">Experiment with different precision thresholds around your conditions to identify the optimal value.</span></span>

  1. <span data-ttu-id="0cad4-227">実験する一致ペア ルールの省略記号 (...) を選択し、**編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-227">Select the ellipsis (...) for the match pair rule that you want to experiment with and select **Edit**.</span></span>

  2. <span data-ttu-id="0cad4-228">実験する状況を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-228">Select the condition that you want to experiment with.</span></span> <span data-ttu-id="0cad4-229">各基準は、**一致ルール** ウィンドウの 1 つの行によって表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-229">Each criterion is represented by one row in the **Match rule** pane.</span></span>

  3. <span data-ttu-id="0cad4-230">**基準プレビュー** ページで表示されるものは、条件に選択した精度レベルに依存します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-230">What you'll see on the **Criteria preview** page depends on the precision level you've selected for a condition.</span></span> <span data-ttu-id="0cad4-231">選択した条件に一致するレコードと一致しないレコードの数を見つけます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-231">Find the number of matched and unmatched records for the selected condition.</span></span>

     <span data-ttu-id="0cad4-232">さまざまなしきい値レベルの影響を十分に理解してください。</span><span class="sxs-lookup"><span data-stu-id="0cad4-232">Get a rich understanding of the effects of different threshold levels.</span></span> <span data-ttu-id="0cad4-233">各しきい値レベルで一致するレコードの数を比較し、各オプションでレコードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-233">You can compare how many records will be matched under each of the threshold levels, and view the records under each option.</span></span> <span data-ttu-id="0cad4-234">各タイルを選択し、テーブル セクションのデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-234">Select each of the tiles and review the data in the table section.</span></span>

## <a name="optimize-your-matches"></a><span data-ttu-id="0cad4-235">一致を最適化する</span><span class="sxs-lookup"><span data-stu-id="0cad4-235">Optimize your matches</span></span>

<span data-ttu-id="0cad4-236">次のいくつかの一致パラメーターを再構成して、品質を向上させます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-236">Increase the quality by reconfiguring some of your match parameters:</span></span>

- <span data-ttu-id="0cad4-237">**編集** を選択して **一致順を変更** して、一致順フィールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-237">**Change the match order** by selecting **Edit** and change the match order fields.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="0cad4-238">![データの一致順を編集する](media/configure-data-match-order-edit.png "データの一致順を編集する")</span><span class="sxs-lookup"><span data-stu-id="0cad4-238">![Edit data match order](media/configure-data-match-order-edit.png "Edit data match order")</span></span>

- <span data-ttu-id="0cad4-239">複数のルールを定義した場合、**ルールの順序を変更** します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-239">**Change the order of your rules** if you defined multiple rules.</span></span> <span data-ttu-id="0cad4-240">一致ルール グリッドで、**上に移動** と **下に移動** オプションを選択して一致ルールの順序を変えます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-240">You can reorder the match rules by selecting the **Move Up** and **Move Down** options in the match rules grid.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="0cad4-241">![ルール順序の変更](media/configure-data-change-rule-order.png "ルール順序の変更")</span><span class="sxs-lookup"><span data-stu-id="0cad4-241">![Change rule order](media/configure-data-change-rule-order.png "Change rule order")</span></span>

- <span data-ttu-id="0cad4-242">一致ルールを定義していて、変更を加えて同様のルールを作成したい場合は、**ルールの複製** をします。</span><span class="sxs-lookup"><span data-stu-id="0cad4-242">**Duplicate your rules** if you've defined a match rule and would like to create a similar rule with modifications.</span></span> <span data-ttu-id="0cad4-243">これをおこなうには、**複製** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-243">Do so by selecting **Duplicate**.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="0cad4-244">![ルールの複製](media/configure-data-duplicate-rule.png "ルールの複製")</span><span class="sxs-lookup"><span data-stu-id="0cad4-244">![Duplicate a rule](media/configure-data-duplicate-rule.png "Duplicate a rule")</span></span>

- <span data-ttu-id="0cad4-245">**編集** シンボルを選択して **ルールを編集します**。</span><span class="sxs-lookup"><span data-stu-id="0cad4-245">**Edit your rules** by selecting the **Edit** symbol.</span></span> <span data-ttu-id="0cad4-246">以下の変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-246">You can apply the following changes:</span></span>

  - <span data-ttu-id="0cad4-247">条件の属性を変更する : 特定の条件行内の新しい属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-247">Change attributes for a condition: Select new attributes within the specific condition row.</span></span>
  - <span data-ttu-id="0cad4-248">条件のしきい値を変更する : 精度スライダーを調整します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-248">Change the threshold for a condition: Adjust the precision slider.</span></span>
  - <span data-ttu-id="0cad4-249">条件の正規化方法を変更する : 正規化方法を更新します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-249">Change the normalization method for a condition: Update the normalization method.</span></span>

## <a name="specify-your-custom-match-records"></a><span data-ttu-id="0cad4-250">カスタム一致レコードを指定する</span><span class="sxs-lookup"><span data-stu-id="0cad4-250">Specify your custom match records</span></span>

<span data-ttu-id="0cad4-251">特定のレコードが常に照合する、または全く照合すべき条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-251">You can specify conditions that certain records should always match or never match.</span></span> <span data-ttu-id="0cad4-252">これらのルールは、一致プロセスに一括でアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-252">These rules can be uploaded in bulk to the match process.</span></span>

1. <span data-ttu-id="0cad4-253">**一致順序** 画面で **カスタム一致** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-253">Select the **Custom match** option on the **Match order** screen.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0cad4-254">![カスタム一致を作成](media/custom-match-create.png "カスタム一致を作成")</span><span class="sxs-lookup"><span data-stu-id="0cad4-254">![Create a custom match](media/custom-match-create.png "Create a custom match")</span></span>

2. <span data-ttu-id="0cad4-255">アップロードされたエンティティがない場合は、一部の詳細に入力する必要がある新しい **カスタム一致** ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-255">If you have no uploaded entities, you'll see a new **Custom match** dialog box that requires you to fill in some details.</span></span> <span data-ttu-id="0cad4-256">これらの詳細を以前に提供した場合は、手順 8 に進みます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-256">If you've provided these details earlier, skip to step 8.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0cad4-257">![新しいカスタム一致ダイアログボックス](media/custom-match-new-dialog-box.png "新しいカスタム一致ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="0cad4-257">![New custom match dialog box](media/custom-match-new-dialog-box.png "New custom match dialog box")</span></span>

3. <span data-ttu-id="0cad4-258">**テンプレートに記入する** を選択して、どのエンティティのどのレコードが常に一致するか、または一致しないかを指定できるテンプレート ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-258">Select **Fill in the template** to get a template file that can specify which records from which entities should always match or never match.</span></span> <span data-ttu-id="0cad4-259">2 つの異なるファイルの「常に一致する」レコードと「全く一致しない」レコードを別々に入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cad4-259">You'll need to separately fill in the "always match" records and "never match" records in two different files.</span></span>

4. <span data-ttu-id="0cad4-260">テンプレートには、カスタム一致で使用されるエンティティとエンティティの主キーの値を指定するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0cad4-260">The template contains fields to specify the entity and the entity primary key values to be used in the custom match.</span></span> <span data-ttu-id="0cad4-261">たとえば、営業エンティティの主キー 12345 を取引先担当者エンティティの主キー 34567 と常に一致させる場合は、次のように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cad4-261">For example, if you want primary key 12345 from Sales entity to always match with primary key 34567 from Contact entity, you'll need to specify as follows:</span></span>
    - <span data-ttu-id="0cad4-262">Entity1: Sales</span><span class="sxs-lookup"><span data-stu-id="0cad4-262">Entity1: Sales</span></span>
    - <span data-ttu-id="0cad4-263">Entity1Key: 12345</span><span class="sxs-lookup"><span data-stu-id="0cad4-263">Entity1Key: 12345</span></span>
    - <span data-ttu-id="0cad4-264">Entity2: Contact</span><span class="sxs-lookup"><span data-stu-id="0cad4-264">Entity2: Contact</span></span>
    - <span data-ttu-id="0cad4-265">Entity2Key: 34567</span><span class="sxs-lookup"><span data-stu-id="0cad4-265">Entity2Key: 34567</span></span>

   <span data-ttu-id="0cad4-266">同じテンプレート ファイルで、複数のエンティティからカスタム一致レコードを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-266">The same template file can specify custom match records from multiple entities.</span></span>

5. <span data-ttu-id="0cad4-267">適用するすべてのオーバーライドを追加したら、テンプレート ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-267">After adding all the overrides you want to apply, save the template file.</span></span>

<span data-ttu-id="0cad4-268">6. **データ** > **データ ソース** に移動し、テンプレート ファイルを新しいエンティティとして取り込みます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-268">6.Go to **Data** > **Data sources** and ingest the template files as new entities.</span></span> <span data-ttu-id="0cad4-269">取り込んだ後、それらを使用して一致構成を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-269">Once ingested, you can use them to specify the Match configuration.</span></span>

7. <span data-ttu-id="0cad4-270">ファイルをアップロードした後、エンティティが利用可能になったら、**カスタム一致** オプションをもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-270">After uploading the files and entities are available, select the **Custom match** option again.</span></span> <span data-ttu-id="0cad4-271">含めるエンティティを指定するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-271">You'll see options to specify the entities you want to include.</span></span> <span data-ttu-id="0cad4-272">ドロップダウン メニューから必要なエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-272">Select the required entities from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0cad4-273">![カスタム一致がオーバーライドします](media/custom-match-overrides.png "カスタム一致がオーバーライドします")</span><span class="sxs-lookup"><span data-stu-id="0cad4-273">![Custom match overrides](media/custom-match-overrides.png "Custom match overrides")</span></span>

8. <span data-ttu-id="0cad4-274">**常に一致** と **一致しない** に使用するエンティティを選択して、**完了** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-274">Select the entities you want to use for **Always match** and **Never match**, select **Done**.</span></span>

9. <span data-ttu-id="0cad4-275">今設定したカスタム一致構成のために、**一致** ページで **保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cad4-275">Select **Save** on the **Match** page for the custom match configuration you just set up.</span></span>

10. <span data-ttu-id="0cad4-276">**一致** ページで **実行** を選択して、一致プロセスを開始し、カスタム一致設定が有効になります。</span><span class="sxs-lookup"><span data-stu-id="0cad4-276">Select **Run** on the **Match** page to start the matching process, and the custom match configuration will be taken into effect.</span></span> <span data-ttu-id="0cad4-277">システムに一致したルールは、構成セットによってオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-277">Any system matched rules are overridden by the configuration set.</span></span>

11. <span data-ttu-id="0cad4-278">一致が完了したら、**ConflationMatchPair** エンティティを確認して、オーバーライドが合成一致に適用されることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-278">Once the matching is complete, you can verify the **ConflationMatchPair** entity to confirm that the overrides are applied in the conflation matches.</span></span>

## <a name="next-step"></a><span data-ttu-id="0cad4-279">次の手順</span><span class="sxs-lookup"><span data-stu-id="0cad4-279">Next step</span></span>

<span data-ttu-id="0cad4-280">1 つ以上の一致ペアの一致プロセスを完了した後、データの矛盾の可能性がある場合は [**マージ**](merge-entities.md) トピックを読んで解決することができます。</span><span class="sxs-lookup"><span data-stu-id="0cad4-280">After completing the match process for at least one match pair, you may resolve possible contradictions in your data by going through the [**Merge**](merge-entities.md) topic.</span></span>
