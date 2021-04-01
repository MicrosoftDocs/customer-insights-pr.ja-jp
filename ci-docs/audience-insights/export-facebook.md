---
title: Customer Insights のデータを Facebook 広告マネージャーにエクスポートする
description: Facebook 広告マネージャへの接続の構成方法を説明します。
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596689"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="430bb-103">Facebook 広告マネージャ向けコネクタ (プレビュー版)</span><span class="sxs-lookup"><span data-stu-id="430bb-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="430bb-104">統合された顧客プロファイルのセグメントを Facebook 広告マネージャにエクスポートして Facebook と Instagram でキャンペーンを作成する。</span><span class="sxs-lookup"><span data-stu-id="430bb-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="430bb-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="430bb-105">Prerequisites</span></span>

- <span data-ttu-id="430bb-106">[**Facebook ビジネス アカウント**](https://business.facebook.com/) を含む [**Facebook 広告アカウント**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) が必要です。</span><span class="sxs-lookup"><span data-stu-id="430bb-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="430bb-107">[**Facebook 広告アカウント**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) の管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="430bb-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="430bb-108">Facebook 広告マネージャに接続する</span><span class="sxs-lookup"><span data-stu-id="430bb-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="430bb-109">**管理** > **エクスポート先** へと移動します。</span><span class="sxs-lookup"><span data-stu-id="430bb-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="430bb-110">**Facebook 広告マネージャ** 配下で、**設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="430bb-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="430bb-111">**表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="430bb-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="430bb-112">**Facebook で続ける** を選択して、Facebook 広告アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="430bb-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="430bb-113">Facebook で認証した後、**ads_management** アクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="430bb-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="430bb-114">作業する **Facebook 広告アカウント** を選択します。</span><span class="sxs-lookup"><span data-stu-id="430bb-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="430bb-115">**既存のカスタム対象ユーザー** ドロップダウン リストから選択するか、または **新しいカスタム対象ユーザー** を作成します。</span><span class="sxs-lookup"><span data-stu-id="430bb-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="430bb-116">詳細については、[**Facebook 広告マネージャの対象ユーザー**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="430bb-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="430bb-117">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="430bb-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="430bb-118">**次へ** を選択してエクスポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="430bb-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="430bb-119">コネクタの構成</span><span class="sxs-lookup"><span data-stu-id="430bb-119">Configure the connector</span></span>

1. <span data-ttu-id="430bb-120">**キー識別子のフィールドを選択する** にて、**E メール**、**名前と住所**、または **電話** を選択して、Facebook 広告マネージャに送信します。</span><span class="sxs-lookup"><span data-stu-id="430bb-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="430bb-121">選択したキー識別子に対応する統合顧客エンティティの対応する属性をマッピングします。</span><span class="sxs-lookup"><span data-stu-id="430bb-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="430bb-122">[ヒント] キー識別子に **E メール** を選択すると、一致する可能性が最も高くなります。</span><span class="sxs-lookup"><span data-stu-id="430bb-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="430bb-123">識別子を追加すると、マッチングが向上する場合があります。</span><span class="sxs-lookup"><span data-stu-id="430bb-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="430bb-124">**属性の追加** を選択して、追加の属性をマッピングして、Facebook 広告マネージャに送信します。</span><span class="sxs-lookup"><span data-stu-id="430bb-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="430bb-125">Facebook 広告マネージャは、次のようなわかりやすい名前にマッピングされています : **FN** = **名**、**LN** = **姓**、**FI** = **最初の頭文字**、**PHONE** = **電話**、**GEN** = **性別**、**DOB** = **生年月日**、**ST** = **状態**、**CT** = **市**、**ZIP** = **郵便番号**、**COUNTRY** = **国/地域**</span><span class="sxs-lookup"><span data-stu-id="430bb-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="430bb-126">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="430bb-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="430bb-127">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="430bb-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="430bb-128">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="430bb-128">Export the data</span></span>

<span data-ttu-id="430bb-129">[オンデマンドでデータをエクスポート](export-destinations.md) できます。</span><span class="sxs-lookup"><span data-stu-id="430bb-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="430bb-130">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="430bb-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="430bb-131">既知の制限</span><span class="sxs-lookup"><span data-stu-id="430bb-131">Known limitations</span></span>

- <span data-ttu-id="430bb-132">Facebook 広告マネージャーへのエクスポートごとに最大 1,000 万の顧客プロファイル </span><span class="sxs-lookup"><span data-stu-id="430bb-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="430bb-133">Facebook 広告マネージャーへのエクスポートはセグメントに制限される</span><span class="sxs-lookup"><span data-stu-id="430bb-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="430bb-134">合計 100 万のプロファイルを持つセグメントのエクスポートには、最大 90 分間かかる</span><span class="sxs-lookup"><span data-stu-id="430bb-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="430bb-135">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="430bb-135">Data privacy and compliance</span></span>

<span data-ttu-id="430bb-136">Dynamics 365 Customer Insights による Facebook 広告マネージャーへのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="430bb-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="430bb-137">Microsoft ではこのようなデータをお客様の指示により転送しますが、Facebook 広告がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="430bb-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="430bb-138">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="430bb-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="430bb-139">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="430bb-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]