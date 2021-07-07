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
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305438"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="ad3f0-103">拡張住所による顧客プロファイルの強化</span><span class="sxs-lookup"><span data-stu-id="ad3f0-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="ad3f0-104">データ内のアドレスは、構造化されていない、不完全である、または正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="ad3f0-105">Microsoft のモデルを使用して、住所を [Common Data Model 形式](/common-data-model/schema/core/applicationcommon/address) に正規化およびエンリッチし、精度とインサイトを向上します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="ad3f0-106">住所の拡張方法</span><span class="sxs-lookup"><span data-stu-id="ad3f0-106">How we enhance addresses</span></span>

<span data-ttu-id="ad3f0-107">このモデルでは、住所を拡張するために 2 ステップのプロセスを行います。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="ad3f0-108">まず、住所を解析してコンポーネントを識別し、構造化された形式にします。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="ad3f0-109">次に、AI を使用して、住所の値を修正して完成させ、標準化します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="ad3f0-110">例</span><span class="sxs-lookup"><span data-stu-id="ad3f0-110">Example</span></span>

<span data-ttu-id="ad3f0-111">住所情報が非標準形式であり、スペルミスが含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="ad3f0-112">モデルでは、これらの問題を修正し、統合顧客プロファイルに一貫のある住所を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

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

### <a name="limitations"></a><span data-ttu-id="ad3f0-113">制限</span><span class="sxs-lookup"><span data-stu-id="ad3f0-113">Limitations</span></span>

<span data-ttu-id="ad3f0-114">拡張住所は、取り込んだ住所データにすでに存在する値でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="ad3f0-115">モデルには、以下は含まれません:</span><span class="sxs-lookup"><span data-stu-id="ad3f0-115">The model doesn't:</span></span> 

1. <span data-ttu-id="ad3f0-116">住所が有効な住所であるかどうかを確認する。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="ad3f0-117">郵便番号や町名などの値のいずれかが有効かどうかを確認する。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="ad3f0-118">認識できない値を変更する。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="ad3f0-119">モデルは、機械学習ベースの手法を使用して住所を拡張します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="ad3f0-120">他の機械学習ベースのモデルと同様に、モデルが入力値を変更するときには信頼性の高いしきい値を適用しますが、100％ の精度は保証されません。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="ad3f0-121">サポートされている国または地域</span><span class="sxs-lookup"><span data-stu-id="ad3f0-121">Supported countries or regions</span></span>

<span data-ttu-id="ad3f0-122">現在、次の国または地域で住所のエンリッチ化をサポートしています:</span><span class="sxs-lookup"><span data-stu-id="ad3f0-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="ad3f0-123">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="ad3f0-123">Australia</span></span>
- <span data-ttu-id="ad3f0-124">カナダ</span><span class="sxs-lookup"><span data-stu-id="ad3f0-124">Canada</span></span>
- <span data-ttu-id="ad3f0-125">イギリス</span><span class="sxs-lookup"><span data-stu-id="ad3f0-125">United Kingdom</span></span>
- <span data-ttu-id="ad3f0-126">米国</span><span class="sxs-lookup"><span data-stu-id="ad3f0-126">United States</span></span>

<span data-ttu-id="ad3f0-127">住所には、国/地域の値が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="ad3f0-128">サポートされていない国または地域の住所、および国または地域が指定されていない住所は処理されません。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="ad3f0-129">エンリッチメントの構成</span><span class="sxs-lookup"><span data-stu-id="ad3f0-129">Configure the enrichment</span></span>

1. <span data-ttu-id="ad3f0-130">**データ** > **エンリッチメント** に移動します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="ad3f0-131">**データのエンリッチ** を **拡張住所** タイルで選択します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="拡張住所タイルのスクリーンショット。":::

1. <span data-ttu-id="ad3f0-133">**顧客データ セット** を選択して、エンリッチする住所を含むエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="ad3f0-134">*顧客* エンティティを選択して、すべての顧客プロファイルの住所をエンリッチするか、セグメント エンティティを選択して、そのセグメントに含まれる顧客プロファイルのみ住所をエンリッチすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="ad3f0-135">データ セットでの住所の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="ad3f0-136">**1 つの属性を持つ住所** は、データ内の住所が 1 つのフィールドを使用する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="ad3f0-137">**複数の属性を持つ住所** は、データ内の住所が複数のデータ フィールドを使用する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ad3f0-138">国/地域は、1 つの属性を持つ住所と複数の属性を持つ住所の両方で必須です。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="ad3f0-139">有効またはサポート対象である国/地域の値を含まない住所はエンリッチされません。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="ad3f0-140">統合顧客エンティティから住所フィールドをマップします。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="拡張住所フィールド マッピング ページ。":::

1. <span data-ttu-id="ad3f0-142">**次へ** を選択し、フィールド マッピングを完了します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="ad3f0-143">エンリッチメントと出力エンティティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="ad3f0-144">選択内容を確認した後、**エンリッチメントの保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ad3f0-145">強化の結果</span><span class="sxs-lookup"><span data-stu-id="ad3f0-145">Enrichment results</span></span>

<span data-ttu-id="ad3f0-146">エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="ad3f0-147">[スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ad3f0-148">処理時間は、顧客データのサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="ad3f0-149">エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイル データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="ad3f0-150">さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ad3f0-151">**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ad3f0-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="ad3f0-152">Next steps</span></span>

<span data-ttu-id="ad3f0-153">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ad3f0-154">[セグメント](segments.md) および [メジャー](measures.md) を作成し、さらに [データのエクスポート](export-destinations.md) を行って、パーソナライズされたエクスペリエンスを顧客に提供します。</span><span class="sxs-lookup"><span data-stu-id="ad3f0-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
