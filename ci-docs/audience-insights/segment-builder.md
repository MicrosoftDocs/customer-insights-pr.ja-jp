---
title: セグメントを作成して管理する
description: 顧客のセグメントを作成して、さまざまな属性に基づいてグループ化します。
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064943"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="84d1a-103">セグメントを作成して管理する</span><span class="sxs-lookup"><span data-stu-id="84d1a-103">Create and manage segments</span></span>

<span data-ttu-id="84d1a-104">統合された顧客エンティティとその関連エンティティに対して複雑なフィルターを定義します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="84d1a-105">処理後の各セグメントには、エクスポートして操作できる顧客エンティティ レコードのセットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="84d1a-106">セグメントは、**セグメント** ページで管理されます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="84d1a-107">次の例は、セグメント化機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="84d1a-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="84d1a-108">過去 90 日間に 500 ドル以上の商品を注文した顧客 *と* エスカレートされた顧客サービス呼び出しに関与した顧客のセグメントを定義しました。</span><span class="sxs-lookup"><span data-stu-id="84d1a-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="顧客セグメントを指定する 2 つのグループを含むセグメント ビルダー UI のスクリーンショット。":::

## <a name="create-a-new-segment"></a><span data-ttu-id="84d1a-110">新しいセグメントの作成</span><span class="sxs-lookup"><span data-stu-id="84d1a-110">Create a new segment</span></span>

<span data-ttu-id="84d1a-111">新しいセグメントを作成するには、複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="84d1a-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="84d1a-112">このセクションでは、*空のセグメント* をゼロから作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="84d1a-113">既存のエンティティに基づいて *クイック セグメント* を作成したり、機械学習モデルを使用して *提案されたセグメント* を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="84d1a-114">詳細情報: [セグメントの概要](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="84d1a-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="84d1a-115">セグメントの作成中に、下書きを保存できます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="84d1a-116">非アクティブなセグメントとして保存され、有効な構成で終了するとアクティブ化することはできません。</span><span class="sxs-lookup"><span data-stu-id="84d1a-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="84d1a-117">**セグメント** ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="84d1a-118">**新規** > **空白のセグメント** を選択します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="84d1a-119">**新しいセグメント** ペインでセグメント タイプを選択します:</span><span class="sxs-lookup"><span data-stu-id="84d1a-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="84d1a-120">**動的セグメント** は、定期的なスケジュールで [更新](segments.md#refresh-segments) されます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="84d1a-121">**静的セグメント** は、作成時に 1 回実行されます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="84d1a-122">セグメントの **出力エンティティ名** を指定します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="84d1a-123">オプションで、表示名と、セグメントの識別に役立つ説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="84d1a-124">**次へ** を選択して、グループを定義する **セグメント ビルダー** ページに移ります。</span><span class="sxs-lookup"><span data-stu-id="84d1a-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="84d1a-125">グループは顧客のセットです。</span><span class="sxs-lookup"><span data-stu-id="84d1a-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="84d1a-126">セグメント出力に含める属性を含むエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="84d1a-127">セグメント化する属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="84d1a-128">この属性は、数値、文字列、日付、ブールの 4 つの値タイプのいずれかを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="84d1a-129">選択した属性の演算子と値を選択します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="84d1a-130">![カスタム グループ フィルタ―](media/customer-group-numbers.png "顧客グループ フィルタ―")</span><span class="sxs-lookup"><span data-stu-id="84d1a-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="84d1a-131">数</span><span class="sxs-lookup"><span data-stu-id="84d1a-131">Number</span></span> |<span data-ttu-id="84d1a-132">定義</span><span class="sxs-lookup"><span data-stu-id="84d1a-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="84d1a-133">1</span><span class="sxs-lookup"><span data-stu-id="84d1a-133">1</span></span>     |<span data-ttu-id="84d1a-134">Entity</span><span class="sxs-lookup"><span data-stu-id="84d1a-134">Entity</span></span>          |
   |<span data-ttu-id="84d1a-135">2</span><span class="sxs-lookup"><span data-stu-id="84d1a-135">2</span></span>     |<span data-ttu-id="84d1a-136">属性</span><span class="sxs-lookup"><span data-stu-id="84d1a-136">Attribute</span></span>          |
   |<span data-ttu-id="84d1a-137">3</span><span class="sxs-lookup"><span data-stu-id="84d1a-137">3</span></span>    |<span data-ttu-id="84d1a-138">演算子</span><span class="sxs-lookup"><span data-stu-id="84d1a-138">Operator</span></span>         |
   |<span data-ttu-id="84d1a-139">4</span><span class="sxs-lookup"><span data-stu-id="84d1a-139">4</span></span>    |<span data-ttu-id="84d1a-140">値</span><span class="sxs-lookup"><span data-stu-id="84d1a-140">Value</span></span>         |

   1. <span data-ttu-id="84d1a-141">グループに条件を追加するには、次の 2 つの論理演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="84d1a-142">**AND** 演算子 : セグメンテーション プロセスの一部として両方の条件が満たされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="84d1a-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="84d1a-143">このオプションは、異なるエンティティにわたって条件を定義するときに最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="84d1a-144">**OR** 演算子 : セグメンテーション プロセスの一部として、いずれかの条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="84d1a-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="84d1a-145">このオプションは、同じエンティティにわたって複数の条件を定義するときに最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="84d1a-146">![いずれかの条件が満たされる必要がある OR 演算子](media/segmentation-either-condition.png "いずれかの条件が満たされる必要がある OR 演算子")</span><span class="sxs-lookup"><span data-stu-id="84d1a-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="84d1a-147">現在、**AND** 演算子下で **OR** 演算子をネストすることが可能ですが、その逆はできません。</span><span class="sxs-lookup"><span data-stu-id="84d1a-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="84d1a-148">各グループは、顧客のセットと一致します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-148">Each group matches set of customers.</span></span> <span data-ttu-id="84d1a-149">グループを連結して、ビジネス案件に必要な顧客を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="84d1a-150">**グループを追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="84d1a-151">![顧客グループ追加グループ](media/customer-group-add-group.png "顧客グループ追加グループ")</span><span class="sxs-lookup"><span data-stu-id="84d1a-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="84d1a-152">集合演算子 (**結合**、**交差**、**例外**) のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="84d1a-153">![顧客グループ追加結合](media/customer-group-union.png "顧客グループ追加結合")</span><span class="sxs-lookup"><span data-stu-id="84d1a-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="84d1a-154">**結合** は 2 つのグループを結合します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="84d1a-155">**交差** は 2 つのグループが重複しています。</span><span class="sxs-lookup"><span data-stu-id="84d1a-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="84d1a-156">両方のグループに *共通である* データのみが、統合グループに保持されます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="84d1a-157">**例外** は 2 つのグループを結合します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-157">**Except** combines the two groups.</span></span> <span data-ttu-id="84d1a-158">グループ B のデータと *共通ではない* グループ A のデータのみが保持されます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="84d1a-159">エンティティが [リレーションシップ](relationships.md) を通して統合型顧客エンティティに接続されている場合、有効なセグメントを作成するには、関係パスを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84d1a-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="84d1a-160">ドロップダウンから **顧客 : CustomerInsights** のエンティティが選択できるまで、関係パスからエンティティを追加します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="84d1a-161">次に、ステップごとに **すべてのレコード** を選択します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="84d1a-162">![セグメント作成中の関係パス](media/segments-multiple-relationships.png "セグメント作成中の関係パス")</span><span class="sxs-lookup"><span data-stu-id="84d1a-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="84d1a-163">既定では、セグメントは、定義されたフィルターに一致する顧客プロファイルのすべての属性を含む出力エンティティーを生成します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="84d1a-164">セグメントが *Customer* エンティティ以外の他のエンティティに基づいている場合は、これらのエンティティから出力エンティティに属性を追加できます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="84d1a-165">**プロジェクトの属性** を選択して、出力エンティティに追加する属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="84d1a-166">例: セグメントは、*Customer* エンティティに関連する顧客活動データを含むエンティティに基づいています。</span><span class="sxs-lookup"><span data-stu-id="84d1a-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="84d1a-167">このセグメントでは、過去 60 日間にヘルプ デスクに連絡したすべての顧客を検索します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="84d1a-168">出力エンティティ内の一致するすべての顧客レコードに、通話時間と通話数を追加することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="84d1a-169">この情報は、頻繁に電話をする顧客にオンライン ヘルプ記事や FAQ への役立つリンクを記載した電子メールを送信するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="84d1a-170">予測した属性は、顧客エンティティと一対多の関連付けを持つエンティティに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="84d1a-171">たとえば、1 人の顧客が複数のサブスクリプションを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="84d1a-172">構築中のセグメント クエリのすべてのグループで使用されているエンティティからのみ属性を予測できます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="84d1a-173">予測した属性は、集合演算子の使用時に考慮されます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="84d1a-174">**保存** を選択してセグメントを保存します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="84d1a-175">すべての要件が検証されると、セグメントが保存および処理されます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="84d1a-176">それ以外の場合は、ドラフトとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="84d1a-177">**セグメントに戻る** を選択して、**セグメント** のページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="84d1a-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="84d1a-178">簡易セグメント</span><span class="sxs-lookup"><span data-stu-id="84d1a-178">Quick segments</span></span>

<span data-ttu-id="84d1a-179">クイック セグメントでは、1 つの演算子で簡単なセグメントをすばやく作成して、より迅速なインサイトを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="84d1a-180">**セグメント** ページで、**新規** > **作成元** を選択します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="84d1a-181">**プロファイル** オプションを選択して、*統合された顧客* エンティティに基づくセグメントを構築します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="84d1a-182">**メジャー** オプションを選択して、以前に作成したメジャーに対してセグメントを構築します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="84d1a-183">**インテリジェンス** オプションを選択して、**予測** または **カスタム モデル** 機能のいずれかを使用して生成した出力エンティティの 1 つにセグメントを構築します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="84d1a-184">**新規簡易セグメント** ダイアログ ボックスで、**フィールド** ドロップダウンから属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="84d1a-185">システムは、顧客のより良いセグメントを作成するのに役立つさらなるインサイトを提供します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="84d1a-186">カテゴリ フィールドに対しては、上位 10 件の顧客数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="84d1a-187">**値** を選択して、**レビュー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="84d1a-188">数値属性の場合、システムは各顧客のパーセンタイルに該当する属性値を表示します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="84d1a-189">**演算子** と **値** を選択して、次に **レビュー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="84d1a-190">システムは、**推定セグメント サイズ** を提供します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="84d1a-191">定義したセグメントを生成するか、最初に再訪して別のセグメント サイズを取得するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="84d1a-192">![クイック セグメントの名前と見積もり](media/quick-segment-name.png "クイック セグメントの名前と見積もり")</span><span class="sxs-lookup"><span data-stu-id="84d1a-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="84d1a-193">セグメントに対して **名前** を入力します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="84d1a-194">オプションで、**表示名** も入力します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="84d1a-195">**保存** を選択して、セグメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="84d1a-196">セグメントの処理が完了すると、作成した他のセグメントと同様に表示できます。</span><span class="sxs-lookup"><span data-stu-id="84d1a-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="84d1a-197">次の手順</span><span class="sxs-lookup"><span data-stu-id="84d1a-197">Next steps</span></span>

<span data-ttu-id="84d1a-198">[セグメントをエクスポート](export-destinations.md) して、[顧客カード](customer-card-add-in.md)  と [コネクター](export-power-bi.md) の詳細を確認して、顧客レベルでのインサイトを獲得します。</span><span class="sxs-lookup"><span data-stu-id="84d1a-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
