---
title: Microsoft のデータで顧客プロファイルをエンリッチする
description: Microsoft が所有するデータを使用して、ブランドや関心のアフィニティで顧客データをエンリッチさせます。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896608"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="eafd4-103">ブランドと関心のアフィニティで顧客プロファイルをエンリッチさせる (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="eafd4-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="eafd4-104">Microsoft の所有するデータを使用して、ブランドや関心のアフィニティで顧客データをエンリッチさせます。</span><span class="sxs-lookup"><span data-stu-id="eafd4-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="eafd4-105">これらの類似性は、既存の顧客と類似した統計を持つ人々のデータに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="eafd4-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="eafd4-106">この情報は、特定のブランドや関心事に対する顧客の親近感に基づいて、顧客をよりよく理解し、セグメント化に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="eafd4-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="eafd4-107">対象者に関するインサイトで、**データ** > **エンリッチメント** を選択して、[エンリッチメントの設定と表示](enrichment-hub.md)へ移動します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="eafd4-108">ブランド アフィニティのエンリッチメントを設定するには、**見つける** タブを選択し、**ブランド** タイルで **データを拡充する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="eafd4-109">関心アフィニティのエンリッチメントを設定するには、**見つける** タブを選択し、**関心** タイルで **データを拡充する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="eafd4-110">![ブランドと関心タイル](media/BrandsInterest-tile-Hub.png "ブランドと関心タイル")</span><span class="sxs-lookup"><span data-stu-id="eafd4-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="eafd4-111">アフィニティの決定方法</span><span class="sxs-lookup"><span data-stu-id="eafd4-111">How we determine affinities</span></span>

<span data-ttu-id="eafd4-112">Microsoft のオンライン検索データを使用して、さまざまな人口統計セグメント (年齢、性別、または場所によって定義される) におけるブランドおよび関心に対するアフィニティを見つけます。</span><span class="sxs-lookup"><span data-stu-id="eafd4-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="eafd4-113">ブランドまたは関心のオンライン検索ボリュームは、他のセグメントと比較して、人口統計セグメントがそのブランドまたは関心にどれだけのアフィニティがあるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="eafd4-114">ブランドまたは関心。</span><span class="sxs-lookup"><span data-stu-id="eafd4-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="eafd4-115">アフィニティ レベルとスコア</span><span class="sxs-lookup"><span data-stu-id="eafd4-115">Affinity level and score</span></span>

<span data-ttu-id="eafd4-116">エンリッチされた顧客プロファイルごとに、アフィニティ レベルとアフィニティ スコアの 2 つの関連値を提供します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="eafd4-117">これらの値は、他の人口統計セグメントと比較して、そのプロファイルの人口統計セグメント、ブランドまたは関心に対するアフィニティがどの程度強いかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="eafd4-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="eafd4-118">*アフィニティ レベル* は、4 つのレベルで構成され、*アフィニティ スコア* はアフィニティ レベルにマッピングされる 100 ポイント スケールで計算されます。</span><span class="sxs-lookup"><span data-stu-id="eafd4-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="eafd4-119">アフィニティ レベル</span><span class="sxs-lookup"><span data-stu-id="eafd4-119">Affinity level</span></span> |<span data-ttu-id="eafd4-120">アフィニティ スコア</span><span class="sxs-lookup"><span data-stu-id="eafd4-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="eafd4-121">非常に多い</span><span class="sxs-lookup"><span data-stu-id="eafd4-121">Very high</span></span>     | <span data-ttu-id="eafd4-122">85-100</span><span class="sxs-lookup"><span data-stu-id="eafd4-122">85-100</span></span>       |
|<span data-ttu-id="eafd4-123">高</span><span class="sxs-lookup"><span data-stu-id="eafd4-123">High</span></span>     | <span data-ttu-id="eafd4-124">70-84</span><span class="sxs-lookup"><span data-stu-id="eafd4-124">70-84</span></span>        |
|<span data-ttu-id="eafd4-125">中</span><span class="sxs-lookup"><span data-stu-id="eafd4-125">Medium</span></span>     | <span data-ttu-id="eafd4-126">35-69</span><span class="sxs-lookup"><span data-stu-id="eafd4-126">35-69</span></span>        |
|<span data-ttu-id="eafd4-127">低</span><span class="sxs-lookup"><span data-stu-id="eafd4-127">Low</span></span>     | <span data-ttu-id="eafd4-128">1-34</span><span class="sxs-lookup"><span data-stu-id="eafd4-128">1-34</span></span>        |

<span data-ttu-id="eafd4-129">アフィニティを測定するために必要な粒度に応じて、アフィニティ レベルまたはスコアのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="eafd4-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="eafd4-130">アフィニティ スコアを使用すると、より正確に制御できます。</span><span class="sxs-lookup"><span data-stu-id="eafd4-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="eafd4-131">サポートされている国/地域</span><span class="sxs-lookup"><span data-stu-id="eafd4-131">Supported countries/regions</span></span>

<span data-ttu-id="eafd4-132">現在、次の国/地域オプションをサポートしています: オーストラリア、カナダ (英語)、フランス、ドイツ、英国、または米国 (英語)。</span><span class="sxs-lookup"><span data-stu-id="eafd4-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="eafd4-133">国を選択するには、**ブランド エンリッチメント** または **関心エンリッチメント** を開き、**国/地域** の横の **変更** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="eafd4-134">**国/地域の設定** ペインでオプションを選択し、**適用** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="eafd4-135">国の選択に関連する影響</span><span class="sxs-lookup"><span data-stu-id="eafd4-135">Implications related to country selection</span></span>

- <span data-ttu-id="eafd4-136">[独自のブランド](#define-your-brands-or-interests)を選ぶと、システムは選択した国またはリージョンに基づいて提案を提供します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="eafd4-137">[業界](#define-your-brands-or-interests)を選択すると、選択した国またはリージョンに基づいて、最も関連性の高いブランドまたは関心を取得します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="eafd4-138">[プロファイル](#refresh-enrichment)をエンリッチする際、選択したブランドと関心のデータを取得するすべての顧客プロファイルをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="eafd4-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="eafd4-139">選択した国またはリージョンにないプロファイルを含みます。</span><span class="sxs-lookup"><span data-stu-id="eafd4-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="eafd4-140">たとえば、ドイツを選択した場合、米国で選択したブランドと関心に関するデータが利用可能であれば、米国にあるプロファイルをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="eafd4-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="eafd4-141">強化の構成</span><span class="sxs-lookup"><span data-stu-id="eafd4-141">Configure Enrichment</span></span>

<span data-ttu-id="eafd4-142">ガイド付きのエクスペリエンスは、エンリッチメントの構成を支援します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="eafd4-143">ブランドや関心の定義</span><span class="sxs-lookup"><span data-stu-id="eafd4-143">Define your brands or interests</span></span>

<span data-ttu-id="eafd4-144">次のいずれかのオプションを選択してください。</span><span class="sxs-lookup"><span data-stu-id="eafd4-144">Select one of the following options:</span></span>

- <span data-ttu-id="eafd4-145">**業界** : このシステムは、業界に関連するトップブランドや関心を識別し、顧客データを拡充します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="eafd4-146">**自分で選択する** : 組織に最も関連のあるブランドや関心のリストから最大 5 つの項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="eafd4-147">ブランドや関心を追加するには、入力エリアに入力して、一致する用語に基づいて提案を取得します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="eafd4-148">探しているブランドや興味が見つからない場合は、**提案する** リンクを使用してフィードバックを送ってください。</span><span class="sxs-lookup"><span data-stu-id="eafd4-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="eafd4-149">エンリッチメントの基本設定をレビューする</span><span class="sxs-lookup"><span data-stu-id="eafd4-149">Review enrichment preferences</span></span>

<span data-ttu-id="eafd4-150">既定のエンリッチメント設定を確認し、必要に応じて更新します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="エンリッチメント基本設定ウィンドウのスクリーンショット。":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="eafd4-152">エンリッチするエンティティを選択する</span><span class="sxs-lookup"><span data-stu-id="eafd4-152">Select entity to enrich</span></span>

<span data-ttu-id="eafd4-153">**エンリッチされたエンティティ** を選択し、Microsoft の企業データでエンリッチするデータ セットを選択します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="eafd4-154">顧客エンティティを選択してすべての顧客プロファイルをエンリッチするか、セグメント エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="eafd4-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="eafd4-155">フィールドのマップ</span><span class="sxs-lookup"><span data-stu-id="eafd4-155">Map your fields</span></span>

<span data-ttu-id="eafd4-156">統合された顧客エンティティのフィールドをマッピングして、システムが顧客データを充実させるために使用する人口統計セグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="eafd4-157">国/リージョンと少なくとも生年月日または性別の属性をマッピングします。</span><span class="sxs-lookup"><span data-stu-id="eafd4-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="eafd4-158">さらに、少なくとも 1 つの都市 (および都道府県) または郵便番号をマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eafd4-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="eafd4-159">**編集** を選択してフィールドのマッピングを定義し、定義完了後に **適用** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="eafd4-160">**保存** を選択して、フィールドのマッピングを完了します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="eafd4-161">次の形式と値がサポートされていますが、値の大文字と小文字は区別されません:</span><span class="sxs-lookup"><span data-stu-id="eafd4-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="eafd4-162">**生年月日**: データ インジェスト中に、生年月日を DateTime の種類に変換することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eafd4-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="eafd4-163">または、[ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) 形式 "yyyy-MM-dd" または "yyyy-MM-ddTHH:mm:ssZ" の文字列にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="eafd4-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="eafd4-164">**性別** : 男性、女性、不明</span><span class="sxs-lookup"><span data-stu-id="eafd4-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="eafd4-165">**郵便番号**: 米国の 5 桁の郵便番号、それ以外の国の標準郵便番号</span><span class="sxs-lookup"><span data-stu-id="eafd4-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="eafd4-166">**市**: 英語での都市名</span><span class="sxs-lookup"><span data-stu-id="eafd4-166">**City**: City name in English</span></span>
- <span data-ttu-id="eafd4-167">**都道府県**: 米国とカナダの 2 文字の省略形。</span><span class="sxs-lookup"><span data-stu-id="eafd4-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="eafd4-168">オーストラリアの 2 文字または 3 文字の省略形。</span><span class="sxs-lookup"><span data-stu-id="eafd4-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="eafd4-169">フランス、ドイツ、英国には適用されません。</span><span class="sxs-lookup"><span data-stu-id="eafd4-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="eafd4-170">**国/地域**:</span><span class="sxs-lookup"><span data-stu-id="eafd4-170">**Country/Region**:</span></span>

  - <span data-ttu-id="eafd4-171">US: アメリカ合衆国、米国、USA、US、アメリカ</span><span class="sxs-lookup"><span data-stu-id="eafd4-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="eafd4-172">CA: カナダ、CA</span><span class="sxs-lookup"><span data-stu-id="eafd4-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="eafd4-173">GB: 英国、UK、イギリス、GB、グレート・ブリテンおよび北アイルランド連合王国、グレート・ブリテン連合王国</span><span class="sxs-lookup"><span data-stu-id="eafd4-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="eafd4-174">AU: オーストラリア、AU、オーストラリア連邦</span><span class="sxs-lookup"><span data-stu-id="eafd4-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="eafd4-175">FR: フランス、FR、フランス共和国</span><span class="sxs-lookup"><span data-stu-id="eafd4-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="eafd4-176">DE: ドイツ、ジャーマン、ドイチュラント、アルマーニュ、DE、ドイツ連邦共和国、ドイツ共和国</span><span class="sxs-lookup"><span data-stu-id="eafd4-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="eafd4-177">エンリッチメントのレビューと命名</span><span class="sxs-lookup"><span data-stu-id="eafd4-177">Review and name the enrichment</span></span>

<span data-ttu-id="eafd4-178">最後に、情報を確認し、エンリッチメントの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="関心のレビューと命名のページ。":::

## <a name="refresh-enrichment"></a><span data-ttu-id="eafd4-180">エンリッチメントの更新</span><span class="sxs-lookup"><span data-stu-id="eafd4-180">Refresh enrichment</span></span>

<span data-ttu-id="eafd4-181">人口統計のブランド、関心、およびフィールド マッピングを設定した後、エンリッチメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="eafd4-182">プロセスを開始するには、ブランドまたは関心の構成ページで **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="eafd4-183">さらに、スケジュールされた更新の一部として、システムで強化の自動実行をすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="eafd4-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="eafd4-184">顧客データのサイズによっては、エンリッチメントの実行が完了するまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="eafd4-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="eafd4-185">タスク/プロセスには、[6 種類の状態](system.md#status-types) があります。</span><span class="sxs-lookup"><span data-stu-id="eafd4-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="eafd4-186">さらに、ほとんどのプロセスは、[その他の下流プロセスに依存します](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="eafd4-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="eafd4-187">プロセスのステータスを選択して、ジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="eafd4-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="eafd4-188">ジョブのタスクの 1 つについて **詳細の表示** を選択すると、処理時間、最終処理日、およびタスクに関連するすべてのエラーと警告などの追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eafd4-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="eafd4-189">強化の結果</span><span class="sxs-lookup"><span data-stu-id="eafd4-189">Enrichment results</span></span>

<span data-ttu-id="eafd4-190">エンリッチメント プロセスの実行後、**自分のエンリッチメント** に移動してエンリッチメントされた顧客の総数と、エンリッチメントされた顧客プロファイルのブランドや関心の内訳を確認します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="強化プロセスの実行結果プレビュー":::

<span data-ttu-id="eafd4-192">チャートで **エンリッチされたデータを表示** を選択することで、エンリッチされたデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="eafd4-193">ブランドのエンリッチされたデータは、**BrandAffinityFromMicrosoft** エンティティへ移動します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="eafd4-194">関心のあるデータは、**InterestAffinityFromMicrosoft** エンティティにあります。</span><span class="sxs-lookup"><span data-stu-id="eafd4-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="eafd4-195">これらのエンティティは、 **データ** > **エンティティ** の **強化** グループにて一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="eafd4-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="eafd4-196">顧客カードで強化されてデータを確認する</span><span class="sxs-lookup"><span data-stu-id="eafd4-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="eafd4-197">ブランドや関心の類似性は、個々の顧客カードでも確認することができます。</span><span class="sxs-lookup"><span data-stu-id="eafd4-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="eafd4-198">**顧客** に移動し、顧客のプロフィールを選択します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="eafd4-199">顧客カードには、その顧客の人口統計プロファイルの人々が親しみを持っているブランドや関心のグラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="eafd4-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="データが強化された顧客カード":::

## <a name="next-steps"></a><span data-ttu-id="eafd4-201">次のステップ</span><span class="sxs-lookup"><span data-stu-id="eafd4-201">Next steps</span></span>

<span data-ttu-id="eafd4-202">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="eafd4-203">[セグメント](segments.md)、[メジャー](measures.md)を作成し、 [データをエクスポート](export-destinations.md) して、顧客にパーソナライズされたエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="eafd4-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
