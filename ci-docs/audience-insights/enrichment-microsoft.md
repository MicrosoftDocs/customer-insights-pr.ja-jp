---
title: Microsoft のデータで顧客プロファイルをエンリッチする
description: Microsoft が所有するデータを使用して、ブランドや関心のアフィニティで顧客データをエンリッチさせます。
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305162"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="e09b5-103">ブランドと関心のアフィニティで顧客プロファイルをエンリッチさせる (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e09b5-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="e09b5-104">Microsoft の所有するデータを使用して、ブランドや関心のアフィニティで顧客データをエンリッチさせます。</span><span class="sxs-lookup"><span data-stu-id="e09b5-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="e09b5-105">これらのアフィニティは、顧客と同じような人口統計層の人々からのデータに基づいています。</span><span class="sxs-lookup"><span data-stu-id="e09b5-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="e09b5-106">この情報は、特定のブランドや関心事に対する顧客の親近感に基づいて、顧客をよりよく理解し、セグメント化に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e09b5-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="e09b5-107">対象者に関するインサイトで、**データ** > **エンリッチメント** を選択して、[エンリッチメントの設定と表示](enrichment-hub.md)へ移動します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="e09b5-108">ブランド アフィニティのエンリッチメントを設定するには、**見つける** タブを選択し、**ブランド** タイルで **データを拡充する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="e09b5-109">関心アフィニティのエンリッチメントを設定するには、**見つける** タブを選択し、**関心** タイルで **データを拡充する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e09b5-110">![ブランドと関心のタイル](media/BrandsInterest-tile-Hub.png "ブランドと関心のタイル")</span><span class="sxs-lookup"><span data-stu-id="e09b5-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="e09b5-111">アフィニティの決定方法</span><span class="sxs-lookup"><span data-stu-id="e09b5-111">How we determine affinities</span></span>

<span data-ttu-id="e09b5-112">Microsoft のオンライン検索データを使用して、さまざまな人口統計セグメント (年齢、性別、または場所によって定義される) におけるブランドおよび関心に対するアフィニティを見つけます。</span><span class="sxs-lookup"><span data-stu-id="e09b5-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="e09b5-113">ブランドまたは関心のオンライン検索ボリュームは、他のセグメントと比較して、人口統計セグメントがそのブランドまたは関心にどれだけのアフィニティがあるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="e09b5-114">アフィニティ レベルとスコア</span><span class="sxs-lookup"><span data-stu-id="e09b5-114">Affinity level and score</span></span>

<span data-ttu-id="e09b5-115">エンリッチされた顧客プロファイルごとに、アフィニティ レベルとアフィニティ スコアの 2 つの関連値を提供します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="e09b5-116">これらの値は、他の人口統計セグメントと比較して、そのプロファイルの人口統計セグメント、ブランドまたは関心に対するアフィニティがどの程度強いかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e09b5-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="e09b5-117">*アフィニティ レベル* は、4 つのレベルで構成され、*アフィニティ スコア* はアフィニティ レベルにマッピングされる 100 ポイント スケールで計算されます。</span><span class="sxs-lookup"><span data-stu-id="e09b5-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="e09b5-118">アフィニティ レベル</span><span class="sxs-lookup"><span data-stu-id="e09b5-118">Affinity level</span></span> |<span data-ttu-id="e09b5-119">アフィニティ スコア</span><span class="sxs-lookup"><span data-stu-id="e09b5-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="e09b5-120">非常に多い</span><span class="sxs-lookup"><span data-stu-id="e09b5-120">Very high</span></span>     | <span data-ttu-id="e09b5-121">85-100</span><span class="sxs-lookup"><span data-stu-id="e09b5-121">85-100</span></span>       |
|<span data-ttu-id="e09b5-122">高</span><span class="sxs-lookup"><span data-stu-id="e09b5-122">High</span></span>     | <span data-ttu-id="e09b5-123">70-84</span><span class="sxs-lookup"><span data-stu-id="e09b5-123">70-84</span></span>        |
|<span data-ttu-id="e09b5-124">中</span><span class="sxs-lookup"><span data-stu-id="e09b5-124">Medium</span></span>     | <span data-ttu-id="e09b5-125">35-69</span><span class="sxs-lookup"><span data-stu-id="e09b5-125">35-69</span></span>        |
|<span data-ttu-id="e09b5-126">低</span><span class="sxs-lookup"><span data-stu-id="e09b5-126">Low</span></span>     | <span data-ttu-id="e09b5-127">1-34</span><span class="sxs-lookup"><span data-stu-id="e09b5-127">1-34</span></span>        |

<span data-ttu-id="e09b5-128">アフィニティを測定するために必要な粒度に応じて、アフィニティ レベルまたはスコアのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e09b5-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="e09b5-129">アフィニティ スコアを使用すると、より正確に制御できます。</span><span class="sxs-lookup"><span data-stu-id="e09b5-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="e09b5-130">サポートされている国/地域</span><span class="sxs-lookup"><span data-stu-id="e09b5-130">Supported countries/regions</span></span>

<span data-ttu-id="e09b5-131">現在、次の国/地域オプションをサポートしています: オーストラリア、カナダ (英語)、フランス、ドイツ、英国、または米国 (英語)。</span><span class="sxs-lookup"><span data-stu-id="e09b5-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="e09b5-132">国または地域を選択するには、**ブランドのエンリッチメント** または **関心のエンリッチメント** を開き、**国/地域** の横にある **変更** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="e09b5-133">**国/地域の設定** ペインでオプションを選択し、**適用** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="e09b5-134">国の選択に関連する影響</span><span class="sxs-lookup"><span data-stu-id="e09b5-134">Implications related to country selection</span></span>

- <span data-ttu-id="e09b5-135">[独自のブランド](#define-your-brands-or-interests)を選ぶと、システムは選択した国またはリージョンに基づいて提案を提供します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="e09b5-136">[業界](#define-your-brands-or-interests)を選択すると、選択した国またはリージョンに基づいて、最も関連性の高いブランドまたは関心を取得します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="e09b5-137">[プロファイルのエンリッチメント](#refresh-enrichment) を行うとき、選択した国または地域にないプロファイルを含む、選択したブランドおよび関心のデータを取得するすべての顧客プロファイルをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="e09b5-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="e09b5-138">たとえば、ドイツを選択した場合、米国で選択したブランドと関心に関するデータが利用可能であれば、米国にあるプロファイルをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="e09b5-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="e09b5-139">エンリッチメントの構成</span><span class="sxs-lookup"><span data-stu-id="e09b5-139">Configure enrichment</span></span>

<span data-ttu-id="e09b5-140">ガイド付きのエクスペリエンスは、エンリッチメントの構成を支援します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="e09b5-141">ブランドや関心の定義</span><span class="sxs-lookup"><span data-stu-id="e09b5-141">Define your brands or interests</span></span>

<span data-ttu-id="e09b5-142">次のオプションのいずれかまたは両方を使用して、最大 5 つのブランドや関心を選択します:</span><span class="sxs-lookup"><span data-stu-id="e09b5-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="e09b5-143">**業界**: ドロップダウン リストから業界を選択してから、その業界のトップブランドまたは関心から選択します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="e09b5-144">**自分で選択する**: 組織に関連するブランドや関心を入力し、一致する候補から選択します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="e09b5-145">探しているブランドや興味が見つからない場合は、**提案する** リンクを使用してフィードバックを送ってください。</span><span class="sxs-lookup"><span data-stu-id="e09b5-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="e09b5-146">エンリッチメントの基本設定をレビューする</span><span class="sxs-lookup"><span data-stu-id="e09b5-146">Review enrichment preferences</span></span>

<span data-ttu-id="e09b5-147">既定のエンリッチメント設定を確認し、必要に応じて更新します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="エンリッチメント基本設定ウィンドウのスクリーンショット。":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="e09b5-149">エンリッチするエンティティを選択する</span><span class="sxs-lookup"><span data-stu-id="e09b5-149">Select entity to enrich</span></span>

<span data-ttu-id="e09b5-150">**エンリッチされたエンティティ** を選択し、Microsoft の企業データでエンリッチするデータ セットを選択します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="e09b5-151">顧客エンティティを選択してすべての顧客プロファイルをエンリッチするか、セグメント エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="e09b5-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="e09b5-152">フィールドのマップ</span><span class="sxs-lookup"><span data-stu-id="e09b5-152">Map your fields</span></span>

<span data-ttu-id="e09b5-153">統合された顧客エンティティのフィールドをマッピングして、システムが顧客データを充実させるために使用する人口統計セグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="e09b5-154">国/リージョンと少なくとも生年月日または性別の属性をマッピングします。</span><span class="sxs-lookup"><span data-stu-id="e09b5-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="e09b5-155">さらに、少なくとも 1 つの都市 (および都道府県) または郵便番号をマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e09b5-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="e09b5-156">**編集** を選択してフィールドのマッピングを定義し、定義完了後に **適用** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="e09b5-157">**保存** を選択して、フィールドのマッピングを完了します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="e09b5-158">次の形式と値がサポートされていますが、値の大文字と小文字は区別されません:</span><span class="sxs-lookup"><span data-stu-id="e09b5-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="e09b5-159">**生年月日**: データ インジェスト中に、生年月日を DateTime の種類に変換することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e09b5-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="e09b5-160">または、[ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) の形式である、「yyyy-MM-dd」または「yyyy-MM-ddTHH:mm:ss」の文字列にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e09b5-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="e09b5-161">**性別** : 男性、女性、不明。</span><span class="sxs-lookup"><span data-stu-id="e09b5-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="e09b5-162">**郵便番号**: 米国の 5 桁の郵便番号、その他の地域の標準の郵便番号。</span><span class="sxs-lookup"><span data-stu-id="e09b5-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="e09b5-163">**市**: 英語での都市名。</span><span class="sxs-lookup"><span data-stu-id="e09b5-163">**City**: City name in English.</span></span>
- <span data-ttu-id="e09b5-164">**都道府県**: 米国とカナダの 2 文字の省略形。</span><span class="sxs-lookup"><span data-stu-id="e09b5-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="e09b5-165">オーストラリアの 2 文字または 3 文字の省略形。</span><span class="sxs-lookup"><span data-stu-id="e09b5-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="e09b5-166">フランス、ドイツ、英国には適用されません。</span><span class="sxs-lookup"><span data-stu-id="e09b5-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="e09b5-167">**国/地域**:</span><span class="sxs-lookup"><span data-stu-id="e09b5-167">**Country/Region**:</span></span>

  - <span data-ttu-id="e09b5-168">US: アメリカ合衆国、米国、USA、US、アメリカ</span><span class="sxs-lookup"><span data-stu-id="e09b5-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="e09b5-169">CA: カナダ、CA</span><span class="sxs-lookup"><span data-stu-id="e09b5-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="e09b5-170">GB: 英国、UK、イギリス、GB、グレート・ブリテンおよび北アイルランド連合王国、グレート・ブリテン連合王国</span><span class="sxs-lookup"><span data-stu-id="e09b5-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="e09b5-171">AU: オーストラリア、AU、オーストラリア連邦</span><span class="sxs-lookup"><span data-stu-id="e09b5-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="e09b5-172">FR: フランス、FR、フランス共和国</span><span class="sxs-lookup"><span data-stu-id="e09b5-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="e09b5-173">DE: ドイツ、ジャーマン、ドイチュラント、アルマーニュ、DE、ドイツ連邦共和国、ドイツ共和国</span><span class="sxs-lookup"><span data-stu-id="e09b5-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="e09b5-174">エンリッチメントのレビューと命名</span><span class="sxs-lookup"><span data-stu-id="e09b5-174">Review and name the enrichment</span></span>

<span data-ttu-id="e09b5-175">最後に、情報を確認し、エンリッチメントの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="関心のレビューと命名のページ。":::

## <a name="refresh-enrichment"></a><span data-ttu-id="e09b5-177">エンリッチメントの更新</span><span class="sxs-lookup"><span data-stu-id="e09b5-177">Refresh enrichment</span></span>

<span data-ttu-id="e09b5-178">人口統計のブランド、関心、およびフィールド マッピングを設定した後、エンリッチメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="e09b5-179">プロセスを開始するには、ブランドまたは関心の構成ページで **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="e09b5-180">さらに、スケジュールされた更新の一部として、システムで強化の自動実行をすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="e09b5-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="e09b5-181">顧客データのサイズによっては、エンリッチメントの実行が完了するまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e09b5-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="e09b5-182">タスク/プロセスには、[6 種類の状態](system.md#status-types) があります。</span><span class="sxs-lookup"><span data-stu-id="e09b5-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e09b5-183">さらに、ほとんどのプロセスは、[その他の下流プロセスに依存します](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="e09b5-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e09b5-184">プロセスのステータスを選択して、ジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e09b5-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e09b5-185">ジョブのタスクで **詳細を見る** を選択すると、処理時間、最終処理日、タスクに関連するすべてのエラーと警告などの追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e09b5-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="e09b5-186">強化の結果</span><span class="sxs-lookup"><span data-stu-id="e09b5-186">Enrichment results</span></span>

<span data-ttu-id="e09b5-187">エンリッチメント プロセスの実行後、**自分のエンリッチメント** に移動してエンリッチメントされた顧客の総数と、エンリッチメントされた顧客プロファイルのブランドや関心の内訳を確認します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="強化プロセスの実行結果プレビュー":::

<span data-ttu-id="e09b5-189">チャートで **エンリッチされたデータを表示** を選択することで、エンリッチされたデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="e09b5-190">ブランドのエンリッチされたデータは、**BrandAffinityFromMicrosoft** エンティティへ移動します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="e09b5-191">関心のあるデータは、**InterestAffinityFromMicrosoft** エンティティにあります。</span><span class="sxs-lookup"><span data-stu-id="e09b5-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="e09b5-192">これらのエンティティは、 **データ** > **エンティティ** の **強化** グループにて一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e09b5-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="e09b5-193">顧客カードで強化されてデータを確認する</span><span class="sxs-lookup"><span data-stu-id="e09b5-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="e09b5-194">ブランドや関心の類似性は、個々の顧客カードでも確認することができます。</span><span class="sxs-lookup"><span data-stu-id="e09b5-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="e09b5-195">**顧客** に移動し、顧客のプロフィールを選択します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="e09b5-196">顧客カードには、その顧客の人口統計プロファイルの人々が親しみを持っているブランドや関心のグラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e09b5-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="データが強化された顧客カード":::

## <a name="next-steps"></a><span data-ttu-id="e09b5-198">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e09b5-198">Next steps</span></span>

<span data-ttu-id="e09b5-199">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e09b5-200">[セグメント](segments.md) および [メジャー](measures.md) を作成し、さらに [データのエクスポート](export-destinations.md) を行って、パーソナライズされたエクスペリエンスを顧客に提供します。</span><span class="sxs-lookup"><span data-stu-id="e09b5-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
