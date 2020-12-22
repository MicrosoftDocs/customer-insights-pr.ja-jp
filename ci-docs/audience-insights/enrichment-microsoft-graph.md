---
title: Microsoft Graph を使用して顧客プロファイルを強化する
description: Microsoft Graph からの独自のデータを使用して、顧客データをブランドや関心のアフィニティでエンリッチさせます。
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406161"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="67833-103">ブランドと関心のアフィニティで顧客プロファイルをエンリッチさせる (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="67833-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="67833-104">Microsoft Graph からの独自のデータを使用して、顧客データをブランドや関心のアフィニティでエンリッチさせます。</span><span class="sxs-lookup"><span data-stu-id="67833-104">Use proprietary data from the Microsoft Graph to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="67833-105">これらの類似性は、既存の顧客と類似した統計を持つ人々のデータに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="67833-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="67833-106">この情報は、特定のブランドや関心事に対する顧客の親近感に基づいて、顧客をよりよく理解し、セグメント化に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="67833-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="67833-107">対象者に関するインサイトで **データ** > **エンリッチメント** に移動して、[エンリッチメントを構成および表示](enrichment-hub.md) します。</span><span class="sxs-lookup"><span data-stu-id="67833-107">In ausience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="67833-108">ブランド アフィニティのエンリッチメントを設定するには、**見つける** タブを選択し、**ブランド** タイルで **データを拡充する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67833-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="67833-109">関心アフィニティのエンリッチメントを設定するには、**見つける** タブを選択し、**関心** タイルで **データを拡充する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67833-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="67833-110">![ブランドと関心タイル](media/BrandsInterest-tile-Hub.png "ブランドと関心タイル")</span><span class="sxs-lookup"><span data-stu-id="67833-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="about-microsoft-graph"></a><span data-ttu-id="67833-111">Microsoft Graph について</span><span class="sxs-lookup"><span data-stu-id="67833-111">About Microsoft Graph</span></span>

<span data-ttu-id="67833-112">Microsoft Graph のオンライン検索データを使用して、さまざまな人口統計セグメント (年齢、性別、または場所による定義) 全体のブランドと関心アフィニティを見つけます。</span><span class="sxs-lookup"><span data-stu-id="67833-112">We use online search data from the Microsoft Graph to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="67833-113">ブランドまたは関心のオンライン検索ボリュームは、他のセグメントと比較して、人口統計セグメントがそのブランドまたは関心にどれだけのアフィニティがあるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="67833-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

<span data-ttu-id="67833-114">[Microsoft Graph について詳しく知る](https://docs.microsoft.com/graph/overview)。</span><span class="sxs-lookup"><span data-stu-id="67833-114">[Learn more about Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="affinity-score-and-confidence"></a><span data-ttu-id="67833-115">類似性スコアと信頼度</span><span class="sxs-lookup"><span data-stu-id="67833-115">Affinity score and confidence</span></span>

<span data-ttu-id="67833-116">**類似性スコア** は 100 点満点のスケールで計算され、100 点がブランドまたは関心対象に対して最も高い類似性を有するセグメントを表します。</span><span class="sxs-lookup"><span data-stu-id="67833-116">The **affinity score** is calculated on a 100-point scale, with 100 representing the segment that has the highest affinity for a brand or interest.</span></span>

<span data-ttu-id="67833-117">**アフィニティの信頼** は 100 ポイントのスケールでも計算されます。</span><span class="sxs-lookup"><span data-stu-id="67833-117">The **affinity confidence** is also calculated on a 100-point scale.</span></span> <span data-ttu-id="67833-118">これは、セグメントがブランドまたは関心に対してアフィニティを持っているというシステムの信頼レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="67833-118">It indicates the system's confidence level that a segment has an affinity for the brand or interest.</span></span> <span data-ttu-id="67833-119">信頼度は、セグメントの大きさとセグメントの粒度に基づいています。</span><span class="sxs-lookup"><span data-stu-id="67833-119">Confidence level is based on the segment size and the segment granularity.</span></span> <span data-ttu-id="67833-120">セグメント サイズは、与えられたセグメントのデータ量によって決まります。</span><span class="sxs-lookup"><span data-stu-id="67833-120">Segment size is determined by the amount of data we have for a given segment.</span></span> <span data-ttu-id="67833-121">セグメントの粒度は、プロファイルで使用できる属性 (年齢、性別、場所) の数によって決まります。</span><span class="sxs-lookup"><span data-stu-id="67833-121">Segment granularity is determined by how many attributes (age, gender, location) are available in a profile.</span></span>

<span data-ttu-id="67833-122">データセットのスコアを正規化することはありません。</span><span class="sxs-lookup"><span data-stu-id="67833-122">We don't normalize the scores for your dataset.</span></span> <span data-ttu-id="67833-123">そのため、データセットの可能な類似性スコア値がすべて表示されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="67833-123">Consequently, you may not see all possible affinity score values for your dataset.</span></span> <span data-ttu-id="67833-124">たとえば、データに類似性スコア 100 のエンリッチされた顧客プロファイルがない場合があります。</span><span class="sxs-lookup"><span data-stu-id="67833-124">For example, there may be no enriched customer profile with affinity score 100 in your data.</span></span> <span data-ttu-id="67833-125">これは、特定のブランドまたは関心に対して100 点を獲得した人口統計セグメントに顧客が存在しない場合に可能です。</span><span class="sxs-lookup"><span data-stu-id="67833-125">That's possible if no customers exist in the demographic segment that scored 100 for a given brand or interest.</span></span>

> [!TIP]
> <span data-ttu-id="67833-126">類似性スコアを使用して [セグメントを作成する](segments.md)場合は、適切なスコアのしきい値を決める前に、データセットの類似性スコアの分布を確認してください。</span><span class="sxs-lookup"><span data-stu-id="67833-126">When [creating segments](segments.md) using affinity scores, review the distribution of affinity scores for your dataset before deciding on the appropriate score thresholds.</span></span> <span data-ttu-id="67833-127">例えば、特定のブランドや関心に対する類似性スコアが最高でも 25 点しかないデータセットでは、類似性スコアが 10 点であっても重要であると考えることができます。</span><span class="sxs-lookup"><span data-stu-id="67833-127">For example, an affinity score of 10 can be considered significant in a dataset that has a highest affinity score of only 25 for a given brand or interest.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="67833-128">サポートされている国/地域</span><span class="sxs-lookup"><span data-stu-id="67833-128">Supported countries/regions</span></span>

<span data-ttu-id="67833-129">現在、次の国/地域オプションをサポートしています: オーストラリア、カナダ (英語)、フランス、ドイツ、英国、または米国 (英語)。</span><span class="sxs-lookup"><span data-stu-id="67833-129">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="67833-130">国を選択するには、**ブランド エンリッチメント** または **関心エンリッチメント** を開き、**国/地域** の横の **変更** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67833-130">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="67833-131">**国/地域の設定** ペインでオプションを選択し、**適用** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67833-131">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="67833-132">国の選択に関連する影響</span><span class="sxs-lookup"><span data-stu-id="67833-132">Implications related to country selection</span></span>

- <span data-ttu-id="67833-133">[自身のブランドを選択](#define-your-brands-or-interests) する場合、選択した国/地域に基づいて提案を提供します。</span><span class="sxs-lookup"><span data-stu-id="67833-133">When [choosing your own brands](#define-your-brands-or-interests), we will provide suggestions based on the selected country/region.</span></span>

- <span data-ttu-id="67833-134">[業種を選択](#define-your-brands-or-interests) するときには、選択した国/地域に基づいて、最も関連性の高いブランドまたは関心を特定します。</span><span class="sxs-lookup"><span data-stu-id="67833-134">When [choosing an industry](#define-your-brands-or-interests), we will identify the most relevant brands or interests based on the selected country/region.</span></span>

- <span data-ttu-id="67833-135">[フィールドをマッピング](#map-your-fields) するときに、国/地域フィールドがマップされていない場合は、選択した国/地域の Microsoft Graph データを使用して顧客プロファイルを充実させます。</span><span class="sxs-lookup"><span data-stu-id="67833-135">When [mapping your fields](#map-your-fields), if the Country/Region field isn't mapped, we'll use Microsoft Graph data from the selected country/region to enrich your customer profiles.</span></span> <span data-ttu-id="67833-136">また、その選択を使用して、利用可能な国/地域データがない顧客プロファイルを充実させます。</span><span class="sxs-lookup"><span data-stu-id="67833-136">We'll also use that selection to enrich your customer profiles that don't have country/region data available.</span></span>

- <span data-ttu-id="67833-137">[プロファイルを充実](#refresh-enrichment) させる場合、選択した国/地域にないプロファイルも含め、選択したブランドと関心について Microsoft Graph データを利用できるすべての顧客プロファイルを充実させます。</span><span class="sxs-lookup"><span data-stu-id="67833-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we have Microsoft Graph data available for the selected brands and interests, including profiles that are not in the selected country/region.</span></span> <span data-ttu-id="67833-138">たとえば、ドイツを選択した場合、米国で選択したブランドと関心について Microsoft Graph データが利用可能であれば、米国にあるプロファイルが充実します。</span><span class="sxs-lookup"><span data-stu-id="67833-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have Microsoft Graph data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="67833-139">強化の構成</span><span class="sxs-lookup"><span data-stu-id="67833-139">Configure Enrichment</span></span>

<span data-ttu-id="67833-140">ブランドまたは関心エンリッチメントの構成は、次の2つのステップで構成されます :</span><span class="sxs-lookup"><span data-stu-id="67833-140">Configuring brands or interests enrichment consists of two steps:</span></span>

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="67833-141">ブランドや関心の定義</span><span class="sxs-lookup"><span data-stu-id="67833-141">Define your brands or interests</span></span>

<span data-ttu-id="67833-142">次のいずれかのオプションを選択してください。</span><span class="sxs-lookup"><span data-stu-id="67833-142">Select one of the following options:</span></span>

- <span data-ttu-id="67833-143">**業界** : このシステムは、業界に関連するトップブランドや関心を識別し、顧客データを拡充します。</span><span class="sxs-lookup"><span data-stu-id="67833-143">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="67833-144">**自分で選択する** : 組織に最も関連のあるブランドや関心のリストから最大 5 つの項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="67833-144">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="67833-145">ブランドや関心を追加するには、入力エリアに入力して、一致する用語に基づいて提案を取得します。</span><span class="sxs-lookup"><span data-stu-id="67833-145">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="67833-146">探しているブランドや興味が見つからない場合は、**提案する** リンクを使用してフィードバックを送ってください。</span><span class="sxs-lookup"><span data-stu-id="67833-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="67833-147">フィールドのマップ</span><span class="sxs-lookup"><span data-stu-id="67833-147">Map your fields</span></span>

<span data-ttu-id="67833-148">統一された顧客エンティティのフィールドを少なくとも 2 つの属性にマップして、顧客データのエンリッチに使用する人口統計セグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="67833-148">Map fields from your unified customer entity to at least two attributes to define the demographic segment you want us to use for enriching your customer data.</span></span> <span data-ttu-id="67833-149">**編集** を選択してフィールドのマッピングを定義し、定義完了後に **適用** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67833-149">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="67833-150">**保存** を選択して、フィールドのマッピングを完了します。</span><span class="sxs-lookup"><span data-stu-id="67833-150">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="67833-151">次の形式と値がサポートされていますが、値の大文字と小文字は区別されません:</span><span class="sxs-lookup"><span data-stu-id="67833-151">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="67833-152">**生年月日**: データ インジェスト中に、生年月日を DateTime の種類に変換することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="67833-152">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="67833-153">または、[ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) 形式 "yyyy-MM-dd" または "yyyy-MM-ddTHH:mm:ssZ" の文字列にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="67833-153">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="67833-154">**性別** : 男性、女性、不明</span><span class="sxs-lookup"><span data-stu-id="67833-154">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="67833-155">**郵便番号**: 米国の 5 桁の郵便番号、それ以外の国の標準郵便番号</span><span class="sxs-lookup"><span data-stu-id="67833-155">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="67833-156">**市**: 英語での都市名</span><span class="sxs-lookup"><span data-stu-id="67833-156">**City**: City name in English</span></span>
- <span data-ttu-id="67833-157">**都道府県**: 米国とカナダの 2 文字の省略形。</span><span class="sxs-lookup"><span data-stu-id="67833-157">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="67833-158">オーストラリアの 2 文字または 3 文字の省略形。</span><span class="sxs-lookup"><span data-stu-id="67833-158">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="67833-159">フランス、ドイツ、英国には適用されません。</span><span class="sxs-lookup"><span data-stu-id="67833-159">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="67833-160">**国/地域**:</span><span class="sxs-lookup"><span data-stu-id="67833-160">**Country/Region**:</span></span>

  - <span data-ttu-id="67833-161">US: アメリカ合衆国、米国、USA、US、アメリカ</span><span class="sxs-lookup"><span data-stu-id="67833-161">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="67833-162">CA: カナダ、CA</span><span class="sxs-lookup"><span data-stu-id="67833-162">CA: Canada, CA</span></span>
  - <span data-ttu-id="67833-163">GB: 英国、UK、イギリス、GB、グレート・ブリテンおよび北アイルランド連合王国、グレート・ブリテン連合王国</span><span class="sxs-lookup"><span data-stu-id="67833-163">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="67833-164">AU: オーストラリア、AU、オーストラリア連邦</span><span class="sxs-lookup"><span data-stu-id="67833-164">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="67833-165">FR: フランス、FR、フランス共和国</span><span class="sxs-lookup"><span data-stu-id="67833-165">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="67833-166">DE: ドイツ、ジャーマン、ドイチュラント、アルマーニュ、DE、ドイツ連邦共和国、ドイツ共和国</span><span class="sxs-lookup"><span data-stu-id="67833-166">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="refresh-enrichment"></a><span data-ttu-id="67833-167">エンリッチメントの更新</span><span class="sxs-lookup"><span data-stu-id="67833-167">Refresh enrichment</span></span>

<span data-ttu-id="67833-168">人口統計のブランド、関心、およびフィールド マッピングを設定した後、エンリッチメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="67833-168">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="67833-169">プロセスを開始するには、ブランドまたは関心の構成ページで **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67833-169">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="67833-170">さらに、スケジュールされた更新の一部として、システムで強化の自動実行をすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="67833-170">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="67833-171">顧客データのサイズによっては、エンリッチメントの実行が完了するまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="67833-171">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="67833-172">タスク/プロセスには、[6 種類の状態](system.md#status-types) があります。</span><span class="sxs-lookup"><span data-stu-id="67833-172">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="67833-173">さらに、ほとんどのプロセスは、[その他の下流プロセスに依存します](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="67833-173">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="67833-174">プロセスのステータスを選択して、ジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="67833-174">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="67833-175">ジョブのタスクの 1 つについて **詳細の表示** を選択すると、処理時間、最終処理日、およびタスクに関連するすべてのエラーと警告などの追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="67833-175">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="67833-176">強化の結果</span><span class="sxs-lookup"><span data-stu-id="67833-176">Enrichment results</span></span>

<span data-ttu-id="67833-177">エンリッチメント プロセスの実行後、**自分のエンリッチメント** に移動してエンリッチメントされた顧客の総数と、エンリッチメントされた顧客プロファイルのブランドや関心の内訳を確認します。</span><span class="sxs-lookup"><span data-stu-id="67833-177">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="強化プロセスの実行結果プレビュー":::

<span data-ttu-id="67833-179">チャートで **エンリッチされたデータを表示** を選択することで、エンリッチされたデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="67833-179">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="67833-180">ブランドのエンリッチされたデータは、**BrandAffinityFromMicrosoft** エンティティへ移動します。</span><span class="sxs-lookup"><span data-stu-id="67833-180">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="67833-181">関心のあるデータは、**InterestAffinityFromMicrosoft** エンティティにあります。</span><span class="sxs-lookup"><span data-stu-id="67833-181">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="67833-182">これらのエンティティは、 **データ** > **エンティティ** の **強化** グループにて一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="67833-182">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="67833-183">顧客カードで強化されてデータを確認する</span><span class="sxs-lookup"><span data-stu-id="67833-183">See enrichment data on the customer card</span></span>

<span data-ttu-id="67833-184">ブランドや関心の類似性は、個々の顧客カードでも確認することができます。</span><span class="sxs-lookup"><span data-stu-id="67833-184">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="67833-185">**顧客** に移動し、顧客のプロフィールを選択します。</span><span class="sxs-lookup"><span data-stu-id="67833-185">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="67833-186">顧客カードには、その顧客の人口統計プロファイルの人々が親しみを持っているブランドや関心のグラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="67833-186">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="データが強化された顧客カード":::

## <a name="next-steps"></a><span data-ttu-id="67833-188">次のステップ</span><span class="sxs-lookup"><span data-stu-id="67833-188">Next steps</span></span>

<span data-ttu-id="67833-189">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="67833-189">Build on top of your enriched customer data.</span></span> <span data-ttu-id="67833-190">[セグメント](segments.md)、[メジャー](measures.md)を作成し、 [データをエクスポート](export-destinations.md) して、顧客にパーソナライズされたエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="67833-190">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>
