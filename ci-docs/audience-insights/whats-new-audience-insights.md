---
title: 新しい機能および今後の機能
description: 新機能、改善、およびバグ修正に関する情報。
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988926"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a><span data-ttu-id="8271b-103">Dynamics 365 Customer Insights の対象者に関するインサイト機能の新機能</span><span class="sxs-lookup"><span data-stu-id="8271b-103">What's new in the audience insights capability of Dynamics 365 Customer Insights</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8271b-104">最新の更新プログラムについてお知らせします !</span><span class="sxs-lookup"><span data-stu-id="8271b-104">We're excited to announce our newest updates!</span></span> <span data-ttu-id="8271b-105">この記事は、パブリック プレビュー機能、全般的な可用性の強化、毎月の更新プログラム、機能の更新をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="8271b-105">This article summarizes public preview features, general availability enhancements, and feature updates.</span></span> <span data-ttu-id="8271b-106">長期的な機能計画を確認するには、[Dynamics 365 と Power Platform のリリース計画](/dynamics365/release-plans/) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8271b-106">To see the long-term feature plans, take a look at the [Dynamics 365 and Power Platform release plans](/dynamics365/release-plans/).</span></span>

<span data-ttu-id="8271b-107">更新プログラムは地域ベースで配信されます。</span><span class="sxs-lookup"><span data-stu-id="8271b-107">We roll out updates on a region-by-region basis.</span></span> <span data-ttu-id="8271b-108">そのため、特定の地域では、他の地域より先に機能が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8271b-108">So certain regions might see features before others.</span></span> <span data-ttu-id="8271b-109">特に指定がない限り、何もする必要はなく、アプリはダウンタイムなしで自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="8271b-109">Unless specified differently, you don't need to take any action and we'll update the app automatically with no downtime.</span></span>

> [!TIP]
> <span data-ttu-id="8271b-110">機能要求と製品に関する提案を送信して投票するには、[Dynamics 365 アプリケーションのアイデア ポータル](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights) に移動してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-110">To submit and vote on feature requests and product suggestions, go to the [Dynamics 365 Application Ideas portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).</span></span>

## <a name="april-2021-updates"></a><span data-ttu-id="8271b-111">2021 年 4 月の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="8271b-111">April 2021 updates</span></span>

<span data-ttu-id="8271b-112">2021 年 4 月の更新プログラムには、いくつかの機能、パフォーマンス アップグレード、およびバグ修正が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8271b-112">The updates in April 2021 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="data-unification"></a><span data-ttu-id="8271b-113">データ統合</span><span class="sxs-lookup"><span data-stu-id="8271b-113">Data unification</span></span>
 
- <span data-ttu-id="8271b-114">**データ統合のための拡張マージ エクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="8271b-114">**Enhanced merge experience for data unification**</span></span>    
  
   <span data-ttu-id="8271b-115">これで、データ統合プロセスのマージ構成でユーザー エクスペリエンスが向上しました。</span><span class="sxs-lookup"><span data-stu-id="8271b-115">We now have an enhanced user experience in the merge configuration of the data unification process.</span></span> <span data-ttu-id="8271b-116">変更には、マージされたフィールドのわかりやすい順序付けや、結合されたフィールドとシングルトン フィールドに関する詳細な統計が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8271b-116">The changes include intuitive ordering of the merged fields and detailed statistics on combined and singleton fields.</span></span>

- <span data-ttu-id="8271b-117">**エンティティの並べ替えとすべてのソース レコードの顧客エンティティへの構成**</span><span class="sxs-lookup"><span data-stu-id="8271b-117">**Entity reordering and configure all source records into the Customer entity**</span></span>  
      
   <span data-ttu-id="8271b-118">データ統合プロセスで、既存の合成プランからエンティティを並べ替えたり削除したりできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-118">You can now reorder and remove entities from an existing conflation plan in the data unification process.</span></span> <span data-ttu-id="8271b-119">これにより、ビジネス ニーズに応じて、照合プロセスにおけるエンティティの順序を柔軟に変更できます。</span><span class="sxs-lookup"><span data-stu-id="8271b-119">It gives flexibility to reorder the entities in the match process according to business needs.</span></span> <span data-ttu-id="8271b-120">さらに、一致しないすべてのレコードを最終的な *顧客* エンティティに含めることができ、顧客プロファイルのデータセット定義を定義できます。</span><span class="sxs-lookup"><span data-stu-id="8271b-120">Additionally, we enable include all non-matched records into the final *Customer* entity, which lets them define their customer profile dataset definition.</span></span>

### <a name="enrichments"></a><span data-ttu-id="8271b-121">エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="8271b-121">Enrichments</span></span>

 - <span data-ttu-id="8271b-122">**新しいエンリッチメント: 拡張住所**</span><span class="sxs-lookup"><span data-stu-id="8271b-122">**New enrichment: Enhanced addresses**</span></span>    
  
   <span data-ttu-id="8271b-123">顧客データの住所を拡張するための新しいエンリッチメントを紹介します。</span><span class="sxs-lookup"><span data-stu-id="8271b-123">We're excited to introduce a new enrichment to enhance addresses in your customer data.</span></span> <span data-ttu-id="8271b-124">データ内のアドレスは、構造化されていない、不完全である、または正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8271b-124">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="8271b-125">この機能は、Microsoft のモデルを使用して、住所を Common Data Model フォーマットに正規化およびエンリッチし、精度とインサイトを向上させます。</span><span class="sxs-lookup"><span data-stu-id="8271b-125">This feature uses Microsoft's models to normalize and enrich your addresses into the Common Data Model format for better accuracy and insights.</span></span>
 
   <span data-ttu-id="8271b-126">詳細については、[拡張住所による顧客プロファイルのエンリッチメント](enrichment-enhanced-addresses.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-126">For more information, see [Enrichment of customer profiles with enhanced addresses](enrichment-enhanced-addresses.md).</span></span>

- <span data-ttu-id="8271b-127">**エンリッチメントのためのガイド付き構成エクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="8271b-127">**Guided configuration experience for enrichments**</span></span>    
  
   <span data-ttu-id="8271b-128">シンプルなガイド付きエクスペリエンスとともに、エンリッチメントの構成エクスペリエンスを再検討しました。</span><span class="sxs-lookup"><span data-stu-id="8271b-128">We revisited the configuration experience for enrichments with a simple, guided experience.</span></span> <span data-ttu-id="8271b-129">これで、エンリッチメントを作成および編集するための明確なステップバイステップのプロセスができました。</span><span class="sxs-lookup"><span data-stu-id="8271b-129">You now have a clear step-by-step process for creating and editing enrichments.</span></span>
 
   <span data-ttu-id="8271b-130">さらに、サード パーティ エンリッチメントの接続構成を分離して、同じ接続を複数のエンリッチメントで使用できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="8271b-130">Additionally, we separated the configuration of connections for third-party enrichments to enable the same connection to be used by multiple enrichments.</span></span> <span data-ttu-id="8271b-131">管理者のみが新しい接続を構成できますが、作成された接続は管理者と共同作成者の両方が使用できます。</span><span class="sxs-lookup"><span data-stu-id="8271b-131">Only administrators can configure new connections, but the created connections are available to both administrators and contributors.</span></span>    

   <span data-ttu-id="8271b-132">詳細については、[接続の概要](connections.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-132">For more information, see [Connections overview](connections.md).</span></span>

- <span data-ttu-id="8271b-133">**同じ種類の複数のエンリッチメント**</span><span class="sxs-lookup"><span data-stu-id="8271b-133">**Multiple enrichments of the same type**</span></span>    
  
   <span data-ttu-id="8271b-134">ユーザーが同じエンリッチメントの種類の複数のエンリッチメントを作成および管理できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-134">We now allow users to create and manage multiple enrichments of the same enrichment type.</span></span> <span data-ttu-id="8271b-135">たとえば、2 つの異なる住所エンリッチメントを作成して、2 つの異なる顧客セグメントをエンリッチできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-135">For example, you can now create two separate address enrichments to enrich two different customer segments.</span></span> <span data-ttu-id="8271b-136">同じ種類のエンリッチメントを作成できる数には制限があり、エンリッチメントの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8271b-136">Limits apply on how many enrichments of the same type can be created and vary depending on the enrichment type.</span></span>
  
   <span data-ttu-id="8271b-137">詳細については、[顧客プロファイルのエンリッチメント](enrichment-hub.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-137">For more information, see [Enrichment for customer profiles](enrichment-hub.md).</span></span>

## <a name="march-2021-updates"></a><span data-ttu-id="8271b-138">2021 年 3 月の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="8271b-138">March 2021 updates</span></span>

<span data-ttu-id="8271b-139">2021 年 3 月の更新プログラムには、いくつかの機能、パフォーマンス アップグレード、およびバグ修正が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8271b-139">The updates in March 2021 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="activities"></a><span data-ttu-id="8271b-140">活動 </span><span class="sxs-lookup"><span data-stu-id="8271b-140">Activities</span></span>

- <span data-ttu-id="8271b-141">**活動ウィザードとセマンティックの種類**</span><span class="sxs-lookup"><span data-stu-id="8271b-141">**Activity wizard and semantic types**</span></span>

   <span data-ttu-id="8271b-142">活動マッピングの作成をガイドおよび簡素化するために、活動マッピング エクスペリエンスを改善および更新しました。</span><span class="sxs-lookup"><span data-stu-id="8271b-142">We have improved and updated our activity mapping experience to guide and simplify the creation of activity mapping.</span></span> <span data-ttu-id="8271b-143">この新しいエクスペリエンスでは、ユーザーはプロセスの各手順の完了に役立つガイド付きエクスペリエンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="8271b-143">In this new experience, users get a guided experience to help completing of each step of the process.</span></span> <span data-ttu-id="8271b-144">活動マッピングの手順では、多くの活動の種類から選択することに加えて、ユーザーは *サブスクリプション* または *SalesOrderLine* あるいはその両方のデータを、ダウンストリーム消費に使用できる業界標準のスキーマにマップすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8271b-144">At the activity mapping step, in addition to choosing from many activity types, the user can choose to semantically map data for *Subscription* and/or *SalesOrderLine* to industry standard schemas, which can be used for downstream consumption.</span></span>   

   <span data-ttu-id="8271b-145">詳細については、[顧客アクティビティ](activities.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-145">For more information, see [Customer activities](activities.md).</span></span>

### <a name="data-ingestion"></a><span data-ttu-id="8271b-146">データ インジェスト</span><span class="sxs-lookup"><span data-stu-id="8271b-146">Data ingestion</span></span>

- <span data-ttu-id="8271b-147">**Power Platform データフローとゲートウェイを使用してオンプレミスのデータ ソースに接続** 関連する Power Platform または Dataverse 環境で Customer Insights のゲートウェイを使用した Power Platform データフローとオンプレミス接続のプレビューをお知らせいたします。</span><span class="sxs-lookup"><span data-stu-id="8271b-147">**Connect to on-premises data sources using Power Platform dataflows and gateways** We are pleased to announce the preview of Power Platform dataflows and on-premises connectivity using gateways in Customer Insights with an associated Power Platform or Dataverse environment.</span></span> <span data-ttu-id="8271b-148">リンクされた Dataverse 環境を持つ Customer Insights 環境で作成された新しいデータ ソースは、既定で Power Platform データフローになり、オンプレミスのデータ接続性と豊富なコネクタおよび変換機能のセットをもたらします。</span><span class="sxs-lookup"><span data-stu-id="8271b-148">Any new data sources created in a Customer Insights environment with a linked Dataverse environment will default to Power Platform dataflows bringing in the on-premises data connectivity and a rich set of connectors and transformation capabilities.</span></span>

### <a name="extensibility"></a><span data-ttu-id="8271b-149">拡張性</span><span class="sxs-lookup"><span data-stu-id="8271b-149">Extensibility</span></span>

- <span data-ttu-id="8271b-150">**接続とエクスポートで編成された** **エクスポート先** ページの名前を **接続** に変更し、**エクスポート** 用の別のページを追加しました。</span><span class="sxs-lookup"><span data-stu-id="8271b-150">**Exports organized in connections and exports** We have changed the name of the **Export destinations** page to **Connections** and added a separate page for **Exports**.</span></span> <span data-ttu-id="8271b-151">この更新の一環として、既存のエクスポートを接続とその接続を使用するエクスポートのペアに移行します。</span><span class="sxs-lookup"><span data-stu-id="8271b-151">As part of this update, we'll transition existing exports into pairs of a connection and an export using that connection.</span></span> <span data-ttu-id="8271b-152">管理者は、**接続** ページで送信データをより明確にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8271b-152">Administrators now have more clarity over outgoing data on the **Connections** page.</span></span> <span data-ttu-id="8271b-153">すべてのユーザー ロールが、**エクスポート** ページにアクセスできますが、管理者のみが共同作成者に共有接続を使用した特定のエクスポートの編集を許可できます。</span><span class="sxs-lookup"><span data-stu-id="8271b-153">All user roles have access to the **Exports** page, but only administrators can choose to allow contributors to edit specific exports with shared connections.</span></span>     
  <span data-ttu-id="8271b-154">詳細については、[接続の概要](connections.md) と [エクスポートの概要](export-destinations.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-154">For more information, see [Connections overview](connections.md) and [Exports overview](export-destinations.md).</span></span>

- <span data-ttu-id="8271b-155">**セグメントの Campaign Monitor へのエクスポート** エクスポート先を Campaign Monitor を含むように拡張しました。</span><span class="sxs-lookup"><span data-stu-id="8271b-155">**Export segments to Campaign Monitor** We have extended our export destinations to include Campaign Monitor.</span></span> <span data-ttu-id="8271b-156">Customer Insights から Campaign Monitor リストにセグメントをエクスポートし、マーケティング キャンペーンのベースラインとして使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-156">You can now export segments from Customer Insights to Campaign Monitor lists and use them as the baseline for your marketing campaigns.</span></span>    
   <span data-ttu-id="8271b-157">詳細については、[Campaign Monitor へのエクスポート](export-campaign-monitor.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-157">For more information, see [Export to Campaign Monitor](export-campaign-monitor.md).</span></span>

- <span data-ttu-id="8271b-158">**セグメントの Constant Contact へのエクスポート** エクスポート先を Constant Contact を含むように拡張しました。</span><span class="sxs-lookup"><span data-stu-id="8271b-158">**Export segments to Constant Contact** We have extended our export destinations to include Constant Contact.</span></span> <span data-ttu-id="8271b-159">Customer Insights から Constant Contact リストにセグメントをエクスポートし、マーケティング キャンペーンのベースラインとして使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-159">You can now export segments from Customer Insights to Constant Contact lists and use them as the baseline for your marketing campaigns.</span></span>   
   <span data-ttu-id="8271b-160">詳細については、[Constant Contact へのエクスポート](export-constant-contact.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-160">For more information, see [Export to Constant Contact](export-constant-contact.md).</span></span>

- <span data-ttu-id="8271b-161">**セグメントの RollWorks へのエクスポート** エクスポート先を RollWorks を含むように拡張しました。</span><span class="sxs-lookup"><span data-stu-id="8271b-161">**Export segments to RollWorks** We have extended our export destinations to include RollWorks.</span></span> <span data-ttu-id="8271b-162">Customer Insights から RollWorks 対象ユーザーにセグメントをエクスポートし、B2B 広告のベースラインとして使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-162">You can now export segments from Customer Insights to RollWorks audiences and use them as the baseline for your B2B advertising.</span></span>    
   <span data-ttu-id="8271b-163">詳細については、[RollWorks へのエクスポート](export-rollworks.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-163">For more information, see [Export to RollWorks ](export-rollworks.md).</span></span>

- <span data-ttu-id="8271b-164">**セグメントの Snapchat へのエクスポート** エクスポート先を Snapchat を含むように拡張しました。</span><span class="sxs-lookup"><span data-stu-id="8271b-164">**Export segments to Snapchat** We have extended our export destinations to include Snapchat.</span></span> <span data-ttu-id="8271b-165">Customer Insights から Snapchat 対象ユーザーにセグメントをエクスポートし、広告のベースラインとして使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-165">You can now export segments from Customer Insights to Snapchat audiences and use them as the baseline for your advertising.</span></span>     
   <span data-ttu-id="8271b-166">詳細については、[Snapchat へのエクスポート](export-snapchat.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-166">For more information, see [Export to Snapchat](export-snapchat.md).</span></span>

### <a name="predictions"></a><span data-ttu-id="8271b-167">予測</span><span class="sxs-lookup"><span data-stu-id="8271b-167">Predictions</span></span>

- <span data-ttu-id="8271b-168">**製品フィルターの予測製品レコメンデーションでの使用** 製品レコメンデーション モデルに製品フィルターを使用する機能を追加しました。</span><span class="sxs-lookup"><span data-stu-id="8271b-168">**Use product filters in predictive product recommendations** We have added the capability to use product filters in our product recommendation model.</span></span> <span data-ttu-id="8271b-169">製品のサブセットのみを使用する予測を作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-169">You can now create a prediction that uses only a subset of your products.</span></span>    
   <span data-ttu-id="8271b-170">詳細については、[製品フィルターの構成](predict-product-recommendation.md#configure-product-filters) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-170">For more information, see [Configure product filters](predict-product-recommendation.md#configure-product-filters).</span></span>

- <span data-ttu-id="8271b-171">**モデル予測からセグメントの作成** 予測モデルの結果を使用して、セグメントを作成する簡単な方法を追加しました。</span><span class="sxs-lookup"><span data-stu-id="8271b-171">**Create segments from model predictions** We have added a quick way to create segments using the results of a prediction model.</span></span> <span data-ttu-id="8271b-172">モデルの結果ページから、新しい **セグメントの作成** オプションを選択して、新しいセグメントを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="8271b-172">From the model results page, you can easily create a new segment by selecting the new **Create segment** option.</span></span>    
  <span data-ttu-id="8271b-173">詳細については、[予測モデルに基づいたセグメントの作成](prediction-based-segment.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-173">For more information, see [Create a segment based on a prediction model](prediction-based-segment.md).</span></span>

- <span data-ttu-id="8271b-174">**製品レコメンデーションの説明** 製品レコメンデーションを生成するために AI モデルによって学習された主な要因と、それらの要因が製品レコメンデーションにどの程度貢献しているかを説明する情報を追加しました。</span><span class="sxs-lookup"><span data-stu-id="8271b-174">**Explanations for product recommendations** We have added information explaining the key factors learned by the AI model to generate product recommendations and the degree to which those factors contribute towards the product recommendations.</span></span> <span data-ttu-id="8271b-175">この情報は、モデルの結果画面に追加されます。</span><span class="sxs-lookup"><span data-stu-id="8271b-175">This information is added to the model results screen.</span></span>    
   <span data-ttu-id="8271b-176">詳細については、[予測の状態と結果の確認](predict-product-recommendation.md#review-a-prediction-status-and-results) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-176">For more information, see [Review a prediction status and results](predict-product-recommendation.md#review-a-prediction-status-and-results).</span></span>

## <a name="february-2021-updates"></a><span data-ttu-id="8271b-177">2021 年 2 月の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="8271b-177">February 2021 updates</span></span>

<span data-ttu-id="8271b-178">2021 年 2 月の更新には、いくつかの機能、パフォーマンスのアップグレード、およびバグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8271b-178">The updates in February 2021 include several features, performance upgrades, and bug fixes.</span></span>

#### <a name="extensibility"></a><span data-ttu-id="8271b-179">拡張性</span><span class="sxs-lookup"><span data-stu-id="8271b-179">Extensibility</span></span>

- <span data-ttu-id="8271b-180">**セグメントを AdRoll にエクスポート**</span><span class="sxs-lookup"><span data-stu-id="8271b-180">**Export segments to AdRoll**</span></span>

  <span data-ttu-id="8271b-181">AdRoll を含むようにエクスポート先を拡張しました。</span><span class="sxs-lookup"><span data-stu-id="8271b-181">We have extended our export destinations to include AdRoll.</span></span> <span data-ttu-id="8271b-182">Customer Insights から AdRoll の対象者にセグメントをエクスポートし、それらを広告のベースラインとして使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-182">You can now export segments from Customer Insights to AdRoll audiences and use them as the baseline for your advertising.</span></span> <span data-ttu-id="8271b-183">詳細については、[AdRoll 用コネクタ](export-adroll.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-183">For more information, see [Connector for AdRoll](export-adroll.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="8271b-184">セグメント</span><span class="sxs-lookup"><span data-stu-id="8271b-184">Segments</span></span>
 
- <span data-ttu-id="8271b-185">**セグメントの複製**</span><span class="sxs-lookup"><span data-stu-id="8271b-185">**Duplicate a segment**</span></span>
  
  <span data-ttu-id="8271b-186">既存のセグメントに基づいて新しいセグメントを作成する場合、セグメントを複製し、複製したセグメントを編集してさらに絞り込むことができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-186">To create a new segment based on an existing one, you can now duplicate a segment and edit the duplicated segment to refine it further.</span></span> 

- <span data-ttu-id="8271b-187">**セグメントに属性を追加**</span><span class="sxs-lookup"><span data-stu-id="8271b-187">**Add additional attributes to a segment**</span></span>

  <span data-ttu-id="8271b-188">これらの属性が顧客プロファイルの一部でない場合でも、セグメント出力に属性を含めることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-188">You can now include attributes in your segment output, even if these attributes are not part of the customer profile.</span></span> <span data-ttu-id="8271b-189">たとえば、顧客エンティティと M:1 の関連付けを持つサブスクリプション エンティティの一部である場合でも、セグメントにサブスクリプション ID を含めます。</span><span class="sxs-lookup"><span data-stu-id="8271b-189">For example, include subscription IDs in a segment even though it is part of the subscription entity that has a M:1 relation with the customer entity.</span></span> <span data-ttu-id="8271b-190">属性が顧客エンティティに関連するエンティティに属している限り、これらの属性を含めることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-190">As long as the attribute belongs to an entity related to the customer entity you can now include these attributes.</span></span>  

#### <a name="predictions"></a><span data-ttu-id="8271b-191">予測</span><span class="sxs-lookup"><span data-stu-id="8271b-191">Predictions</span></span>

- <span data-ttu-id="8271b-192">**予測製品レコメンデーションの作成**</span><span class="sxs-lookup"><span data-stu-id="8271b-192">**Create predictive product recommendations**</span></span>

  <span data-ttu-id="8271b-193">顧客が購入に興味を持っているものを理解することは、個人設定とエンゲージメントを通じてビジネスの収益を改善し、顧客ロイヤルティを構築するために必要な最初のステップの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="8271b-193">Understanding what customers are interested in purchasing is one of the first steps needed to improve business revenue and build customer loyalty through personalization and engagement.</span></span> <span data-ttu-id="8271b-194">顧客の関心に合わない製品にレコメンデーションを提示すると、顧客とビジネスの間に断絶感が生まれ、最終的には顧客の潜在的な収益と経験を全体的に制限することになります。</span><span class="sxs-lookup"><span data-stu-id="8271b-194">Providing recommendations for products that aren’t aligned to your customer’s interests can create a sense of disconnect between the customer and your business, and ultimately limit the overall potential revenue and experience for a customer.</span></span> 

  <span data-ttu-id="8271b-195">独自のデータを使用して、顧客が今後購入する可能性のある製品の予測を作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-195">Using your own data, you can now create predictions for what products your customers are likely to purchase in the future.</span></span> <span data-ttu-id="8271b-196">詳細については、[製品のレコメンデーション予測](predict-product-recommendation.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-196">For more information, see [Product recommendation prediction](predict-product-recommendation.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="8271b-197">システム管理</span><span class="sxs-lookup"><span data-stu-id="8271b-197">System administration</span></span>

- <span data-ttu-id="8271b-198">**コピー環境では、より多くの種類のデータ ソースをサポート**</span><span class="sxs-lookup"><span data-stu-id="8271b-198">**Copy environment support more types of data sources**</span></span>

  <span data-ttu-id="8271b-199">管理者は、環境構成を同じ組織内の新しい環境にコピーできます。</span><span class="sxs-lookup"><span data-stu-id="8271b-199">Admins can copy environment configurations to a new environment in the same organization.</span></span> <span data-ttu-id="8271b-200">この機能は、Common Data Service データ レイクまたは Common Data Model フォルダーに基づくデータ ソースが使用される場合のコピー環境機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="8271b-200">This feature extends the copy environment functionality for cases in which data sources based on a Common Data Service data lake or a Common Data Model folder are used.</span></span>

## <a name="january-2021-updates"></a><span data-ttu-id="8271b-201">2021 年 1 月の更新</span><span class="sxs-lookup"><span data-stu-id="8271b-201">January 2021 updates</span></span>

<span data-ttu-id="8271b-202">2021 年 1 月の更新には、いくつかの機能、パフォーマンスのアップグレード、およびバグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8271b-202">The updates in January 2021 include several features, performance upgrades, and bug fixes.</span></span>

#### <a name="extensibility"></a><span data-ttu-id="8271b-203">拡張性</span><span class="sxs-lookup"><span data-stu-id="8271b-203">Extensibility</span></span>

- <span data-ttu-id="8271b-204">**SFTP エクスポートの拡張機能と強化されたパフォーマンス** すべての出力エンティティを Customer Insights から SFTP ホストにエクスポートできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-204">**Extended functionality and enhanced performance for SFTP export** You can now export all output entities from Customer Insights to an SFTP host.</span></span> <span data-ttu-id="8271b-205">以前は、エクスポートはセグメント エンティティに制限されていました。</span><span class="sxs-lookup"><span data-stu-id="8271b-205">Previously, export was limited to segment entities.</span></span> <span data-ttu-id="8271b-206">さらに、SFTP エクスポートのパフォーマンスにより、SFTP ホストのパフォーマンスに応じて、より多くのデータ量をより短い時間で実行できます。</span><span class="sxs-lookup"><span data-stu-id="8271b-206">Additionally, the performance of the SFTP export allows more data volume in less time, depending on the performance of your SFTP host.</span></span>    
  <span data-ttu-id="8271b-207">詳細については、[SFTP 用コネクタ (プレビュー)](export-sftp.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-207">For more information, see [Connector for SFTP (preview)](export-sftp.md).</span></span>  

#### <a name="segments"></a><span data-ttu-id="8271b-208">セグメント</span><span class="sxs-lookup"><span data-stu-id="8271b-208">Segments</span></span>

- <span data-ttu-id="8271b-209">**機械学習は、メトリックを改善するために提案されたセグメントを強化しました** セグメントを検出して作成する新しい方法が加わりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-209">**Machine learning powered suggested segments to improve metrics** There's a new way do discover and create segments.</span></span> <span data-ttu-id="8271b-210">システムは AI モデルを使用して、すでに追跡している KPI (メジャー) の改善に役立つセグメントを提案します。</span><span class="sxs-lookup"><span data-stu-id="8271b-210">The system uses an AI model to suggest segments that can help improve a KPI (measure) you are already tracking.</span></span> <span data-ttu-id="8271b-211">メジャーまたは別の主要属性に対して選択した属性の影響の程度を示します。</span><span class="sxs-lookup"><span data-stu-id="8271b-211">We show the extent of influence of attributes that you select on a measure or another primary attribute.</span></span> <span data-ttu-id="8271b-212">この情報は、機会を提供する潜在的なセグメントを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8271b-212">This information helps finding potential segments that present opportunities.</span></span>    
  <span data-ttu-id="8271b-213">詳細については、[提案されたセグメント (プレビュー)](suggested-segments.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-213">For more information, see [Suggested segments (preview)](suggested-segments.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="8271b-214">データ統合</span><span class="sxs-lookup"><span data-stu-id="8271b-214">Data unification</span></span>

- <span data-ttu-id="8271b-215">**強化された照合エクスペリエンス** データ統合エリアでは、照合エクスペリエンスが更新されました。</span><span class="sxs-lookup"><span data-stu-id="8271b-215">**Enhanced match experience** In the data unification area, the match experience was updated.</span></span> <span data-ttu-id="8271b-216">照合がどのように機能するかをさらに説明するための詳細な統計など、照合ルールを構成および表示できます。</span><span class="sxs-lookup"><span data-stu-id="8271b-216">It lets you configure and view the match rules, including detailed stats to further explain how matching works.</span></span> <span data-ttu-id="8271b-217">照合ルールを無効にして、構成を保持している間はアクティブでなくなったり、照合ルールをドラッグ アンド ドロップしたりするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8271b-217">There are options to disable a match rule so it's no longer active while retaining the configuration, drag and drop match rules, and more.</span></span>
  <span data-ttu-id="8271b-218">詳細については、「[エンティティの照合](match-entities.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-218">For more information, see [Match entities](match-entities.md).</span></span>

- <span data-ttu-id="8271b-219">**照合プロセスからの重複排除出力は、エンティティとして利用できます** 照合プロセスから出力された重複排除プロセスは、さらに分析するために別のエンティティに書き込まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-219">**Deduplication output from the match process is available as an entity** Deduplication process output from the match process is now written into a separate entity for further analysis.</span></span> <span data-ttu-id="8271b-220">このエンティティは、重複排除プロセスで使用されるフィールドと、勝者レコード、および勝者レコードとマージされる対応代替レコードで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8271b-220">This entity consists of the fields used in the deduplication process and the winner record and the corresponding alternate records that get merged with the winner record.</span></span>
  <span data-ttu-id="8271b-221">詳細については、[エンティティとしての重複排除出力](match-entities.md#deduplication-output-as-an-entity) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-221">For more information, see [Deduplication output as an entity](match-entities.md#deduplication-output-as-an-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="8271b-222">システム管理</span><span class="sxs-lookup"><span data-stu-id="8271b-222">System administration</span></span>

- <span data-ttu-id="8271b-223">**シームレスにデータを Microsoft Dataverse と共有する** Customer Insights 出力を、Microsoft Dataverse マネージド Data Lake を使って Microsoft Dataverse アプリケーションと共有できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8271b-223">**Seamlessly share data to Microsoft Dataverse** You can now share Customer Insights output with Microsoft Dataverse applications using the Microsoft Dataverse Managed Data Lake.</span></span> <span data-ttu-id="8271b-224">Dataverse 環境を Customer Insights と関連付けたら、データ共有を有効にするオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8271b-224">Once you associate a Dataverse environment with Customer Insights, you get the option to enable data sharing.</span></span>
  <span data-ttu-id="8271b-225">詳細については、[環境を管理する](manage-environments.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8271b-225">For more information, see [Manage environments](manage-environments.md).</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]