---
title: 新しい機能および今後の機能
description: 新機能、改善、およびバグ修正に関する情報。
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 9183c8af4fb9f9f08ac63d8d0cd37c6868bba310
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270438"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a><span data-ttu-id="89d65-103">Dynamics 365 Customer Insights の対象者に関するインサイト機能の新機能</span><span class="sxs-lookup"><span data-stu-id="89d65-103">What's new in the audience insights capability of Dynamics 365 Customer Insights</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="89d65-104">最新の更新プログラムについてお知らせします !</span><span class="sxs-lookup"><span data-stu-id="89d65-104">We're excited to announce our newest updates!</span></span> <span data-ttu-id="89d65-105">この記事は、パブリック プレビュー機能、全般的な可用性の強化、毎月の更新プログラム、機能の更新をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="89d65-105">This article summarizes public preview features, general availability enhancements, and feature updates.</span></span> <span data-ttu-id="89d65-106">長期的な機能計画を確認するには、[Dynamics 365 と Power Platform のリリース計画](https://docs.microsoft.com/dynamics365/release-plans/) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="89d65-106">To see the long-term feature plans, take a look at the [Dynamics 365 and Power Platform release plans](https://docs.microsoft.com/dynamics365/release-plans/).</span></span>

<span data-ttu-id="89d65-107">次のビデオを見て、過去 6 か月間に予定された機能の詳細を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="89d65-107">You can also watch the following video to learn more about the capabilities planned for the last six months.</span></span>

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

<span data-ttu-id="89d65-108">更新プログラムは地域ベースで配信されます。</span><span class="sxs-lookup"><span data-stu-id="89d65-108">We roll out updates on a region-by-region basis.</span></span> <span data-ttu-id="89d65-109">そのため、特定の地域では、他の地域より先に機能が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="89d65-109">So certain regions might see features before others.</span></span> <span data-ttu-id="89d65-110">特に指定がない限り、何もする必要はなく、アプリはダウンタイムなしで自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="89d65-110">Unless specified differently, you don't need to take any action and we'll update the app automatically with no downtime.</span></span>

> [!TIP]
> <span data-ttu-id="89d65-111">機能要求と製品に関する提案を送信して投票するには、[Dynamics 365 アプリケーションのアイデア ポータル](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights) に移動してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-111">To submit and vote on feature requests and product suggestions, go to the [Dynamics 365 Application Ideas portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).</span></span>

## <a name="january-2021-updates"></a><span data-ttu-id="89d65-112">2021 年 1 月の更新</span><span class="sxs-lookup"><span data-stu-id="89d65-112">January 2021 updates</span></span>

<span data-ttu-id="89d65-113">2021 年 1 月の更新には、いくつかの機能、パフォーマンスのアップグレード、およびバグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89d65-113">The updates in January 2021 include several features, performance upgrades, and bug fixes.</span></span>

#### <a name="extensibility"></a><span data-ttu-id="89d65-114">拡張性</span><span class="sxs-lookup"><span data-stu-id="89d65-114">Extensibility</span></span>

- <span data-ttu-id="89d65-115">**SFTP エクスポートの拡張機能と強化されたパフォーマンス** すべての出力エンティティを Customer Insights から SFTP ホストにエクスポートできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="89d65-115">**Extended functionality and enhanced performance for SFTP export** You can now export all output entities from Customer Insights to an SFTP host.</span></span> <span data-ttu-id="89d65-116">以前は、エクスポートはセグメント エンティティに制限されていました。</span><span class="sxs-lookup"><span data-stu-id="89d65-116">Previously, export was limited to segment entities.</span></span> <span data-ttu-id="89d65-117">さらに、SFTP エクスポートのパフォーマンスにより、SFTP ホストのパフォーマンスに応じて、より多くのデータ量をより短い時間で実行できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-117">Additionally, the performance of the SFTP export allows more data volume in less time, depending on the performance of your SFTP host.</span></span>    
  <span data-ttu-id="89d65-118">詳細については、[SFTP 用コネクタ (プレビュー)](export-sftp.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-118">For more information, see [Connector for SFTP (preview)](export-sftp.md).</span></span>  

#### <a name="segments"></a><span data-ttu-id="89d65-119">セグメント</span><span class="sxs-lookup"><span data-stu-id="89d65-119">Segments</span></span>

- <span data-ttu-id="89d65-120">**機械学習は、メトリックを改善するために提案されたセグメントを強化しました** セグメントを検出して作成する新しい方法が加わりました。</span><span class="sxs-lookup"><span data-stu-id="89d65-120">**Machine learning powered suggested segments to improve metrics** There's a new way do discover and create segments.</span></span> <span data-ttu-id="89d65-121">システムは AI モデルを使用して、すでに追跡している KPI (メジャー) の改善に役立つセグメントを提案します。</span><span class="sxs-lookup"><span data-stu-id="89d65-121">The system uses an AI model to suggest segments that can help improve a KPI (measure) you are already tracking.</span></span> <span data-ttu-id="89d65-122">メジャーまたは別の主要属性に対して選択した属性の影響の程度を示します。</span><span class="sxs-lookup"><span data-stu-id="89d65-122">We show the extent of influence of attributes that you select on a measure or another primary attribute.</span></span> <span data-ttu-id="89d65-123">この情報は、機会を提供する潜在的なセグメントを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="89d65-123">This information helps finding potential segments that present opportunities.</span></span>    
  <span data-ttu-id="89d65-124">詳細については、[提案されたセグメント (プレビュー)](suggested-segments.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-124">For more information, see [Suggested segments (preview)](suggested-segments.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="89d65-125">データ統合</span><span class="sxs-lookup"><span data-stu-id="89d65-125">Data unification</span></span>

- <span data-ttu-id="89d65-126">**強化された照合エクスペリエンス** データ統合エリアでは、照合エクスペリエンスが更新されました。</span><span class="sxs-lookup"><span data-stu-id="89d65-126">**Enhanced match experience** In the data unification area, the match experience was updated.</span></span> <span data-ttu-id="89d65-127">照合がどのように機能するかをさらに説明するための詳細な統計など、照合ルールを構成および表示できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-127">It lets you configure and view the match rules, including detailed stats to further explain how matching works.</span></span> <span data-ttu-id="89d65-128">照合ルールを無効にして、構成を保持している間はアクティブでなくなったり、照合ルールをドラッグ アンド ドロップしたりするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="89d65-128">There are options to disable a match rule so it's no longer active while retaining the configuration, drag and drop match rules, and more.</span></span>
  <span data-ttu-id="89d65-129">詳細については、「[エンティティの照合](match-entities.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-129">For more information, see [Match entities](match-entities.md).</span></span>

- <span data-ttu-id="89d65-130">**照合プロセスからの重複排除出力は、エンティティとして利用できます** 照合プロセスから出力された重複排除プロセスは、さらに分析するために別のエンティティに書き込まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="89d65-130">**Deduplication output from the match process is available as an entity** Deduplication process output from the match process is now written into a separate entity for further analysis.</span></span> <span data-ttu-id="89d65-131">このエンティティは、重複排除プロセスで使用されるフィールドと、勝者レコード、および勝者レコードとマージされる対応代替レコードで構成されます。</span><span class="sxs-lookup"><span data-stu-id="89d65-131">This entity consists of the fields used in the deduplication process and the winner record and the corresponding alternate records that get merged with the winner record.</span></span>
  <span data-ttu-id="89d65-132">詳細については、[エンティティとしての重複排除出力](match-entities.md#deduplication-output-as-an-entity) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-132">For more information, see [Deduplication output as an entity](match-entities.md#deduplication-output-as-an-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="89d65-133">システム管理</span><span class="sxs-lookup"><span data-stu-id="89d65-133">System administration</span></span>

- <span data-ttu-id="89d65-134">**シームレスにデータを Microsoft Dataverse と共有する** Customer Insights 出力を、Microsoft Dataverse マネージド Data Lake を使って Microsoft Dataverse アプリケーションと共有できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="89d65-134">**Seamlessly share data to Microsoft Dataverse** You can now share Customer Insights output with Microsoft Dataverse applications using the Microsoft Dataverse Managed Data Lake.</span></span> <span data-ttu-id="89d65-135">Dataverse 環境を Customer Insights と関連付けたら、データ共有を有効にするオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="89d65-135">Once you associate a Dataverse environment with Customer Insights, you get the option to enable data sharing.</span></span>
  <span data-ttu-id="89d65-136">詳細については、[環境を管理する](manage-environments.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-136">For more information, see [Manage environments](manage-environments.md).</span></span>


## <a name="december-2020-updates"></a><span data-ttu-id="89d65-137">2020 年 12 月の更新</span><span class="sxs-lookup"><span data-stu-id="89d65-137">December 2020 updates</span></span>

<span data-ttu-id="89d65-138">2020 年 12 月の更新には、いくつかの機能、パフォーマンス アップグレード、およびバグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89d65-138">The updates in December 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-december-2020"></a><span data-ttu-id="89d65-139">2020 年 12 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="89d65-139">New and updated features in December 2020</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="89d65-140">データ エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="89d65-140">Data enrichment</span></span>

- <span data-ttu-id="89d65-141">**ブランドと関心のアフィニティ エンリッチメントの改善**</span><span class="sxs-lookup"><span data-stu-id="89d65-141">**Improved Brand and Interest affinity enrichments**</span></span>
  
  <span data-ttu-id="89d65-142">アフィニティ スコアを簡略化して、わかりやすくかつ使いやすくしました。</span><span class="sxs-lookup"><span data-stu-id="89d65-142">We simplified our affinity scores to make them easier to understand and use.</span></span> <span data-ttu-id="89d65-143">特定のブランドまたは関心に対する顧客のアフィニティに基づいて、顧客をすばやく特定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="89d65-143">You can now quickly identify customers based on how much affinity they have for a given brand or interest.</span></span>

  <span data-ttu-id="89d65-144">さらに、顧客プロファイルをどのようにエンリッチするかに関する制御を向上させるため、新しい構成オプションを追加しました。</span><span class="sxs-lookup"><span data-stu-id="89d65-144">Additionally, we have added new configuration options to better control how you want your customer profiles to be enriched.</span></span> 

  <span data-ttu-id="89d65-145">詳細については、[ブランドと興味のアフィニティで顧客プロファイルを強化する](enrichment-microsoft-graph.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-145">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

- <span data-ttu-id="89d65-146">**どのプロファイルをエンリッチするかを制御する**</span><span class="sxs-lookup"><span data-stu-id="89d65-146">**Control which profiles to enrich**</span></span>

  <span data-ttu-id="89d65-147">既定の顧客エンティティの代わりにセグメント エンティティを選択するオプションを使用して、顧客プロファイルのサブセットのみをエンリッチできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="89d65-147">You can now enrich only a subset of your customer profiles with the option to select a segment entity instead of the default customer entity.</span></span> <span data-ttu-id="89d65-148">エンリッチする顧客プロファイルを使用してセグメントを作成し、顧客データ セットのエンリッチメント構成で選択します。</span><span class="sxs-lookup"><span data-stu-id="89d65-148">Create a segment with the customer profiles you would like to enrich and select it in the enrichment configuration for your customer data set.</span></span>
  <span data-ttu-id="89d65-149">この機能は現在、Experian および HERE Technologies が提供するエンリッチメントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-149">This feature is currently available only for enrichments provided by Experian and HERE Technologies.</span></span> <span data-ttu-id="89d65-150">より多くのエンリッチメントにこの機能を有効にする予定です。</span><span class="sxs-lookup"><span data-stu-id="89d65-150">We will be enabling this capability to more enrichments soon.</span></span>

  <span data-ttu-id="89d65-151">詳細については、[Experian の人口統計で顧客プロファイルをエンリッチする](enrichment-experian.md)または[HERE Technologies を使用して顧客プロファイルのエンリッチメント](enrichment-here.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-151">For more information, see [Enrich customer profiles with demographics from Experian](enrichment-experian.md) or [Enrichment of customer profiles with HERE Technologies](enrichment-here.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="89d65-152">拡張性</span><span class="sxs-lookup"><span data-stu-id="89d65-152">Extensibility</span></span>

- <span data-ttu-id="89d65-153">**Autopilot でセグメントをアクティブ化する**</span><span class="sxs-lookup"><span data-stu-id="89d65-153">**Activate your segments through Autopilot**</span></span>

  <span data-ttu-id="89d65-154">セグメントを Autopilot にエクスポートし、マーケティング目的で使用します。</span><span class="sxs-lookup"><span data-stu-id="89d65-154">Export segments to Autopilot and use them for marketing purposes.</span></span> <span data-ttu-id="89d65-155">詳細については、[Autopilot 用コネクタ (プレビュー)](export-autopilot.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-155">For more information, see [Connector for Autopilot (preview)](export-autopilot.md).</span></span>

- <span data-ttu-id="89d65-156">**SendGrid でセグメントをアクティブ化する**</span><span class="sxs-lookup"><span data-stu-id="89d65-156">**Activate your segments through SendGrid**</span></span>

  <span data-ttu-id="89d65-157">セグメントを SendGrid にエクスポートし、マーケティング目的で使用します。</span><span class="sxs-lookup"><span data-stu-id="89d65-157">Export segments to SendGrid and use them for marketing purposes.</span></span> <span data-ttu-id="89d65-158">詳細については、[SendGrid 用コネクタ](export-sendgrid.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-158">For more information, see [Connector for SendGrid](export-sendgrid.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="89d65-159">システム管理</span><span class="sxs-lookup"><span data-stu-id="89d65-159">System administration</span></span>

- <span data-ttu-id="89d65-160">**更新された環境管理エクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="89d65-160">**Updated environment management experience**</span></span>
  
  <span data-ttu-id="89d65-161">アプリ ヘッダーの環境ピッカーから直接環境を作成、編集、削除、リセットできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="89d65-161">You can now create, edit, delete, and reset environments directly from the environment picker in the app header.</span></span> 
  
  <span data-ttu-id="89d65-162">さらに、使用している環境は環境パネルの上部に固定されるため、検索は不要になりました。</span><span class="sxs-lookup"><span data-stu-id="89d65-162">Additionally, the environment you are using will be pinned at the top of the environment panel so you don't need to search for it anymore.</span></span>

  <span data-ttu-id="89d65-163">詳細については、[環境を管理する](manage-environments.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-163">For more information, see [Manage environments](manage-environments.md).</span></span>

## <a name="november-2020-updates"></a><span data-ttu-id="89d65-164">2020 年 11 月 の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="89d65-164">November 2020 updates</span></span>

<span data-ttu-id="89d65-165">2020 年 11 月の更新には、いくつかの機能、パフォーマンス アップグレード、およびバグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89d65-165">The updates in November 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-november-2020"></a><span data-ttu-id="89d65-166">2020 年 11 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="89d65-166">New and updated features in November 2020</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="89d65-167">データ エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="89d65-167">Data enrichment</span></span>

- <span data-ttu-id="89d65-168">**セキュリティで保護されたファイル転送プロトコル (SFTP) によるカスタム インポートで独自のエンリッチメント データを取り込む**</span><span class="sxs-lookup"><span data-stu-id="89d65-168">**Bring your own enrichment data via Secure File Transfer Protocol (SFTP) custom import**</span></span>
  
  <span data-ttu-id="89d65-169">SFTP によるカスタム インポートを使用すると、データ統合のプロセスを行う必要のないエンリッチメント データをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="89d65-169">SFTP custom import lets you import enrichment data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="89d65-170">SFTP によるカスタム インポートについて。</span><span class="sxs-lookup"><span data-stu-id="89d65-170">Learn more about SFTP custom import.</span></span>

  <span data-ttu-id="89d65-171">詳細については、[カスタム データで顧客プロファイルを強化する (プレビュー)](enrichment-SFTP-custom-import.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-171">For more information, see [Enrich customer profiles with custom data (preview)](enrichment-SFTP-custom-import.md).</span></span>
 
- <span data-ttu-id="89d65-172">**HERE Technologies の位置データで顧客データを強化する**</span><span class="sxs-lookup"><span data-stu-id="89d65-172">**Enrich your customer data with location data from HERE Technologies**</span></span>

  <span data-ttu-id="89d65-173">HERE Technologies のデータ エンリッチメント サービスを使用すると、住所の正規化、緯度と経度の抽出などにより、顧客のより正確な位置情報を把握できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-173">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span> <span data-ttu-id="89d65-174">HERE Technologies を利用した強化について。</span><span class="sxs-lookup"><span data-stu-id="89d65-174">Learn more about enriching with HERE Technologies.</span></span>

  <span data-ttu-id="89d65-175">詳細については、[HERE Technologies による顧客プロファイルの強化](enrichment-here.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-175">For more information, see [Enrichment of customer profiles with HERE Technologies](enrichment-here.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="89d65-176">データ統合</span><span class="sxs-lookup"><span data-stu-id="89d65-176">Data unification</span></span>

- <span data-ttu-id="89d65-177">**ストレージ アカウントから選択したエンティティとフィールドでデータ プロファイリングを有効にする柔軟性**</span><span class="sxs-lookup"><span data-stu-id="89d65-177">**Flexibility to enable data profiling on selected entities and fields from your storage account**</span></span>

  <span data-ttu-id="89d65-178">データ インジェスト プロセスの一部としてデータ プロファイリングを有効にする、Azure Data Lake ストレージ アカウントで Common Data Model フォルダーのデータ エンティティとフィールドを指定できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-178">You can indicate which data entities and fields from a Common Data Model folder in your Azure Data Lake storage account you want to enable data profiling as part of the data ingestion process.</span></span>

  <span data-ttu-id="89d65-179">詳細については、[Common Data Model フォルダーへの接続](connect-common-data-model.md#connect-to-a-common-data-model-folder) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-179">For more information, see [Connect to a Common Data Model folder](connect-common-data-model.md#connect-to-a-common-data-model-folder).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="89d65-180">拡張性</span><span class="sxs-lookup"><span data-stu-id="89d65-180">Extensibility</span></span>

- <span data-ttu-id="89d65-181">**Google 広告でセグメントをアクティブ化する**</span><span class="sxs-lookup"><span data-stu-id="89d65-181">**Activate your segments through Google Ads**</span></span>

  <span data-ttu-id="89d65-182">セグメントを Google 広告のオーディエンス リストにエクスポートし、それらを使用して Google 検索、Google ディスプレイ ネットワーク、YouTube、Gmail に広告を掲載します。</span><span class="sxs-lookup"><span data-stu-id="89d65-182">Export segments from to Google Ads audience lists and use these lists to advertise on Google Search, Google Display Network, YouTube, and Gmail.</span></span> <span data-ttu-id="89d65-183">Google 広告でセグメントをアクティブ化する方法について。</span><span class="sxs-lookup"><span data-stu-id="89d65-183">Learn more about activating your segments through Google Ads.</span></span>

  <span data-ttu-id="89d65-184">詳細については、[Google 広告用コネクタ](export-google-ads.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-184">For more information, see [Connector for Google Ads](export-google-ads.md).</span></span>

- <span data-ttu-id="89d65-185">**Marketo でセグメントをアクティブ化する**</span><span class="sxs-lookup"><span data-stu-id="89d65-185">**Activate your segments through Marketo**</span></span>

  <span data-ttu-id="89d65-186">セグメントを Marketo オーディエンスにエクスポートし、これらのオーディエンスをマーケティングの自動化に使用します。</span><span class="sxs-lookup"><span data-stu-id="89d65-186">Export segments to Marketo audiences and use these audiences for marketing automation.</span></span> <span data-ttu-id="89d65-187">Marketo でセグメントをアクティブ化する方法について。</span><span class="sxs-lookup"><span data-stu-id="89d65-187">Learn more about activating your segments through Marketo.</span></span> 

  <span data-ttu-id="89d65-188">詳細については、[Marketo 用コネクタ](export-marketo.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-188">For more information, see [Connector for Marketo](export-marketo.md).</span></span>

- <span data-ttu-id="89d65-189">**DotDigital でセグメントをアクティブ化する**</span><span class="sxs-lookup"><span data-stu-id="89d65-189">**Activate your segments through DotDigital**</span></span>

  <span data-ttu-id="89d65-190">セグメントを DotDigital にエクスポートし、マーケティング目的で使用します。</span><span class="sxs-lookup"><span data-stu-id="89d65-190">Export segments to DotDigital and use them for marketing purposes.</span></span> <span data-ttu-id="89d65-191">DotDigital でセグメントをアクティブ化する方法について。</span><span class="sxs-lookup"><span data-stu-id="89d65-191">Learn more about activating your segments through DotDigital.</span></span> 

  <span data-ttu-id="89d65-192">詳細については、[DotDigital 用コネクタ](export-dotdigital.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-192">For more information, see [Connector for DotDigital](export-dotdigital.md).</span></span>

#### <a name="predictions"></a><span data-ttu-id="89d65-193">予測</span><span class="sxs-lookup"><span data-stu-id="89d65-193">Predictions</span></span>

- <span data-ttu-id="89d65-194">**トランザクション解約を予測する**</span><span class="sxs-lookup"><span data-stu-id="89d65-194">**Predict transactional churn**</span></span>

  <span data-ttu-id="89d65-195">トランザクション解約予測機能を使用すると、データ サイエンティストの助けを借りずに、顧客が製品やサービスの購入を停止する可能性を予測できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-195">The transaction churn prediction feature enables you, without the help of a data scientist, to predict the likelihood of a customer to stop purchasing products or services.</span></span>  <span data-ttu-id="89d65-196">予測スコアを使用すると、顧客価値など、顧客に関する他の情報を組み合わせて、解約リスクの高い顧客または価値の高い顧客のセグメントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-196">Using the prediction score, you can combine other information about your customers, like customer value, to create segments of high churn risk or high value customers.</span></span> <span data-ttu-id="89d65-197">このセグメントを使用して、マーケティング活動、カスタマー サポート、およびその他のシナリオを通じて顧客を直接ターゲットにして、解約リスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="89d65-197">Use this segment to directly target customers through marketing activities, customer support, and other scenarios to reduce churn risk.</span></span>
 
  <span data-ttu-id="89d65-198">解約の定義をビジネスに固有の時間ベース ウィンドウとして構成し、顧客が解約されたとみなされる時期を定義します。</span><span class="sxs-lookup"><span data-stu-id="89d65-198">Configure the definition of churn as a time-based window specific to your business and define when customers are considered churned.</span></span> <span data-ttu-id="89d65-199">たとえば、食料品店は、過去 30 日間何も購入していない場合、顧客が解約したと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="89d65-199">For example, a grocery store may want to consider a customer churned if they have not purchased anything in the past 30 days.</span></span>
 
  <span data-ttu-id="89d65-200">予測の作成を続けると、必要なデータが案内され、顧客の解約を予測するために必要なフィールドにビジネスに関するデータをマッピングできるようになります。</span><span class="sxs-lookup"><span data-stu-id="89d65-200">As you continue creating the prediction, we'll guide you what data is needed, and enable you to map data about your business to fields required to predict churn for your customers.</span></span> <span data-ttu-id="89d65-201">また、変化するビジネス状況に適応するために、システム内の新しい情報に基づいてモデルを再トレーニングするスケジュールを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="89d65-201">You can also set a schedule to retrain the model based on new information in your system to adapt to changing business circumstances.</span></span>
 
  <span data-ttu-id="89d65-202">詳細については、[トランザクション解約予測 (プレビュー)](predict-transactional-churn.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-202">For more information, see [Transactional churn prediction (preview)](predict-transactional-churn.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="89d65-203">システム管理者</span><span class="sxs-lookup"><span data-stu-id="89d65-203">System administration</span></span>

- <span data-ttu-id="89d65-204">**環境のリセット**</span><span class="sxs-lookup"><span data-stu-id="89d65-204">**Reset environment**</span></span>

  <span data-ttu-id="89d65-205">選択したインスタンスの環境内のすべてをリセットして、最初からやり直します。</span><span class="sxs-lookup"><span data-stu-id="89d65-205">Reset everything in an environment of a selected instance to start fresh.</span></span>

  <span data-ttu-id="89d65-206">詳細については、[既存の環境のリセット](manage-environments.md#reset-an-existing-environment) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-206">For more information, see [Reset an existing environment](manage-environments.md#reset-an-existing-environment).</span></span>


- <span data-ttu-id="89d65-207">**サービス プリンシパルを使用して、Azure Data Lake ストレージ アカウントに接続する**</span><span class="sxs-lookup"><span data-stu-id="89d65-207">**Connect to your Azure Data Lake storage account using a service principal**</span></span>

  <span data-ttu-id="89d65-208">Azure サービス プリンシパルを使用して、ストレージ アカウントにデータ出力を書き込み、ストレージア カウントからデータを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="89d65-208">Write data output to and read data from your storage account using an Azure service principal.</span></span> <span data-ttu-id="89d65-209">既存のストレージ アカウント接続は、引き続きアカウント キーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-209">Existing storage account connections can continue to use the account key.</span></span> <span data-ttu-id="89d65-210">また、今後サービス プリンシパルを使用するためのアップグレード オプションも提供します。</span><span class="sxs-lookup"><span data-stu-id="89d65-210">They also offer an upgrade option to use the service principal moving forward.</span></span> <span data-ttu-id="89d65-211">新しい接続は、ストレージ アカウントのサービス プリンシパル認証方法に基づきます。</span><span class="sxs-lookup"><span data-stu-id="89d65-211">New connections will be based on the service principal authentication method for your storage account.</span></span>

  <span data-ttu-id="89d65-212">詳細については、[対象者に関するインサイトの Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-212">For more information, see [Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights](connect-service-principal.md).</span></span>

## <a name="october-2020-updates"></a><span data-ttu-id="89d65-213">2020 年 10 月の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="89d65-213">October 2020 updates</span></span>

<span data-ttu-id="89d65-214">2020 年 10 月の更新には、いくつかの機能、パフォーマンス アップグレード、およびバグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89d65-214">The updates in October 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-october-2020"></a><span data-ttu-id="89d65-215">2020 年 10 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="89d65-215">New and updated features in October 2020</span></span>

#### <a name="extensibility"></a><span data-ttu-id="89d65-216">拡張性</span><span class="sxs-lookup"><span data-stu-id="89d65-216">Extensibility</span></span>

- <span data-ttu-id="89d65-217">**Mailchimp にエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="89d65-217">**Export to Mailchimp**</span></span>

<span data-ttu-id="89d65-218">Mailchimp の既存のオーディエンス リストにセグメントをエクスポートして、顧客にパーソナライズされた電子メール エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="89d65-218">Export segments to existing audience lists in Mailchimp to provide a personalized email experience for your customers.</span></span>

<span data-ttu-id="89d65-219">詳細については、[Mailchimp 用コネクタ](export-mailchimp.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-219">For more information, see [Connector for Mailchimp](export-mailchimp.md).</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="89d65-220">データ エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="89d65-220">Data enrichment</span></span>

- <span data-ttu-id="89d65-221">**照合エンティティのソース レコードを重複排除する**</span><span class="sxs-lookup"><span data-stu-id="89d65-221">**Deduplicate the source records in a Match entity**</span></span>

<span data-ttu-id="89d65-222">重複レコードを識別するために、照合プロセスで使用されるエンティティに重複排除ルールを指定します。</span><span class="sxs-lookup"><span data-stu-id="89d65-222">Specify deduplication rules on entities used in the match process to identify duplicate records.</span></span> <span data-ttu-id="89d65-223">それらを 1 つのレコードにマージし、すべてのソース レコードをこのマージされたレコードにリンクします。</span><span class="sxs-lookup"><span data-stu-id="89d65-223">Merge them into one record and link all the source records to this merged record.</span></span> <span data-ttu-id="89d65-224">この重複排除されたレコードは、エンティティ間の照合プロセスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="89d65-224">This deduplicated record will then be used in the cross-entity matching process.</span></span>

<span data-ttu-id="89d65-225">詳細については、[照合エンティティで重複排除を定義する](match-entities.md#define-deduplication-on-a-match-entity) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-225">For more information, see [Define deduplication on a match entity](match-entities.md#define-deduplication-on-a-match-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="89d65-226">システム管理者</span><span class="sxs-lookup"><span data-stu-id="89d65-226">System administration</span></span>

- <span data-ttu-id="89d65-227">**オーケストレーション: マージの新しい更新オプション**</span><span class="sxs-lookup"><span data-stu-id="89d65-227">**Orchestration: New refresh option in Merge**</span></span>

<span data-ttu-id="89d65-228">これまで、マージ プロセスを実行すると、システムはマージと後続のプロセスに依存する、すべてのダウンストリーム プロセスを実行していました。</span><span class="sxs-lookup"><span data-stu-id="89d65-228">Until today, when you run the merge process, the system ran all the downstream processes that depend on merge and subsequent processes.</span></span> <span data-ttu-id="89d65-229">これで、セグメントやメジャーなどのダウンストリーム プロセスで使用する前に、マージ プロセス (統合された顧客エンティティ) の出力を確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="89d65-229">You can now verify the output of the merge process (the unified customer entity) before using it in downstream processing like segments or measures.</span></span>
<span data-ttu-id="89d65-230">マージ ページで、マージ ステップのみを実行し、このプロセスのみを実行することを選択できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="89d65-230">On the merge page, you can now choose to run only the merge step and run only this process.</span></span> <span data-ttu-id="89d65-231">ダウンストリーム プロセスもすべて更新するには、マージの実行とダウンストリーム プロセスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-231">To refresh all the downstream processes too, you can choose run merge and downstream processes.</span></span> 

## <a name="september-2020-updates"></a><span data-ttu-id="89d65-232">2020 年 9 月の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="89d65-232">September 2020 updates</span></span>

<span data-ttu-id="89d65-233">2020 年 9 月の更新には、いくつかの機能、パフォーマンスのアップグレード、バグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89d65-233">The updates in September 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-september-2020"></a><span data-ttu-id="89d65-234">2020 年 9 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="89d65-234">New and updated features in September 2020</span></span>

#### <a name="activities"></a><span data-ttu-id="89d65-235">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="89d65-235">Activities</span></span>

- <span data-ttu-id="89d65-236">**属性セマンティクスのインテリジェントな予測**</span><span class="sxs-lookup"><span data-stu-id="89d65-236">**Intelligent prediction of attribute semantics**</span></span>

<span data-ttu-id="89d65-237">この新機能は、データ統合プロセスに渡される入力属性のセマンティック タイプを予測します。</span><span class="sxs-lookup"><span data-stu-id="89d65-237">This new feature predicts the semantic types of input attributes that are passed on to the data unification process.</span></span> <span data-ttu-id="89d65-238">これは精度を向上させ、時間を節約する機械学習モデルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="89d65-238">It uses machine learning models that improve accuracy and save time.</span></span>

#### <a name="enrichments"></a><span data-ttu-id="89d65-239">エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="89d65-239">Enrichments</span></span>

- <span data-ttu-id="89d65-240">**説明による統計情報のエンリッチメント**</span><span class="sxs-lookup"><span data-stu-id="89d65-240">**Demographics enrichment from Experian**</span></span>

<span data-ttu-id="89d65-241">Experian の統計情報のエンリッチメントがプレビューで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="89d65-241">The demographics enrichment from Experian is now available in preview.</span></span> <span data-ttu-id="89d65-242">Experian は、消費者および企業の信用調査およびマーケティング サービスの世界的リーダーです。</span><span class="sxs-lookup"><span data-stu-id="89d65-242">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="89d65-243">[Experian のデータ エンリッチメント サービス](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) を使用することで、世帯サイズや収入などの統計情報データで顧客プロファイルをエンリッチさせ、顧客をより深く理解することができます。</span><span class="sxs-lookup"><span data-stu-id="89d65-243">With [Experian’s data enrichment services](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

<span data-ttu-id="89d65-244">この機能を使用するには、有効な Experian サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="89d65-244">To use this feature, you must have an active Experian subscription.</span></span>

<span data-ttu-id="89d65-245">詳細については、[Experian の統計情報で顧客プロファイルをエンリッチする](enrichment-experian.md) を参照してください</span><span class="sxs-lookup"><span data-stu-id="89d65-245">For more information, see [Enrich customer profiles with demographics from Experian](enrichment-experian.md)</span></span>


#### <a name="system-administration"></a><span data-ttu-id="89d65-246">システム管理者</span><span class="sxs-lookup"><span data-stu-id="89d65-246">System administration</span></span>

- <span data-ttu-id="89d65-247">**タスクの詳細ペイン**</span><span class="sxs-lookup"><span data-stu-id="89d65-247">**Task details pane**</span></span>

<span data-ttu-id="89d65-248">タスクの詳細ペインでは、システムが実行するタスクの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-248">The task details pane enables you to see details about tasks that the system runs.</span></span> <span data-ttu-id="89d65-249">これは、構成の問題を特定し、解決策を見つけるための便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="89d65-249">It's a handy way to identify issues with the configuration and find solutions.</span></span>
<span data-ttu-id="89d65-250">エラー メッセージを確認して、潜在的な問題に対処する方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-250">Review the error messages see how you address potential issues.</span></span>
 
- <span data-ttu-id="89d65-251">**処理情報をより多くのページに追加**</span><span class="sxs-lookup"><span data-stu-id="89d65-251">**Processing information added to more pages**</span></span>

<span data-ttu-id="89d65-252">この改善により、**エンティティ** と **顧客** ページでエンティティのステータスに関する情報が追加されます。</span><span class="sxs-lookup"><span data-stu-id="89d65-252">This improvement adds information about the status of your entities on the **Entities** and **Customers** page.</span></span>
 
<span data-ttu-id="89d65-253">さらに、これらの両方のページで、プロセスの進行状況に関する詳細とタスクの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-253">Additionally, you can find details about the progress of processes, along with the task details, on both of these pages.</span></span>

- <span data-ttu-id="89d65-254">**システム ステータス ページの改善**</span><span class="sxs-lookup"><span data-stu-id="89d65-254">**Improvements to system status page**</span></span>

<span data-ttu-id="89d65-255">データのエクスポートを確認する際の、**システム** > **状態** のステータス詳細テーブルの構造を改善しました。</span><span class="sxs-lookup"><span data-stu-id="89d65-255">We improved the structure of the status details table on **System** > **Status** when reviewing data exports.</span></span>
 
<span data-ttu-id="89d65-256">さらに、**詳細** 列のエラーがより詳細でアクション可能なものになりました。</span><span class="sxs-lookup"><span data-stu-id="89d65-256">Additionally, errors in the **Details** column are now more detailed and actionable.</span></span> 
 
- <span data-ttu-id="89d65-257">**キャンセルすると、ジョブが前の状態に戻ります**</span><span class="sxs-lookup"><span data-stu-id="89d65-257">**Cancel reverts job back to previous state**</span></span>

<span data-ttu-id="89d65-258">たとえば、一致プロセスでタスクをキャンセルすると、タスクは最新の状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="89d65-258">When you cancel a task, for example, in the match process, it will revert back to its latest state.</span></span> <span data-ttu-id="89d65-259">たとえば、一致プロセスが昨日完了し、今日キャンセルした場合、昨日の成功状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="89d65-259">For example, if the Match process completed yesterday and you cancel it today, it will revert to yesterday's successful state.</span></span>


## <a name="august-2020-updates"></a><span data-ttu-id="89d65-260">2020 年 8 月の更新</span><span class="sxs-lookup"><span data-stu-id="89d65-260">August 2020 updates</span></span>

<span data-ttu-id="89d65-261">2020 年 8 月の更新には、いくつかの機能、パフォーマンスのアップグレード、バグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89d65-261">The updates in August 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-august-2020"></a><span data-ttu-id="89d65-262">2020 年 8 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="89d65-262">New and updated features in August 2020</span></span>

#### <a name="data-unification"></a><span data-ttu-id="89d65-263">データ統合</span><span class="sxs-lookup"><span data-stu-id="89d65-263">Data unification</span></span>

- <span data-ttu-id="89d65-264">**データ統合中のマップ ステージのエクスペリエンスの向上**</span><span class="sxs-lookup"><span data-stu-id="89d65-264">**Improved experience for the map stage during data unification**</span></span>

  <span data-ttu-id="89d65-265">データ統合プロセスのマップ段階でのエクスペリエンスにより、エンティティ、属性を選択し、よりシームレスな方法でセマンティクスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-265">The experience to the map stage in the data unification process lets you select entities, attributes, and define semantics in a more seamless way.</span></span>

  <span data-ttu-id="89d65-266">変更内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="89d65-266">The changes include:</span></span>
  
  - <span data-ttu-id="89d65-267">エンティティとフィールドを追加に必要な対話がより少なく</span><span class="sxs-lookup"><span data-stu-id="89d65-267">fewer interactions required to add entities and fields</span></span>
  - <span data-ttu-id="89d65-268">マップ ページの検索機能の改善</span><span class="sxs-lookup"><span data-stu-id="89d65-268">improved search capabilities on the map page</span></span>
  - <span data-ttu-id="89d65-269">提案されたフィールド タイプの視覚的かつ簡単な識別</span><span class="sxs-lookup"><span data-stu-id="89d65-269">visual and easy identification of the suggested field type</span></span>

#### <a name="enrichment"></a><span data-ttu-id="89d65-270">エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="89d65-270">Enrichment</span></span>

- <span data-ttu-id="89d65-271">**より多くの市場で関心アフィニティ エンリッチメントを利用可能**</span><span class="sxs-lookup"><span data-stu-id="89d65-271">**Interest affinities enrichment available in more markets**</span></span>

  <span data-ttu-id="89d65-272">関心アフィニティ エンリッチメントの利用可能性は、米国にとどまらず、カナダ、オーストラリア、英国、フランス、ドイツの 5 つの市場に拡大しました。</span><span class="sxs-lookup"><span data-stu-id="89d65-272">We're extending the availability of the interest affinities enrichment beyond the United States to five other markets: Canada, Australia, United Kingdom, France, and Germany.</span></span> <span data-ttu-id="89d65-273">この拡張機能を使用すると、これらの市場に該当するよりも多くの関心で顧客データをエンリッチできます。</span><span class="sxs-lookup"><span data-stu-id="89d65-273">With this extension, you can enrich your customer data with more interests applicable to these markets.</span></span> <span data-ttu-id="89d65-274">また、Microsoft Graph のローカルの独自データを使用して、これらの市場にある顧客プロファイルを充実させます。</span><span class="sxs-lookup"><span data-stu-id="89d65-274">We'll also enrich your customer profiles that are located in these markets by using local proprietary data from Microsoft Graph.</span></span>
  <span data-ttu-id="89d65-275">詳細については、[ブランドと興味のアフィニティで顧客プロファイルを強化する](enrichment-microsoft-graph.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-275">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md)</span></span>


## <a name="july-2020-updates"></a><span data-ttu-id="89d65-276">2020 年 7 月の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="89d65-276">July 2020 updates</span></span>

<span data-ttu-id="89d65-277">2020 年 7 月の更新には、いくつかの機能、パフォーマンスのアップグレード、およびバグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89d65-277">The updates in July 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-july-2020"></a><span data-ttu-id="89d65-278">2020 年 7 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="89d65-278">New and updated features in July 2020</span></span>

#### <a name="extensibility"></a><span data-ttu-id="89d65-279">拡張性</span><span class="sxs-lookup"><span data-stu-id="89d65-279">Extensibility</span></span>

- <span data-ttu-id="89d65-280">**完了した統合プロセスの Power Automate トリガー**</span><span class="sxs-lookup"><span data-stu-id="89d65-280">**Power Automate trigger for completed unification process**</span></span>

  <span data-ttu-id="89d65-281">Power Automate のトリガーを拡張し、統合プロセス (マップ、一致、マージ) の更新が完了したときに通知またはアクションを作成できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="89d65-281">We have extended our triggers for Power Automate and let you create a notification or action when a refresh of the unification process (map, match, merge) is completed.</span></span>    
  <span data-ttu-id="89d65-282">詳細については、[Power Automate コネクタ](export-power-automate.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-282">For more information, see [Power Automate connector](export-power-automate.md)</span></span>

#### <a name="enrichment"></a><span data-ttu-id="89d65-283">エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="89d65-283">Enrichment</span></span>

- <span data-ttu-id="89d65-284">**より多くの市場でブランド アフィニティ エンリッチメントを利用可能**</span><span class="sxs-lookup"><span data-stu-id="89d65-284">**Brand affinities enrichment available in more markets**</span></span>

  <span data-ttu-id="89d65-285">ブランド アフィニティ エンリッチメントの利用可能性は、米国にとどまらず、カナダ、オーストラリア、英国、フランス、ドイツの 5 つの市場に拡大しました。</span><span class="sxs-lookup"><span data-stu-id="89d65-285">We're extending the availability of the brand affinities enrichment beyond the United States to five other markets: Canada, Australia, United Kingdom, France, and Germany.</span></span> <span data-ttu-id="89d65-286">この拡張機能を使用すると、これらの市場のローカル ブランドで顧客データを充実させることができます。</span><span class="sxs-lookup"><span data-stu-id="89d65-286">With this extension, you can enrich your customer data with local brands in these markets.</span></span> <span data-ttu-id="89d65-287">また、Microsoft Graph のローカルの独自データを使用して、これらの市場にある顧客プロファイルを充実させます。</span><span class="sxs-lookup"><span data-stu-id="89d65-287">We'll also enrich your customer profiles that are located in these markets by using local proprietary data from Microsoft Graph.</span></span>
  <span data-ttu-id="89d65-288">詳細については、[ブランドと興味のアフィニティで顧客プロファイルを強化する](enrichment-microsoft-graph.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-288">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md)</span></span>

## <a name="june-2020-updates"></a><span data-ttu-id="89d65-289">2020 年 6 月の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="89d65-289">June 2020 updates</span></span>

<span data-ttu-id="89d65-290">2020 年 6 月の更新には、いくつかの機能、パフォーマンスのアップグレード、およびバグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89d65-290">The updates in June 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-june-2020"></a><span data-ttu-id="89d65-291">2020 年 6 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="89d65-291">New and updated features in June 2020</span></span>

#### <a name="enrichment"></a><span data-ttu-id="89d65-292">エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="89d65-292">Enrichment</span></span>

- <span data-ttu-id="89d65-293">**Leadspace からの企業データの充実**</span><span class="sxs-lookup"><span data-stu-id="89d65-293">**Enrichment with company data from Leadspace**</span></span>
  
  <span data-ttu-id="89d65-294">Leadspace から関連する企業データを検索するために使用される統合顧客プロファイルのフィールドを定義します。</span><span class="sxs-lookup"><span data-stu-id="89d65-294">Define fields in unified customer profiles that are used to look up related company data from Leadspace.</span></span> <span data-ttu-id="89d65-295">エンリッチメント プロセスを実行した後、B2B プロファイルは、会社の規模、場所、業界など、より多くの属性でエンリッチされます。</span><span class="sxs-lookup"><span data-stu-id="89d65-295">After running the enrichment process, B2B profiles are enriched with more attributes including company size, location, industry, and more.</span></span>    
  <span data-ttu-id="89d65-296">このコラボレーションにより、サードパーティ サービスからの入力によりデータの品質を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="89d65-296">This collaboration allows you to improve the quality of your data with input from third-party services.</span></span> <span data-ttu-id="89d65-297">このエンリッチメントを使用するには、B2B 企業データにアクセスするための Leadspace からのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="89d65-297">To use this enrichment, you'll need a license from Leadspace to access its B2B company data.</span></span> <span data-ttu-id="89d65-298">システムはそのライセンスを使用して、データを継続的に強化します。</span><span class="sxs-lookup"><span data-stu-id="89d65-298">The system will use that license to keep your data enriched continuously.</span></span>    
  <span data-ttu-id="89d65-299">詳細については、[Leadspace による企業プロファイルのエンリッチメント](enrichment-leadspace.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-299">For more information, see [Enrichment of company profiles with Leadspace](enrichment-leadspace.md).</span></span>

- <span data-ttu-id="89d65-300">**エンリッチメント ハブ ページ**</span><span class="sxs-lookup"><span data-stu-id="89d65-300">**Enrichment hub page**</span></span>

  <span data-ttu-id="89d65-301">ファーストパーティおよびサードパーティのエンリッチメント プロバイダーから利用可能なすべてのデータ エンリッチメントは、同じ場所で構成されます。</span><span class="sxs-lookup"><span data-stu-id="89d65-301">All available data enrichment from first- and third-party enrichment providers gets configured in the same place.</span></span> <span data-ttu-id="89d65-302">データ エンリッチメントの構成は、共通の場所から管理されるシームレスなエクスペリエンスです。</span><span class="sxs-lookup"><span data-stu-id="89d65-302">Configuring data enrichment is a seamless experience that is managed from a common place.</span></span>    
  <span data-ttu-id="89d65-303">詳細については、[顧客プロファイルのエンリッチメント](enrichment-hub.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-303">For more information, see [Enrichment for customer profiles](enrichment-hub.md).</span></span>

- <span data-ttu-id="89d65-304">**個別のブランドと関心のアフィニティのエンリッチメント**</span><span class="sxs-lookup"><span data-stu-id="89d65-304">**Separate brand and interest affinity enrichment**</span></span>

  <span data-ttu-id="89d65-305">ブランドと興味のアフィニティが、2 つの独立したエンリッチメントとして利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="89d65-305">The brands and interests affinities are now available as two independent enrichments.</span></span> <span data-ttu-id="89d65-306">エンリッチメントを分離すると、ビジネス要件やニーズに応じて、個別に設定および管理する柔軟性が得られます。</span><span class="sxs-lookup"><span data-stu-id="89d65-306">Separated enrichments give you the flexibility to configure and manage them individually, depending on your business requirements or needs.</span></span>    
  <span data-ttu-id="89d65-307">詳細については、[ブランドと興味のアフィニティで顧客プロファイルを強化する](enrichment-microsoft-graph.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-307">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="89d65-308">拡張性</span><span class="sxs-lookup"><span data-stu-id="89d65-308">Extensibility</span></span>

- <span data-ttu-id="89d65-309">**Dynamics 365 Customer Card Add-in の統合アクティビティのクリック可能な URL**</span><span class="sxs-lookup"><span data-stu-id="89d65-309">**Clickable URLs for unified activities on the Dynamics 365 Customer Card Add-in**</span></span>

  <span data-ttu-id="89d65-310">顧客カード アドインの統合アクティビティは、アクティビティの構成中にそのような URL が定義されている場合、クリック可能な URL を表示するようになりました。</span><span class="sxs-lookup"><span data-stu-id="89d65-310">The unified activities in the Customer Card Add-in are now showing clickable URLs if such URLs have been defined during the configuration of activities.</span></span>    
  <span data-ttu-id="89d65-311">詳細については、[顧客カード アドイン](customer-card-add-in.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-311">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="89d65-312">**Dynamics 365 Customer カード アドインで利用できるブランドと興味のアフィニティ**</span><span class="sxs-lookup"><span data-stu-id="89d65-312">**Brand and interest affinities available on the Dynamics 365 Customer Card Add-in**</span></span>

  <span data-ttu-id="89d65-313">Dynamics 365 Customer カード アドインの新しいコントロールを使用すると、Dynamics 365 の顧客エンゲージメント アプリの連絡先にブランドと興味のエンリッチメントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-313">A new control on the Dynamics 365 Customer Card Add-in lets you show brand and interest enrichments on your contacts in customer engagement apps in Dynamics 365.</span></span>    
  <span data-ttu-id="89d65-314">詳細については、[顧客カード アドイン](customer-card-add-in.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-314">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="89d65-315">**Power Automate トリガーを増加**</span><span class="sxs-lookup"><span data-stu-id="89d65-315">**More Power Automate triggers**</span></span>

  <span data-ttu-id="89d65-316">Power Automate のトリガーを延長し、次のトリガーを追加しました。</span><span class="sxs-lookup"><span data-stu-id="89d65-316">We have extended our triggers for Power Automate and added the following triggers:</span></span>
  - <span data-ttu-id="89d65-317">自動完全更新 (データソース、統合、セグメント、メジャー、エクスポート) が完了したときに通知を受け取るか、アクションを実行する</span><span class="sxs-lookup"><span data-stu-id="89d65-317">Get a notification or perform an action when an automated full refresh (data sources, unification, segments, measures, exports) completes</span></span>
  - <span data-ttu-id="89d65-318">ビジネス指標のしきい値を定義します。</span><span class="sxs-lookup"><span data-stu-id="89d65-318">Define a threshold for a business measure.</span></span> <span data-ttu-id="89d65-319">たとえば、定義されたしきい値を超えたときに送信される通知を作成できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-319">For example, you can create a notification that gets sent when the defined threshold is passed.</span></span> <span data-ttu-id="89d65-320">さらに、トリガーは Power Automate でより複雑なワークフローを構築できる情報をもたらします。</span><span class="sxs-lookup"><span data-stu-id="89d65-320">Additionally, the trigger brings information that allows you to build more complex workflows in Power Automate.</span></span>    
  <span data-ttu-id="89d65-321">詳細については、[Power Automate コネクタ](export-power-automate.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-321">For more information, see [Power Automate connector](export-power-automate.md)</span></span>

- <span data-ttu-id="89d65-322">**Facebook 広告マネージャーにエクスポートする**</span><span class="sxs-lookup"><span data-stu-id="89d65-322">**Export to Facebook Ads Manager**</span></span>
  
  <span data-ttu-id="89d65-323">この機能を使用すると、セグメントを Facebook 広告マネージャーにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="89d65-323">This capability lets you export segments to Facebook Ads Manager.</span></span> <span data-ttu-id="89d65-324">セグメントはカスタム オーディエンスとしてエクスポートされ、Facebook マーケティング キャンペーンや広告で統合顧客プロファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="89d65-324">Segments are exported as custom audiences to use unified customer profiles in Facebook marketing campaigns and ads.</span></span> <span data-ttu-id="89d65-325">カスタム対象者は、Facebook 広告マネージャーを介して Instagram でキャンペーンを作成するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-325">The custom audiences are also usable to create campaigns on Instagram through Facebook Ads Manager.</span></span>    
  <span data-ttu-id="89d65-326">詳細については、[Facebook広告マネージャーのコネクタ](export-facebook.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-326">For more information, see [Connector for Facebook Ads Manager](export-facebook.md).</span></span>

#### <a name="predictions"></a><span data-ttu-id="89d65-327">予測</span><span class="sxs-lookup"><span data-stu-id="89d65-327">Predictions</span></span>

- <span data-ttu-id="89d65-328">**サブスクリプション離反予測**</span><span class="sxs-lookup"><span data-stu-id="89d65-328">**Subscription churn prediction**</span></span>

  <span data-ttu-id="89d65-329">ガイド式のエクスペリエンスに従って、クラウド サービス、顧客メンバーシップ、その他のセクターなどのサブスクリプション エリアに離反予測を作成します。</span><span class="sxs-lookup"><span data-stu-id="89d65-329">Follow a guided experience to create churn prediction in subscription areas like cloud services, customer membership, and other sectors.</span></span> 

  <span data-ttu-id="89d65-330">サブスクリプション離反予測機能を使用すると、データ サイエンティストに依頼することなく、顧客がサブスクリプション ベースの製品またはサービスの使用を停止する可能性を予測できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-330">The subscription churn prediction feature enables you to predict the likelihood of a customer stopping the use of subscription-based products or services without engaging a data scientist.</span></span> <span data-ttu-id="89d65-331">予測スコアを使用すると、顧客に関する他の情報を組み合わせて、離反リスクの高いセグメントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-331">Using the prediction score, you can combine other information about your customers to create segments of high churn risk.</span></span> <span data-ttu-id="89d65-332">このセグメントのおかげで、マーケティング、顧客サポート、およびその他のシナリオで顧客を直接ターゲットにして、特定の顧客の解約のリスクを減らし、収益を改善し、コストを削減することができます。</span><span class="sxs-lookup"><span data-stu-id="89d65-332">With the help of this segment, you can directly target customers in marketing, customer support, and other scenarios to reduce the risk of churn for specific customers to improve revenue and reduce cost.</span></span>

  <span data-ttu-id="89d65-333">エクスペリエンス内で、離反の定義をビジネスに固有の時間ベースのウィンドウとして構成できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-333">Within the experience, you can configure the definition of churn as a time-based window specific to your business.</span></span> <span data-ttu-id="89d65-334">たとえば、月単位のサブスクリプション プロセスがあるビデオ ストリーミング ビジネスでは、サブスクリプションの有効期限が切れてから 15 日後に顧客が解約したと見なす場合があります。</span><span class="sxs-lookup"><span data-stu-id="89d65-334">For example, a video streaming business that has a monthly subscription process might want to consider a customer to have churned after 15 days after the expiration of their subscription.</span></span>

  <span data-ttu-id="89d65-335">予測を続けると、どのデータが必要かがわかり、顧客のチャーンの予測に必要なフィールドにビジネスに関するデータをマッピングできるようになります。</span><span class="sxs-lookup"><span data-stu-id="89d65-335">As you continue through the prediction, we'll guide you through what data is needed, and enable you to map data about your business to fields required to predict churn for your customers.</span></span> <span data-ttu-id="89d65-336">ビジネス情報の変化に応じて、変化するビジネス環境に適応するためにシステムの新しい情報を再トレーニングするスケジュールを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="89d65-336">As business information changes, you can also set a schedule to retrain on new information in your system to adapt to changing business circumstances.</span></span>    
  <span data-ttu-id="89d65-337">詳細については、[サブスクリプション離反予測 (プレビュー)](predict-subscription-churn.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-337">For more information, see [Subscription churn prediction (preview)](predict-subscription-churn.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="89d65-338">セグメント</span><span class="sxs-lookup"><span data-stu-id="89d65-338">Segments</span></span>

- <span data-ttu-id="89d65-339">**類似する顧客を見つける**</span><span class="sxs-lookup"><span data-stu-id="89d65-339">**Find similar customers**</span></span>
  
  <span data-ttu-id="89d65-340">人工知能を使用して、顧客ベースで同様の顧客を見つけます。</span><span class="sxs-lookup"><span data-stu-id="89d65-340">Find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="89d65-341">二項分類機械学習モデルは、拡張セグメントの顧客に類似性スコアを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="89d65-341">A binary classification machine learning model assigns a similarity score to customers in the expanded segment.</span></span> <span data-ttu-id="89d65-342">このスコアは、ソース セグメント内の顧客との類似性に基づいています。</span><span class="sxs-lookup"><span data-stu-id="89d65-342">The score is based on the similarity to customers in the source segment.</span></span> <span data-ttu-id="89d65-343">類似性スコアに応じて、新しく作成されたセグメントに顧客プロファイルが追加されます。</span><span class="sxs-lookup"><span data-stu-id="89d65-343">Depending on the similarity score, customer profiles are added to a newly created segment.</span></span>

  <span data-ttu-id="89d65-344">デジタル マーケティングでは類似モデリングと呼ばれることもあり、AI モデルを使用して、より多くの属性を考慮に入れることで、顧客の別のセグメントに類似している顧客を見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="89d65-344">Sometimes referred to as lookalike modeling in digital marketing, it uses an AI model to help find customers who are similar to another segment of your customers by factoring in more attributes.</span></span> <span data-ttu-id="89d65-345">これにより、属性を選択できるだけでなく、この新しいセグメントに含める必要のある顧客の最大数を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="89d65-345">It not only allows you to pick the attributes but also allows you to specify the maximum number of customers who should be in this new segment.</span></span> <span data-ttu-id="89d65-346">AI モデルは、選択した属性に基づいて各顧客の類似度スコアを計算し、平均類似度スコアが高い顧客を見つけます。</span><span class="sxs-lookup"><span data-stu-id="89d65-346">The AI model will then compute similarity scores for each customer based on your selected attributes and find customers with the higher average similarity score.</span></span> <span data-ttu-id="89d65-347">結果のセグメントには、元のセグメントの顧客に類似する顧客が含まれます。</span><span class="sxs-lookup"><span data-stu-id="89d65-347">The resulting segment will include customers who look similar to the customer in your original segment.</span></span>    
  <span data-ttu-id="89d65-348">詳細については、[類似顧客](find-similar-customer-segments.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-348">For more information, see [Similar Customers](find-similar-customer-segments.md).</span></span>

- <span data-ttu-id="89d65-349">**セグメントの重複と差別化要因**</span><span class="sxs-lookup"><span data-stu-id="89d65-349">**Segment overlap and differentiators**</span></span>

  <span data-ttu-id="89d65-350">セグメントの重複により、2 つ以上のセグメントに共通する顧客の数と数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-350">Segment overlap lets you see how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="89d65-351">たとえば、高支出のセグメントが満足度の高い顧客セグメントとどのようにオーバーラップするか、離反する顧客セグメントが満足度の低い顧客セグメントとどのように重複するかなどです。</span><span class="sxs-lookup"><span data-stu-id="89d65-351">For example, how a high-spenders segment overlaps with a high-satisfaction customers segment or how a churning customer segment overlaps with a low-satisfaction customers segment.</span></span> <span data-ttu-id="89d65-352">さらに、選択した追加の属性に基づいて重複がどのように変化するかを分析できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-352">Additionally, you can analyze how the overlap changes based on an extra attribute of your choice.</span></span>

  <span data-ttu-id="89d65-353">セグメントの差別化要因は、あるセグメントを他の顧客や他のセグメントと差別化する要素を明らかにします。</span><span class="sxs-lookup"><span data-stu-id="89d65-353">Segment differentiators reveal what differentiates one segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="89d65-354">必要なのはセグメントを特定することだけであり、システムは、差別化要因のランク付けされたリストの形式で、セグメントを区別するプロファイル属性とメジャーを識別します。</span><span class="sxs-lookup"><span data-stu-id="89d65-354">All you need to do is identify a segment and the system will identify profile attributes and measures that distinguish the segment in the form of a ranked list of differentiators—from the strongest differentiator to the weakest.</span></span>    
  <span data-ttu-id="89d65-355">詳細については、[セグメント インサイト (プレビュー)](segment-insights.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-355">For more information, see [Segment insights (preview)](segment-insights.md).</span></span>

- <span data-ttu-id="89d65-356">**セグメントの寿命**</span><span class="sxs-lookup"><span data-stu-id="89d65-356">**Segment lifetime**</span></span>
  
  <span data-ttu-id="89d65-357">セグメントをアクティブまたは非アクティブにするスケジュールを定義します。</span><span class="sxs-lookup"><span data-stu-id="89d65-357">Define a schedule to activate or deactivate a segment.</span></span>    
  <span data-ttu-id="89d65-358">詳細については、[既存セグメントの管理](segments.md#manage-existing-segments)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-358">For more information, see [Manage existing segments](segments.md#manage-existing-segments).</span></span>

## <a name="may-2020-updates"></a><span data-ttu-id="89d65-359">2020 年 5 月の更新</span><span class="sxs-lookup"><span data-stu-id="89d65-359">May 2020 updates</span></span>

<span data-ttu-id="89d65-360">2020 年 5 月の更新には、いくつかの機能、パフォーマンスのアップグレード、バグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89d65-360">The updates in May 2020 includes several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-may-2020"></a><span data-ttu-id="89d65-361">2020 年 5 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="89d65-361">New and updated features in May 2020</span></span>

#### <a name="data-ingestion"></a><span data-ttu-id="89d65-362">データ インジェスト</span><span class="sxs-lookup"><span data-stu-id="89d65-362">Data ingestion</span></span>

- <span data-ttu-id="89d65-363">**リアルタイムのデータ インジェスト: 履歴ビュー**</span><span class="sxs-lookup"><span data-stu-id="89d65-363">**Real-time data ingestion: history views**</span></span>

  <span data-ttu-id="89d65-364">API を使用してリアルタイムの更新を取り込むと、これらの更新の最大 30 日間の集計履歴を表示できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-364">When using our API to ingest real-time updates, you can see up to 30 days of aggregated history for these updates.</span></span> <span data-ttu-id="89d65-365">結果、ソースシステム、その他の有用なメタデータを含む、成功または失敗したすべての API 呼び出しの集計にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="89d65-365">You have access to aggregates of all successful or failed API calls including their outcome, source system, and other useful metadata.</span></span>    
  <span data-ttu-id="89d65-366">詳細については、[リアルタイム ワークフロー インジェスト](real-time-data-ingestion.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-366">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

- <span data-ttu-id="89d65-367">**リアルタイムのデータ取り込み: プロファイルの更新**</span><span class="sxs-lookup"><span data-stu-id="89d65-367">**Real-time data ingestion: profile updates**</span></span>

  <span data-ttu-id="89d65-368">リアルタイム データ取り込みのこの拡張により、特定のユーザー プロファイル フィールドへの変更を数秒以内に確認できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-368">This extension of the real-time data ingestion lets you see, within seconds, changes to specific user profile fields.</span></span>    
  <span data-ttu-id="89d65-369">アクティビティのリアルタイム機能に加えて、システムはプロファイル フィールドへの待ち時間が少ない更新をサポートします。</span><span class="sxs-lookup"><span data-stu-id="89d65-369">In addition to the real-time functionality for activities, the system supports low latency updates to profile fields.</span></span> <span data-ttu-id="89d65-370">プロファイル フィールドのリアルタイム更新には有効期限があるため、スケジュールされた更新の代わりにはなりません。</span><span class="sxs-lookup"><span data-stu-id="89d65-370">Real-time updates for profile fields have an expiration time and are therefore not a replacement for scheduled refreshes.</span></span>    
  <span data-ttu-id="89d65-371">詳細については、[リアルタイム ワークフロー インジェスト](real-time-data-ingestion.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-371">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="89d65-372">拡張性</span><span class="sxs-lookup"><span data-stu-id="89d65-372">Extensibility</span></span>

- <span data-ttu-id="89d65-373">**カスタマー カード アドインのタイムラインとページ編集を更新**</span><span class="sxs-lookup"><span data-stu-id="89d65-373">**Updated timeline and pagination on the Customer Card Add-in**</span></span>

  <span data-ttu-id="89d65-374">顧客カード アドイン ソリューションのタイムラインは、活動のタイムラインと一致します。</span><span class="sxs-lookup"><span data-stu-id="89d65-374">The timeline of the Customer Card Add-in solution matches the activity timeline.</span></span> <span data-ttu-id="89d65-375">タイムラインのページ編集が改善され、一度に最大 50 のアクティビティが表示されました。</span><span class="sxs-lookup"><span data-stu-id="89d65-375">The pagination of the timeline improved, showing up to 50 activities at once.</span></span> <span data-ttu-id="89d65-376">また、タイムラインでより多くのアクティビティをロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="89d65-376">It also allows loading more activities in the timeline.</span></span>    
  <span data-ttu-id="89d65-377">詳細については、[顧客カード アドイン](customer-card-add-in.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-377">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="89d65-378">セグメント変更の **Power Automate トリガー**</span><span class="sxs-lookup"><span data-stu-id="89d65-378">**Power Automate trigger for segment changes**</span></span>

  <span data-ttu-id="89d65-379">Power Automate のトリガーはフローを何から構築できるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="89d65-379">Triggers for Power Automate define what you can build a flow from.</span></span> <span data-ttu-id="89d65-380">新しく追加されたトリガーを使用すると、セグメントのしきい値を定義できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-380">The newly added trigger lets you define a threshold for a segment.</span></span> <span data-ttu-id="89d65-381">たとえば、定義されたしきい値を超えたときに送信される通知を作成できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-381">For example, you can create a notification that gets sent when the defined threshold is passed.</span></span>    
  <span data-ttu-id="89d65-382">詳細については  [Power Automate コネクタ](export-power-automate.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-382">For more information, see [Power Automate connector](export-power-automate.md).</span></span>

- <span data-ttu-id="89d65-383">**カスタム モデルのマルチテナント型のサポート**</span><span class="sxs-lookup"><span data-stu-id="89d65-383">**Multitenant support for custom models**</span></span>

  <span data-ttu-id="89d65-384">異なる Azure Machine Learning テナントの Web サービスを使用して、カスタム モデルのワークフローを構成します。</span><span class="sxs-lookup"><span data-stu-id="89d65-384">Configure workflows for custom models with a web service of a different Azure Machine Learning tenant.</span></span> <span data-ttu-id="89d65-385">カスタム モデルの新しいワークフローを作成するときに、Azure Machine Learning のテナントにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="89d65-385">You can sign in to the Azure Machine Learning tenant when creating a new workflow for custom models.</span></span> <span data-ttu-id="89d65-386">この機能は、独自のカスタム Azure Machine Learning Webサービスと統合する既存の機能への追加です。</span><span class="sxs-lookup"><span data-stu-id="89d65-386">This capability is an addition to the existing capability of integrating with your own custom Azure Machine Learning web service.</span></span>    
  <span data-ttu-id="89d65-387">詳細については、[カスタム機械学習モデル](custom-models.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-387">For more information, see [Custom machine learning models](custom-models.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="89d65-388">セグメント</span><span class="sxs-lookup"><span data-stu-id="89d65-388">Segments</span></span>

- <span data-ttu-id="89d65-389">**エンティティ パスの自動化**</span><span class="sxs-lookup"><span data-stu-id="89d65-389">**Entity path automation**</span></span>

  <span data-ttu-id="89d65-390">セグメントを作成するとき、ユーザーはエンティティ パスを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89d65-390">When creating a segment, users need to define the entity path.</span></span> <span data-ttu-id="89d65-391">この機能は、エンティティ パスの定義を自動化する最初のステップとして、念頭に置いているセグメンテーション基準に集中できるようにします。</span><span class="sxs-lookup"><span data-stu-id="89d65-391">This capability takes a first step at automating the entity path definition so you can focus on the segmentation criteria that you have in mind.</span></span>    
  <span data-ttu-id="89d65-392">顧客のセグメント化に使用するエンティティが統合顧客エンティティに直接関連している場合、エンティティ パスを定義する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="89d65-392">If the entity by which you want to segment your customers is directly related to the unified customer entity, you won't need to define the entity path anymore.</span></span> <span data-ttu-id="89d65-393">ただし、エンティティ パスが複数ある場合でも、手動で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89d65-393">However, if there is more than one possible entity path, you still need to define it manually.</span></span>

- <span data-ttu-id="89d65-394">**複数のセグメントでのアクション**</span><span class="sxs-lookup"><span data-stu-id="89d65-394">**Actions on multiple segments**</span></span>
  
  <span data-ttu-id="89d65-395">ユーザーは複数のセグメントを選択して、ワンクリックでセグメントの更新などのアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-395">Users can select multiple segments and take actions on them, like refreshing the segments, with a single click.</span></span>    

- <span data-ttu-id="89d65-396">**セグメントを最新の情報に更新する**</span><span class="sxs-lookup"><span data-stu-id="89d65-396">**Refresh segments**</span></span>

  <span data-ttu-id="89d65-397">ユーザーは単一のセグメントを更新するか、更新するセグメントのみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-397">Users can refresh a single segment or select only the segments they want to refresh.</span></span>    

  
- <span data-ttu-id="89d65-398">**複合セグメントの改善**</span><span class="sxs-lookup"><span data-stu-id="89d65-398">**Improvements to compounded segments**</span></span>

  <span data-ttu-id="89d65-399">ユーザーは、他のセグメントに基づくセグメントを作成、編集、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-399">Users can create, edit, and delete segments that are based on other segments.</span></span> <span data-ttu-id="89d65-400">たとえば、3 番目のセグメント上に構築された別のセグメント上に構築されたセグメントです。</span><span class="sxs-lookup"><span data-stu-id="89d65-400">For example, a segment constructed on another segment that was constructed on a third segment.</span></span>    

- <span data-ttu-id="89d65-401">**セグメントのリスト ページ**</span><span class="sxs-lookup"><span data-stu-id="89d65-401">**Segment list page**</span></span>

  <span data-ttu-id="89d65-402">セグメント ページの新しいデザインでは、より多くのセグメントを一度に表示できるリスト形式を使用しています。</span><span class="sxs-lookup"><span data-stu-id="89d65-402">The new design of the segments page uses a list format that lets you see more segments at once.</span></span> <span data-ttu-id="89d65-403">検索フィールドが追加され、セグメントをすばやく見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="89d65-403">A search field is added to find segments quickly.</span></span> <span data-ttu-id="89d65-404">ユーザーは、ダウンロードや削除などのアクションを一度に複数のセグメントに適用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="89d65-404">Users can now apply actions like downloading or deleting on multiple segments at once.</span></span> <span data-ttu-id="89d65-405">新しいトレンド エクスペリエンスが導入され、セグメントの重要な変更をすばやく識別します。</span><span class="sxs-lookup"><span data-stu-id="89d65-405">A new trend experience is introduced to quickly identify significant changes on segments.</span></span>    
  <span data-ttu-id="89d65-406">詳細については、[セグメントの作成と管理](segments.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="89d65-406">For more information, see [Create and manage segments](segments.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="89d65-407">システム管理者</span><span class="sxs-lookup"><span data-stu-id="89d65-407">System administration</span></span>

- <span data-ttu-id="89d65-408">**Microsoft Dynamics 365 Online Government で利用可能な Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="89d65-408">**Customer Insights available in Microsoft Dynamics 365 Online Government**</span></span>

  <span data-ttu-id="89d65-409">インタラクション用のチャネルがますます増えており、市民データは無数のシステムに分散しており、サイロ化されたデータや市民インタラクションに関する情報の断片化されたビューにつながります。</span><span class="sxs-lookup"><span data-stu-id="89d65-409">With more and more channels for interactions, citizen data is scattered across myriad systems, leading to siloed data, and a fragmented view of information about citizen interactions.</span></span> <span data-ttu-id="89d65-410">各市民のチャネル間の相互作用を完全に把握することなくして、政府が大規模に近代化することは不可能です。</span><span class="sxs-lookup"><span data-stu-id="89d65-410">Without a complete view of each citizen's interactions across channels, it's impossible for governments to modernize at scale.</span></span> <span data-ttu-id="89d65-411">Microsoft は、一貫性のある応答性の高いエクスペリエンスに対する市民の期待に応えるために、政府のテクノロジー ニーズをサポートすることに尽力しています。</span><span class="sxs-lookup"><span data-stu-id="89d65-411">Microsoft is committed to supporting the technology needs of government to keep up with citizen expectations for consistent and responsive experiences.</span></span>    
  <span data-ttu-id="89d65-412">2020 年リリースのウェーブ 1 があれば、Dynamics 365 Customer Insights は米国政府機関のより高いコンプライアンス ニーズを満たすために構築された環境である、Government Community Cloud (GCC) で利用できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-412">With 2020 release wave 1, Dynamics 365 Customer Insights will be available for the Government Community Cloud (GCC), an environment built to meet the higher compliance needs of United States government agencies.</span></span> <span data-ttu-id="89d65-413">代理店は、市民の統一されたビューを取得し、構築済みの AI を使用して、相互作用を改善し、従業員に力を与え、コミュニティを変革する一方で、IT の複雑さを軽減し、米国のコンプライアンスおよびセキュリティ基準を満たします。</span><span class="sxs-lookup"><span data-stu-id="89d65-413">Agencies gain a unified view of citizens and use prebuilt AI to derive insights that improve interactions, empower employees, and transform communities, while reducing IT complexity and meeting United States compliance and security standards.</span></span> <span data-ttu-id="89d65-414">Dynamics 365 Government は、US Federal Risk and Authorization Management Program (FedRAMP) の厳しい要件を満たし、米国連邦政府機関が Microsoft Cloud のコスト削減と厳格なセキュリティの恩恵を受けることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="89d65-414">Dynamics 365 Government meets the demanding requirements of the US Federal Risk and Authorization Management Program (FedRAMP), enabling United States federal agencies to benefit from the cost savings and rigorous security of the Microsoft Cloud.</span></span>

## <a name="april-2020-updates"></a><span data-ttu-id="89d65-415">2020 年 4 月の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="89d65-415">April 2020 updates</span></span>

<span data-ttu-id="89d65-416">2020 年 4 月の更新には、いくつかの機能、パフォーマンスのアップグレード、バグ修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89d65-416">The updates in April 2020 includes several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-april-2020"></a><span data-ttu-id="89d65-417">2020 年 4 月の新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="89d65-417">New and updated features in April 2020</span></span>

#### <a name="activities"></a><span data-ttu-id="89d65-418">活動 </span><span class="sxs-lookup"><span data-stu-id="89d65-418">Activities</span></span>

- <span data-ttu-id="89d65-419">**アクティビティ エンティティを標準のアクティビティ タイプにマッピングする**</span><span class="sxs-lookup"><span data-stu-id="89d65-419">**Map activity entity to standard activity type**</span></span>
  
  <span data-ttu-id="89d65-420">アクティビティの構成とストレージは現在、それらをタイムラインで表示するための静的な設計に基づいています。</span><span class="sxs-lookup"><span data-stu-id="89d65-420">Activity configuration and storage are currently based on a static design to view them in a timeline.</span></span> <span data-ttu-id="89d65-421">現時点では、AI モデルで複数のユースケースが発生する可能性のあるアクティビティの意味的な意味が十分に活用されていません。</span><span class="sxs-lookup"><span data-stu-id="89d65-421">The semantic meaning of activities, which has potential for multiple use-cases in AI models, isn't fully used at the moment.</span></span> <span data-ttu-id="89d65-422">私たちは、活動のタイプと活動のより良い意味の理解に基づいて、活動のタイムラインをより動的にする予定です。</span><span class="sxs-lookup"><span data-stu-id="89d65-422">We plan to make the activity timeline more dynamic, based on the activity type and better semantic understanding of the activities.</span></span> <span data-ttu-id="89d65-423">この機能は、取り込まれたアクティビティの Common Data Model で定義されているアクティビティ タイプを識別することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="89d65-423">This feature aims to identify the activity type as defined in Common Data Model for any ingested activity.</span></span>
  <span data-ttu-id="89d65-424">詳細については、[顧客アクティビティ](activities.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-424">For more information, see [Customer activities](activities.md).</span></span>

#### <a name="data-ingestion"></a><span data-ttu-id="89d65-425">データ インジェスト</span><span class="sxs-lookup"><span data-stu-id="89d65-425">Data ingestion</span></span>

- <span data-ttu-id="89d65-426">**リアルタイムのデータ取り込み: アクティビティ**</span><span class="sxs-lookup"><span data-stu-id="89d65-426">**Real-time data ingestion: activities**</span></span>
  
  <span data-ttu-id="89d65-427">リアルタイム データ インジェストは、後続のスケジュールされた更新が、このデータをデータ ソースから取得するまで、データを即座に使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="89d65-427">Real-time data ingestion provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>    
  <span data-ttu-id="89d65-428">詳細については、[リアルタイム ワークフロー インジェスト](real-time-data-ingestion.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-428">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

- <span data-ttu-id="89d65-429">**データ準備の改善**</span><span class="sxs-lookup"><span data-stu-id="89d65-429">**Improvements to data preparation**</span></span>
  
  <span data-ttu-id="89d65-430">エンティティで取り込んだデータの詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="89d65-430">Learn more about the data ingested in an entity.</span></span> <span data-ttu-id="89d65-431">データサマリーを使用すると、適切なアクションを実行するのに役立つデータ品質特性を理解できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-431">With the data summary, you can understand the data quality characteristics that can help to take appropriate action.</span></span>    
  <span data-ttu-id="89d65-432">詳細については、[エンティティ データの検索](entities.md#exploring-a-specific-entitys-data) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-432">For more information, see [Explore entity data](entities.md#exploring-a-specific-entitys-data).</span></span>

- <span data-ttu-id="89d65-433">**Common Data Service でDynamics 365 から分析データを取り込む**</span><span class="sxs-lookup"><span data-stu-id="89d65-433">**Ingest analytical data from Dynamics 365 with Common Data Service**</span></span>
  
  <span data-ttu-id="89d65-434">Common Data Service は、データ ソースを作成する方法として利用できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-434">Common Data Service is available as a way to create data sources.</span></span> <span data-ttu-id="89d65-435">既存の Dynamics 365 のお客様は、分析エンティティを Common Data Service から Customer Insights へ取り込めます。</span><span class="sxs-lookup"><span data-stu-id="89d65-435">Existing Dynamics 365 customers can ingest analytical entities from Common Data Service to Customer Insights.</span></span> <span data-ttu-id="89d65-436">1 つのデータ ソースは、Customer Insights 環境で同じ Common Data Service 管理のレイクを同時に使用できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-436">A single data source can simultaneously use the same Common Data Service-managed lake in a Customer Insights environment.</span></span>    
  <span data-ttu-id="89d65-437">詳細については、[Common Data Service 管理型データ レイクでデータに接続する](connect-common-data-service-lake.md)。</span><span class="sxs-lookup"><span data-stu-id="89d65-437">For more information, see [Connect to data in a Common Data Service managed data lake](connect-common-data-service-lake.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="89d65-438">拡張性</span><span class="sxs-lookup"><span data-stu-id="89d65-438">Extensibility</span></span>

- <span data-ttu-id="89d65-439">**LiveRamp へのエクスポート**</span><span class="sxs-lookup"><span data-stu-id="89d65-439">**Export to LiveRamp**</span></span>

  <span data-ttu-id="89d65-440">LiveRamp® でデータをアクティブ化して、デジタル、ソーシャル、テレビのエコシステム全体で 500 を超えるプラットフォームに接続します。</span><span class="sxs-lookup"><span data-stu-id="89d65-440">Activate your data in LiveRamp® to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="89d65-441">LiveRamp のデータを、広告キャンペーンのターゲット設定、非表示、パーソナライズに使用します。</span><span class="sxs-lookup"><span data-stu-id="89d65-441">Use your data in LiveRamp for targeting, suppressing, and personalizing ad campaigns.</span></span>    
  <span data-ttu-id="89d65-442">詳細については [LiveRamp&reg; コネクタ](export-liveramp.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-442">For more information, see [LiveRamp&reg; connector](export-liveramp.md).</span></span>

- <span data-ttu-id="89d65-443">**Customer Insights のチーム アドイン**</span><span class="sxs-lookup"><span data-stu-id="89d65-443">**Customer Insights Teams Add-in**</span></span>
  
  <span data-ttu-id="89d65-444">ボットは、統合された顧客プロファイルの検索機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="89d65-444">The bot provides lookup capabilities for unified customer profiles.</span></span> <span data-ttu-id="89d65-445">結果の顧客プロファイルから最大 15 フィールドのカードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="89d65-445">It will show a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="89d65-446">複数の一致は、プロファイルを選択できる結果の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="89d65-446">Multiple matches return a list of results where you can select a profile.</span></span>    
  <span data-ttu-id="89d65-447">詳しくは、[Customer Insights のチーム ボット](export-teams-bot.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="89d65-447">For more information, see [Teams bot for Customer Insights](export-teams-bot.md).</span></span>

#### <a name="measures"></a><span data-ttu-id="89d65-448">メジャー</span><span class="sxs-lookup"><span data-stu-id="89d65-448">Measures</span></span>

- <span data-ttu-id="89d65-449">**メジャー リスト ページ**</span><span class="sxs-lookup"><span data-stu-id="89d65-449">**Measure list page**</span></span>
  
  <span data-ttu-id="89d65-450">メジャー ページの改善には、単一のメジャーや複数のメジャーに対するアクションのサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="89d65-450">Improvements to the measures page include support for actions on a single measure and on multiple measures at once.</span></span> <span data-ttu-id="89d65-451">さらに、メジャーをすばやく見つけて追跡するための検索フィールドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="89d65-451">Additionally, you'll find a search field to find and track measures quickly.</span></span>    
  <span data-ttu-id="89d65-452">詳細については、[セグメントの作成と管理](segments.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="89d65-452">For more information, see [Create and manage segments](segments.md).</span></span>

- <span data-ttu-id="89d65-453">**複合型メジャーの改善**</span><span class="sxs-lookup"><span data-stu-id="89d65-453">**Improvements to compounded measures**</span></span>
  
  <span data-ttu-id="89d65-454">ユーザーは、他のメジャーに基づくメジャーを作成、編集、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-454">Users can create, edit, and delete measures that are based on other measures.</span></span> <span data-ttu-id="89d65-455">たとえば、3 番目のメジャー上に構築された別のメジャー上に構築されたメジャーです。</span><span class="sxs-lookup"><span data-stu-id="89d65-455">For example, a measure constructed on another measure that was constructed on a third measure.</span></span>

#### <a name="segments"></a><span data-ttu-id="89d65-456">セグメント</span><span class="sxs-lookup"><span data-stu-id="89d65-456">Segments</span></span>

- <span data-ttu-id="89d65-457">**別の演算子**</span><span class="sxs-lookup"><span data-stu-id="89d65-457">**Another operator**</span></span>
  
  <span data-ttu-id="89d65-458">インセット演算子を使用すると、いくつかの可能な文字列値で顧客をセグメント化できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-458">The In-set operator allows segmentation for customers by several possible string values.</span></span> <span data-ttu-id="89d65-459">この演算子が追加される前は、複数の OR 条件でそのようなセグメントを作成する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="89d65-459">Before this operator was added, you had to construct such segments with multiple OR conditions.</span></span> <span data-ttu-id="89d65-460">インセット演算子を使用すると、単一の条件でそれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="89d65-460">The In-set operator lets you do that with a single condition.</span></span>    
  <span data-ttu-id="89d65-461">詳細については、[セグメントの作成と管理](segments.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="89d65-461">For more information, see [Create and manage segments](segments.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="89d65-462">システム管理者</span><span class="sxs-lookup"><span data-stu-id="89d65-462">System administration</span></span>

- <span data-ttu-id="89d65-463">**構成設定を新規環境にコピーする**</span><span class="sxs-lookup"><span data-stu-id="89d65-463">**Copy configuration settings to a new environment**</span></span>
  
  <span data-ttu-id="89d65-464">構成をある環境から別の環境にコピーします。</span><span class="sxs-lookup"><span data-stu-id="89d65-464">Copy your configuration from one environment to another.</span></span> <span data-ttu-id="89d65-465">新しい環境を作成するときに、構成のコピー元となる既存の環境を選択できます。</span><span class="sxs-lookup"><span data-stu-id="89d65-465">While creating a new environment, you can select an existing environment you want to copy the configuration from.</span></span> <span data-ttu-id="89d65-466">現在、データソース、データ統合、リレーションシップ、メジャー、コピーするセグメントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="89d65-466">We currently support data sources, data unification, relationships, measures, and segments to be copied.</span></span> <span data-ttu-id="89d65-467">データ ソース認証情報と実際のデータはコピーされません。</span><span class="sxs-lookup"><span data-stu-id="89d65-467">Data source credentials and actual data aren't copied.</span></span>    
  <span data-ttu-id="89d65-468">詳細については、[環境を管理する](manage-environments.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d65-468">For more information, see [Manage environments](manage-environments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]