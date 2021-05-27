---
title: 住所拡張エンリッチメント
description: Microsoft のモデルを使用して、顧客プロファイルの住所情報をエンリッチおよび正規化します。
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965584"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="5c9d3-103">拡張住所による顧客プロファイルの強化</span><span class="sxs-lookup"><span data-stu-id="5c9d3-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="5c9d3-104">データ内のアドレスは、構造化されていない、不完全である、または正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="5c9d3-105">Microsoft のモデルを使用して、住所を [Common Data Model 形式](/common-data-model/schema/core/applicationcommon/address) に正規化およびエンリッチし、精度とインサイトを向上します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="5c9d3-106">住所の拡張方法</span><span class="sxs-lookup"><span data-stu-id="5c9d3-106">How we enhance addresses</span></span>

<span data-ttu-id="5c9d3-107">このモデルでは、住所を拡張するために 2 ステップのプロセスを行います。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="5c9d3-108">まず、住所を解析してコンポーネントを識別し、構造化された形式にします。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="5c9d3-109">次に、人工知能を使用して、住所の値を修正、補完、標準化します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="5c9d3-110">例</span><span class="sxs-lookup"><span data-stu-id="5c9d3-110">Example</span></span>

<span data-ttu-id="5c9d3-111">住所情報が非標準形式であり、スペルミスが含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="5c9d3-112">モデルでは、これらの問題を修正し、統合顧客プロファイルに一貫のある住所を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="5c9d3-113">制限</span><span class="sxs-lookup"><span data-stu-id="5c9d3-113">Limitations</span></span>

<span data-ttu-id="5c9d3-114">拡張住所は、取り込んだ住所データにすでに存在する値でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="5c9d3-115">モデルには、以下は含まれません:</span><span class="sxs-lookup"><span data-stu-id="5c9d3-115">The model doesn't:</span></span> 

1. <span data-ttu-id="5c9d3-116">住所が有効な住所であるかどうかを確認する。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="5c9d3-117">郵便番号や町名などの値のいずれかが有効かどうかを確認する。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="5c9d3-118">認識できない値を変更する。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="5c9d3-119">モデルは、機械学習ベースの手法を使用して住所を拡張します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="5c9d3-120">ML ベースのモデルと同様に、モデルが入力値を変更するときに高い信頼性のしきい値を適用しますが、100% の精度は保証されません。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="5c9d3-121">サポートされている国または地域</span><span class="sxs-lookup"><span data-stu-id="5c9d3-121">Supported countries or regions</span></span>

<span data-ttu-id="5c9d3-122">現在、次の国または地域で住所のエンリッチ化をサポートしています:</span><span class="sxs-lookup"><span data-stu-id="5c9d3-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="5c9d3-123">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="5c9d3-123">Australia</span></span>
- <span data-ttu-id="5c9d3-124">カナダ</span><span class="sxs-lookup"><span data-stu-id="5c9d3-124">Canada</span></span>
- <span data-ttu-id="5c9d3-125">イギリス</span><span class="sxs-lookup"><span data-stu-id="5c9d3-125">United Kingdom</span></span>
- <span data-ttu-id="5c9d3-126">米国</span><span class="sxs-lookup"><span data-stu-id="5c9d3-126">United States</span></span>

<span data-ttu-id="5c9d3-127">住所には、国/地域の値が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="5c9d3-128">サポートされていない国または地域の住所、および国または地域が指定されていない住所は処理されません。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="5c9d3-129">エンリッチメントの構成</span><span class="sxs-lookup"><span data-stu-id="5c9d3-129">Configure the enrichment</span></span>

1. <span data-ttu-id="5c9d3-130">**データ** > **エンリッチメント** に移動します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="5c9d3-131">**データのエンリッチ** を **拡張住所** タイルで選択します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="拡張住所タイルのスクリーンショット。":::

1. <span data-ttu-id="5c9d3-133">**顧客データ セット** を選択して、エンリッチする住所を含むエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="5c9d3-134">*顧客* エンティティを選択して、すべての顧客プロファイルの住所をエンリッチするか、セグメント エンティティを選択して、そのセグメントに含まれる顧客プロファイルのみ住所をエンリッチすることができます。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="5c9d3-135">データ セットでの住所の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="5c9d3-136">**1 つの属性を持つ住所** は、データ内の住所が 1 つのフィールドを使用する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="5c9d3-137">**複数の属性を持つ住所** は、データ内の住所が複数のデータ フィールドを使用する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5c9d3-138">国/地域は、1 つの属性を持つ住所と複数の属性を持つ住所の両方で必須です。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="5c9d3-139">有効またはサポート対象の国/地域の値を含まない住所はエンリッチされません</span><span class="sxs-lookup"><span data-stu-id="5c9d3-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="5c9d3-140">統合顧客エンティティから住所フィールドをマップします。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="拡張住所フィールド マッピング ページ。":::

1. <span data-ttu-id="5c9d3-142">**次へ** を選択し、フィールド マッピングを完了します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="5c9d3-143">エンリッチメントと出力エンティティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="5c9d3-144">選択内容を確認した後、**エンリッチメントの保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="5c9d3-145">強化の結果</span><span class="sxs-lookup"><span data-stu-id="5c9d3-145">Enrichment results</span></span>

<span data-ttu-id="5c9d3-146">エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="5c9d3-147">[スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5c9d3-148">処理時間は、顧客データのサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="5c9d3-149">エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイル データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="5c9d3-150">さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="5c9d3-151">**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5c9d3-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="5c9d3-152">Next steps</span></span>

<span data-ttu-id="5c9d3-153">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="5c9d3-154">[セグメント](segments.md)、[メジャー](measures.md) を作成し、[データをエクスポート](export-destinations.md) して、顧客にパーソナライズされたエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5c9d3-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
