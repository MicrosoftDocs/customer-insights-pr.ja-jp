---
title: セグメントを作成して管理する
description: 顧客のセグメントを作成して、さまざまな属性に基づいてグループ化します。
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597058"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="78b92-103">セグメントを作成して管理する</span><span class="sxs-lookup"><span data-stu-id="78b92-103">Create and manage segments</span></span>

<span data-ttu-id="78b92-104">セグメントでは、統計、トランザクション、または行動の属性に基づいて、顧客をグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="78b92-105">セグメントを使用すると、プロモーション キャンペーン、営業活動、顧客サポート アクションを対象にして、ビジネス目標を達成することができます。</span><span class="sxs-lookup"><span data-stu-id="78b92-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="78b92-106">顧客プロファイル エンティティとそれに関連するエンティティの周りに複雑なフィルターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="78b92-107">処理後の各セグメントには、エクスポートして操作できる顧客エンティティ レコードのセットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="78b92-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="78b92-108">一部の [サービス制限](service-limits.md) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="78b92-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="78b92-109">特に明記されていない限り、すべてのセグメントは **動的セグメント** であり、定期的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="78b92-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="78b92-110">次の例は、セグメント化機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="78b92-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="78b92-111">過去 90 日間に 500 ドル以上の商品を注文した顧客 *と* エスカレートされた顧客サービス呼び出しに関与した顧客のセグメントを定義しました。</span><span class="sxs-lookup"><span data-stu-id="78b92-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="78b92-112">![複数のグループ化](media/segmentation-group1-2.png "複数のグループ化")</span><span class="sxs-lookup"><span data-stu-id="78b92-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="78b92-113">新しいセグメントの作成</span><span class="sxs-lookup"><span data-stu-id="78b92-113">Create a new segment</span></span>

<span data-ttu-id="78b92-114">セグメントは、**セグメント** ページで管理されます。</span><span class="sxs-lookup"><span data-stu-id="78b92-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="78b92-115">対象者に関するインサイトで、**セグメント** ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="78b92-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="78b92-116">**新規** > **空白のセグメント** を選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="78b92-117">**新規セグメント** ウィンドウで、セグメントの種類を選択し、**名前** を入力します。</span><span class="sxs-lookup"><span data-stu-id="78b92-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="78b92-118">オプションで、表示名と、セグメントの識別に役立つ説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="78b92-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="78b92-119">**次へ** を選択して、グループを定義する **セグメント ビルダー** ページに移ります。</span><span class="sxs-lookup"><span data-stu-id="78b92-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="78b92-120">グループは顧客のセットです。</span><span class="sxs-lookup"><span data-stu-id="78b92-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="78b92-121">セグメント出力に含める属性を含むエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="78b92-122">セグメント化する属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="78b92-123">この属性は、数値、文字列、日付、ブールの 4 つの値タイプのいずれかを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="78b92-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="78b92-124">選択した属性の演算子と値を選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="78b92-125">![カスタム グループ フィルタ―](media/customer-group-numbers.png "顧客グループ フィルタ―")</span><span class="sxs-lookup"><span data-stu-id="78b92-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="78b92-126">番号</span><span class="sxs-lookup"><span data-stu-id="78b92-126">Number</span></span> |<span data-ttu-id="78b92-127">定義</span><span class="sxs-lookup"><span data-stu-id="78b92-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="78b92-128">1</span><span class="sxs-lookup"><span data-stu-id="78b92-128">1</span></span>     |<span data-ttu-id="78b92-129">Entity</span><span class="sxs-lookup"><span data-stu-id="78b92-129">Entity</span></span>          |
   |<span data-ttu-id="78b92-130">2</span><span class="sxs-lookup"><span data-stu-id="78b92-130">2</span></span>     |<span data-ttu-id="78b92-131">属性</span><span class="sxs-lookup"><span data-stu-id="78b92-131">Attribute</span></span>          |
   |<span data-ttu-id="78b92-132">3</span><span class="sxs-lookup"><span data-stu-id="78b92-132">3</span></span>    |<span data-ttu-id="78b92-133">演算子</span><span class="sxs-lookup"><span data-stu-id="78b92-133">Operator</span></span>         |
   |<span data-ttu-id="78b92-134">4</span><span class="sxs-lookup"><span data-stu-id="78b92-134">4</span></span>    |<span data-ttu-id="78b92-135">値</span><span class="sxs-lookup"><span data-stu-id="78b92-135">Value</span></span>         |

8. <span data-ttu-id="78b92-136">エンティティが [リレーションシップ](relationships.md) を通して統合型顧客エンティティに接続されている場合、有効なセグメントを作成するには、関係パスを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78b92-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="78b92-137">ドロップダウンから **顧客 : CustomerInsights** のエンティティが選択できるまで、関係パスからエンティティを追加します。</span><span class="sxs-lookup"><span data-stu-id="78b92-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="78b92-138">次に、各条件について **すべての記録** を選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="78b92-139">![セグメント作成中の関係パス](media/segments-multiple-relationships.png "セグメント作成中の関係パス")</span><span class="sxs-lookup"><span data-stu-id="78b92-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="78b92-140">既定では、セグメントは、定義されたフィルターに一致する顧客プロファイルのすべての属性を含む出力エンティティーを生成します。</span><span class="sxs-lookup"><span data-stu-id="78b92-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="78b92-141">セグメントが *Customer* エンティティ以外の他のエンティティに基づいている場合は、これらのエンティティから出力エンティティに属性を追加できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="78b92-142">**プロジェクトの属性** を選択して、出力エンティティに追加する属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="78b92-143">例: セグメントは、*Customer* エンティティに関連する顧客活動データを含むエンティティに基づいています。</span><span class="sxs-lookup"><span data-stu-id="78b92-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="78b92-144">このセグメントでは、過去 60 日間にヘルプ デスクに連絡したすべての顧客を検索します。</span><span class="sxs-lookup"><span data-stu-id="78b92-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="78b92-145">出力エンティティ内の一致するすべての顧客レコードに、通話時間と通話数を追加することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="78b92-146">この情報は、頻繁に電話をする顧客にオンライン ヘルプ記事や FAQ への役立つリンクを記載した電子メールを送信するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="78b92-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="78b92-147">**保存** を選択してセグメントを保存します。</span><span class="sxs-lookup"><span data-stu-id="78b92-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="78b92-148">すべての要件が検証されると、セグメントが保存および処理されます。</span><span class="sxs-lookup"><span data-stu-id="78b92-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="78b92-149">それ以外の場合は、ドラフトとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="78b92-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="78b92-150">**セグメントに戻る** を選択して、**セグメント** のページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="78b92-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="78b92-151">既存のセグメントを管理する</span><span class="sxs-lookup"><span data-stu-id="78b92-151">Manage existing segments</span></span>

<span data-ttu-id="78b92-152">**セグメント** ページでは、保存したすべてのセグメントを表示して管理できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="78b92-153">各セグメントは、セグメントに関する追加情報を含む行で表されます。</span><span class="sxs-lookup"><span data-stu-id="78b92-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="78b92-154">列の見出しを選択すると、列のセグメントを並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="78b92-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="78b92-155">右上隅にある **検索** ボックスを使用して、セグメントをフィルタ―します。</span><span class="sxs-lookup"><span data-stu-id="78b92-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="78b92-156">![既存のセグメントを管理するオプション](media/segments-selected-segment.png "既存のセグメントを管理するオプション")</span><span class="sxs-lookup"><span data-stu-id="78b92-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="78b92-157">セグメントを選択すると、次のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="78b92-158">セグメント メンバーのプレビューなどメンバー数の傾向など、セグメントの詳細を **表示** します。</span><span class="sxs-lookup"><span data-stu-id="78b92-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="78b92-159">プロパティを変更するセグメントを **編集** します。</span><span class="sxs-lookup"><span data-stu-id="78b92-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="78b92-160">セグメントの **複製を作成** します。</span><span class="sxs-lookup"><span data-stu-id="78b92-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="78b92-161">プロパティをすぐに編集するか、単に複製を保存するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="78b92-162">最新のデータを含めるセグメントを **最新の情報に更新します**。</span><span class="sxs-lookup"><span data-stu-id="78b92-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="78b92-163">セグメントを **アクティブ化** または **非アクティブ化** します。</span><span class="sxs-lookup"><span data-stu-id="78b92-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="78b92-164">セグメントには、アクティブまたは非アクティブの 2 つの状態があります。</span><span class="sxs-lookup"><span data-stu-id="78b92-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="78b92-165">これらの状態は、セグメントを編集するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="78b92-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="78b92-166">非アクティブなセグメントの場合、セグメント定義は存在しますが、まだ顧客は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="78b92-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="78b92-167">セグメントをアクティブ化すると、その状態が '非アクティブ' から 'アクティブ' に変わり、セグメント定義に一致する顧客の検索が開始されます。</span><span class="sxs-lookup"><span data-stu-id="78b92-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="78b92-168">[スケジュールされた更新](system.md#schedule-tab) が構成されている場合、非アクティブなセグメントには **状態** が **スキップされた** としてリストされ、更新も試行されなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="78b92-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="78b92-169">非アクティブなセグメントがアクティブ化されると、これによって最新の情報に更新され、これはスケジュールされた更新に含まれます。</span><span class="sxs-lookup"><span data-stu-id="78b92-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="78b92-170">または、**アクティブ化/非アクティブ化** ドロップダウンで **後でスケジュール** 機能を使用して、特定のセグメントをアクティブ化および非アクティブ化する未来の日時を指定します。</span><span class="sxs-lookup"><span data-stu-id="78b92-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="78b92-171">セグメントの **名前を変更します**。</span><span class="sxs-lookup"><span data-stu-id="78b92-171">**Rename** the segment.</span></span>
- <span data-ttu-id="78b92-172">メンバーのリストを、CSV ファイル形式で **ダウンロード** します。</span><span class="sxs-lookup"><span data-stu-id="78b92-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="78b92-173">**追加先** オプションは、別のアプリケーションで処理するために、セグメント内の顧客 ID のリストを送信します。</span><span class="sxs-lookup"><span data-stu-id="78b92-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="78b92-174">セグメントを **削除** します。</span><span class="sxs-lookup"><span data-stu-id="78b92-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="78b92-175">セグメントを最新の情報に更新する</span><span class="sxs-lookup"><span data-stu-id="78b92-175">Refresh segments</span></span>

<span data-ttu-id="78b92-176">**セグメント** pページで **すべて更新** を選択すると、すべてのセグメントを一度に更新することができ、1つまたは複数のセグメントを選択してオプションから **更新** を選択すると、該当するセグメントを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="78b92-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="78b92-177">または、**管理者** > **システム** > **スケジュール** で定期的な更新を構成できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="78b92-178">タスク/プロセスには、[6 種類の状態](system.md#status-types) があります。</span><span class="sxs-lookup"><span data-stu-id="78b92-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="78b92-179">さらに、ほとんどのプロセスは、[その他の下流プロセスに依存します](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="78b92-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="78b92-180">プロセスのステータスを選択して、ジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="78b92-181">ジョブのタスクの 1 つについて **詳細の表示** を選択すると、処理時間、最終処理日、およびタスクに関連するすべてのエラーと警告などの追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78b92-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="78b92-182">セグメントをダウンロードしてエクスポートする</span><span class="sxs-lookup"><span data-stu-id="78b92-182">Download and export segments</span></span>

<span data-ttu-id="78b92-183">セグメントを CSV ファイルにダウンロードするか、Dynamics 365 Sales にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="78b92-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="78b92-184">セグメントを CSV ファイルにダウンロードする</span><span class="sxs-lookup"><span data-stu-id="78b92-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="78b92-185">対象者に関するインサイトで、**セグメント** ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="78b92-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="78b92-186">特定のセグメントのタイルで省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="78b92-187">アクション ドロップダウン リストから **CSV としてダウンロード** を選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="78b92-188">セグメントを Dynamics 365 Sales にエクスポートします</span><span class="sxs-lookup"><span data-stu-id="78b92-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="78b92-189">Dynamics 365 Sales にセグメントをエクスポートする前に、管理者は Dynamics 365 Sales の [エクスポート先を作成する](export-destinations.md) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="78b92-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="78b92-190">対象者に関するインサイトで、**セグメント** ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="78b92-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="78b92-191">特定のセグメントのタイルで省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="78b92-192">アクションドロップダウンリストから **追加先** を選択して、データを送信するエクスポート先を選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="78b92-193">セグメントのドラフト モード</span><span class="sxs-lookup"><span data-stu-id="78b92-193">Draft mode for segments</span></span>

<span data-ttu-id="78b92-194">セグメントを処理するためのすべての要件が満たされていない場合は、**セグメント** ページからセグメントをドラフトとして保存します。</span><span class="sxs-lookup"><span data-stu-id="78b92-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="78b92-195">これは無効なセグメントとして保存され、有効になるまでアクティブ化にできません。</span><span class="sxs-lookup"><span data-stu-id="78b92-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="78b92-196">グループに条件を追加する</span><span class="sxs-lookup"><span data-stu-id="78b92-196">Add more conditions to a group</span></span>

<span data-ttu-id="78b92-197">グループに条件を追加するには、次の 2 つの論理演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="78b92-198">**AND** 演算子 : セグメンテーション プロセスの一部として両方の条件が満たされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="78b92-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="78b92-199">このオプションは、異なるエンティティにわたって条件を定義するときに最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="78b92-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="78b92-200">**OR** 演算子 : セグメンテーション プロセスの一部として、いずれかの条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="78b92-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="78b92-201">このオプションは、同じエンティティにわたって複数の条件を定義するときに最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="78b92-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="78b92-202">![いずれかの条件が満たされる必要がある OR 演算子](media/segmentation-either-condition.png "いずれかの条件が満たされる必要がある OR 演算子")</span><span class="sxs-lookup"><span data-stu-id="78b92-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="78b92-203">現在、**AND** 演算子下で **OR** 演算子をネストすることが可能ですが、その逆はできません。</span><span class="sxs-lookup"><span data-stu-id="78b92-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="78b92-204">複数のグループを結合する</span><span class="sxs-lookup"><span data-stu-id="78b92-204">Combine multiple groups</span></span>

<span data-ttu-id="78b92-205">各グループは、特定の顧客のセットを生成します。</span><span class="sxs-lookup"><span data-stu-id="78b92-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="78b92-206">これらのグループを組み合わせて、自分のビジネス ケースに必要な顧客を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="78b92-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="78b92-207">対象者に関するインサイトで、**セグメント** ページに移動し、セグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="78b92-208">**グループを追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="78b92-209">![顧客グループ追加グループ](media/customer-group-add-group.png "顧客グループ追加グループ")</span><span class="sxs-lookup"><span data-stu-id="78b92-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="78b92-210">次の演算子、**連合**、**交差**、または **除外** のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="78b92-211">![顧客グループ追加結合](media/customer-group-union.png "顧客グループ追加結合")</span><span class="sxs-lookup"><span data-stu-id="78b92-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="78b92-212">セット演算子を選択すると、新しいグループを定義できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="78b92-213">異なるグループを保存して、保持されるデータを決定します:</span><span class="sxs-lookup"><span data-stu-id="78b92-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="78b92-214">**結合** は 2 つのグループを結合します。</span><span class="sxs-lookup"><span data-stu-id="78b92-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="78b92-215">**交差** は 2 つのグループが重複しています。</span><span class="sxs-lookup"><span data-stu-id="78b92-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="78b92-216">両方のグループに *共通である* データのみが、統合グループに保持されます。</span><span class="sxs-lookup"><span data-stu-id="78b92-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="78b92-217">**例外** は 2 つのグループを結合します。</span><span class="sxs-lookup"><span data-stu-id="78b92-217">**Except** combines the two groups.</span></span> <span data-ttu-id="78b92-218">グループ B のデータと *共通ではない* グループ A のデータのみが保持されます。</span><span class="sxs-lookup"><span data-stu-id="78b92-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="78b92-219">処理履歴とセグメント メンバーの表示</span><span class="sxs-lookup"><span data-stu-id="78b92-219">View processing history and segment members</span></span>

<span data-ttu-id="78b92-220">セグメントの詳細を確認すると、セグメントに関する統合データを表示できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="78b92-221">**セグメント** ページで、レビューするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="78b92-222">ページの上部には、メンバー数の変化を視覚化する傾向グラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="78b92-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="78b92-223">データ ポイントにカーソルを合わせると、特定の日付のメンバー数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78b92-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="78b92-224">視覚化の概算時間を更新できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="78b92-225">![時間の範囲のセグメント化](media/segment-time-range.png "時間の範囲のセグメント化")</span><span class="sxs-lookup"><span data-stu-id="78b92-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="78b92-226">下部には、セグメント メンバーのリストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="78b92-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="78b92-227">このリストに表示されるフィールドは、セグメントのエンティティの属性に基づいています。</span><span class="sxs-lookup"><span data-stu-id="78b92-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="78b92-228">このリストは、一致するセグメント メンバーのプレビューであり、セグメントの最初の 100 レコードが表示されるため、必要に応じてセグメントをすばやく評価し、定義をレビューできます。</span><span class="sxs-lookup"><span data-stu-id="78b92-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="78b92-229">一致するすべてのレコードを表示するには、[セグメントをエクスポートする](export-destinations.md) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="78b92-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="78b92-230">簡易セグメント</span><span class="sxs-lookup"><span data-stu-id="78b92-230">Quick segments</span></span>

<span data-ttu-id="78b92-231">セグメント ビルダーに加えて、セグメントを作成するための別のパスがあります。</span><span class="sxs-lookup"><span data-stu-id="78b92-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="78b92-232">簡易セグメントを使用すると、1 人のオペレーターが簡単なセグメントをすばやく、簡易インスタントと構築できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="78b92-233">**セグメント** ページで、**新着** > **簡易作成フォーム** を選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="78b92-234">**プロフィール** オプションを選択して、統一された顧客エンティティに基づくセグメントを構築します。</span><span class="sxs-lookup"><span data-stu-id="78b92-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="78b92-235">**メジャー** オプションを選択して、**メジャー** ページで以前作成したメジャーの各顧客属性の種類周辺にセグメントを構築します。</span><span class="sxs-lookup"><span data-stu-id="78b92-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="78b92-236">**インテリジェンス** オプションを選択して、**予測** または **カスタム モデル** 機能のいずれかを使用して生成した出力エンティティの 1 つにセグメントを構築します。</span><span class="sxs-lookup"><span data-stu-id="78b92-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="78b92-237">**新規簡易セグメント** ダイアログ ボックスで、**フィールド** ドロップダウンから属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="78b92-238">システムは、顧客のより良いセグメントを作成するのに役立つさらなるインサイトを提供します。</span><span class="sxs-lookup"><span data-stu-id="78b92-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="78b92-239">カテゴリ フィールドに対しては、上位 10 件の顧客数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78b92-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="78b92-240">**値** を選択して、**レビュー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="78b92-241">数値属性の場合、システムは各顧客のパーセンタイルに該当する属性値を表示します。</span><span class="sxs-lookup"><span data-stu-id="78b92-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="78b92-242">**演算子** と **値** を選択して、次に **レビュー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="78b92-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="78b92-243">システムは、**推定セグメント サイズ** を提供します。</span><span class="sxs-lookup"><span data-stu-id="78b92-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="78b92-244">定義したセグメントを生成するか、最初に再訪して別のセグメント サイズを取得するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="78b92-245">![クイック セグメントの名前と見積もり](media/quick-segment-name.png "クイック セグメントの名前と見積もり")</span><span class="sxs-lookup"><span data-stu-id="78b92-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="78b92-246">セグメントに対して **名前** を入力します。</span><span class="sxs-lookup"><span data-stu-id="78b92-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="78b92-247">オプションで、**表示名** も入力します。</span><span class="sxs-lookup"><span data-stu-id="78b92-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="78b92-248">**保存** を選択して、セグメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="78b92-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="78b92-249">セグメントの処理が完了すると、作成した他のセグメントと同様に表示できます。</span><span class="sxs-lookup"><span data-stu-id="78b92-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="78b92-250">次のシナリオでは、推奨されるセグメント機能ではなく、セグメント ビルダーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="78b92-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="78b92-251">演算子が **Is** 演算子とは異なるカテゴリ フィールドでフィルターを使用してセグメントを作成する</span><span class="sxs-lookup"><span data-stu-id="78b92-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="78b92-252">演算子が **Between**、**Greater than**、そして **Less than** 演算子とは異なる数値フィールドにフィルターを使用してセグメントを作成する</span><span class="sxs-lookup"><span data-stu-id="78b92-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="78b92-253">日付の種類のフィールドにフィルターを使用してセグメントを作成する</span><span class="sxs-lookup"><span data-stu-id="78b92-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="78b92-254">次のステップ</span><span class="sxs-lookup"><span data-stu-id="78b92-254">Next steps</span></span>

<span data-ttu-id="78b92-255">[セグメントをエクスポート](export-destinations.md) して、[顧客カード](customer-card-add-in.md)  と [コネクター](export-power-bi.md) の詳細を確認して、顧客レベルでのインサイトを獲得します。</span><span class="sxs-lookup"><span data-stu-id="78b92-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]