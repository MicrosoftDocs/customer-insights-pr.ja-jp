---
title: サードパーティのエンリッチメント HERE Technologies によるエンリッチメント
description: HERE Technologies サードパーティ エンリッチメントに関する一般情報。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305300"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="c9383-103">HERE Technologies による顧客プロファイルの強化 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="c9383-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="c9383-104">HERE Technologies は、位置中心のデータとサービスを提供するロケーション プラットフォーム企業です。</span><span class="sxs-lookup"><span data-stu-id="c9383-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="c9383-105">HERE Technologies のデータ エンリッチメント サービスを使用すると、住所の正規化、緯度と経度の抽出などにより、顧客のより正確な位置情報を把握できます。</span><span class="sxs-lookup"><span data-stu-id="c9383-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c9383-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="c9383-106">Prerequisites</span></span>

<span data-ttu-id="c9383-107">HERE Technologies のエンリッチメントを構成するには、次の前提条件が満たされている必要があります:</span><span class="sxs-lookup"><span data-stu-id="c9383-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c9383-108">HERE Technologies のアクティブなサブスクリプションがあること。</span><span class="sxs-lookup"><span data-stu-id="c9383-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="c9383-109">サブスクリプションを取得するには、[ここでサインアップする](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) か、または直接 [HERE Technologies に問い合わせ](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c9383-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="c9383-110">HERE Technologies 位置情報エンリッチメントの詳細。</span><span class="sxs-lookup"><span data-stu-id="c9383-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="c9383-111">HERE [接続](connections.md) が利用可能であるか、*または* [管理者](permissions.md#administrator) 権限と HERE Technologies API キーを所有していること。</span><span class="sxs-lookup"><span data-stu-id="c9383-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="c9383-112">エンリッチメントの構成</span><span class="sxs-lookup"><span data-stu-id="c9383-112">Configure the enrichment</span></span>

1. <span data-ttu-id="c9383-113">**データ** > **エンリッチメント** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c9383-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="c9383-114">HERE Technologies タイルで **データのエンリッチ** を選択し、**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9383-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c9383-115">![HERE Technologies タイル](media/HERE-tile.png "HERE Technologies タイル")</span><span class="sxs-lookup"><span data-stu-id="c9383-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="c9383-116">ドロップダウン リストから [接続](connections.md) を選択してください。</span><span class="sxs-lookup"><span data-stu-id="c9383-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="c9383-117">接続できない場合は、管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="c9383-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="c9383-118">管理者の場合は、**つながりの追加** を選択して接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="c9383-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="c9383-119">ドロップダウン リストから、**HERE Technologies** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9383-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="c9383-120">**HERE Technologies に接続する** を選択し、選択内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="c9383-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="c9383-121">**次へ** を選択し、HERE Technologies の位置情報データで強化する **顧客データ セット** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9383-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="c9383-122">**顧客** エンティティを選択してすべての顧客プロファイルをエンリッチするか、セグメント エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="c9383-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="顧客データ セットを選択するときのスクリーンショット。":::

1. <span data-ttu-id="c9383-124">フィールドを住所 1 または住所 2、あるいはその両方にマップするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9383-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="c9383-125">両方の住所のフィールド マッピングを指定し、、両方の住所のプロファイルを別々に強化できます。</span><span class="sxs-lookup"><span data-stu-id="c9383-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="c9383-126">たとえば、自宅と会社の住所がある場合です。</span><span class="sxs-lookup"><span data-stu-id="c9383-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="c9383-127">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9383-127">Select **Next**.</span></span>

1. <span data-ttu-id="c9383-128">HERE Technologies から一致する位置データを検索するために、統合プロファイルのどのフィールドを使用するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="c9383-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="c9383-129">**番地 1** と **郵便番号** フィールドは、住所 1 または住所 2、あるいはその両方に必要です。</span><span class="sxs-lookup"><span data-stu-id="c9383-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="c9383-130">一致精度を高めるために、より多くのフィールドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="c9383-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c9383-131">![HERE Technologies エンリッチメント構成ページ](media/enrichment-HERE-configuration.png "HERE Technologies エンリッチメント構成ページ")</span><span class="sxs-lookup"><span data-stu-id="c9383-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="c9383-132">**次へ** を選択し、フィールド マッピングを完了します。</span><span class="sxs-lookup"><span data-stu-id="c9383-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="c9383-133">エンリッチメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c9383-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="c9383-134">選択内容を確認した後、**エンリッチメントの保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9383-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="c9383-135">HERE Technologies の接続を構成する</span><span class="sxs-lookup"><span data-stu-id="c9383-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="c9383-136">接続を構成するには、管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9383-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="c9383-137">エンリッチメントの構成時に **つながりの追加** を選択するか、*または* **管理** > **接続** に移動し、HERE Technologies タイルで **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9383-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="c9383-138">**表示名** ボックスに接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c9383-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="c9383-139">有効な HERE Technologies API キーを入力します。</span><span class="sxs-lookup"><span data-stu-id="c9383-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="c9383-140">確認して、**同意する** を選択して、**データのプライバシーとコンプライアンス** に同意します。</span><span class="sxs-lookup"><span data-stu-id="c9383-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="c9383-141">**検証** を選択して、構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="c9383-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="c9383-142">検証が完了したら、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9383-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c9383-143">![HERE Technologies 接続構成ページ](media/enrichment-HERE-connection.png "HERE Technologies 接続構成ページ")</span><span class="sxs-lookup"><span data-stu-id="c9383-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="c9383-144">強化の結果</span><span class="sxs-lookup"><span data-stu-id="c9383-144">Enrichment results</span></span>

<span data-ttu-id="c9383-145">エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9383-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="c9383-146">[スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。</span><span class="sxs-lookup"><span data-stu-id="c9383-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c9383-147">処理時間は、顧客データのサイズと HERE Technologies からの API 応答時間によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c9383-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="c9383-148">エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイル データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c9383-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="c9383-149">さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9383-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c9383-150">**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c9383-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c9383-151">次の手順</span><span class="sxs-lookup"><span data-stu-id="c9383-151">Next steps</span></span>

<span data-ttu-id="c9383-152">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="c9383-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c9383-153">[セグメント](segments.md) および [メジャー](measures.md) を作成し、さらに [データのエクスポート](export-destinations.md) を行って、パーソナライズされたエクスペリエンスを顧客に提供します。</span><span class="sxs-lookup"><span data-stu-id="c9383-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c9383-154">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="c9383-154">Data privacy and compliance</span></span>

<span data-ttu-id="c9383-155">Dynamics 365 Customer Insights による HERE Technologies へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="c9383-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c9383-156">Microsoft ではこのようなデータをお客様の指示により転送しますが、HERE Technologies がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="c9383-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c9383-157">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9383-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c9383-158">Dynamics 365 Customer Insights 管理者は、いつでもエンリッチメントを削除して、この機能の使用を中止することができます。</span><span class="sxs-lookup"><span data-stu-id="c9383-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
