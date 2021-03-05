---
title: Microsoft Graph を使用して顧客プロファイルを強化する
description: Microsoft Graph からの独自のデータを使用して、顧客データをブランドや関心のアフィニティでエンリッチさせます。
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2c95369c778f592bc1460799aca0fa8cff813d68
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269336"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="50a51-103">ブランドと関心のアフィニティで顧客プロファイルをエンリッチさせる (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="50a51-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="50a51-104">Microsoft Graph からの独自のデータを使用して、顧客データをブランドや関心のアフィニティでエンリッチさせます。</span><span class="sxs-lookup"><span data-stu-id="50a51-104">Use proprietary data from the Microsoft Graph to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="50a51-105">これらの類似性は、既存の顧客と類似した統計を持つ人々のデータに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="50a51-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="50a51-106">この情報は、特定のブランドや関心事に対する顧客の親近感に基づいて、顧客をよりよく理解し、セグメント化に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="50a51-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="50a51-107">対象者に関するインサイトで、**データ** > **エンリッチメント** を選択して、[エンリッチメントの設定と表示](enrichment-hub.md)へ移動します。</span><span class="sxs-lookup"><span data-stu-id="50a51-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="50a51-108">ブランド アフィニティのエンリッチメントを設定するには、**見つける** タブを選択し、**ブランド** タイルで **データを拡充する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="50a51-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="50a51-109">関心アフィニティのエンリッチメントを設定するには、**見つける** タブを選択し、**関心** タイルで **データを拡充する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="50a51-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="50a51-110">![ブランドと関心タイル](media/BrandsInterest-tile-Hub.png "ブランドと関心タイル")</span><span class="sxs-lookup"><span data-stu-id="50a51-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="about-microsoft-graph"></a><span data-ttu-id="50a51-111">Microsoft Graph について</span><span class="sxs-lookup"><span data-stu-id="50a51-111">About Microsoft Graph</span></span>

<span data-ttu-id="50a51-112">Microsoft Graph のオンライン検索データを使用して、さまざまな人口統計セグメント (年齢、性別、または場所による定義) 全体のブランドと関心アフィニティを見つけます。</span><span class="sxs-lookup"><span data-stu-id="50a51-112">We use online search data from the Microsoft Graph to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="50a51-113">ブランドまたは関心のオンライン検索ボリュームは、他のセグメントと比較して、人口統計セグメントがそのブランドまたは関心にどれだけのアフィニティがあるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="50a51-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

<span data-ttu-id="50a51-114">[Microsoft Graph について詳しく知る](https://docs.microsoft.com/graph/overview)。</span><span class="sxs-lookup"><span data-stu-id="50a51-114">[Learn more about Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="50a51-115">アフィニティ レベルとスコア</span><span class="sxs-lookup"><span data-stu-id="50a51-115">Affinity level and score</span></span>

<span data-ttu-id="50a51-116">エンリッチされた顧客プロファイルごとに、アフィニティ レベルとアフィニティ スコアの 2 つの関連値を提供します。</span><span class="sxs-lookup"><span data-stu-id="50a51-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="50a51-117">これらの値は、他の人口統計セグメントと比較して、そのプロファイルの人口統計セグメント、ブランドまたは関心に対するアフィニティがどの程度強いかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="50a51-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="50a51-118">*アフィニティ レベル* は、4 つのレベルで構成され、*アフィニティ スコア* はアフィニティ レベルにマッピングされる 100 ポイント スケールで計算されます。</span><span class="sxs-lookup"><span data-stu-id="50a51-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="50a51-119">アフィニティ レベル</span><span class="sxs-lookup"><span data-stu-id="50a51-119">Affinity level</span></span> |<span data-ttu-id="50a51-120">アフィニティ スコア</span><span class="sxs-lookup"><span data-stu-id="50a51-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="50a51-121">非常に多い</span><span class="sxs-lookup"><span data-stu-id="50a51-121">Very high</span></span>     | <span data-ttu-id="50a51-122">85-100</span><span class="sxs-lookup"><span data-stu-id="50a51-122">85-100</span></span>       |
|<span data-ttu-id="50a51-123">高</span><span class="sxs-lookup"><span data-stu-id="50a51-123">High</span></span>     | <span data-ttu-id="50a51-124">70-84</span><span class="sxs-lookup"><span data-stu-id="50a51-124">70-84</span></span>        |
|<span data-ttu-id="50a51-125">中</span><span class="sxs-lookup"><span data-stu-id="50a51-125">Medium</span></span>     | <span data-ttu-id="50a51-126">35-69</span><span class="sxs-lookup"><span data-stu-id="50a51-126">35-69</span></span>        |
|<span data-ttu-id="50a51-127">低</span><span class="sxs-lookup"><span data-stu-id="50a51-127">Low</span></span>     | <span data-ttu-id="50a51-128">1-34</span><span class="sxs-lookup"><span data-stu-id="50a51-128">1-34</span></span>        |

<span data-ttu-id="50a51-129">アフィニティを測定するために必要な粒度に応じて、アフィニティ レベルまたはスコアのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="50a51-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="50a51-130">アフィニティ スコアを使用すると、より正確に制御できます。</span><span class="sxs-lookup"><span data-stu-id="50a51-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="50a51-131">サポートされている国/地域</span><span class="sxs-lookup"><span data-stu-id="50a51-131">Supported countries/regions</span></span>

<span data-ttu-id="50a51-132">現在、次の国/地域オプションをサポートしています: オーストラリア、カナダ (英語)、フランス、ドイツ、英国、または米国 (英語)。</span><span class="sxs-lookup"><span data-stu-id="50a51-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="50a51-133">国を選択するには、**ブランド エンリッチメント** または **関心エンリッチメント** を開き、**国/地域** の横の **変更** を選択します。</span><span class="sxs-lookup"><span data-stu-id="50a51-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="50a51-134">**国/地域の設定** ペインでオプションを選択し、**適用** を選択します。</span><span class="sxs-lookup"><span data-stu-id="50a51-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="50a51-135">国の選択に関連する影響</span><span class="sxs-lookup"><span data-stu-id="50a51-135">Implications related to country selection</span></span>

- <span data-ttu-id="50a51-136">[独自のブランド](#define-your-brands-or-interests)を選ぶと、システムは選択した国またはリージョンに基づいて提案を提供します。</span><span class="sxs-lookup"><span data-stu-id="50a51-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="50a51-137">[業界](#define-your-brands-or-interests)を選択すると、選択した国またはリージョンに基づいて、最も関連性の高いブランドまたは関心を取得します。</span><span class="sxs-lookup"><span data-stu-id="50a51-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="50a51-138">[プロファイル](#refresh-enrichment)をエンリッチする際、選択したブランドと関心のデータを取得するすべての顧客プロファイルをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="50a51-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="50a51-139">選択した国またはリージョンにないプロファイルを含みます。</span><span class="sxs-lookup"><span data-stu-id="50a51-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="50a51-140">たとえば、ドイツを選択した場合、米国で選択したブランドと関心について Microsoft Graph データが利用可能であれば、米国にあるプロファイルが充実します。</span><span class="sxs-lookup"><span data-stu-id="50a51-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have Microsoft Graph data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="50a51-141">強化の構成</span><span class="sxs-lookup"><span data-stu-id="50a51-141">Configure Enrichment</span></span>

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="50a51-142">ブランドや関心の定義</span><span class="sxs-lookup"><span data-stu-id="50a51-142">Define your brands or interests</span></span>

<span data-ttu-id="50a51-143">次のいずれかのオプションを選択してください。</span><span class="sxs-lookup"><span data-stu-id="50a51-143">Select one of the following options:</span></span>

- <span data-ttu-id="50a51-144">**業界** : このシステムは、業界に関連するトップブランドや関心を識別し、顧客データを拡充します。</span><span class="sxs-lookup"><span data-stu-id="50a51-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="50a51-145">**自分で選択する** : 組織に最も関連のあるブランドや関心のリストから最大 5 つの項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="50a51-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="50a51-146">ブランドや関心を追加するには、入力エリアに入力して、一致する用語に基づいて提案を取得します。</span><span class="sxs-lookup"><span data-stu-id="50a51-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="50a51-147">探しているブランドや興味が見つからない場合は、**提案する** リンクを使用してフィードバックを送ってください。</span><span class="sxs-lookup"><span data-stu-id="50a51-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="50a51-148">エンリッチメントの基本設定をレビューする</span><span class="sxs-lookup"><span data-stu-id="50a51-148">Review enrichment preferences</span></span>

<span data-ttu-id="50a51-149">既定のエンリッチメント設定を確認し、必要に応じて更新します。</span><span class="sxs-lookup"><span data-stu-id="50a51-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="エンリッチメント基本設定ウィンドウのスクリーンショット。":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="50a51-151">エンリッチするエンティティを選択する</span><span class="sxs-lookup"><span data-stu-id="50a51-151">Select entity to enrich</span></span>

<span data-ttu-id="50a51-152">**エンティティをエンリッチする** を選択して、Microsoft Graph からの会社データをエンリッチするデータ セットを選択します。</span><span class="sxs-lookup"><span data-stu-id="50a51-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft Graph.</span></span> <span data-ttu-id="50a51-153">顧客エンティティを選択してすべての顧客プロファイルをエンリッチするか、セグメント エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="50a51-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="50a51-154">フィールドのマップ</span><span class="sxs-lookup"><span data-stu-id="50a51-154">Map your fields</span></span>

<span data-ttu-id="50a51-155">統合された顧客エンティティのフィールドをマッピングして、システムが顧客データを充実させるために使用する人口統計セグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="50a51-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="50a51-156">国/リージョンと少なくとも生年月日または性別の属性をマッピングします。</span><span class="sxs-lookup"><span data-stu-id="50a51-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="50a51-157">さらに、少なくとも 1 つの都市 (および都道府県) または郵便番号をマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="50a51-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="50a51-158">**編集** を選択してフィールドのマッピングを定義し、定義完了後に **適用** を選択します。</span><span class="sxs-lookup"><span data-stu-id="50a51-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="50a51-159">**保存** を選択して、フィールドのマッピングを完了します。</span><span class="sxs-lookup"><span data-stu-id="50a51-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="50a51-160">次の形式と値がサポートされていますが、値の大文字と小文字は区別されません:</span><span class="sxs-lookup"><span data-stu-id="50a51-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="50a51-161">**生年月日**: データ インジェスト中に、生年月日を DateTime の種類に変換することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="50a51-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="50a51-162">または、[ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) 形式 "yyyy-MM-dd" または "yyyy-MM-ddTHH:mm:ssZ" の文字列にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="50a51-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="50a51-163">**性別** : 男性、女性、不明</span><span class="sxs-lookup"><span data-stu-id="50a51-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="50a51-164">**郵便番号**: 米国の 5 桁の郵便番号、それ以外の国の標準郵便番号</span><span class="sxs-lookup"><span data-stu-id="50a51-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="50a51-165">**市**: 英語での都市名</span><span class="sxs-lookup"><span data-stu-id="50a51-165">**City**: City name in English</span></span>
- <span data-ttu-id="50a51-166">**都道府県**: 米国とカナダの 2 文字の省略形。</span><span class="sxs-lookup"><span data-stu-id="50a51-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="50a51-167">オーストラリアの 2 文字または 3 文字の省略形。</span><span class="sxs-lookup"><span data-stu-id="50a51-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="50a51-168">フランス、ドイツ、英国には適用されません。</span><span class="sxs-lookup"><span data-stu-id="50a51-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="50a51-169">**国/地域**:</span><span class="sxs-lookup"><span data-stu-id="50a51-169">**Country/Region**:</span></span>

  - <span data-ttu-id="50a51-170">US: アメリカ合衆国、米国、USA、US、アメリカ</span><span class="sxs-lookup"><span data-stu-id="50a51-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="50a51-171">CA: カナダ、CA</span><span class="sxs-lookup"><span data-stu-id="50a51-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="50a51-172">GB: 英国、UK、イギリス、GB、グレート・ブリテンおよび北アイルランド連合王国、グレート・ブリテン連合王国</span><span class="sxs-lookup"><span data-stu-id="50a51-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="50a51-173">AU: オーストラリア、AU、オーストラリア連邦</span><span class="sxs-lookup"><span data-stu-id="50a51-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="50a51-174">FR: フランス、FR、フランス共和国</span><span class="sxs-lookup"><span data-stu-id="50a51-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="50a51-175">DE: ドイツ、ジャーマン、ドイチュラント、アルマーニュ、DE、ドイツ連邦共和国、ドイツ共和国</span><span class="sxs-lookup"><span data-stu-id="50a51-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="refresh-enrichment"></a><span data-ttu-id="50a51-176">エンリッチメントの更新</span><span class="sxs-lookup"><span data-stu-id="50a51-176">Refresh enrichment</span></span>

<span data-ttu-id="50a51-177">人口統計のブランド、関心、およびフィールド マッピングを設定した後、エンリッチメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="50a51-177">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="50a51-178">プロセスを開始するには、ブランドまたは関心の構成ページで **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="50a51-178">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="50a51-179">さらに、スケジュールされた更新の一部として、システムで強化の自動実行をすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="50a51-179">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="50a51-180">顧客データのサイズによっては、エンリッチメントの実行が完了するまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="50a51-180">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="50a51-181">タスク/プロセスには、[6 種類の状態](system.md#status-types) があります。</span><span class="sxs-lookup"><span data-stu-id="50a51-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="50a51-182">さらに、ほとんどのプロセスは、[その他の下流プロセスに依存します](system.md#refresh-policies)。</span><span class="sxs-lookup"><span data-stu-id="50a51-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="50a51-183">プロセスのステータスを選択して、ジョブ全体の進行状況の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="50a51-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="50a51-184">ジョブのタスクの 1 つについて **詳細の表示** を選択すると、処理時間、最終処理日、およびタスクに関連するすべてのエラーと警告などの追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="50a51-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="50a51-185">強化の結果</span><span class="sxs-lookup"><span data-stu-id="50a51-185">Enrichment results</span></span>

<span data-ttu-id="50a51-186">エンリッチメント プロセスの実行後、**自分のエンリッチメント** に移動してエンリッチメントされた顧客の総数と、エンリッチメントされた顧客プロファイルのブランドや関心の内訳を確認します。</span><span class="sxs-lookup"><span data-stu-id="50a51-186">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="強化プロセスの実行結果プレビュー":::

<span data-ttu-id="50a51-188">チャートで **エンリッチされたデータを表示** を選択することで、エンリッチされたデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="50a51-188">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="50a51-189">ブランドのエンリッチされたデータは、**BrandAffinityFromMicrosoft** エンティティへ移動します。</span><span class="sxs-lookup"><span data-stu-id="50a51-189">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="50a51-190">関心のあるデータは、**InterestAffinityFromMicrosoft** エンティティにあります。</span><span class="sxs-lookup"><span data-stu-id="50a51-190">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="50a51-191">これらのエンティティは、 **データ** > **エンティティ** の **強化** グループにて一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="50a51-191">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="50a51-192">顧客カードで強化されてデータを確認する</span><span class="sxs-lookup"><span data-stu-id="50a51-192">See enrichment data on the customer card</span></span>

<span data-ttu-id="50a51-193">ブランドや関心の類似性は、個々の顧客カードでも確認することができます。</span><span class="sxs-lookup"><span data-stu-id="50a51-193">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="50a51-194">**顧客** に移動し、顧客のプロフィールを選択します。</span><span class="sxs-lookup"><span data-stu-id="50a51-194">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="50a51-195">顧客カードには、その顧客の人口統計プロファイルの人々が親しみを持っているブランドや関心のグラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50a51-195">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="データが強化された顧客カード":::

## <a name="next-steps"></a><span data-ttu-id="50a51-197">次のステップ</span><span class="sxs-lookup"><span data-stu-id="50a51-197">Next steps</span></span>

<span data-ttu-id="50a51-198">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="50a51-198">Build on top of your enriched customer data.</span></span> <span data-ttu-id="50a51-199">[セグメント](segments.md)、[メジャー](measures.md)を作成し、 [データをエクスポート](export-destinations.md) して、顧客にパーソナライズされたエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="50a51-199">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]