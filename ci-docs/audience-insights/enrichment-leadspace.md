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
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305208"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="0d139-103">Leadspace を使用した企業プロファイルの拡充 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="0d139-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="0d139-104">Leadspace は、B2B の顧客データ プラットフォームを提供するデータ サイエンス企業です。</span><span class="sxs-lookup"><span data-stu-id="0d139-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="0d139-105">これを使用することで、企業の顧客プロファイルが統一された顧客は、データを充実させることができます。</span><span class="sxs-lookup"><span data-stu-id="0d139-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="0d139-106">エンリッチメントには、会社の規模、所在地、業界など、より多くの属性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0d139-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0d139-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="0d139-107">Prerequisites</span></span>

<span data-ttu-id="0d139-108">Leadspace を構成するには、次の前提条件が満たしている必要があります :</span><span class="sxs-lookup"><span data-stu-id="0d139-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="0d139-109">アクティブな Leadspace ライセンスを所有していること。</span><span class="sxs-lookup"><span data-stu-id="0d139-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="0d139-110">企業向けの[統一された顧客プロファイル](customer-profiles.md)を持っていること。</span><span class="sxs-lookup"><span data-stu-id="0d139-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="0d139-111">Leadspace 接続は、管理者によって既に構成されているか、[管理者](permissions.md#administrator) アクセス許可と "永続キー" (**Leadspace トークン** と呼ばれます) を所有していること。</span><span class="sxs-lookup"><span data-stu-id="0d139-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="0d139-112">製品の詳細については、[Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) に直接お問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="0d139-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="0d139-113">エンリッチメントの構成</span><span class="sxs-lookup"><span data-stu-id="0d139-113">Configure the enrichment</span></span>

1. <span data-ttu-id="0d139-114">対象者に関するインサイトで、**データ** > **エンリッチメント** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0d139-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="0d139-115">Leadspace タイルで **データのエンリッチ** を選択し、**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d139-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace タイルのスクリーンショット。":::

1. <span data-ttu-id="0d139-117">ドロップダウン リストから [接続](connections.md) を選択してください。</span><span class="sxs-lookup"><span data-stu-id="0d139-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="0d139-118">接続できない場合は、管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="0d139-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="0d139-119">管理者の場合は、**つながりの追加** を選択し、**Leadspace** を選択することで、接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0d139-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="0d139-120">**Leadspace に接続する** を選択し、接続を確定します。</span><span class="sxs-lookup"><span data-stu-id="0d139-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="0d139-121">**次へ** を選択し、Leadspace の企業データで強化する **顧客データ セット** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d139-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="0d139-122">**顧客** エンティティを選択してすべての顧客プロファイルをエンリッチするか、セグメント エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="0d139-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="顧客データ セットを選択するときのスクリーンショット。":::

1. <span data-ttu-id="0d139-124">**次へ** を選択し、統合プロファイルからどのフィールドを使用して、Leadspace から一致する企業データを検索するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="0d139-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="0d139-125">**会社名** フィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="0d139-125">The **Name of company** field is required.</span></span> <span data-ttu-id="0d139-126">一致精度を高めるために、**会社の Web サイト** と **会社所在地** の 2 つのフィールドまで追加できます。</span><span class="sxs-lookup"><span data-stu-id="0d139-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace フィールド マッピング ペイン。":::

1. <span data-ttu-id="0d139-128">**次へ** を選択し、フィールド マッピングを完了します。</span><span class="sxs-lookup"><span data-stu-id="0d139-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="0d139-129">エンリッチメントの名前を入力して、選択内容を確認した後 **エンリッチメントの保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d139-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="0d139-130">Leadspace の接続を構成する</span><span class="sxs-lookup"><span data-stu-id="0d139-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="0d139-131">接続を構成するには、管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d139-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="0d139-132">エンリッチメントの構成時に **つながりの追加** を選択するか、*または* **管理** > **接続** に移動し、Leadspace タイルで **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d139-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="0d139-133">**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d139-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="0d139-134">**表示名** ボックスに接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d139-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="0d139-135">有効な Leadspace トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d139-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="0d139-136">確認して、**同意する** を選択して、**データのプライバシーとコンプライアンス** に同意します。</span><span class="sxs-lookup"><span data-stu-id="0d139-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="0d139-137">**検証** を選択して、構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="0d139-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="0d139-138">検証が完了したら、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d139-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace 接続構成ページ。":::

## <a name="enrichment-results"></a><span data-ttu-id="0d139-140">強化の結果</span><span class="sxs-lookup"><span data-stu-id="0d139-140">Enrichment results</span></span>

<span data-ttu-id="0d139-141">エンリッチメントを更新した後、[自分のエンリッチメント](enrichment-hub.md) で新しくエンリッチされた会社データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0d139-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="0d139-142">最終更新時刻と、エンリッチされたプロファイル数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0d139-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="0d139-143">**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0d139-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="0d139-144">詳細については、[Leadspace の API](https://support.leadspace.com/hc/en-us/sections/201997649-API) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d139-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0d139-145">次の手順</span><span class="sxs-lookup"><span data-stu-id="0d139-145">Next steps</span></span>

<span data-ttu-id="0d139-146">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="0d139-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0d139-147">[セグメント](segments.md) および [メジャー](measures.md) を作成し、さらに [データのエクスポート](export-destinations.md) を行って、パーソナライズされたエクスペリエンスを顧客に提供します。</span><span class="sxs-lookup"><span data-stu-id="0d139-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0d139-148">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="0d139-148">Data privacy and compliance</span></span>

<span data-ttu-id="0d139-149">Dynamics 365 Customer Insights による Leadspace へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="0d139-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0d139-150">Microsoft ではこのようなデータをお客様の指示により転送しますが、Leadspace がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="0d139-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0d139-151">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d139-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0d139-152">Dynamics 365 Customer Insights 管理者は、いつでもエンリッチメントを削除して、この機能の使用を中止することができます。</span><span class="sxs-lookup"><span data-stu-id="0d139-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
