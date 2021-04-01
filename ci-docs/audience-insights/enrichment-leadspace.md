---
title: サードパーティ エンリッチメント Leadspace による会社プロファイルのエンリッチメント
description: Leadspace サードパーティ エンリッチメントに関する一般情報。
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597655"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="d74c5-103">Leadspace を使用した企業プロファイルの拡充 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d74c5-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="d74c5-104">Leadspace は、B2B の顧客データ プラットフォームを提供するデータ サイエンス企業です。</span><span class="sxs-lookup"><span data-stu-id="d74c5-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="d74c5-105">これを使用することで、企業の顧客プロファイルが統一された顧客は、データを充実させることができます。</span><span class="sxs-lookup"><span data-stu-id="d74c5-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="d74c5-106">エンリッチメントには、会社の規模、所在地、業種などの追加属性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d74c5-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d74c5-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="d74c5-107">Prerequisites</span></span>

<span data-ttu-id="d74c5-108">Leadspace を構成するには、次の前提条件が満たしている必要があります :</span><span class="sxs-lookup"><span data-stu-id="d74c5-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d74c5-109">アクティブな Leadspace ライセンスと "永久キー" (**Leadspace トークン** と呼ばれる) があります。</span><span class="sxs-lookup"><span data-stu-id="d74c5-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="d74c5-110">製品の詳細について、[Leadspace](https://www.leadspace.com/products/leadspace-on-demand/)に直接に問い合わせます。</span><span class="sxs-lookup"><span data-stu-id="d74c5-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="d74c5-111">[管理者](permissions.md#administrator) のアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="d74c5-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="d74c5-112">企業向けの[統一された顧客プロファイル](customer-profiles.md)を持っていること。</span><span class="sxs-lookup"><span data-stu-id="d74c5-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="d74c5-113">構成</span><span class="sxs-lookup"><span data-stu-id="d74c5-113">Configuration</span></span>

1. <span data-ttu-id="d74c5-114">対象者に関するインサイトで、**データ** > **エンリッチメント** に移動します。</span><span class="sxs-lookup"><span data-stu-id="d74c5-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="d74c5-115">Leadspace のタイル上で、**データを充実させる** を選択します 。</span><span class="sxs-lookup"><span data-stu-id="d74c5-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace タイルのスクリーンショット。":::

1. <span data-ttu-id="d74c5-117">**開始する** を選択し、アクティブな **Leadspace トークン** (永久キー) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d74c5-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="d74c5-118">内容を確認し、**同意する** チェックボックスを選択して、**データのプライバシーとコンプライアンス** に同意してください。</span><span class="sxs-lookup"><span data-stu-id="d74c5-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="d74c5-119">**Leadspace に接続** を選択して両方の入力を確認します。</span><span class="sxs-lookup"><span data-stu-id="d74c5-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="d74c5-120">**データをマップする** を選択して、Leadspace からの会社データをエンリッチするデータ セットを選択します。</span><span class="sxs-lookup"><span data-stu-id="d74c5-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="d74c5-121">*顧客* エンティティを選択してすべての顧客プロファイルをエンリッチするか、セグメント エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="d74c5-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="顧客プロファイルとセグメント エンリッチメントのどちらかを選択します。":::

1. <span data-ttu-id="d74c5-123">**次へ** をクリックし、統合プロファイルのどのフィールドを使用して、Leadspace から一致する会社データを検索するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="d74c5-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="d74c5-124">**会社名** フィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="d74c5-124">The **Name of company** field is required.</span></span> <span data-ttu-id="d74c5-125">一致精度を高めるために、**会社の Web サイト** と **会社所在地** の 2 つのフィールドまで追加できます。</span><span class="sxs-lookup"><span data-stu-id="d74c5-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace フィールド マッピング ペイン。":::
   
1. <span data-ttu-id="d74c5-127">**適用** を選択して、フィールド マッピングを完了します。</span><span class="sxs-lookup"><span data-stu-id="d74c5-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="d74c5-128">**実行** を選択して会社のプロフィールを拡充します。</span><span class="sxs-lookup"><span data-stu-id="d74c5-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="d74c5-129">エンリッチメントにかかる時間は、統合顧客プロファイルの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d74c5-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="d74c5-130">強化の結果</span><span class="sxs-lookup"><span data-stu-id="d74c5-130">Enrichment results</span></span>

<span data-ttu-id="d74c5-131">エンリッチメントを更新した後、[自分のエンリッチメント](enrichment-hub.md) で新しくエンリッチされた会社データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d74c5-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="d74c5-132">最終更新時刻と、エンリッチされたプロファイル数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d74c5-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d74c5-133">**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d74c5-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="d74c5-134">詳細については、[Leadspace の API](https://support.leadspace.com/hc/en-us/sections/201997649-API) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d74c5-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d74c5-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="d74c5-135">Next steps</span></span>

<span data-ttu-id="d74c5-136">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="d74c5-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d74c5-137">[セグメント](segments.md)、[メジャー](measures.md) を作成し、[データをエクスポート](export-destinations.md) して、顧客にパーソナライズされたエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d74c5-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d74c5-138">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="d74c5-138">Data privacy and compliance</span></span>

<span data-ttu-id="d74c5-139">Dynamics 365 Customer Insights による Leadspace へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="d74c5-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d74c5-140">Microsoft ではこのようなデータをお客様の指示により転送しますが、Leadspace がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="d74c5-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d74c5-141">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d74c5-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d74c5-142">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエンリッチメントはいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="d74c5-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]