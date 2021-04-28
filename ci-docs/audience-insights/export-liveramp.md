---
title: LiveRamp コネクタ
description: LiveRamp への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760333"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="13fea-103">セグメントを LiveRamp&reg; にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="13fea-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="13fea-104">LiveRamp でデータを有効にし、デジタル、ソーシャル、およびテレビなど 500 以上のプラットフォームに接続します。</span><span class="sxs-lookup"><span data-stu-id="13fea-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="13fea-105">LiveRamp でデータを操作して、広告キャンペーンをターゲット設定、非表示、パーソナライズします。</span><span class="sxs-lookup"><span data-stu-id="13fea-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="13fea-106">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="13fea-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="13fea-107">このコネクタを使用するには、LiveRamp サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="13fea-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="13fea-108">サブスクリプションを取得するには、直接 [LiveRamp に連絡](https://liveramp.com/contact/) します。</span><span class="sxs-lookup"><span data-stu-id="13fea-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="13fea-109">[LiveRamp オンボードについて](https://liveramp.com/our-platform/data-onboarding/)。</span><span class="sxs-lookup"><span data-stu-id="13fea-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="13fea-110">LiveRamp への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="13fea-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="13fea-111">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="13fea-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="13fea-112">**つながりの追加** を選択し、**LiveRamp** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="13fea-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="13fea-113">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="13fea-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="13fea-114">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="13fea-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="13fea-115">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="13fea-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="13fea-116">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="13fea-116">Choose who can use this connection.</span></span> <span data-ttu-id="13fea-117">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="13fea-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="13fea-118">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13fea-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="13fea-119">LiveRamp Secure FTP (SFTP) アカウント の **ユーザー名** と **パスワード** を入力します。</span><span class="sxs-lookup"><span data-stu-id="13fea-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="13fea-120">これらの資格情報は、LiveRamp オンボードの資格情報とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="13fea-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="13fea-121">**検証** を選択して、LiveRamp への接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="13fea-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="13fea-122">検証に成功したら、**同意する** チェックボックスを選択して、**データのプライバシーとコンプライアンス** に同意します。</span><span class="sxs-lookup"><span data-stu-id="13fea-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="13fea-123">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="13fea-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="13fea-124">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="13fea-124">Configure an export</span></span>

<span data-ttu-id="13fea-125">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="13fea-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="13fea-126">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13fea-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="13fea-127">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="13fea-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="13fea-128">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="13fea-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="13fea-129">**エクスポートの接続** フィールドで、LiveRamp セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="13fea-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="13fea-130">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="13fea-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="13fea-131">**キー識別子の選択** フィールドで、**メール**、**名前と住所**、または **電話** を選択して、ID 解決のために LiveRamp に送信します。</span><span class="sxs-lookup"><span data-stu-id="13fea-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="13fea-132">![属性マッピング付きの LiveRamp コネクタ](media/export-liveramp-segments.png "属性マッピング付きの LiveRamp コネクタ")</span><span class="sxs-lookup"><span data-stu-id="13fea-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="13fea-133">選択したキー識別子に対応する統合顧客エンティティの対応する属性をマッピングします。</span><span class="sxs-lookup"><span data-stu-id="13fea-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="13fea-134">**属性の追加** を選択し、送信する属性をさらに LiveRamp にマップします。</span><span class="sxs-lookup"><span data-stu-id="13fea-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="13fea-135">より多くのキー識別子属性を LiveRamp に送信すると、一致率が高くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="13fea-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="13fea-136">LiveRamp にエクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="13fea-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="13fea-137">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="13fea-137">Select **Save**.</span></span>

<span data-ttu-id="13fea-138">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="13fea-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="13fea-139">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="13fea-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="13fea-140">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="13fea-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="13fea-141">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="13fea-141">Data privacy and compliance</span></span>

<span data-ttu-id="13fea-142">Dynamics 365 Customer Insights による Liveramp へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="13fea-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="13fea-143">Microsoft ではこのようなデータをお客様の指示により転送しますが、LiveRamp がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="13fea-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="13fea-144">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13fea-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="13fea-145">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="13fea-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
