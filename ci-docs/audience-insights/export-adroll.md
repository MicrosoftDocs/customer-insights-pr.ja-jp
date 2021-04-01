---
title: Customer Insights のデータを AdRollにエクスポート
description: AdRoll への接続を構成する方法について説明します。
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697080"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="3498c-103">AdRoll 用コネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="3498c-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="3498c-104">統合顧客プロファイルのセグメントを AdRoll にエクスポートし、広告に使用します。</span><span class="sxs-lookup"><span data-stu-id="3498c-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="3498c-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="3498c-105">Prerequisites</span></span>

-   <span data-ttu-id="3498c-106">[AdRoll アカウント](https://www.adroll.com/) と対応する管理者資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="3498c-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3498c-107">対象者に関するインサイトで [セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="3498c-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3498c-108">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3498c-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="3498c-109">AdRoll に接続する</span><span class="sxs-lookup"><span data-stu-id="3498c-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="3498c-110">**管理** > **エクスポート先** へと移動します。</span><span class="sxs-lookup"><span data-stu-id="3498c-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3498c-111">**AdRoll** で **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3498c-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="3498c-112">**表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="3498c-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll 接続の構成ペイン。":::

1. <span data-ttu-id="3498c-114">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3498c-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3498c-115">**接続** を選択して、AdRoll への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="3498c-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="3498c-116">**AdRoll による認証** を選択し、AdRoll の管理者資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="3498c-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="3498c-117">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="3498c-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3498c-118">**AdRoll 広告者 ID** [AdRoll 広告](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles) を入力します。</span><span class="sxs-lookup"><span data-stu-id="3498c-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="3498c-119">**次へ** を選択してエクスポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="3498c-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="3498c-120">コネクタの構成</span><span class="sxs-lookup"><span data-stu-id="3498c-120">Configure the connector</span></span>

1. <span data-ttu-id="3498c-121">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="3498c-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="3498c-122">セグメントを AdRoll にエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3498c-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="3498c-123">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="3498c-123">Select the segments you want to export.</span></span> <span data-ttu-id="3498c-124">メンバー数が 100 以上のセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="3498c-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="3498c-125">小さいセグメントをエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3498c-125">You can't export smaller segments.</span></span> <span data-ttu-id="3498c-126">さらに、エクスポートするセグメントの最大サイズは、エクスポートごとに 250'000 メンバーです。</span><span class="sxs-lookup"><span data-stu-id="3498c-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="3498c-127">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3498c-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3498c-128">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="3498c-128">Export the data</span></span>

<span data-ttu-id="3498c-129">[オンデマンドでデータをエクスポート](export-destinations.md) できます。</span><span class="sxs-lookup"><span data-stu-id="3498c-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3498c-130">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="3498c-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3498c-131">既知の制限</span><span class="sxs-lookup"><span data-stu-id="3498c-131">Known limitations</span></span>

- <span data-ttu-id="3498c-132">1 回のエクスポートで 250'000 プロファイルを AdRoll にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="3498c-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="3498c-133">プロファイルが 100 未満のセグメントを AdRoll にエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="3498c-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="3498c-134">AdRoll へのエクスポートはセグメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="3498c-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="3498c-135">最大 250'000 のプロファイルを AdRoll にエクスポートすると、完了するまでに最大 10 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3498c-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="3498c-136">AdRoll にエクスポートできるプロファイルの数は、AdRoll との契約に依存し、制限されています。</span><span class="sxs-lookup"><span data-stu-id="3498c-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3498c-137">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="3498c-137">Data privacy and compliance</span></span>

<span data-ttu-id="3498c-138">Dynamics 365 Customer Insights による AdRoll へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="3498c-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3498c-139">Microsoft ではこのようなデータをお客様の指示により転送しますが、AdRoll がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="3498c-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3498c-140">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3498c-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="3498c-141">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="3498c-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
