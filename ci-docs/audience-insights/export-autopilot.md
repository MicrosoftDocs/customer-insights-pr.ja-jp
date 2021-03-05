---
title: Customer Insights のデータを Autopilot にエクスポートする
description: Autopilot への接続を構成する方法を説明します。
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269244"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="18429-103">Autopilot 用コネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="18429-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="18429-104">統合された顧客プロファイルのセグメントを Autopilot にエクスポートし、Autopilot での E メール マーケティングに使用します。</span><span class="sxs-lookup"><span data-stu-id="18429-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="18429-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="18429-105">Prerequisites</span></span>

-   <span data-ttu-id="18429-106">[Autopilot 広告アカウント](https://www.autopilothq.com/) と対応する管理者資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="18429-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="18429-107">対象者に関するインサイトで [セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="18429-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="18429-108">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="18429-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="18429-109">Autopilot に接続する</span><span class="sxs-lookup"><span data-stu-id="18429-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="18429-110">**管理** > **エクスポート先** へと移動します。</span><span class="sxs-lookup"><span data-stu-id="18429-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="18429-111">**Autopilot** で **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="18429-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="18429-112">**表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="18429-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Autopilot 接続の構成ペイン。":::

1. <span data-ttu-id="18429-114">**Autopilot API キー** [自動操縦 API キー](https://autopilot.docs.apiary.io/#)を入力します。</span><span class="sxs-lookup"><span data-stu-id="18429-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="18429-115">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="18429-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="18429-116">**接続** を選択して、Autopilot への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="18429-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="18429-117">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="18429-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="18429-118">**次へ** を選択してエクスポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="18429-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="18429-119">コネクタの構成</span><span class="sxs-lookup"><span data-stu-id="18429-119">Configure the connector</span></span>

1. <span data-ttu-id="18429-120">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="18429-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="18429-121">**名**、**姓** など、他の任意フィールドに同じ手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="18429-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="18429-122">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="18429-122">Select the segments you want to export.</span></span> <span data-ttu-id="18429-123">Autopilot に対しては **合計で 10 万件を超える顧客プロファイルは、エクスポートしないことをお勧めします**。</span><span class="sxs-lookup"><span data-stu-id="18429-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="18429-124">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="18429-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="18429-125">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="18429-125">Export the data</span></span>

<span data-ttu-id="18429-126">[オンデマンドでデータをエクスポート](export-destinations.md) できます。</span><span class="sxs-lookup"><span data-stu-id="18429-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="18429-127">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="18429-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="18429-128">既知の制限</span><span class="sxs-lookup"><span data-stu-id="18429-128">Known limitations</span></span>

- <span data-ttu-id="18429-129">合計で最大 10 万の顧客プロファイルを Autopilot にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="18429-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="18429-130">Autopilot へのエクスポートはセグメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="18429-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="18429-131">最大 10 万件のプロファイルを Autopilot にエクスポートすると、完了するまでに最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="18429-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="18429-132">Autopilot にエクスポートできるプロファイルの数は、Autopilot との契約に依存し、制限されています。</span><span class="sxs-lookup"><span data-stu-id="18429-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="18429-133">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="18429-133">Data privacy and compliance</span></span>

<span data-ttu-id="18429-134">Dynamics 365 Customer Insights による Autopilot へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="18429-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="18429-135">Microsoft ではこのようなデータをお客様の指示により転送しますが、Autopilot がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="18429-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="18429-136">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18429-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="18429-137">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="18429-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]