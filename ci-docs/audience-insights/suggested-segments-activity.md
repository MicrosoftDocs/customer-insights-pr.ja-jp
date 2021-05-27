---
title: 活動に基づく提案されたセグメント。
description: 機械学習により、顧客の活動に基づいて新しく興味深いセグメントを見つけることができます。
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034087"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="db2bf-103">活動データに基づく提案されたセグメント (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="db2bf-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="db2bf-104">Customer Insights に取り込まれた顧客活動データに基づいて、顧客の興味深いセグメントを検出します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="db2bf-105">活動データの例としては、トランザクション、サポート コールの時間、購入、返品などがあります。</span><span class="sxs-lookup"><span data-stu-id="db2bf-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="db2bf-106">セグメントを提案するために、活動データは、最新性、頻度、金銭的価値 (または期間) について分析されます。</span><span class="sxs-lookup"><span data-stu-id="db2bf-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="db2bf-107">また、[メジャーを改善したり、属性に影響を与えるものをよりよく理解するために提案されたセグメント](suggested-segments.md) を生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="db2bf-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="活動ベースおよび属性ベースのセグメントに対するセグメント提案を表示する提案されたセグメント タブ。":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="db2bf-109">活動別に顧客を分類する</span><span class="sxs-lookup"><span data-stu-id="db2bf-109">Categorize customers by activity</span></span>

<span data-ttu-id="db2bf-110">Customer Insights で利用可能な [活動データ](activities.md) を使用して、顧客グループを表す提案を生成できます:</span><span class="sxs-lookup"><span data-stu-id="db2bf-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="db2bf-111">最もアクティブな顧客</span><span class="sxs-lookup"><span data-stu-id="db2bf-111">most active customers</span></span> 
- <span data-ttu-id="db2bf-112">最も多く購入した顧客</span><span class="sxs-lookup"><span data-stu-id="db2bf-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="db2bf-113">最も収益を上げた顧客</span><span class="sxs-lookup"><span data-stu-id="db2bf-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="db2bf-114">最近活動していない顧客</span><span class="sxs-lookup"><span data-stu-id="db2bf-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="db2bf-115">ビジネスと頻繁にやり取りする顧客</span><span class="sxs-lookup"><span data-stu-id="db2bf-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="db2bf-116">小売業であれば、どの顧客が最も多くの収益を生み出しているかを調べ、クーポンで特典を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="db2bf-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="db2bf-117">または、たまにしか利用しない顧客を特定して、特典プログラムへの参加を提案することで、より頻繁にビジネスを訪問してもらうこともできます。</span><span class="sxs-lookup"><span data-stu-id="db2bf-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="db2bf-118">公的医療を提供する医療事業に従事していて、個々の患者の費用を最小限に抑えることを目標としている場合。</span><span class="sxs-lookup"><span data-stu-id="db2bf-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="db2bf-119">そのためには、可能な限り少ない訪問で可能な限り最善のケアを提供することにより、定期的な訪問を減らす方法があります。</span><span class="sxs-lookup"><span data-stu-id="db2bf-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="db2bf-120">この場合、目標は、訪問頻度を低く保ち、患者の定期的な費用を最小限に抑えることです。</span><span class="sxs-lookup"><span data-stu-id="db2bf-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="db2bf-121">または、頻繁に予約を取り、定期的な費用が高い患者のセグメントを特定し、これらのケースを分析して、個人の治療を改善することもできます。</span><span class="sxs-lookup"><span data-stu-id="db2bf-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="db2bf-122">必須データ</span><span class="sxs-lookup"><span data-stu-id="db2bf-122">Required data</span></span>

<span data-ttu-id="db2bf-123">提案は、選択した入力データに基づいて生成されます。</span><span class="sxs-lookup"><span data-stu-id="db2bf-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="db2bf-124">顧客プロファイル: すべての顧客または特定のセグメントのメンバー。</span><span class="sxs-lookup"><span data-stu-id="db2bf-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="db2bf-125">期間: 先月、昨年、または任意のカスタム期間。</span><span class="sxs-lookup"><span data-stu-id="db2bf-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="db2bf-126">活動の種類: 購入、小売トランザクション、オンライン トランザクション、顧客サポート案件、サブスクリプションなど。</span><span class="sxs-lookup"><span data-stu-id="db2bf-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="db2bf-127">活動データを含む Customer Insights のエンティティ: UnifiedActivity エンティティまたは特定活動のエンティティ。</span><span class="sxs-lookup"><span data-stu-id="db2bf-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="db2bf-128">含めるディメンション: ビジネス要件に応じて、最新性、頻度、または金銭的ディメンション。</span><span class="sxs-lookup"><span data-stu-id="db2bf-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="db2bf-129">提案されたセグメントを生成する</span><span class="sxs-lookup"><span data-stu-id="db2bf-129">Generate suggested segments</span></span>

1. <span data-ttu-id="db2bf-130">**セグメント** に移動します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="db2bf-131">**提案 (プレビュー)** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="db2bf-132">**新しい提案を検索する** を選択して、**顧客の行動を表示または予測する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="db2bf-133">**開始** を選択して、ガイド付きのエクスペリエンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="活動に基づいて提案されたセグメントの構成ウィザードの最初のステップ。":::

1. <span data-ttu-id="db2bf-135">必要な入力データを入力して、**次へ** を選択して続行します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="db2bf-136">顧客の選択: すべての顧客または特定のセグメントを含めます。</span><span class="sxs-lookup"><span data-stu-id="db2bf-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="db2bf-137">活動の選択: 活動の種類と活動を説明するエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="db2bf-138">基本設定: 検討する期間、提案の要因を設定し、属性をマップします。</span><span class="sxs-lookup"><span data-stu-id="db2bf-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="db2bf-139">入力内容を確認し、**実行** を選択してモデルを実行し、提案を生成します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="db2bf-140">顧客プロファイルと選択した活動の数によっては、完了するまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="db2bf-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="db2bf-141">提案を生成した後、最も関心のあるディメンションまたは値で提案をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="db2bf-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="db2bf-142">提案されたセグメントの詳細を見る</span><span class="sxs-lookup"><span data-stu-id="db2bf-142">View details of a suggested segment</span></span>

<span data-ttu-id="db2bf-143">提案が生成されると、**活動ベースの提案** セクションの **セグメント** > **提案 (プレビュー)** の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="db2bf-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="提案されたセグメントの詳細データを示す展開されたサイド ペイン。":::

<span data-ttu-id="db2bf-145">提案されたセグメントで **提案を表示する** を選択して、そのセグメントの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="db2bf-146">サイド ペインには、ターゲット グループと比較した各ディメンションの範囲などの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="db2bf-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="db2bf-147">また、セグメント内の潜在的なメンバー数と、それに対応する総顧客数の割合も強調表示します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="db2bf-148">提案をセグメントとして保持する場合は、**セグメントの作成** を選択します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="db2bf-149">標準セグメントをセグメントとして保存する</span><span class="sxs-lookup"><span data-stu-id="db2bf-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="db2bf-150">**セグメント** > **提案 (プレビュー)** に移動します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="db2bf-151">保存するセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="db2bf-152">サイド ペインで、**セグメントの作成** を選択します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="db2bf-153">セグメントを保存すると、**すべてのセグメント** タブのセグメント一覧に表示されます。これで、[他のセグメントと同様に更新または削除](segments.md) できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="db2bf-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="db2bf-154">セグメントの詳細を編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="db2bf-154">You can't edit the segment details.</span></span> <span data-ttu-id="db2bf-155">ただし、提案の入力基準を変更して、さまざまな提案を生成することができます。</span><span class="sxs-lookup"><span data-stu-id="db2bf-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="db2bf-156">一連の提案を更新または編集する</span><span class="sxs-lookup"><span data-stu-id="db2bf-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="db2bf-157">**セグメント** > **提案 (プレビュー)** に移動し、**活動ベースの提案** セクションでセグメントを探します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="db2bf-158">**提案を更新する** を選択して、構成された属性を保持しながら提案を更新します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="db2bf-159">または、**提案を編集する** を選択して、構成された属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="db2bf-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="db2bf-160">システムはプロセスを再実行し、最新データに基づいてセグメント提案を生成し、現在の提案を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="db2bf-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
