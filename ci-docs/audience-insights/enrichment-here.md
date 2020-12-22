---
title: サードパーティ エンリッチメント HERE Technologies によるエンリッチメント
description: HERE Technologies サードパーティ エンリッチメントに関する一般情報。
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668684"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="f835e-103">HERE Technologies による顧客プロファイルの強化 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="f835e-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="f835e-104">HERE Technologies は、位置中心のデータとサービスを提供するロケーション プラットフォーム企業です。</span><span class="sxs-lookup"><span data-stu-id="f835e-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="f835e-105">HERE Technologies のデータ エンリッチメント サービスを使用すると、住所の正規化、緯度と経度の抽出などにより、顧客のより正確な位置情報を把握できます。</span><span class="sxs-lookup"><span data-stu-id="f835e-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f835e-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="f835e-106">Prerequisites</span></span>

<span data-ttu-id="f835e-107">HERE Technologies のエンリッチメントを構成するには、次の前提条件が満たされている必要があります:</span><span class="sxs-lookup"><span data-stu-id="f835e-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f835e-108">HERE Technologies のアクティブなサブスクリプションがあります。</span><span class="sxs-lookup"><span data-stu-id="f835e-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="f835e-109">サブスクリプションを取得するには、[ここでサインアップ](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic)、または直接 [HERE Technologies に連絡](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) することができます。</span><span class="sxs-lookup"><span data-stu-id="f835e-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="f835e-110">HERE Technologies 位置情報エンリッチメントの詳細。</span><span class="sxs-lookup"><span data-stu-id="f835e-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="f835e-111">HERE Technologies API キーがあります。</span><span class="sxs-lookup"><span data-stu-id="f835e-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="f835e-112">[管理者](permissions.md#administrator) のアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="f835e-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="f835e-113">構成</span><span class="sxs-lookup"><span data-stu-id="f835e-113">Configuration</span></span>

1. <span data-ttu-id="f835e-114">**データ** > **エンリッチメント** に移動します。</span><span class="sxs-lookup"><span data-stu-id="f835e-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="f835e-115">HERE Technologies タイルで **データの強化** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f835e-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f835e-116">![HERE Technologies タイル](media/HERE-tile.png "HERE Technologies タイル")</span><span class="sxs-lookup"><span data-stu-id="f835e-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="f835e-117">アクティブな **HERE Technologies API キー** を入力します。</span><span class="sxs-lookup"><span data-stu-id="f835e-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="f835e-118">内容を確認し、**同意する** チェックボックスを選択して、**データのプライバシーとコンプライアンス** に同意してください。</span><span class="sxs-lookup"><span data-stu-id="f835e-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="f835e-119">**HERE に接続** を選択して両方の入力を確認します。</span><span class="sxs-lookup"><span data-stu-id="f835e-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="f835e-120">**データの追加** を選択して、フィールドを住所 1 または住所 2、あるいはその両方にマップするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f835e-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="f835e-121">両方の住所 (例えば、自宅と会社の住所) のフィールド マッピングを指定し、両方の住所のプロファイルを個別に強化できます。</span><span class="sxs-lookup"><span data-stu-id="f835e-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="f835e-122">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f835e-122">Select **Next**.</span></span>

1. <span data-ttu-id="f835e-123">HERE Technologies から一致する位置データを検索するために、統合プロファイルのどのフィールドを使用するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="f835e-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="f835e-124">**番地 1** と **郵便番号** フィールドは、住所 1 または住所 2、あるいはその両方に必要です。</span><span class="sxs-lookup"><span data-stu-id="f835e-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="f835e-125">一致精度を高めるために、より多くのフィールドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f835e-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f835e-126">![HERE Technologies エンリッチメント構成ページ](media/enrichment-HERE-configuration.png "HERE Technologies エンリッチメント構成ページ")</span><span class="sxs-lookup"><span data-stu-id="f835e-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="f835e-127">**適用** を選択して、フィールド マッピングを完了します。</span><span class="sxs-lookup"><span data-stu-id="f835e-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f835e-128">強化の結果</span><span class="sxs-lookup"><span data-stu-id="f835e-128">Enrichment results</span></span>

<span data-ttu-id="f835e-129">エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f835e-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f835e-130">[スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。</span><span class="sxs-lookup"><span data-stu-id="f835e-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f835e-131">処理時間は、顧客データのサイズと HERE Technologies からの API 応答時間によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f835e-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="f835e-132">エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイル データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f835e-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f835e-133">さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f835e-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f835e-134">**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f835e-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f835e-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="f835e-135">Next steps</span></span>

<span data-ttu-id="f835e-136">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="f835e-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f835e-137">[セグメント](segments.md)、[メジャー](measures.md) を作成し、[データをエクスポート](export-destinations.md) して、顧客にパーソナライズされたエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f835e-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f835e-138">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="f835e-138">Data privacy and compliance</span></span>

<span data-ttu-id="f835e-139">Dynamics 365 Customer Insights による HERE Technologies へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="f835e-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f835e-140">Microsoft ではこのようなデータをお客様の指示により転送しますが、HERE Technologies がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="f835e-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f835e-141">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f835e-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f835e-142">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエンリッチメントはいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="f835e-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
