---
title: サードパーティ エンリッチメント HERE Technologies によるエンリッチメント
description: HERE Technologies サードパーティ エンリッチメントに関する一般情報。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896057"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="443a3-103">HERE Technologies による顧客プロファイルの強化 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="443a3-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="443a3-104">HERE Technologies は、位置中心のデータとサービスを提供するロケーション プラットフォーム企業です。</span><span class="sxs-lookup"><span data-stu-id="443a3-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="443a3-105">HERE Technologies のデータ エンリッチメント サービスを使用すると、住所の正規化、緯度と経度の抽出などにより、顧客のより正確な位置情報を把握できます。</span><span class="sxs-lookup"><span data-stu-id="443a3-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="443a3-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="443a3-106">Prerequisites</span></span>

<span data-ttu-id="443a3-107">HERE Technologies のエンリッチメントを構成するには、次の前提条件が満たされている必要があります:</span><span class="sxs-lookup"><span data-stu-id="443a3-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="443a3-108">HERE Technologies のアクティブなサブスクリプションがあります。</span><span class="sxs-lookup"><span data-stu-id="443a3-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="443a3-109">サブスクリプションを取得するには、[ここでサインアップ](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic)、または直接 [HERE Technologies に連絡](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) することができます。</span><span class="sxs-lookup"><span data-stu-id="443a3-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="443a3-110">HERE Technologies 位置情報エンリッチメントの詳細。</span><span class="sxs-lookup"><span data-stu-id="443a3-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="443a3-111">HERE [接続](connections.md) が可能であるか、*または* [管理者](permissions.md#administrator) アクセス許可とHERE Technologies API キーを所有していること。</span><span class="sxs-lookup"><span data-stu-id="443a3-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="443a3-112">エンリッチメントの構成</span><span class="sxs-lookup"><span data-stu-id="443a3-112">Configure the enrichment</span></span>

1. <span data-ttu-id="443a3-113">**データ** > **エンリッチメント** に移動します。</span><span class="sxs-lookup"><span data-stu-id="443a3-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="443a3-114">HERE Technologies タイルで **データのエンリッチ** を選択し、**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="443a3-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="443a3-115">![HERE Technologies タイル](media/HERE-tile.png "HERE Technologies タイル")</span><span class="sxs-lookup"><span data-stu-id="443a3-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="443a3-116">ドロップダウンから [接続](connections.md) を選択します。</span><span class="sxs-lookup"><span data-stu-id="443a3-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="443a3-117">接続できない場合は、管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="443a3-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="443a3-118">管理者の場合は、**つながりの追加** を選択して接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="443a3-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="443a3-119">ドロップダウンから **HERE Technologies** を選択します。</span><span class="sxs-lookup"><span data-stu-id="443a3-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="443a3-120">**HERE Technologies に接続する** を選択し、選択内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="443a3-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="443a3-121">**次へ** を選択し、HERE Technologies の位置情報データで強化する **顧客データ セット** を選択します。</span><span class="sxs-lookup"><span data-stu-id="443a3-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="443a3-122">**顧客** エンティティを選択してすべての顧客プロファイルをエンリッチするか、セグメント エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="443a3-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="顧客データ セットを選択するときのスクリーンショット。":::

1. <span data-ttu-id="443a3-124">フィールドを住所 1 または住所 2、あるいはその両方にマップするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="443a3-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="443a3-125">両方の住所のフィールド マッピングを指定し、、両方の住所のプロファイルを別々に強化できます。</span><span class="sxs-lookup"><span data-stu-id="443a3-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="443a3-126">たとえば、自宅と会社の住所がある場合です。</span><span class="sxs-lookup"><span data-stu-id="443a3-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="443a3-127">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="443a3-127">Select **Next**.</span></span>

1. <span data-ttu-id="443a3-128">HERE Technologies から一致する位置データを検索するために、統合プロファイルのどのフィールドを使用するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="443a3-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="443a3-129">**番地 1** と **郵便番号** フィールドは、住所 1 または住所 2、あるいはその両方に必要です。</span><span class="sxs-lookup"><span data-stu-id="443a3-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="443a3-130">一致精度を高めるために、より多くのフィールドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="443a3-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="443a3-131">![HERE Technologies エンリッチメント構成ページ](media/enrichment-HERE-configuration.png "HERE Technologies エンリッチメント構成ページ")</span><span class="sxs-lookup"><span data-stu-id="443a3-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="443a3-132">**次へ** を選択し、フィールド マッピングを完了します。</span><span class="sxs-lookup"><span data-stu-id="443a3-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="443a3-133">エンリッチメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="443a3-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="443a3-134">1.選択内容を確認した後、**エンリッチメントの保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="443a3-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="443a3-135">HERE Technologies の接続を構成する</span><span class="sxs-lookup"><span data-stu-id="443a3-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="443a3-136">接続を構成するには、管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="443a3-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="443a3-137">エンリッチメントの構成時に **つながりの追加** を選択するか、*または* **管理** > **接続** に移動し、HERE Technologies タイルで **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="443a3-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="443a3-138">**表示名** ボックスに接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="443a3-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="443a3-139">有効な HERE Technologies API キーを入力します。</span><span class="sxs-lookup"><span data-stu-id="443a3-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="443a3-140">**データのプライバシーとコンプライアンス** を確認し、**同意する** チェックボックスを選択して、同意します</span><span class="sxs-lookup"><span data-stu-id="443a3-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="443a3-141">**検証** を選択して、構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="443a3-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="443a3-142">検証が完了したら、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="443a3-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="443a3-143">![HERE Technologies 接続構成ページ](media/enrichment-HERE-connection.png "HERE Technologies 接続構成ページ")</span><span class="sxs-lookup"><span data-stu-id="443a3-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="443a3-144">強化の結果</span><span class="sxs-lookup"><span data-stu-id="443a3-144">Enrichment results</span></span>

<span data-ttu-id="443a3-145">エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="443a3-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="443a3-146">[スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。</span><span class="sxs-lookup"><span data-stu-id="443a3-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="443a3-147">処理時間は、顧客データのサイズと HERE Technologies からの API 応答時間によって異なります。</span><span class="sxs-lookup"><span data-stu-id="443a3-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="443a3-148">エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイル データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="443a3-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="443a3-149">さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="443a3-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="443a3-150">**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="443a3-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="443a3-151">次の手順</span><span class="sxs-lookup"><span data-stu-id="443a3-151">Next steps</span></span>

<span data-ttu-id="443a3-152">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="443a3-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="443a3-153">[セグメント](segments.md)、[メジャー](measures.md) を作成し、[データをエクスポート](export-destinations.md) して、顧客にパーソナライズされたエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="443a3-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="443a3-154">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="443a3-154">Data privacy and compliance</span></span>

<span data-ttu-id="443a3-155">Dynamics 365 Customer Insights による HERE Technologies へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="443a3-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="443a3-156">Microsoft ではこのようなデータをお客様の指示により転送しますが、HERE Technologies がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="443a3-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="443a3-157">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="443a3-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="443a3-158">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエンリッチメントはいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="443a3-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
