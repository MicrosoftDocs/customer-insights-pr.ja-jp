---
title: サードパーティ エンリッチメント Experian によるエンリッチメント
description: Experian サードパーティ エンリッチメントに関する一般情報。
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668818"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="f459f-103">Experian の人口統計で顧客プロファイルをエンリッチする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="f459f-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="f459f-104">Experian は、消費者および企業の信用調査およびマーケティング サービスの世界的リーダーです。</span><span class="sxs-lookup"><span data-stu-id="f459f-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="f459f-105">Experian のデータ エンリッチメント サービスを使用することで、世帯規模や収入などの人口統計データで顧客プロファイルをエンリッチさせ、より深い顧客理解を構築することができます。</span><span class="sxs-lookup"><span data-stu-id="f459f-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f459f-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="f459f-106">Prerequisites</span></span>

<span data-ttu-id="f459f-107">Experian を構成するには、次の前提条件が満たされている必要があります:</span><span class="sxs-lookup"><span data-stu-id="f459f-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f459f-108">Experian のサブスクリプションがアクティブです。</span><span class="sxs-lookup"><span data-stu-id="f459f-108">You have an active Experian subscription.</span></span> <span data-ttu-id="f459f-109">サブスクリプションを取得するには、直接 [Experian にお問い合わせください](https://www.experian.com/marketing-services/contact)。</span><span class="sxs-lookup"><span data-stu-id="f459f-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="f459f-110">[Experian データ エンリッチメントの詳細情報](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) を確認する。</span><span class="sxs-lookup"><span data-stu-id="f459f-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="f459f-111">Experian が作成した SSH 対応のセキュア トランスポート (ST) アカウントのユーザー ID、パーティ ID、およびモデル番号があります。</span><span class="sxs-lookup"><span data-stu-id="f459f-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="f459f-112">対象者に関するインサイトに [管理者](permissions.md#administrator) のアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="f459f-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="f459f-113">構成</span><span class="sxs-lookup"><span data-stu-id="f459f-113">Configuration</span></span>

1. <span data-ttu-id="f459f-114">**データ** > **エンリッチメント** に移動し、**検出** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="f459f-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f459f-115">Experian タイルで **データのエンリッチ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f459f-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f459f-116">![Experian タイル](media/experian-tile.png "Experian タイル")</span><span class="sxs-lookup"><span data-stu-id="f459f-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="f459f-117">**開始する** を選択して、Experian セキュア トランスポート アカウントのユーザー ID、パーティ ID、およびモデル番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="f459f-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="f459f-118">内容を確認し、**同意する** チェックボックスを選択して、**データのプライバシーとコンプライアンス** に同意してください。</span><span class="sxs-lookup"><span data-stu-id="f459f-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="f459f-119">**適用** を選択して、すべての入力を確認します。</span><span class="sxs-lookup"><span data-stu-id="f459f-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="f459f-120">フィールドのマップ</span><span class="sxs-lookup"><span data-stu-id="f459f-120">Map your fields</span></span>

1. <span data-ttu-id="f459f-121">**データの追加** を選択して、**名前と住所**、**電子メール**、または **電話** からキー識別子を選択し、ID 解決のために Experian に送信します。</span><span class="sxs-lookup"><span data-stu-id="f459f-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="f459f-122">Experian に送信されるキー識別子属性が多いほど、一致率が高くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f459f-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="f459f-123">**次へ** を選択して、選択したキー識別子フィールドの統合顧客エンティティから対応する属性をマップします。</span><span class="sxs-lookup"><span data-stu-id="f459f-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="f459f-124">**属性の追加** を選択して、Experian に送信する追加属性をマップします。</span><span class="sxs-lookup"><span data-stu-id="f459f-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="f459f-125">**保存** を選択して、フィールドのマッピングを完了します。</span><span class="sxs-lookup"><span data-stu-id="f459f-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f459f-126">![Experian フィールド マッピング](media/experian-field-mapping.png "Experian フィールド マッピング")</span><span class="sxs-lookup"><span data-stu-id="f459f-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f459f-127">強化の結果</span><span class="sxs-lookup"><span data-stu-id="f459f-127">Enrichment results</span></span>

<span data-ttu-id="f459f-128">エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f459f-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f459f-129">[スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。</span><span class="sxs-lookup"><span data-stu-id="f459f-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f459f-130">処理時間は、顧客データのサイズと Experian がカウントに設定したエンリッチメント プロセスによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f459f-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="f459f-131">エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイル データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f459f-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f459f-132">さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f459f-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f459f-133">**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f459f-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f459f-134">次の手順</span><span class="sxs-lookup"><span data-stu-id="f459f-134">Next steps</span></span>

<span data-ttu-id="f459f-135">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="f459f-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f459f-136">[セグメント](segments.md)、[メジャー](measures.md) を作成し、[データをエクスポート](export-destinations.md) して、顧客にパーソナライズされたエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f459f-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f459f-137">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="f459f-137">Data privacy and compliance</span></span>

<span data-ttu-id="f459f-138">Dynamics 365 Customer Insights による Experian へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="f459f-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f459f-139">Microsoft ではこのようなデータをお客様の指示により転送しますが、Experian がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="f459f-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f459f-140">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f459f-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f459f-141">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエンリッチメントはいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="f459f-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
