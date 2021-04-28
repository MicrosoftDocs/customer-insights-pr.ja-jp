---
title: Customer Insights のデータを Google 広告にエクスポートする
description: Google Ads への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759699"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="8ece7-103">セグメントを Google Ads にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="8ece7-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="8ece7-104">統合顧客プロファイルのセグメントを Google 広告のオーディエンス リストにエクスポートし、それらを使用して Google 検索、Gmail、YouTube、Google ディスプレイ ネットワークに広告を掲載します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="8ece7-105">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="8ece7-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="8ece7-106">[Google 広告アカウント](https://ads.google.com/) と対応する管理者資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="8ece7-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8ece7-107">[承認済みの Google Ads 開発者トークン](https://developers.google.com/google-ads/api/docs/first-call/dev-token) がある</span><span class="sxs-lookup"><span data-stu-id="8ece7-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="8ece7-108">[顧客一致ポリシー](https://support.google.com/adspolicy/answer/6299717) の要件を満たしている</span><span class="sxs-lookup"><span data-stu-id="8ece7-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="8ece7-109">[リマーケティング リスト サイズ](https://support.google.com/google-ads/answer/7558048) の要件を満たしている</span><span class="sxs-lookup"><span data-stu-id="8ece7-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="8ece7-110">Google 広告には既存のオーディエンスと対応する ID があります。</span><span class="sxs-lookup"><span data-stu-id="8ece7-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="8ece7-111">詳細については、[Google 広告のオーディエンス](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ece7-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="8ece7-112">[セグメントを構成](segments.md) しました</span><span class="sxs-lookup"><span data-stu-id="8ece7-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="8ece7-113">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレス、名、姓を表示するフィールドが含まれています</span><span class="sxs-lookup"><span data-stu-id="8ece7-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8ece7-114">既知の制限</span><span class="sxs-lookup"><span data-stu-id="8ece7-114">Known limitations</span></span>

- <span data-ttu-id="8ece7-115">Google 広告 へのエクスポートごとに 100 万プロファイルまで。</span><span class="sxs-lookup"><span data-stu-id="8ece7-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="8ece7-116">Google 広告へのエクスポートはセグメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="8ece7-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="8ece7-117">プロバイダー側の制限により、合計 100 万のプロファイルを持つセグメントのエクスポートには、最大 5 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ece7-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="8ece7-118">Google 広告でのマッチングには、最大 48 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ece7-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="8ece7-119">Google Ads への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="8ece7-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="8ece7-120">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8ece7-121">**つながりの追加** を選択し、**Google Ads** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="8ece7-122">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="8ece7-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8ece7-123">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8ece7-124">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ece7-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8ece7-125">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-125">Choose who can use this connection.</span></span> <span data-ttu-id="8ece7-126">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="8ece7-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8ece7-127">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ece7-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8ece7-128">**[Google 広告の顧客 ID](https://support.google.com/google-ads/answer/1704344)** を入力します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="8ece7-129">**[Google 広告で承認された開発者トークン](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** を入力します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="8ece7-130">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ece7-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8ece7-131">**Google 広告による認証** を選択し、Google 広告の認証情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="8ece7-132">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8ece7-133">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="8ece7-134">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="8ece7-134">Configure an export</span></span>

<span data-ttu-id="8ece7-135">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8ece7-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8ece7-136">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ece7-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8ece7-137">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8ece7-138">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8ece7-139">**エクスポートの接続** フィールドで、Google Ads セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="8ece7-140">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="8ece7-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8ece7-141">**[Google 広告オーディエンス ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** を入力して、**接続** を選択し、Google 広告への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="8ece7-142">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8ece7-143">**名** フィールドと **姓** フィールドに同じ手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="8ece7-144">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ece7-144">Select the segments you want to export.</span></span> <span data-ttu-id="8ece7-145">合計で最大 100 万の顧客プロファイルを Google 広告にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="8ece7-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="8ece7-146">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="8ece7-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8ece7-147">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="8ece7-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8ece7-148">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ece7-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8ece7-149">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="8ece7-149">Data privacy and compliance</span></span>

<span data-ttu-id="8ece7-150">Dynamics 365 Customer Insights による Google 広告へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="8ece7-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8ece7-151">Microsoft ではこのようなデータをお客様の指示により転送しますが、Google 広告がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="8ece7-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="8ece7-152">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ece7-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8ece7-153">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="8ece7-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
