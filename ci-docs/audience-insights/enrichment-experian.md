---
title: サードパーティ エンリッチメント Experian によるエンリッチメント
description: Experian サードパーティ エンリッチメントに関する一般情報。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896379"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="9859d-103">Experian の人口統計で顧客プロファイルをエンリッチする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9859d-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="9859d-104">Experian は、消費者および企業の信用調査およびマーケティング サービスの世界的リーダーです。</span><span class="sxs-lookup"><span data-stu-id="9859d-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="9859d-105">Experian のデータ エンリッチメント サービスを使用することで、世帯規模や収入などの人口統計データで顧客プロファイルをエンリッチさせ、より深い顧客理解を構築することができます。</span><span class="sxs-lookup"><span data-stu-id="9859d-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9859d-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="9859d-106">Prerequisites</span></span>

<span data-ttu-id="9859d-107">Experian を構成するには、次の前提条件が満たされている必要があります:</span><span class="sxs-lookup"><span data-stu-id="9859d-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="9859d-108">Experian のサブスクリプションがアクティブです。</span><span class="sxs-lookup"><span data-stu-id="9859d-108">You have an active Experian subscription.</span></span> <span data-ttu-id="9859d-109">サブスクリプションを取得するには、直接 [Experian にお問い合わせください](https://www.experian.com/marketing-services/contact)。</span><span class="sxs-lookup"><span data-stu-id="9859d-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="9859d-110">[Experian データ エンリッチメントの詳細情報](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) を確認する。</span><span class="sxs-lookup"><span data-stu-id="9859d-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="9859d-111">Experian 接続はすでに管理者によって構成されている、*または* [管理者](permissions.md#administrator) アクセス許可を所有していること。</span><span class="sxs-lookup"><span data-stu-id="9859d-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="9859d-112">また、Experian がユーザーのために作成した、SSH 対応セキュア トランスポート (ST) アカウントのユーザー ID、関係者 ID、およびモデル番号も必要です。</span><span class="sxs-lookup"><span data-stu-id="9859d-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="9859d-113">エンリッチメントの構成</span><span class="sxs-lookup"><span data-stu-id="9859d-113">Configure the enrichment</span></span>

1. <span data-ttu-id="9859d-114">**データ** > **エンリッチメント** に移動し、**検出** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="9859d-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="9859d-115">Experian タイルで **データのエンリッチ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9859d-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9859d-116">![Experian タイル](media/experian-tile.png "Experian タイル")</span><span class="sxs-lookup"><span data-stu-id="9859d-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="9859d-117">ドロップダウンから [接続](connections.md) を選択します。</span><span class="sxs-lookup"><span data-stu-id="9859d-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="9859d-118">接続できない場合は、管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="9859d-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="9859d-119">管理者の場合は、**つながりの追加** を選択し、ドロップダウンから Experian を選択することで、接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9859d-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="9859d-120">**Experian に接続する** を選択し、接続の選択内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="9859d-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="9859d-121">**次へ** を選択し、Experian の人口統計データで強化する **顧客データ セット** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9859d-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="9859d-122">**顧客** エンティティを選択してすべての顧客プロファイルをエンリッチするか、セグメント エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="9859d-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="顧客データ セットを選択するときのスクリーンショット。":::

1. <span data-ttu-id="9859d-124">**次へ** を選択し、統合プロファイルからどの種類のフィールドを使用して、Experian から一致する人口統計データを検索するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="9859d-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="9859d-125">**名前と住所**、**電話**、または **メール** フィールドの少なくとも 1 つが必要です。</span><span class="sxs-lookup"><span data-stu-id="9859d-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="9859d-126">一致精度を高めるために、他に最大 2 つのフィールドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="9859d-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="9859d-127">この選択は、次の手順でアクセスできるマッピング フィールドに影響します。</span><span class="sxs-lookup"><span data-stu-id="9859d-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="9859d-128">Experian に送信されるキー識別子属性が多いほど、一致率が高くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9859d-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="9859d-129">**次へ** を選択し、フィールド マッピングを開始します。</span><span class="sxs-lookup"><span data-stu-id="9859d-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="9859d-130">統合プロファイルからどのフィールドを使用して、Experian から一致する人口統計データを検索するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="9859d-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="9859d-131">必須フィールドはマークされます。</span><span class="sxs-lookup"><span data-stu-id="9859d-131">Required fields are marked.</span></span>

1. <span data-ttu-id="9859d-132">エンリッチメントの名前と出力エンティティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9859d-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="9859d-133">選択内容を確認した後、**エンリッチメントの保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9859d-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="9859d-134">Experian の接続を構成する</span><span class="sxs-lookup"><span data-stu-id="9859d-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="9859d-135">接続を構成するには、管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9859d-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="9859d-136">エンリッチメントの構成時に **つながりの追加** を選択するか、*または* **管理** > **接続** に移動し、Experian タイルで **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9859d-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="9859d-137">**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9859d-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="9859d-138">**表示名** ボックスに接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9859d-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="9859d-139">Experian セキュア トランスポート アカウントの有効なユーザー ID、関係者 ID、およびモデル番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="9859d-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="9859d-140">**データのプライバシーとコンプライアンス** を確認し、**同意する** チェックボックスを選択して、同意します</span><span class="sxs-lookup"><span data-stu-id="9859d-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="9859d-141">**検証** を選択して、構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="9859d-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="9859d-142">検証が完了したら、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9859d-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian 接続構成ペイン。":::

## <a name="enrichment-results"></a><span data-ttu-id="9859d-144">強化の結果</span><span class="sxs-lookup"><span data-stu-id="9859d-144">Enrichment results</span></span>

<span data-ttu-id="9859d-145">エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9859d-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="9859d-146">[スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。</span><span class="sxs-lookup"><span data-stu-id="9859d-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9859d-147">処理時間は、顧客データのサイズと Experian がカウントに設定したエンリッチメント プロセスによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9859d-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="9859d-148">エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイル データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9859d-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="9859d-149">さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9859d-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="9859d-150">**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9859d-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9859d-151">次の手順</span><span class="sxs-lookup"><span data-stu-id="9859d-151">Next steps</span></span>

<span data-ttu-id="9859d-152">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="9859d-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="9859d-153">[セグメント](segments.md)、[メジャー](measures.md) を作成し、[データをエクスポート](export-destinations.md) して、顧客にパーソナライズされたエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9859d-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9859d-154">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="9859d-154">Data privacy and compliance</span></span>

<span data-ttu-id="9859d-155">Dynamics 365 Customer Insights による Experian へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="9859d-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9859d-156">Microsoft ではこのようなデータをお客様の指示により転送しますが、Experian がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="9859d-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9859d-157">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9859d-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9859d-158">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエンリッチメントはいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="9859d-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
