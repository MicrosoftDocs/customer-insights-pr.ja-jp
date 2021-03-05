---
title: Customer Insights のデータを Google 広告にエクスポートする
description: Google 広告への接続を構成する方法を説明します。
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268968"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="b4941-103">Google 広告用コネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="b4941-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="b4941-104">統合顧客プロファイルのセグメントを Google 広告のオーディエンス リストにエクスポートし、それらを使用して Google 検索、Gmail、YouTube、Google ディスプレイ ネットワークに広告を掲載します。</span><span class="sxs-lookup"><span data-stu-id="b4941-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b4941-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="b4941-105">Prerequisites</span></span>

-   <span data-ttu-id="b4941-106">[Google 広告アカウント](https://ads.google.com/) と対応する管理者資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="b4941-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b4941-107">Google 広告には既存のオーディエンスと対応する ID があります。</span><span class="sxs-lookup"><span data-stu-id="b4941-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="b4941-108">詳細については、[Google 広告のオーディエンス](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4941-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="b4941-109">[セグメントを構成](segments.md) しました</span><span class="sxs-lookup"><span data-stu-id="b4941-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="b4941-110">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレス、名、姓を表示するフィールドが含まれています</span><span class="sxs-lookup"><span data-stu-id="b4941-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="b4941-111">Google Ads に接続する</span><span class="sxs-lookup"><span data-stu-id="b4941-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="b4941-112">**管理** > **エクスポート先** へと移動します。</span><span class="sxs-lookup"><span data-stu-id="b4941-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b4941-113">**Google 広告** で **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4941-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="b4941-114">**表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="b4941-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b4941-115">**[Google 広告の顧客 ID](https://support.google.com/google-ads/answer/1704344)** を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4941-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="b4941-116">**[Google 広告で承認された開発者トークン](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4941-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="b4941-117">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b4941-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b4941-118">**[Google 広告オーディエンス ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** を入力して、**接続** を選択し、Google 広告への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="b4941-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="b4941-119">**Google 広告による認証** を選択し、Google 広告の認証情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4941-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="b4941-120">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4941-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Google 広告 接続のスクリーンショットをエクスポートする":::

1. <span data-ttu-id="b4941-122">**次へ** を選択してエクスポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="b4941-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b4941-123">コネクタの構成</span><span class="sxs-lookup"><span data-stu-id="b4941-123">Configure the connector</span></span>

1. <span data-ttu-id="b4941-124">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4941-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b4941-125">**名** フィールドと **姓** フィールドに同じ手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b4941-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="b4941-126">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4941-126">Select the segments you want to export.</span></span> <span data-ttu-id="b4941-127">合計で最大 100 万の顧客プロファイルを Google 広告にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="b4941-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="b4941-128">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4941-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b4941-129">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b4941-129">Export the data</span></span>

<span data-ttu-id="b4941-130">[オンデマンドでデータをエクスポート](export-destinations.md) できます。</span><span class="sxs-lookup"><span data-stu-id="b4941-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b4941-131">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="b4941-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b4941-132">Google 広告では、セグメントが [Google 広告のオーディエンス](https://support.google.com/google-ads/answer/7558048?hl=en/) の下に表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b4941-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b4941-133">既知の制限</span><span class="sxs-lookup"><span data-stu-id="b4941-133">Known limitations</span></span>

- <span data-ttu-id="b4941-134">Google 広告 へのエクスポートごとに 100 万プロファイルまで。</span><span class="sxs-lookup"><span data-stu-id="b4941-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="b4941-135">Google 広告へのエクスポートはセグメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="b4941-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="b4941-136">プロバイダー側の制限により、合計 100 万のプロファイルを持つセグメントのエクスポートには、最大 5 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b4941-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="b4941-137">Google 広告でのマッチングには、最大 48 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b4941-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b4941-138">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="b4941-138">Data privacy and compliance</span></span>

<span data-ttu-id="b4941-139">Dynamics 365 Customer Insights による Google 広告へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="b4941-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b4941-140">Microsoft ではこのようなデータをお客様の指示により転送しますが、Google 広告がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="b4941-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b4941-141">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4941-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b4941-142">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="b4941-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]