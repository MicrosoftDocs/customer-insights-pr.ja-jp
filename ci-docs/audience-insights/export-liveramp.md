---
title: LiveRamp コネクタ
description: データを LiveRamp にエクスポートする方法について説明します。
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597563"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="50ac3-103">LiveRamp&reg; コネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="50ac3-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="50ac3-104">LiveRampでデータをアクティブ化して、デジタル、ソーシャル、テレビのエコシステム全体で 500 を超えるプラットフォームに接続します。</span><span class="sxs-lookup"><span data-stu-id="50ac3-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="50ac3-105">LiveRamp でデータを操作して、広告キャンペーンをターゲット設定、非表示、パーソナライズします。</span><span class="sxs-lookup"><span data-stu-id="50ac3-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="50ac3-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="50ac3-106">Prerequisites</span></span>

- <span data-ttu-id="50ac3-107">このコネクタを使用するには、LiveRamp サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="50ac3-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="50ac3-108">サブスクリプションを取得するには、直接 [LiveRamp に連絡](https://liveramp.com/contact/) します。</span><span class="sxs-lookup"><span data-stu-id="50ac3-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="50ac3-109">[LiveRamp オンボードについて](https://liveramp.com/our-platform/data-onboarding/)。</span><span class="sxs-lookup"><span data-stu-id="50ac3-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="50ac3-110">LiveRamp への接続</span><span class="sxs-lookup"><span data-stu-id="50ac3-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="50ac3-111">対象者に関するインサイトで、**管理** > **エクスポート先** に移動します。</span><span class="sxs-lookup"><span data-stu-id="50ac3-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="50ac3-112">**LiveRamp** タイルで、**設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="50ac3-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="50ac3-113">出力先となる **表示名称** フィールドにはわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="50ac3-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="50ac3-114">LiveRamp Secure FTP (SFTP) アカウント の **ユーザー名** と **パスワード** を入力します。</span><span class="sxs-lookup"><span data-stu-id="50ac3-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="50ac3-115">これらの資格情報は、LiveRamp オンボードの資格情報とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="50ac3-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="50ac3-116">**検証** を選択して、LiveRamp への接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="50ac3-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="50ac3-117">検証に成功したら、**同意する** チェックボックスを選択して、**データのプライバシーとコンプライアンス** に同意します。</span><span class="sxs-lookup"><span data-stu-id="50ac3-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="50ac3-118">**次へ** を選択して、LiveRamp コネクタを設定します。</span><span class="sxs-lookup"><span data-stu-id="50ac3-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="50ac3-119">コネクタの構成</span><span class="sxs-lookup"><span data-stu-id="50ac3-119">Configure the connector</span></span>

1. <span data-ttu-id="50ac3-120">**キー識別子の選択** フィールドで、**メール**、**名前と住所**、または **電話** を選択して、ID 解決のために LiveRamp に送信します。</span><span class="sxs-lookup"><span data-stu-id="50ac3-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="50ac3-121">選択したキー識別子に対応する統合顧客エンティティの対応する属性をマッピングします。</span><span class="sxs-lookup"><span data-stu-id="50ac3-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="50ac3-122">**属性を追加** を選択して、LiveRamp に送信する追加の属性をマップします。</span><span class="sxs-lookup"><span data-stu-id="50ac3-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="50ac3-123">より多くのキー識別子属性を LiveRamp に送信すると、一致率が高くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="50ac3-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="50ac3-124">LiveRamp にエクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="50ac3-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="50ac3-125">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="50ac3-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="50ac3-126">![属性マッピング付きの LiveRamp コネクタ](media/export-liveramp-segments.png "属性マッピング付きの LiveRamp コネクタ")</span><span class="sxs-lookup"><span data-stu-id="50ac3-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="50ac3-127">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="50ac3-127">Export the data</span></span>

<span data-ttu-id="50ac3-128">エクスポートのすべての前提条件が完了すると、まもなくエクスポートが開始されます。</span><span class="sxs-lookup"><span data-stu-id="50ac3-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="50ac3-129">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="50ac3-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="50ac3-130">エクスポートが正常に完了したら、LiveRamp オンボードにサインインして、データをアクティブ化して配布できます。</span><span class="sxs-lookup"><span data-stu-id="50ac3-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="50ac3-131">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="50ac3-131">Data privacy and compliance</span></span>

<span data-ttu-id="50ac3-132">Dynamics 365 Customer Insights による Liveramp へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="50ac3-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="50ac3-133">Microsoft ではこのようなデータをお客様の指示により転送しますが、LiveRamp がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="50ac3-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="50ac3-134">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50ac3-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="50ac3-135">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="50ac3-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]