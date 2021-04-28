---
title: サードパーティ エンリッチメント Leadspace による会社プロファイルのエンリッチメント
description: Leadspace サードパーティ エンリッチメントに関する一般情報。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895919"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="0b13c-103">Leadspace を使用した企業プロファイルの拡充 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="0b13c-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="0b13c-104">Leadspace は、B2B の顧客データ プラットフォームを提供するデータ サイエンス企業です。</span><span class="sxs-lookup"><span data-stu-id="0b13c-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="0b13c-105">これを使用することで、企業の顧客プロファイルが統一された顧客は、データを充実させることができます。</span><span class="sxs-lookup"><span data-stu-id="0b13c-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="0b13c-106">エンリッチメントには、会社の規模、所在地、業界など、より多くの属性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0b13c-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0b13c-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="0b13c-107">Prerequisites</span></span>

<span data-ttu-id="0b13c-108">Leadspace を構成するには、次の前提条件が満たしている必要があります :</span><span class="sxs-lookup"><span data-stu-id="0b13c-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="0b13c-109">アクティブな Leadspace ライセンスを所有していること。</span><span class="sxs-lookup"><span data-stu-id="0b13c-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="0b13c-110">企業向けの[統一された顧客プロファイル](customer-profiles.md)を持っていること。</span><span class="sxs-lookup"><span data-stu-id="0b13c-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="0b13c-111">Leadspace 接続は、管理者によって既に構成されているか、[管理者](permissions.md#administrator) アクセス許可と "永続キー" (**Leadspace トークン** と呼ばれます) を所有していること。</span><span class="sxs-lookup"><span data-stu-id="0b13c-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="0b13c-112">製品の詳細については、[Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) に直接お問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="0b13c-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="0b13c-113">エンリッチメントの構成</span><span class="sxs-lookup"><span data-stu-id="0b13c-113">Configure the enrichment</span></span>

1. <span data-ttu-id="0b13c-114">対象者に関するインサイトで、**データ** > **エンリッチメント** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0b13c-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="0b13c-115">Leadspace タイルで **データのエンリッチ** を選択し、**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b13c-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace タイルのスクリーンショット。":::

1. <span data-ttu-id="0b13c-117">ドロップダウンから [接続](connections.md) を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b13c-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="0b13c-118">接続できない場合は、管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="0b13c-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="0b13c-119">管理者の場合は、**つながりの追加** を選択し、**Leadspace** を選択することで、接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0b13c-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="0b13c-120">**Leadspace に接続する** を選択し、接続を確定します。</span><span class="sxs-lookup"><span data-stu-id="0b13c-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="0b13c-121">**次へ** を選択し、Leadspace の企業データで強化する **顧客データ セット** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b13c-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="0b13c-122">**顧客** エンティティを選択してすべての顧客プロファイルをエンリッチするか、セグメント エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="0b13c-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="顧客データ セットを選択するときのスクリーンショット。":::

1. <span data-ttu-id="0b13c-124">**次へ** を選択し、統合プロファイルからどのフィールドを使用して、Leadspace から一致する企業データを検索するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="0b13c-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="0b13c-125">**会社名** フィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="0b13c-125">The **Name of company** field is required.</span></span> <span data-ttu-id="0b13c-126">一致精度を高めるために、**会社の Web サイト** と **会社所在地** の 2 つのフィールドまで追加できます。</span><span class="sxs-lookup"><span data-stu-id="0b13c-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace フィールド マッピング ペイン。":::

1. <span data-ttu-id="0b13c-128">**次へ** を選択し、フィールド マッピングを完了します。</span><span class="sxs-lookup"><span data-stu-id="0b13c-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="0b13c-129">エンリッチメントの名前を入力して、選択内容を確認した後 **エンリッチメントの保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b13c-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="0b13c-130">Leadspace の接続を構成する</span><span class="sxs-lookup"><span data-stu-id="0b13c-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="0b13c-131">接続を構成するには、管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b13c-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="0b13c-132">エンリッチメントの構成時に **つながりの追加** を選択するか、*または* **管理** > **接続** に移動し、Leadspace タイルで **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b13c-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="0b13c-133">**開始する** を選択します</span><span class="sxs-lookup"><span data-stu-id="0b13c-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="0b13c-134">**表示名** ボックスに接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0b13c-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="0b13c-135">有効な Leadspace トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="0b13c-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="0b13c-136">**データのプライバシーとコンプライアンス** を確認し、**同意する** チェックボックスを選択して、同意します</span><span class="sxs-lookup"><span data-stu-id="0b13c-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="0b13c-137">**検証** を選択して、構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="0b13c-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="0b13c-138">検証が完了したら、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b13c-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace 接続構成ページ。":::

## <a name="enrichment-results"></a><span data-ttu-id="0b13c-140">強化の結果</span><span class="sxs-lookup"><span data-stu-id="0b13c-140">Enrichment results</span></span>

<span data-ttu-id="0b13c-141">エンリッチメントを更新した後、[自分のエンリッチメント](enrichment-hub.md) で新しくエンリッチされた会社データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0b13c-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="0b13c-142">最終更新時刻と、エンリッチされたプロファイル数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0b13c-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="0b13c-143">**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0b13c-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="0b13c-144">詳細については、[Leadspace の API](https://support.leadspace.com/hc/en-us/sections/201997649-API) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b13c-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0b13c-145">次の手順</span><span class="sxs-lookup"><span data-stu-id="0b13c-145">Next steps</span></span>

<span data-ttu-id="0b13c-146">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="0b13c-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0b13c-147">[セグメント](segments.md)、[メジャー](measures.md) を作成し、[データをエクスポート](export-destinations.md) して、顧客にパーソナライズされたエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0b13c-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0b13c-148">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="0b13c-148">Data privacy and compliance</span></span>

<span data-ttu-id="0b13c-149">Dynamics 365 Customer Insights による Leadspace へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="0b13c-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0b13c-150">Microsoft ではこのようなデータをお客様の指示により転送しますが、Leadspace がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="0b13c-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0b13c-151">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b13c-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0b13c-152">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエンリッチメントはいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="0b13c-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
