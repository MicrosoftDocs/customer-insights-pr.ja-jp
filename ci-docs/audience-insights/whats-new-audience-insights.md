---
title: 新しい機能および今後の機能
description: 新機能、改善、およびバグ修正に関する情報。
ms.date: 11/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 07b4bee0445f9cd7d53a37cd405af839feb07ae3
ms.sourcegitcommit: 4004eadac7a65e50e0a409cb925958523c2b6348
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2020
ms.locfileid: "4650010"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a><span data-ttu-id="ec131-103">Dynamics 365 Customer Insights の対象者に関するインサイト機能の新機能</span><span class="sxs-lookup"><span data-stu-id="ec131-103">What's new in the audience insights capability of Dynamics 365 Customer Insights</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ec131-104">最新の更新プログラムについてお知らせします !</span><span class="sxs-lookup"><span data-stu-id="ec131-104">We're excited to announce our newest updates!</span></span> <span data-ttu-id="ec131-105">この記事は、パブリック プレビュー機能、全般的な可用性の強化、毎月の更新プログラム、機能の更新をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="ec131-105">This article summarizes public preview features, general availability enhancements, and feature updates.</span></span> <span data-ttu-id="ec131-106">長期的な機能計画を確認するには、[Dynamics 365 と Power Platform のリリース計画](https://docs.microsoft.com/dynamics365/release-plans/) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ec131-106">To see the long-term feature plans, take a look at the [Dynamics 365 and Power Platform release plans](https://docs.microsoft.com/dynamics365/release-plans/).</span></span>

<span data-ttu-id="ec131-107">次のビデオを見て、過去 6 か月間に予定された機能の詳細を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="ec131-107">You can also watch the following video to learn more about the capabilities planned for the last six months.</span></span>

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

<span data-ttu-id="ec131-108">更新プログラムは地域ベースで配信されます。</span><span class="sxs-lookup"><span data-stu-id="ec131-108">We roll out updates on a region-by-region basis.</span></span> <span data-ttu-id="ec131-109">そのため、特定の地域では、他の地域より先に機能が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec131-109">So certain regions might see features before others.</span></span> <span data-ttu-id="ec131-110">特に指定がない限り、何もする必要はなく、アプリはダウンタイムなしで自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="ec131-110">Unless specified differently, you don't need to take any action and we'll update the app automatically with no downtime.</span></span>

> [!TIP]
> <span data-ttu-id="ec131-111">機能要求と製品に関する提案を送信して投票するには、[Dynamics 365 アプリケーションのアイデア ポータル](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights) に移動してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-111">To submit and vote on feature requests and product suggestions, go to the [Dynamics 365 Application Ideas portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).</span></span>

## <a name="november-2020-updates"></a><span data-ttu-id="ec131-112">2020 年 11 月 の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="ec131-112">November 2020 updates</span></span>

<span data-ttu-id="ec131-113">2020 年 11 月の更新には、いくつかの機能、パフォーマンス アップグレード、およびバグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec131-113">The updates in November 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-november-2020"></a><span data-ttu-id="ec131-114">2020 年 11 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="ec131-114">New and updated features in November 2020</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="ec131-115">データ エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="ec131-115">Data enrichment</span></span>

- <span data-ttu-id="ec131-116">**セキュリティで保護されたファイル転送プロトコル (SFTP) によるカスタム インポートで独自のエンリッチメント データを取り込む**</span><span class="sxs-lookup"><span data-stu-id="ec131-116">**Bring your own enrichment data via Secure File Transfer Protocol (SFTP) custom import**</span></span>
  
  <span data-ttu-id="ec131-117">SFTP によるカスタム インポートを使用すると、データ統合のプロセスを行う必要のないエンリッチメント データをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="ec131-117">SFTP custom import lets you to import enrichment data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="ec131-118">SFTP によるカスタム インポートについて。</span><span class="sxs-lookup"><span data-stu-id="ec131-118">Learn more about SFTP custom import.</span></span>

  <span data-ttu-id="ec131-119">詳細については、[カスタム データで顧客プロファイルを強化する (プレビュー)](enrichment-SFTP-custom-import.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-119">For more information, see [Enrich customer profiles with custom data (preview)](enrichment-SFTP-custom-import.md).</span></span>
 
- <span data-ttu-id="ec131-120">**HERE Technologies の位置データで顧客データを強化する**</span><span class="sxs-lookup"><span data-stu-id="ec131-120">**Enrich your customer data with location data from HERE Technologies**</span></span>

  <span data-ttu-id="ec131-121">HERE Technologies のデータ エンリッチメント サービスを使用すると、住所の正規化、緯度と経度の抽出などにより、顧客のより正確な位置情報を把握できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-121">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span> <span data-ttu-id="ec131-122">HERE Technologies を利用した強化について。</span><span class="sxs-lookup"><span data-stu-id="ec131-122">Learn more about enriching with HERE Technologies.</span></span>

  <span data-ttu-id="ec131-123">詳細については、[HERE Technologies による顧客プロファイルの強化](enrichment-here.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-123">For more information, see [Enrichment of customer profiles with HERE Technologies](enrichment-here.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="ec131-124">データ統合</span><span class="sxs-lookup"><span data-stu-id="ec131-124">Data unification</span></span>

- <span data-ttu-id="ec131-125">**ストレージ アカウントから選択したエンティティとフィールドでデータ プロファイリングを有効にする柔軟性**</span><span class="sxs-lookup"><span data-stu-id="ec131-125">**Flexibility to enable data profiling on selected entities and fields from your storage account**</span></span>

  <span data-ttu-id="ec131-126">データ インジェスト プロセスの一部としてデータ プロファイリングを有効にする、Azure Data Lake ストレージ アカウントで Common Data Model フォルダーのデータ エンティティとフィールドを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-126">You can indicate which data entities and fields from a Common Data Model folder in your Azure Data Lake storage account you want to enable data profiling as part of the data ingestion process.</span></span>

  <span data-ttu-id="ec131-127">詳細については、[Common Data Model フォルダーへの接続](connect-common-data-model.md#connect-to-a-common-data-model-folder) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-127">For more information, see [Connect to a Common Data Model folder](connect-common-data-model.md#connect-to-a-common-data-model-folder).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="ec131-128">拡張性</span><span class="sxs-lookup"><span data-stu-id="ec131-128">Extensibility</span></span>

- <span data-ttu-id="ec131-129">**Google 広告でセグメントをアクティブ化する**</span><span class="sxs-lookup"><span data-stu-id="ec131-129">**Activate your segments through Google Ads**</span></span>

  <span data-ttu-id="ec131-130">セグメントを Google 広告のオーディエンス リストにエクスポートし、それらを使用して Google 検索、Google ディスプレイ ネットワーク、YouTube、Gmail に広告を掲載します。</span><span class="sxs-lookup"><span data-stu-id="ec131-130">Export segments from to Google Ads audience lists and use these lists to advertise on Google Search, Google Display Network, YouTube, and Gmail.</span></span> <span data-ttu-id="ec131-131">Google 広告でセグメントをアクティブ化する方法について。</span><span class="sxs-lookup"><span data-stu-id="ec131-131">Learn more about activating your segments through Google Ads.</span></span>

  <span data-ttu-id="ec131-132">詳細については、[Google 広告用コネクタ](export-google-ads.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-132">For more information, see [Connector for Google Ads](export-google-ads.md).</span></span>

- <span data-ttu-id="ec131-133">**Marketo でセグメントをアクティブ化する**</span><span class="sxs-lookup"><span data-stu-id="ec131-133">**Activate your segments through Marketo**</span></span>

  <span data-ttu-id="ec131-134">セグメントを Marketo オーディエンスにエクスポートし、これらのオーディエンスをマーケティングの自動化に使用します。</span><span class="sxs-lookup"><span data-stu-id="ec131-134">Export segments to Marketo audiences and use these audiences for marketing automation.</span></span> <span data-ttu-id="ec131-135">Marketo でセグメントをアクティブ化する方法について。</span><span class="sxs-lookup"><span data-stu-id="ec131-135">Learn more about activating your segments through Marketo.</span></span> 

  <span data-ttu-id="ec131-136">詳細については、[Marketo 用コネクタ](export-marketo.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-136">For more information, see [Connector for Marketo](export-marketo.md).</span></span>

- <span data-ttu-id="ec131-137">**DotDigital でセグメントをアクティブ化する**</span><span class="sxs-lookup"><span data-stu-id="ec131-137">**Activate your segments through DotDigital**</span></span>

  <span data-ttu-id="ec131-138">セグメントを DotDigital にエクスポートし、マーケティング目的で使用します。</span><span class="sxs-lookup"><span data-stu-id="ec131-138">Export segments to DotDigital and use them for marketing purposes.</span></span> <span data-ttu-id="ec131-139">DotDigital でセグメントをアクティブ化する方法について。</span><span class="sxs-lookup"><span data-stu-id="ec131-139">Learn more about activating your segments through DotDigital.</span></span> 

  <span data-ttu-id="ec131-140">詳細については、[DotDigital 用コネクタ](export-dotdigital.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-140">For more information, see [Connector for DotDigital](export-dotdigital.md).</span></span>

#### <a name="predictions"></a><span data-ttu-id="ec131-141">予測</span><span class="sxs-lookup"><span data-stu-id="ec131-141">Predictions</span></span>

- <span data-ttu-id="ec131-142">**トランザクション解約を予測する**</span><span class="sxs-lookup"><span data-stu-id="ec131-142">**Predict transactional churn**</span></span>

  <span data-ttu-id="ec131-143">トランザクション解約予測機能を使用すると、データ サイエンティストの助けを借りずに、顧客が製品やサービスの購入を停止する可能性を予測できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-143">The transaction churn prediction feature enables you, without the help of a data scientist, to predict the likelihood of a customer to stop purchasing products or services.</span></span>  <span data-ttu-id="ec131-144">予測スコアを使用すると、顧客価値など、顧客に関する他の情報を組み合わせて、解約リスクの高い顧客または価値の高い顧客のセグメントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-144">Using the prediction score, you can combine other information about your customers, like customer value, to create segments of high churn risk or high value customers.</span></span> <span data-ttu-id="ec131-145">このセグメントを使用して、マーケティング活動、カスタマー サポート、およびその他のシナリオを通じて顧客を直接ターゲットにして、解約リスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="ec131-145">Use this segment to directly target customers through marketing activities, customer support, and other scenarios to reduce churn risk.</span></span>
 
  <span data-ttu-id="ec131-146">解約の定義をビジネスに固有の時間ベース ウィンドウとして構成し、顧客が解約されたとみなされる時期を定義します。</span><span class="sxs-lookup"><span data-stu-id="ec131-146">Configure the definition of churn as a time-based window specific to your business and define when customers are considered churned.</span></span> <span data-ttu-id="ec131-147">たとえば、食料品店は、過去 30 日間何も購入していない場合、顧客が解約したと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="ec131-147">For example, a grocery store may want to consider a customer churned if they have not purchased anything in the past 30 days.</span></span>
 
  <span data-ttu-id="ec131-148">予測の作成を続けると、必要なデータが案内され、顧客の解約を予測するために必要なフィールドにビジネスに関するデータをマッピングできるようになります。</span><span class="sxs-lookup"><span data-stu-id="ec131-148">As you continue creating the prediction, we'll guide you what data is needed, and enable you to map data about your business to fields required to predict churn for your customers.</span></span> <span data-ttu-id="ec131-149">また、変化するビジネス状況に適応するために、システム内の新しい情報に基づいてモデルを再トレーニングするスケジュールを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ec131-149">You can also set a schedule to retrain the model based on new information in your system to adapt to changing business circumstances.</span></span>
 
  <span data-ttu-id="ec131-150">詳細については、[トランザクション解約予測 (プレビュー)](predict-transactional-churn.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-150">For more information, see [Transactional churn prediction (preview)](predict-transactional-churn.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="ec131-151">システム管理者</span><span class="sxs-lookup"><span data-stu-id="ec131-151">System administration</span></span>

- <span data-ttu-id="ec131-152">**環境のリセット**</span><span class="sxs-lookup"><span data-stu-id="ec131-152">**Reset environment**</span></span>

  <span data-ttu-id="ec131-153">選択したインスタンスの環境内のすべてをリセットして、最初からやり直します。</span><span class="sxs-lookup"><span data-stu-id="ec131-153">Reset everything in an environment of a selected instance to start fresh.</span></span>

  <span data-ttu-id="ec131-154">詳細については、[既存の環境のリセット](manage-environments.md#reset-an-existing-environment) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-154">For more information, see [Reset an existing environment](manage-environments.md#reset-an-existing-environment).</span></span>


- <span data-ttu-id="ec131-155">**サービス プリンシパルを使用して、Azure Data Lake ストレージ アカウントに接続する**</span><span class="sxs-lookup"><span data-stu-id="ec131-155">**Connect to your Azure Data Lake storage account using a service principal**</span></span>

  <span data-ttu-id="ec131-156">Azure サービス プリンシパルを使用して、ストレージ アカウントにデータ出力を書き込み、ストレージア カウントからデータを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="ec131-156">Write data output to and read data from your storage account using an Azure service principal.</span></span> <span data-ttu-id="ec131-157">既存のストレージ アカウント接続は、引き続きアカウント キーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-157">Existing storage account connections can continue to use the account key.</span></span> <span data-ttu-id="ec131-158">また、今後サービス プリンシパルを使用するためのアップグレード オプションも提供します。</span><span class="sxs-lookup"><span data-stu-id="ec131-158">They also offer an upgrade option to use the service principal moving forward.</span></span> <span data-ttu-id="ec131-159">新しい接続は、ストレージ アカウントのサービス プリンシパル認証方法に基づきます。</span><span class="sxs-lookup"><span data-stu-id="ec131-159">New connections will be based on the service principal authentication method for your storage account.</span></span>

  <span data-ttu-id="ec131-160">詳細については、[対象者に関するインサイトの Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-160">For more information, see [Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights](connect-service-principal.md).</span></span>

## <a name="october-2020-updates"></a><span data-ttu-id="ec131-161">2020 年 10 月の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="ec131-161">October 2020 updates</span></span>

<span data-ttu-id="ec131-162">2020 年 10 月の更新には、いくつかの機能、パフォーマンス アップグレード、およびバグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec131-162">The updates in October 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-october-2020"></a><span data-ttu-id="ec131-163">2020 年 10 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="ec131-163">New and updated features in October 2020</span></span>

#### <a name="extensibility"></a><span data-ttu-id="ec131-164">拡張性</span><span class="sxs-lookup"><span data-stu-id="ec131-164">Extensibility</span></span>

- <span data-ttu-id="ec131-165">**Mailchimp にエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="ec131-165">**Export to Mailchimp**</span></span>

<span data-ttu-id="ec131-166">Mailchimp の既存のオーディエンス リストにセグメントをエクスポートして、顧客にパーソナライズされた電子メール エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ec131-166">Export segments to existing audience lists in Mailchimp to provide a personalized email experience for your customers.</span></span>

<span data-ttu-id="ec131-167">詳細については、[Mailchimp 用コネクタ](export-mailchimp.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-167">For more information, see [Connector for Mailchimp](export-mailchimp.md).</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="ec131-168">データ エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="ec131-168">Data enrichment</span></span>

- <span data-ttu-id="ec131-169">**照合エンティティのソース レコードを重複排除する**</span><span class="sxs-lookup"><span data-stu-id="ec131-169">**Deduplicate the source records in a Match entity**</span></span>

<span data-ttu-id="ec131-170">重複レコードを識別するために、照合プロセスで使用されるエンティティに重複排除ルールを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec131-170">Specify deduplication rules on entities used in the match process to identify duplicate records.</span></span> <span data-ttu-id="ec131-171">それらを 1 つのレコードにマージし、すべてのソース レコードをこのマージされたレコードにリンクします。</span><span class="sxs-lookup"><span data-stu-id="ec131-171">Merge them into one record and link all the source records to this merged record.</span></span> <span data-ttu-id="ec131-172">この重複排除されたレコードは、エンティティ間の照合プロセスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="ec131-172">This deduplicated record will then be used in the cross-entity matching process.</span></span>

<span data-ttu-id="ec131-173">詳細については、[照合エンティティで重複排除を定義する](match-entities.md#define-deduplication-on-a-match-entity) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-173">For more information, see [Define deduplication on a match entity](match-entities.md#define-deduplication-on-a-match-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="ec131-174">システム管理者</span><span class="sxs-lookup"><span data-stu-id="ec131-174">System administration</span></span>

- <span data-ttu-id="ec131-175">**オーケストレーション: マージの新しい更新オプション**</span><span class="sxs-lookup"><span data-stu-id="ec131-175">**Orchestration: New refresh option in Merge**</span></span>

<span data-ttu-id="ec131-176">これまで、マージ プロセスを実行すると、システムはマージと後続のプロセスに依存する、すべてのダウンストリーム プロセスを実行していました。</span><span class="sxs-lookup"><span data-stu-id="ec131-176">Until today, when you run the merge process, the system ran all the downstream processes that depend on merge and subsequent processes.</span></span> <span data-ttu-id="ec131-177">これで、セグメントやメジャーなどのダウンストリーム プロセスで使用する前に、マージ プロセス (統合された顧客エンティティ) の出力を確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ec131-177">You can now verify the output of the merge process (the unified customer entity) before using it in downstream processing like segments or measures.</span></span>
<span data-ttu-id="ec131-178">マージ ページで、マージ ステップのみを実行し、このプロセスのみを実行することを選択できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ec131-178">On the merge page, you can now choose to run only the merge step and run only this process.</span></span> <span data-ttu-id="ec131-179">ダウンストリーム プロセスもすべて更新するには、マージの実行とダウンストリーム プロセスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-179">To refresh all the downstream processes too, you can choose run merge and downstream processes.</span></span> 

## <a name="september-2020-updates"></a><span data-ttu-id="ec131-180">2020 年 9 月の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="ec131-180">September 2020 updates</span></span>

<span data-ttu-id="ec131-181">2020 年 9 月の更新には、いくつかの機能、パフォーマンスのアップグレード、バグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec131-181">The updates in September 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-september-2020"></a><span data-ttu-id="ec131-182">2020 年 9 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="ec131-182">New and updated features in September 2020</span></span>

#### <a name="activities"></a><span data-ttu-id="ec131-183">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="ec131-183">Activities</span></span>

- <span data-ttu-id="ec131-184">**属性セマンティクスのインテリジェントな予測**</span><span class="sxs-lookup"><span data-stu-id="ec131-184">**Intelligent prediction of attribute semantics**</span></span>

<span data-ttu-id="ec131-185">この新機能は、データ統合プロセスに渡される入力属性のセマンティック タイプを予測します。</span><span class="sxs-lookup"><span data-stu-id="ec131-185">This new feature predicts the semantic types of input attributes that are passed on to the data unification process.</span></span> <span data-ttu-id="ec131-186">これは精度を向上させ、時間を節約する機械学習モデルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="ec131-186">It uses machine learning models that improve accuracy and save time.</span></span>

#### <a name="enrichments"></a><span data-ttu-id="ec131-187">エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="ec131-187">Enrichments</span></span>

- <span data-ttu-id="ec131-188">**説明による統計情報のエンリッチメント**</span><span class="sxs-lookup"><span data-stu-id="ec131-188">**Demographics enrichment from Experian**</span></span>

<span data-ttu-id="ec131-189">Experian の統計情報のエンリッチメントがプレビューで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ec131-189">The demographics enrichment from Experian is now available in preview.</span></span> <span data-ttu-id="ec131-190">Experian は、消費者および企業の信用調査およびマーケティング サービスの世界的リーダーです。</span><span class="sxs-lookup"><span data-stu-id="ec131-190">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="ec131-191">[Experian のデータ エンリッチメント サービス](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) を使用することで、世帯サイズや収入などの統計情報データで顧客プロファイルをエンリッチさせ、顧客をより深く理解することができます。</span><span class="sxs-lookup"><span data-stu-id="ec131-191">With [Experian’s data enrichment services](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

<span data-ttu-id="ec131-192">この機能を使用するには、有効な Experian サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="ec131-192">To use this feature, you must have an active Experian subscription.</span></span>

<span data-ttu-id="ec131-193">詳細については、[Experian の統計情報で顧客プロファイルをエンリッチする](enrichment-experian.md) を参照してください</span><span class="sxs-lookup"><span data-stu-id="ec131-193">For more information, see [Enrich customer profiles with demographics from Experian](enrichment-experian.md)</span></span>


#### <a name="system-administration"></a><span data-ttu-id="ec131-194">システム管理者</span><span class="sxs-lookup"><span data-stu-id="ec131-194">System administration</span></span>

- <span data-ttu-id="ec131-195">**タスクの詳細ペイン**</span><span class="sxs-lookup"><span data-stu-id="ec131-195">**Task details pane**</span></span>

<span data-ttu-id="ec131-196">タスクの詳細ペインでは、システムが実行するタスクの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-196">The task details pane enables you to see details about tasks that the system runs.</span></span> <span data-ttu-id="ec131-197">これは、構成の問題を特定し、解決策を見つけるための便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="ec131-197">It's a handy way to identify issues with the configuration and find solutions.</span></span>
<span data-ttu-id="ec131-198">エラー メッセージを確認して、潜在的な問題に対処する方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-198">Review the error messages see how you address potential issues.</span></span>
 
- <span data-ttu-id="ec131-199">**追加ページに追加された情報を処理する**</span><span class="sxs-lookup"><span data-stu-id="ec131-199">**Processing information added to additional pages**</span></span>

<span data-ttu-id="ec131-200">この改善により、**エンティティ** と **顧客** ページでエンティティのステータスに関する情報が追加されます。</span><span class="sxs-lookup"><span data-stu-id="ec131-200">This improvement adds information about the status of your entities on the **Entities** and **Customers** page.</span></span>
 
<span data-ttu-id="ec131-201">さらに、これらの両方のページで、プロセスの進行状況に関する詳細とタスクの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-201">Additionally, you can find details about the progress of processes, along with the task details, on both of these pages.</span></span>

- <span data-ttu-id="ec131-202">**システム ステータス ページの改善**</span><span class="sxs-lookup"><span data-stu-id="ec131-202">**Improvements to system status page**</span></span>

<span data-ttu-id="ec131-203">データのエクスポートを確認する際の、**システム** > **状態** のステータス詳細テーブルの構造を改善しました。</span><span class="sxs-lookup"><span data-stu-id="ec131-203">We improved the structure of the status details table on **System** > **Status** when reviewing data exports.</span></span>
 
<span data-ttu-id="ec131-204">さらに、**詳細** 列のエラーがより詳細でアクション可能なものになりました。</span><span class="sxs-lookup"><span data-stu-id="ec131-204">Additionally, errors in the **Details** column are now more detailed and actionable.</span></span> 
 
- <span data-ttu-id="ec131-205">**キャンセルすると、ジョブが前の状態に戻ります**</span><span class="sxs-lookup"><span data-stu-id="ec131-205">**Cancel reverts job back to previous state**</span></span>

<span data-ttu-id="ec131-206">たとえば、一致プロセスでタスクをキャンセルすると、タスクは最新の状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="ec131-206">When you cancel a task, for example, in the match process, it will revert back to its latest state.</span></span> <span data-ttu-id="ec131-207">たとえば、一致プロセスが昨日完了し、今日キャンセルした場合、昨日の成功状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="ec131-207">For example, if the Match process completed yesterday and you cancel it today, it will revert to yesterday's successful state.</span></span>


## <a name="august-2020-updates"></a><span data-ttu-id="ec131-208">2020 年 8 月の更新</span><span class="sxs-lookup"><span data-stu-id="ec131-208">August 2020 updates</span></span>

<span data-ttu-id="ec131-209">2020 年 8 月の更新には、いくつかの機能、パフォーマンスのアップグレード、バグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec131-209">The updates in August 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-august-2020"></a><span data-ttu-id="ec131-210">2020 年 8 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="ec131-210">New and updated features in August 2020</span></span>

#### <a name="data-unification"></a><span data-ttu-id="ec131-211">データ統合</span><span class="sxs-lookup"><span data-stu-id="ec131-211">Data unification</span></span>

- <span data-ttu-id="ec131-212">**データ統合中のマップ ステージのエクスペリエンスの向上**</span><span class="sxs-lookup"><span data-stu-id="ec131-212">**Improved experience for the map stage during data unification**</span></span>

  <span data-ttu-id="ec131-213">データ統合プロセスのマップ段階でのエクスペリエンスにより、エンティティ、属性を選択し、よりシームレスな方法でセマンティクスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-213">The experience to the map stage in the data unification process lets you select entities, attributes, and define semantics in a more seamless way.</span></span>

  <span data-ttu-id="ec131-214">変更内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ec131-214">The changes include:</span></span>
  
  - <span data-ttu-id="ec131-215">エンティティとフィールドを追加に必要な対話がより少なく</span><span class="sxs-lookup"><span data-stu-id="ec131-215">fewer interactions required to add entities and fields</span></span>
  - <span data-ttu-id="ec131-216">マップ ページの検索機能の改善</span><span class="sxs-lookup"><span data-stu-id="ec131-216">improved search capabilities on the map page</span></span>
  - <span data-ttu-id="ec131-217">提案されたフィールド タイプの視覚的かつ簡単な識別</span><span class="sxs-lookup"><span data-stu-id="ec131-217">visual and easy identification of the suggested field type</span></span>

#### <a name="enrichment"></a><span data-ttu-id="ec131-218">エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="ec131-218">Enrichment</span></span>

- <span data-ttu-id="ec131-219">**その他の市場で関心アフィニティー エンリッチメントが利用可能に**</span><span class="sxs-lookup"><span data-stu-id="ec131-219">**Interest affinities enrichment available in additional markets**</span></span>

  <span data-ttu-id="ec131-220">関心アフィニティー エンリッチメントの利用可能を、米国を超えて、カナダ、オーストラリア、英国、フランス、ドイツの 5 つの追加市場に拡大しています。</span><span class="sxs-lookup"><span data-stu-id="ec131-220">We're extending the availability of the interest affinities enrichment beyond the United States to five additional markets: Canada, Australia, United Kingdom, France, and Germany.</span></span> <span data-ttu-id="ec131-221">この拡張機能を使用すると、これらの市場に適用可能な追加の関心事で顧客データを充実させることができます。</span><span class="sxs-lookup"><span data-stu-id="ec131-221">With this extension, you can enrich your customer data with additional interests applicable to these markets.</span></span> <span data-ttu-id="ec131-222">また、Microsoft Graph のローカルの独自データを使用して、これらの市場にある顧客プロファイルを充実させます。</span><span class="sxs-lookup"><span data-stu-id="ec131-222">We'll also enrich your customer profiles that are located in these markets by using local proprietary data from Microsoft Graph.</span></span>
  <span data-ttu-id="ec131-223">詳細については、[ブランドと興味のアフィニティで顧客プロファイルを強化する](enrichment-microsoft-graph.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-223">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md)</span></span>


## <a name="july-2020-updates"></a><span data-ttu-id="ec131-224">2020 年 7 月の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="ec131-224">July 2020 updates</span></span>

<span data-ttu-id="ec131-225">2020 年 7 月の更新には、いくつかの機能、パフォーマンスのアップグレード、およびバグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec131-225">The updates in July 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-july-2020"></a><span data-ttu-id="ec131-226">2020 年 7 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="ec131-226">New and updated features in July 2020</span></span>

#### <a name="extensibility"></a><span data-ttu-id="ec131-227">拡張性</span><span class="sxs-lookup"><span data-stu-id="ec131-227">Extensibility</span></span>

- <span data-ttu-id="ec131-228">**完了した統合プロセスの Power Automate トリガー**</span><span class="sxs-lookup"><span data-stu-id="ec131-228">**Power Automate trigger for completed unification process**</span></span>

  <span data-ttu-id="ec131-229">Power Automate のトリガーを拡張し、統合プロセス (マップ、一致、マージ) の更新が完了したときに通知またはアクションを作成できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="ec131-229">We have extended our triggers for Power Automate and let you create a notification or action when a refresh of the unification process (map, match, merge) is completed.</span></span>    
  <span data-ttu-id="ec131-230">詳細については、[Power Automate コネクタ](export-power-automate.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-230">For more information, see [Power Automate connector](export-power-automate.md)</span></span>

#### <a name="enrichment"></a><span data-ttu-id="ec131-231">エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="ec131-231">Enrichment</span></span>

- <span data-ttu-id="ec131-232">**追加の市場で利用可能なブランド アフィニティのエンリッチメント**</span><span class="sxs-lookup"><span data-stu-id="ec131-232">**Brand affinities enrichment available in additional markets**</span></span>

  <span data-ttu-id="ec131-233">ブランド アフィニティのエンリッチメントの可用性を、米国だけでなく、カナダ、オーストラリア、英国、フランス、ドイツの 5 つの追加市場に拡大しています。</span><span class="sxs-lookup"><span data-stu-id="ec131-233">We're extending the availability of the brand affinities enrichment beyond the United States to five additional markets: Canada, Australia, United Kingdom, France, and Germany.</span></span> <span data-ttu-id="ec131-234">この拡張機能を使用すると、これらの市場のローカル ブランドで顧客データを充実させることができます。</span><span class="sxs-lookup"><span data-stu-id="ec131-234">With this extension, you can enrich your customer data with local brands in these markets.</span></span> <span data-ttu-id="ec131-235">また、Microsoft Graph のローカルの独自データを使用して、これらの市場にある顧客プロファイルを充実させます。</span><span class="sxs-lookup"><span data-stu-id="ec131-235">We'll also enrich your customer profiles that are located in these markets by using local proprietary data from Microsoft Graph.</span></span>
  <span data-ttu-id="ec131-236">詳細については、[ブランドと興味のアフィニティで顧客プロファイルを強化する](enrichment-microsoft-graph.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-236">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md)</span></span>

## <a name="june-2020-updates"></a><span data-ttu-id="ec131-237">2020 年 6 月の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="ec131-237">June 2020 updates</span></span>

<span data-ttu-id="ec131-238">2020 年 6 月の更新には、いくつかの機能、パフォーマンスのアップグレード、およびバグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec131-238">The updates in June 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-june-2020"></a><span data-ttu-id="ec131-239">2020 年 6 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="ec131-239">New and updated features in June 2020</span></span>

#### <a name="enrichment"></a><span data-ttu-id="ec131-240">エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="ec131-240">Enrichment</span></span>

- <span data-ttu-id="ec131-241">**Leadspace からの企業データの充実**</span><span class="sxs-lookup"><span data-stu-id="ec131-241">**Enrichment with company data from Leadspace**</span></span>
  
  <span data-ttu-id="ec131-242">Leadspace から関連する企業データを検索するために使用される統合顧客プロファイルのフィールドを定義します。</span><span class="sxs-lookup"><span data-stu-id="ec131-242">Define fields in unified customer profiles that are used to look up related company data from Leadspace.</span></span> <span data-ttu-id="ec131-243">エンリッチ プロセスを実行した後、B2B プロファイルは、会社の規模、場所、業界などの追加の属性で強化されます。</span><span class="sxs-lookup"><span data-stu-id="ec131-243">After running the enrichment process, B2B profiles are enriched with additional attributes including company size, location, industry, and more.</span></span>    
  <span data-ttu-id="ec131-244">このコラボレーションにより、サードパーティ サービスからの入力によりデータの品質を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="ec131-244">This collaboration allows you to improve the quality of your data with input from third-party services.</span></span> <span data-ttu-id="ec131-245">このエンリッチメントを使用するには、B2B 企業データにアクセスするための Leadspace からのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ec131-245">To use this enrichment, you'll need a license from Leadspace to access its B2B company data.</span></span> <span data-ttu-id="ec131-246">システムはそのライセンスを使用して、データを継続的に強化します。</span><span class="sxs-lookup"><span data-stu-id="ec131-246">The system will use that license to keep your data enriched continuously.</span></span>    
  <span data-ttu-id="ec131-247">詳細については、[Leadspace による企業プロファイルのエンリッチメント](enrichment-leadspace.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-247">For more information, see [Enrichment of company profiles with Leadspace](enrichment-leadspace.md).</span></span>

- <span data-ttu-id="ec131-248">**エンリッチメント ハブ ページ**</span><span class="sxs-lookup"><span data-stu-id="ec131-248">**Enrichment hub page**</span></span>

  <span data-ttu-id="ec131-249">ファーストパーティおよびサードパーティのエンリッチメント プロバイダーから利用可能なすべてのデータ エンリッチメントは、同じ場所で構成されます。</span><span class="sxs-lookup"><span data-stu-id="ec131-249">All available data enrichment from first- and third-party enrichment providers gets configured in the same place.</span></span> <span data-ttu-id="ec131-250">データ エンリッチメントの構成は、共通の場所から管理されるシームレスなエクスペリエンスです。</span><span class="sxs-lookup"><span data-stu-id="ec131-250">Configuring data enrichment is a seamless experience that is managed from a common place.</span></span>    
  <span data-ttu-id="ec131-251">詳細については、[顧客プロファイルのエンリッチメント](enrichment-hub.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-251">For more information, see [Enrichment for customer profiles](enrichment-hub.md).</span></span>

- <span data-ttu-id="ec131-252">**個別のブランドと関心のアフィニティのエンリッチメント**</span><span class="sxs-lookup"><span data-stu-id="ec131-252">**Separate brand and interest affinity enrichment**</span></span>

  <span data-ttu-id="ec131-253">ブランドと興味のアフィニティが、2 つの独立したエンリッチメントとして利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ec131-253">The brands and interests affinities are now available as two independent enrichments.</span></span> <span data-ttu-id="ec131-254">エンリッチメントを分離すると、ビジネス要件やニーズに応じて、個別に設定および管理する柔軟性が得られます。</span><span class="sxs-lookup"><span data-stu-id="ec131-254">Separated enrichments give you the flexibility to configure and manage them individually, depending on your business requirements or needs.</span></span>    
  <span data-ttu-id="ec131-255">詳細については、[ブランドと興味のアフィニティで顧客プロファイルを強化する](enrichment-microsoft-graph.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-255">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="ec131-256">拡張性</span><span class="sxs-lookup"><span data-stu-id="ec131-256">Extensibility</span></span>

- <span data-ttu-id="ec131-257">**Dynamics 365 Customer Card Add-in の統合アクティビティのクリック可能な URL**</span><span class="sxs-lookup"><span data-stu-id="ec131-257">**Clickable URLs for unified activities on the Dynamics 365 Customer Card Add-in**</span></span>

  <span data-ttu-id="ec131-258">顧客カード アドインの統合アクティビティは、アクティビティの構成中にそのような URL が定義されている場合、クリック可能な URL を表示するようになりました。</span><span class="sxs-lookup"><span data-stu-id="ec131-258">The unified activities in the Customer Card Add-in are now showing clickable URLs if such URLs have been defined during the configuration of activities.</span></span>    
  <span data-ttu-id="ec131-259">詳細については、[顧客カード アドイン](customer-card-add-in.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-259">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="ec131-260">**Dynamics 365 Customer カード アドインで利用できるブランドと興味のアフィニティ**</span><span class="sxs-lookup"><span data-stu-id="ec131-260">**Brand and interest affinities available on the Dynamics 365 Customer Card Add-in**</span></span>

  <span data-ttu-id="ec131-261">Dynamics 365 Customer カード アドインの新しいコントロールを使用すると、Dynamics 365 の顧客エンゲージメント アプリの連絡先にブランドと興味のエンリッチメントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-261">A new control on the Dynamics 365 Customer Card Add-in lets you show brand and interest enrichments on your contacts in customer engagement apps in Dynamics 365.</span></span>    
  <span data-ttu-id="ec131-262">詳細については、[顧客カード アドイン](customer-card-add-in.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-262">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="ec131-263">**追加の Power Automate トリガー**</span><span class="sxs-lookup"><span data-stu-id="ec131-263">**Additional Power Automate triggers**</span></span>

  <span data-ttu-id="ec131-264">Power Automate のトリガーを延長し、次のトリガーを追加しました。</span><span class="sxs-lookup"><span data-stu-id="ec131-264">We have extended our triggers for Power Automate and added the following triggers:</span></span>
  - <span data-ttu-id="ec131-265">自動完全更新 (データソース、統合、セグメント、メジャー、エクスポート) が完了したときに通知を受け取るか、アクションを実行する</span><span class="sxs-lookup"><span data-stu-id="ec131-265">Get a notification or perform an action when an automated full refresh (data sources, unification, segments, measures, exports) completes</span></span>
  - <span data-ttu-id="ec131-266">ビジネス指標のしきい値を定義します。</span><span class="sxs-lookup"><span data-stu-id="ec131-266">Define a threshold for a business measure.</span></span> <span data-ttu-id="ec131-267">たとえば、定義されたしきい値を超えたときに送信される通知を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-267">For example, you can create a notification that gets sent when the defined threshold is passed.</span></span> <span data-ttu-id="ec131-268">さらに、トリガーは Power Automate でより複雑なワークフローを構築できる情報をもたらします。</span><span class="sxs-lookup"><span data-stu-id="ec131-268">Additionally, the trigger brings information that allows you to build more complex workflows in Power Automate.</span></span>    
  <span data-ttu-id="ec131-269">詳細については、[Power Automate コネクタ](export-power-automate.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-269">For more information, see [Power Automate connector](export-power-automate.md)</span></span>

- <span data-ttu-id="ec131-270">**Facebook 広告マネージャーにエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="ec131-270">**Export to Facebook Ads Manager**</span></span>
  
  <span data-ttu-id="ec131-271">この機能を使用すると、セグメントを Facebook 広告マネージャーにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="ec131-271">This capability lets you export segments to Facebook Ads Manager.</span></span> <span data-ttu-id="ec131-272">セグメントはカスタム オーディエンスとしてエクスポートされ、Facebook マーケティング キャンペーンや広告で統合顧客プロファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="ec131-272">Segments are exported as custom audiences to use unified customer profiles in Facebook marketing campaigns and ads.</span></span> <span data-ttu-id="ec131-273">カスタム対象者は、Facebook 広告マネージャーを介して Instagram でキャンペーンを作成するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-273">The custom audiences are also usable to create campaigns on Instagram through Facebook Ads Manager.</span></span>    
  <span data-ttu-id="ec131-274">詳細については、[Facebook広告マネージャーのコネクタ](export-facebook.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-274">For more information, see [Connector for Facebook Ads Manager](export-facebook.md).</span></span>

#### <a name="predictions"></a><span data-ttu-id="ec131-275">予測</span><span class="sxs-lookup"><span data-stu-id="ec131-275">Predictions</span></span>

- <span data-ttu-id="ec131-276">**サブスクリプション離反予測**</span><span class="sxs-lookup"><span data-stu-id="ec131-276">**Subscription churn prediction**</span></span>

  <span data-ttu-id="ec131-277">ガイド式のエクスペリエンスに従って、クラウド サービス、顧客メンバーシップ、その他のセクターなどのサブスクリプション エリアに離反予測を作成します。</span><span class="sxs-lookup"><span data-stu-id="ec131-277">Follow a guided experience to create churn prediction in subscription areas like cloud services, customer membership, and other sectors.</span></span> 

  <span data-ttu-id="ec131-278">サブスクリプション離反予測機能を使用すると、データ サイエンティストに依頼することなく、顧客がサブスクリプション ベースの製品またはサービスの使用を停止する可能性を予測できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-278">The subscription churn prediction feature enables you to predict the likelihood of a customer stopping the use of subscription-based products or services without engaging a data scientist.</span></span> <span data-ttu-id="ec131-279">予測スコアを使用すると、顧客に関する他の情報を組み合わせて、離反リスクの高いセグメントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-279">Using the prediction score, you can combine other information about your customers to create segments of high churn risk.</span></span> <span data-ttu-id="ec131-280">このセグメントのおかげで、マーケティング、顧客サポート、およびその他のシナリオで顧客を直接ターゲットにして、特定の顧客の解約のリスクを減らし、収益を改善し、コストを削減することができます。</span><span class="sxs-lookup"><span data-stu-id="ec131-280">With the help of this segment, you can directly target customers in marketing, customer support, and other scenarios to reduce the risk of churn for specific customers to improve revenue and reduce cost.</span></span>

  <span data-ttu-id="ec131-281">エクスペリエンス内で、離反の定義をビジネスに固有の時間ベースのウィンドウとして構成できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-281">Within the experience, you can configure the definition of churn as a time-based window specific to your business.</span></span> <span data-ttu-id="ec131-282">たとえば、月単位のサブスクリプション プロセスがあるビデオ ストリーミング ビジネスでは、サブスクリプションの有効期限が切れてから 15 日後に顧客が解約したと見なす場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec131-282">For example, a video streaming business that has a monthly subscription process might want to consider a customer to have churned after 15 days after the expiration of their subscription.</span></span>

  <span data-ttu-id="ec131-283">予測を続けると、どのデータが必要かがわかり、顧客のチャーンの予測に必要なフィールドにビジネスに関するデータをマッピングできるようになります。</span><span class="sxs-lookup"><span data-stu-id="ec131-283">As you continue through the prediction, we'll guide you through what data is needed, and enable you to map data about your business to fields required to predict churn for your customers.</span></span> <span data-ttu-id="ec131-284">ビジネス情報の変化に応じて、変化するビジネス環境に適応するためにシステムの新しい情報を再トレーニングするスケジュールを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ec131-284">As business information changes, you can also set a schedule to retrain on new information in your system to adapt to changing business circumstances.</span></span>    
  <span data-ttu-id="ec131-285">詳細については、[サブスクリプション離反予測 (プレビュー)](predict-subscription-churn.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-285">For more information, see [Subscription churn prediction (preview)](predict-subscription-churn.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="ec131-286">セグメント</span><span class="sxs-lookup"><span data-stu-id="ec131-286">Segments</span></span>

- <span data-ttu-id="ec131-287">**類似する顧客を見つける**</span><span class="sxs-lookup"><span data-stu-id="ec131-287">**Find similar customers**</span></span>
  
  <span data-ttu-id="ec131-288">人工知能を使用して、顧客ベースで同様の顧客を見つけます。</span><span class="sxs-lookup"><span data-stu-id="ec131-288">Find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="ec131-289">二項分類機械学習モデルは、拡張セグメントの顧客に類似性スコアを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ec131-289">A binary classification machine learning model assigns a similarity score to customers in the expanded segment.</span></span> <span data-ttu-id="ec131-290">このスコアは、ソース セグメント内の顧客との類似性に基づいています。</span><span class="sxs-lookup"><span data-stu-id="ec131-290">The score is based on the similarity to customers in the source segment.</span></span> <span data-ttu-id="ec131-291">類似性スコアに応じて、新しく作成されたセグメントに顧客プロファイルが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ec131-291">Depending on the similarity score, customer profiles are added to a newly created segment.</span></span>

  <span data-ttu-id="ec131-292">デジタル マーケティングで類似モデルと呼ばれることもあります。AI モデルを使用して、追加の属性を考慮に入れることにより、顧客の別のセグメントに類似する顧客を見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ec131-292">Sometimes referred to as lookalike modeling in digital marketing, it uses an AI model to help find customers who are similar to another segment of your customers by factoring in additional attributes.</span></span> <span data-ttu-id="ec131-293">これにより、属性を選択できるだけでなく、この新しいセグメントに含める必要のある顧客の最大数を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ec131-293">It not only allows you to pick the attributes but also allows you to specify the maximum number of customers who should be in this new segment.</span></span> <span data-ttu-id="ec131-294">AI モデルは、選択した属性に基づいて各顧客の類似度スコアを計算し、平均類似度スコアが高い顧客を見つけます。</span><span class="sxs-lookup"><span data-stu-id="ec131-294">The AI model will then compute similarity scores for each customer based on your selected attributes and find customers with the higher average similarity score.</span></span> <span data-ttu-id="ec131-295">結果のセグメントには、元のセグメントの顧客に類似する顧客が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ec131-295">The resulting segment will include customers who look similar to the customer in your original segment.</span></span>    
  <span data-ttu-id="ec131-296">詳細については、[類似顧客](find-similar-customer-segments.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-296">For more information, see [Similar Customers](find-similar-customer-segments.md).</span></span>

- <span data-ttu-id="ec131-297">**セグメントの重複と差別化要因**</span><span class="sxs-lookup"><span data-stu-id="ec131-297">**Segment overlap and differentiators**</span></span>

  <span data-ttu-id="ec131-298">セグメントの重複により、2 つ以上のセグメントに共通する顧客の数と数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-298">Segment overlap lets you see how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="ec131-299">たとえば、高支出のセグメントが満足度の高い顧客セグメントとどのようにオーバーラップするか、離反する顧客セグメントが満足度の低い顧客セグメントとどのように重複するかなどです。</span><span class="sxs-lookup"><span data-stu-id="ec131-299">For example, how a high-spenders segment overlaps with a high-satisfaction customers segment or how a churning customer segment overlaps with a low-satisfaction customers segment.</span></span> <span data-ttu-id="ec131-300">さらに、選択した追加の属性に基づいて、重複がどのように変化するかを分析できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-300">Additionally, you can analyze how the overlap changes based on an additional attribute of your choice.</span></span>

  <span data-ttu-id="ec131-301">セグメントの差別化要因は、あるセグメントを他の顧客や他のセグメントと差別化する要素を明らかにします。</span><span class="sxs-lookup"><span data-stu-id="ec131-301">Segment differentiators reveal what differentiates one segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="ec131-302">必要なのはセグメントを特定することだけであり、システムは、差別化要因のランク付けされたリストの形式で、セグメントを区別するプロファイル属性とメジャーを識別します。</span><span class="sxs-lookup"><span data-stu-id="ec131-302">All you need to do is identify a segment and the system will identify profile attributes and measures that distinguish the segment in the form of a ranked list of differentiators—from the strongest differentiator to the weakest.</span></span>    
  <span data-ttu-id="ec131-303">詳細については、[セグメント インサイト (プレビュー)](segment-insights.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-303">For more information, see [Segment insights (preview)](segment-insights.md).</span></span>

- <span data-ttu-id="ec131-304">**セグメントの寿命**</span><span class="sxs-lookup"><span data-stu-id="ec131-304">**Segment lifetime**</span></span>
  
  <span data-ttu-id="ec131-305">セグメントをアクティブまたは非アクティブにするスケジュールを定義します。</span><span class="sxs-lookup"><span data-stu-id="ec131-305">Define a schedule to activate or deactivate a segment.</span></span>    
  <span data-ttu-id="ec131-306">詳細については、[既存セグメントの管理](segments.md#manage-existing-segments)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-306">For more information, see [Manage existing segments](segments.md#manage-existing-segments).</span></span>

## <a name="may-2020-updates"></a><span data-ttu-id="ec131-307">2020 年 5 月の更新</span><span class="sxs-lookup"><span data-stu-id="ec131-307">May 2020 updates</span></span>

<span data-ttu-id="ec131-308">2020 年 5 月の更新には、いくつかの機能、パフォーマンスのアップグレード、バグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec131-308">The updates in May 2020 includes several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-may-2020"></a><span data-ttu-id="ec131-309">2020 年 5 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="ec131-309">New and updated features in May 2020</span></span>

#### <a name="data-ingestion"></a><span data-ttu-id="ec131-310">データ インジェスト</span><span class="sxs-lookup"><span data-stu-id="ec131-310">Data ingestion</span></span>

- <span data-ttu-id="ec131-311">**リアルタイムのデータ インジェスト: 履歴ビュー**</span><span class="sxs-lookup"><span data-stu-id="ec131-311">**Real-time data ingestion: history views**</span></span>

  <span data-ttu-id="ec131-312">API を使用してリアルタイムの更新を取り込むと、これらの更新の最大 30 日間の集計履歴を表示できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-312">When using our API to ingest real-time updates, you can see up to 30 days of aggregated history for these updates.</span></span> <span data-ttu-id="ec131-313">結果、ソースシステム、その他の有用なメタデータを含む、成功または失敗したすべての API 呼び出しの集計にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ec131-313">You have access to aggregates of all successful or failed API calls including their outcome, source system, and other useful metadata.</span></span>    
  <span data-ttu-id="ec131-314">詳細については、[リアルタイム ワークフロー インジェスト](real-time-data-ingestion.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-314">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

- <span data-ttu-id="ec131-315">**リアルタイムのデータ取り込み: プロファイルの更新**</span><span class="sxs-lookup"><span data-stu-id="ec131-315">**Real-time data ingestion: profile updates**</span></span>

  <span data-ttu-id="ec131-316">リアルタイム データ取り込みのこの拡張により、特定のユーザー プロファイル フィールドへの変更を数秒以内に確認できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-316">This extension of the real-time data ingestion lets you see, within seconds, changes to specific user profile fields.</span></span>    
  <span data-ttu-id="ec131-317">アクティビティのリアルタイム機能に加えて、システムはプロファイル フィールドへの待ち時間が少ない更新をサポートします。</span><span class="sxs-lookup"><span data-stu-id="ec131-317">In addition to the real-time functionality for activities, the system supports low latency updates to profile fields.</span></span> <span data-ttu-id="ec131-318">プロファイル フィールドのリアルタイム更新には有効期限があるため、スケジュールされた更新の代わりにはなりません。</span><span class="sxs-lookup"><span data-stu-id="ec131-318">Real-time updates for profile fields have an expiration time and are therefore not a replacement for scheduled refreshes.</span></span>    
  <span data-ttu-id="ec131-319">詳細については、[リアルタイム ワークフロー インジェスト](real-time-data-ingestion.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-319">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="ec131-320">拡張性</span><span class="sxs-lookup"><span data-stu-id="ec131-320">Extensibility</span></span>

- <span data-ttu-id="ec131-321">**カスタマー カード アドインのタイムラインとページ編集を更新**</span><span class="sxs-lookup"><span data-stu-id="ec131-321">**Updated timeline and pagination on the Customer Card Add-in**</span></span>

  <span data-ttu-id="ec131-322">顧客カード アドイン ソリューションのタイムラインは、活動のタイムラインと一致します。</span><span class="sxs-lookup"><span data-stu-id="ec131-322">The timeline of the Customer Card Add-in solution matches the activity timeline.</span></span> <span data-ttu-id="ec131-323">タイムラインのページ編集が改善され、一度に最大 50 のアクティビティが表示されました。</span><span class="sxs-lookup"><span data-stu-id="ec131-323">The pagination of the timeline improved, showing up to 50 activities at once.</span></span> <span data-ttu-id="ec131-324">また、タイムラインに追加のアクティビティをロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ec131-324">It also allows loading additional activities in the timeline.</span></span>    
  <span data-ttu-id="ec131-325">詳細については、[顧客カード アドイン](customer-card-add-in.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-325">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="ec131-326">セグメント変更の **Power Automate トリガー**</span><span class="sxs-lookup"><span data-stu-id="ec131-326">**Power Automate trigger for segment changes**</span></span>

  <span data-ttu-id="ec131-327">Power Automate のトリガーはフローを何から構築できるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="ec131-327">Triggers for Power Automate define what you can build a flow from.</span></span> <span data-ttu-id="ec131-328">新しく追加されたトリガーを使用すると、セグメントのしきい値を定義できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-328">The newly added trigger lets you define a threshold for a segment.</span></span> <span data-ttu-id="ec131-329">たとえば、定義されたしきい値を超えたときに送信される通知を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-329">For example, you can create a notification that gets sent when the defined threshold is passed.</span></span>    
  <span data-ttu-id="ec131-330">詳細については  [Power Automate コネクタ](export-power-automate.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-330">For more information, see [Power Automate connector](export-power-automate.md).</span></span>

- <span data-ttu-id="ec131-331">**カスタム モデルのマルチテナント型のサポート**</span><span class="sxs-lookup"><span data-stu-id="ec131-331">**Multitenant support for custom models**</span></span>

  <span data-ttu-id="ec131-332">異なる Azure Machine Learning テナントの Web サービスを使用して、カスタム モデルのワークフローを構成します。</span><span class="sxs-lookup"><span data-stu-id="ec131-332">Configure workflows for custom models with a web service of a different Azure Machine Learning tenant.</span></span> <span data-ttu-id="ec131-333">カスタム モデルの新しいワークフローを作成するときに、Azure Machine Learning のテナントにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="ec131-333">You can sign in to the Azure Machine Learning tenant when creating a new workflow for custom models.</span></span> <span data-ttu-id="ec131-334">この機能は、独自のカスタム Azure Machine Learning Webサービスと統合する既存の機能への追加です。</span><span class="sxs-lookup"><span data-stu-id="ec131-334">This capability is an addition to the existing capability of integrating with your own custom Azure Machine Learning web service.</span></span>    
  <span data-ttu-id="ec131-335">詳細については、[カスタム機械学習モデル](custom-models.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-335">For more information, see [Custom machine learning models](custom-models.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="ec131-336">セグメント</span><span class="sxs-lookup"><span data-stu-id="ec131-336">Segments</span></span>

- <span data-ttu-id="ec131-337">**エンティティ パスの自動化**</span><span class="sxs-lookup"><span data-stu-id="ec131-337">**Entity path automation**</span></span>

  <span data-ttu-id="ec131-338">セグメントを作成するとき、ユーザーはエンティティ パスを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec131-338">When creating a segment, users need to define the entity path.</span></span> <span data-ttu-id="ec131-339">この機能は、エンティティ パスの定義を自動化する最初のステップとして、念頭に置いているセグメンテーション基準に集中できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ec131-339">This capability takes a first step at automating the entity path definition so you can focus on the segmentation criteria that you have in mind.</span></span>    
  <span data-ttu-id="ec131-340">顧客のセグメント化に使用するエンティティが統合顧客エンティティに直接関連している場合、エンティティ パスを定義する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ec131-340">If the entity by which you want to segment your customers is directly related to the unified customer entity, you won't need to define the entity path anymore.</span></span> <span data-ttu-id="ec131-341">ただし、エンティティ パスが複数ある場合でも、手動で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec131-341">However, if there is more than one possible entity path, you still need to define it manually.</span></span>

- <span data-ttu-id="ec131-342">**複数のセグメントでのアクション**</span><span class="sxs-lookup"><span data-stu-id="ec131-342">**Actions on multiple segments**</span></span>
  
  <span data-ttu-id="ec131-343">ユーザーは複数のセグメントを選択して、ワンクリックでセグメントの更新などのアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-343">Users can select multiple segments and take actions on them, like refreshing the segments, with a single click.</span></span>    

- <span data-ttu-id="ec131-344">**セグメントを最新の情報に更新する**</span><span class="sxs-lookup"><span data-stu-id="ec131-344">**Refresh segments**</span></span>

  <span data-ttu-id="ec131-345">ユーザーは単一のセグメントを更新するか、更新するセグメントのみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-345">Users can refresh a single segment or select only the segments they want to refresh.</span></span>    

  
- <span data-ttu-id="ec131-346">**複合セグメントの改善**</span><span class="sxs-lookup"><span data-stu-id="ec131-346">**Improvements to compounded segments**</span></span>

  <span data-ttu-id="ec131-347">ユーザーは、他のセグメントに基づくセグメントを作成、編集、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-347">Users can create, edit, and delete segments that are based on other segments.</span></span> <span data-ttu-id="ec131-348">たとえば、3 番目のセグメント上に構築された別のセグメント上に構築されたセグメントです。</span><span class="sxs-lookup"><span data-stu-id="ec131-348">For example, a segment constructed on another segment that was constructed on a third segment.</span></span>    

- <span data-ttu-id="ec131-349">**セグメントのリスト ページ**</span><span class="sxs-lookup"><span data-stu-id="ec131-349">**Segment list page**</span></span>

  <span data-ttu-id="ec131-350">セグメント ページの新しいデザインでは、より多くのセグメントを一度に表示できるリスト形式を使用しています。</span><span class="sxs-lookup"><span data-stu-id="ec131-350">The new design of the segments page uses a list format that lets you see more segments at once.</span></span> <span data-ttu-id="ec131-351">検索フィールドが追加され、セグメントをすばやく見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="ec131-351">A search field is added to find segments quickly.</span></span> <span data-ttu-id="ec131-352">ユーザーは、ダウンロードや削除などのアクションを一度に複数のセグメントに適用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ec131-352">Users can now apply actions like downloading or deleting on multiple segments at once.</span></span> <span data-ttu-id="ec131-353">新しいトレンド エクスペリエンスが導入され、セグメントの重要な変更をすばやく識別します。</span><span class="sxs-lookup"><span data-stu-id="ec131-353">A new trend experience is introduced to quickly identify significant changes on segments.</span></span>    
  <span data-ttu-id="ec131-354">詳細については、[セグメントの作成と管理](segments.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ec131-354">For more information, see [Create and manage segments](segments.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="ec131-355">システム管理者</span><span class="sxs-lookup"><span data-stu-id="ec131-355">System administration</span></span>

- <span data-ttu-id="ec131-356">**Microsoft Dynamics 365 Online Government で利用可能な Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="ec131-356">**Customer Insights available in Microsoft Dynamics 365 Online Government**</span></span>

  <span data-ttu-id="ec131-357">インタラクション用のチャネルがますます増えており、市民データは無数のシステムに分散しており、サイロ化されたデータや市民インタラクションに関する情報の断片化されたビューにつながります。</span><span class="sxs-lookup"><span data-stu-id="ec131-357">With more and more channels for interactions, citizen data is scattered across myriad systems, leading to siloed data, and a fragmented view of information about citizen interactions.</span></span> <span data-ttu-id="ec131-358">各市民のチャネル間の相互作用を完全に把握することなくして、政府が大規模に近代化することは不可能です。</span><span class="sxs-lookup"><span data-stu-id="ec131-358">Without a complete view of each citizen's interactions across channels, it's impossible for governments to modernize at scale.</span></span> <span data-ttu-id="ec131-359">Microsoft は、一貫性のある応答性の高いエクスペリエンスに対する市民の期待に応えるために、政府のテクノロジー ニーズをサポートすることに尽力しています。</span><span class="sxs-lookup"><span data-stu-id="ec131-359">Microsoft is committed to supporting the technology needs of government to keep up with citizen expectations for consistent and responsive experiences.</span></span>    
  <span data-ttu-id="ec131-360">2020 年リリースのウェーブ 1 があれば、Dynamics 365 Customer Insights は米国政府機関のより高いコンプライアンス ニーズを満たすために構築された環境である、Government Community Cloud (GCC) で利用できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-360">With 2020 release wave 1, Dynamics 365 Customer Insights will be available for the Government Community Cloud (GCC), an environment built to meet the higher compliance needs of United States government agencies.</span></span> <span data-ttu-id="ec131-361">代理店は、市民の統一されたビューを取得し、構築済みの AI を使用して、相互作用を改善し、従業員に力を与え、コミュニティを変革する一方で、IT の複雑さを軽減し、米国のコンプライアンスおよびセキュリティ基準を満たします。</span><span class="sxs-lookup"><span data-stu-id="ec131-361">Agencies gain a unified view of citizens and use prebuilt AI to derive insights that improve interactions, empower employees, and transform communities, while reducing IT complexity and meeting United States compliance and security standards.</span></span> <span data-ttu-id="ec131-362">Dynamics 365 Government は、US Federal Risk and Authorization Management Program (FedRAMP) の厳しい要件を満たし、米国連邦政府機関が Microsoft Cloud のコスト削減と厳格なセキュリティの恩恵を受けることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="ec131-362">Dynamics 365 Government meets the demanding requirements of the US Federal Risk and Authorization Management Program (FedRAMP), enabling United States federal agencies to benefit from the cost savings and rigorous security of the Microsoft Cloud.</span></span>

## <a name="april-2020-updates"></a><span data-ttu-id="ec131-363">2020 年 4 月の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="ec131-363">April 2020 updates</span></span>

<span data-ttu-id="ec131-364">2020 年 4 月の更新には、いくつかの機能、パフォーマンスのアップグレード、バグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec131-364">The updates in April 2020 includes several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-april-2020"></a><span data-ttu-id="ec131-365">2020 年 4 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="ec131-365">New and updated features in April 2020</span></span>

#### <a name="activities"></a><span data-ttu-id="ec131-366">活動 </span><span class="sxs-lookup"><span data-stu-id="ec131-366">Activities</span></span>

- <span data-ttu-id="ec131-367">**アクティビティ エンティティを標準のアクティビティ タイプにマッピングする**</span><span class="sxs-lookup"><span data-stu-id="ec131-367">**Map activity entity to standard activity type**</span></span>
  
  <span data-ttu-id="ec131-368">アクティビティの構成とストレージは現在、それらをタイムラインで表示するための静的な設計に基づいています。</span><span class="sxs-lookup"><span data-stu-id="ec131-368">Activity configuration and storage are currently based on a static design to view them in a timeline.</span></span> <span data-ttu-id="ec131-369">現時点では、AI モデルで複数のユースケースが発生する可能性のあるアクティビティの意味的な意味が十分に活用されていません。</span><span class="sxs-lookup"><span data-stu-id="ec131-369">The semantic meaning of activities, which has potential for multiple use-cases in AI models, isn't fully used at the moment.</span></span> <span data-ttu-id="ec131-370">私たちは、活動のタイプと活動のより良い意味の理解に基づいて、活動のタイムラインをより動的にする予定です。</span><span class="sxs-lookup"><span data-stu-id="ec131-370">We plan to make the activity timeline more dynamic, based on the activity type and better semantic understanding of the activities.</span></span> <span data-ttu-id="ec131-371">この機能は、取り込まれたアクティビティの Common Data Model で定義されているアクティビティ タイプを識別することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="ec131-371">This feature aims to identify the activity type as defined in Common Data Model for any ingested activity.</span></span>
  <span data-ttu-id="ec131-372">詳細については、[顧客アクティビティ](activities.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-372">For more information, see [Customer activities](activities.md).</span></span>

#### <a name="data-ingestion"></a><span data-ttu-id="ec131-373">データ インジェスト</span><span class="sxs-lookup"><span data-stu-id="ec131-373">Data ingestion</span></span>

- <span data-ttu-id="ec131-374">**リアルタイムのデータ取り込み: アクティビティ**</span><span class="sxs-lookup"><span data-stu-id="ec131-374">**Real-time data ingestion: activities**</span></span>
  
  <span data-ttu-id="ec131-375">リアルタイム データ インジェストは、後続のスケジュールされた更新が、このデータをデータ ソースから取得するまで、データを即座に使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ec131-375">Real-time data ingestion provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>    
  <span data-ttu-id="ec131-376">詳細については、[リアルタイム ワークフロー インジェスト](real-time-data-ingestion.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-376">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

- <span data-ttu-id="ec131-377">**データ準備の改善**</span><span class="sxs-lookup"><span data-stu-id="ec131-377">**Improvements to data preparation**</span></span>
  
  <span data-ttu-id="ec131-378">エンティティで取り込んだデータの詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ec131-378">Learn more about the data ingested in an entity.</span></span> <span data-ttu-id="ec131-379">データサマリーを使用すると、適切なアクションを実行するのに役立つデータ品質特性を理解できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-379">With the data summary, you can understand the data quality characteristics that can help to take appropriate action.</span></span>    
  <span data-ttu-id="ec131-380">詳細については、[エンティティ データの検索](entities.md#exploring-a-specific-entitys-data) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-380">For more information, see [Explore entity data](entities.md#exploring-a-specific-entitys-data).</span></span>

- <span data-ttu-id="ec131-381">**Common Data Service でDynamics 365 から分析データを取り込む**</span><span class="sxs-lookup"><span data-stu-id="ec131-381">**Ingest analytical data from Dynamics 365 with Common Data Service**</span></span>
  
  <span data-ttu-id="ec131-382">Common Data Service は、データ ソースを作成する方法として利用できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-382">Common Data Service is available as a way to create data sources.</span></span> <span data-ttu-id="ec131-383">既存の Dynamics 365 のお客様は、分析エンティティを Common Data Service から Customer Insights へ取り込めます。</span><span class="sxs-lookup"><span data-stu-id="ec131-383">Existing Dynamics 365 customers can ingest analytical entities from Common Data Service to Customer Insights.</span></span> <span data-ttu-id="ec131-384">1 つのデータ ソースは、Customer Insights 環境で同じ Common Data Service 管理のレイクを同時に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-384">A single data source can simultaneously use the same Common Data Service-managed lake in a Customer Insights environment.</span></span>    
  <span data-ttu-id="ec131-385">詳細については、[Common Data Service 管理型データ レイクでデータに接続する](connect-common-data-service-lake.md)。</span><span class="sxs-lookup"><span data-stu-id="ec131-385">For more information, see [Connect to data in a Common Data Service managed data lake](connect-common-data-service-lake.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="ec131-386">拡張性</span><span class="sxs-lookup"><span data-stu-id="ec131-386">Extensibility</span></span>

- <span data-ttu-id="ec131-387">**LiveRamp へのエクスポート**</span><span class="sxs-lookup"><span data-stu-id="ec131-387">**Export to LiveRamp**</span></span>

  <span data-ttu-id="ec131-388">LiveRamp® でデータをアクティブ化して、デジタル、ソーシャル、テレビのエコシステム全体で 500 を超えるプラットフォームに接続します。</span><span class="sxs-lookup"><span data-stu-id="ec131-388">Activate your data in LiveRamp® to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="ec131-389">LiveRamp のデータを活用して、広告キャンペーンのターゲティング、抑制、広告キャンペーンのパーソナライズを行います。</span><span class="sxs-lookup"><span data-stu-id="ec131-389">Leverage your data in LiveRamp for targeting, suppressing, and personalizing ad campaigns.</span></span>    
  <span data-ttu-id="ec131-390">詳細については [LiveRamp&reg; コネクタ](export-liveramp.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-390">For more information, see [LiveRamp&reg; connector](export-liveramp.md).</span></span>

- <span data-ttu-id="ec131-391">**Customer Insights のチーム アドイン**</span><span class="sxs-lookup"><span data-stu-id="ec131-391">**Customer Insights Teams Add-in**</span></span>
  
  <span data-ttu-id="ec131-392">ボットは、統合された顧客プロファイルの検索機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ec131-392">The bot provides lookup capabilities for unified customer profiles.</span></span> <span data-ttu-id="ec131-393">結果の顧客プロファイルから最大 15 フィールドのカードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec131-393">It will show a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="ec131-394">複数の一致は、プロファイルを選択できる結果の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="ec131-394">Multiple matches return a list of results where you can select a profile.</span></span>    
  <span data-ttu-id="ec131-395">詳しくは、[Customer Insights のチーム ボット](export-teams-bot.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ec131-395">For more information, see [Teams bot for Customer Insights](export-teams-bot.md).</span></span>

#### <a name="measures"></a><span data-ttu-id="ec131-396">メジャー</span><span class="sxs-lookup"><span data-stu-id="ec131-396">Measures</span></span>

- <span data-ttu-id="ec131-397">**メジャー リスト ページ**</span><span class="sxs-lookup"><span data-stu-id="ec131-397">**Measure list page**</span></span>
  
  <span data-ttu-id="ec131-398">メジャー ページの改善には、単一のメジャーや複数のメジャーに対するアクションのサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec131-398">Improvements to the measures page include support for actions on a single measure and on multiple measures at once.</span></span> <span data-ttu-id="ec131-399">さらに、メジャーをすばやく見つけて追跡するための検索フィールドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec131-399">Additionally, you'll find a search field to find and track measures quickly.</span></span>    
  <span data-ttu-id="ec131-400">詳細については、[セグメントの作成と管理](segments.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ec131-400">For more information, see [Create and manage segments](segments.md).</span></span>

- <span data-ttu-id="ec131-401">**複合型メジャーの改善**</span><span class="sxs-lookup"><span data-stu-id="ec131-401">**Improvements to compounded measures**</span></span>
  
  <span data-ttu-id="ec131-402">ユーザーは、他のメジャーに基づくメジャーを作成、編集、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-402">Users can create, edit, and delete measures that are based on other measures.</span></span> <span data-ttu-id="ec131-403">たとえば、3 番目のメジャー上に構築された別のメジャー上に構築されたメジャーです。</span><span class="sxs-lookup"><span data-stu-id="ec131-403">For example, a measure constructed on another measure that was constructed on a third measure.</span></span>

#### <a name="segments"></a><span data-ttu-id="ec131-404">セグメント</span><span class="sxs-lookup"><span data-stu-id="ec131-404">Segments</span></span>

- <span data-ttu-id="ec131-405">**追加の演算子**</span><span class="sxs-lookup"><span data-stu-id="ec131-405">**Additional operator**</span></span>
  
  <span data-ttu-id="ec131-406">インセット演算子を使用すると、いくつかの可能な文字列値で顧客をセグメント化できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-406">The In-set operator allows segmentation for customers by several possible string values.</span></span> <span data-ttu-id="ec131-407">この演算子が追加される前は、複数の OR 条件でそのようなセグメントを作成する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="ec131-407">Before this operator was added, you had to construct such segments with multiple OR conditions.</span></span> <span data-ttu-id="ec131-408">インセット演算子を使用すると、単一の条件でそれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ec131-408">The In-set operator lets you do that with a single condition.</span></span>    
  <span data-ttu-id="ec131-409">詳細については、[セグメントの作成と管理](segments.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ec131-409">For more information, see [Create and manage segments](segments.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="ec131-410">システム管理者</span><span class="sxs-lookup"><span data-stu-id="ec131-410">System administration</span></span>

- <span data-ttu-id="ec131-411">**構成設定を新規環境にコピーする**</span><span class="sxs-lookup"><span data-stu-id="ec131-411">**Copy configuration settings to a new environment**</span></span>
  
  <span data-ttu-id="ec131-412">構成をある環境から別の環境にコピーします。</span><span class="sxs-lookup"><span data-stu-id="ec131-412">Copy your configuration from one environment to another.</span></span> <span data-ttu-id="ec131-413">新しい環境を作成するときに、構成のコピー元となる既存の環境を選択できます。</span><span class="sxs-lookup"><span data-stu-id="ec131-413">While creating a new environment, you can select an existing environment you want to copy the configuration from.</span></span> <span data-ttu-id="ec131-414">現在、データソース、データ統合、リレーションシップ、メジャー、コピーするセグメントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ec131-414">We currently support data sources, data unification, relationships, measures, and segments to be copied.</span></span> <span data-ttu-id="ec131-415">データ ソース認証情報と実際のデータはコピーされません。</span><span class="sxs-lookup"><span data-stu-id="ec131-415">Data source credentials and actual data aren't copied.</span></span>    
  <span data-ttu-id="ec131-416">詳細については、[環境を管理する](manage-environments.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec131-416">For more information, see [Manage environments](manage-environments.md).</span></span>
