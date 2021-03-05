---
title: Customer Insights のデータを SendGrid にエクスポートする
description: SendGrid への接続を構成する方法を説明します。
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268738"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="52ba6-103">SendGrid 用コネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="52ba6-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="52ba6-104">統合された顧客プロファイルのセグメントを SendGrid 取引先担当者リストにエクスポートし、SendGrid でのキャンペーンと E メール マーケティングに使用します。</span><span class="sxs-lookup"><span data-stu-id="52ba6-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="52ba6-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="52ba6-105">Prerequisites</span></span>

-   <span data-ttu-id="52ba6-106">[SendGrid アカウント](https://sendgrid.com/) と対応する管理者資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="52ba6-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="52ba6-107">SendGrid に既存取引先担当者リストと対応する ID があります。</span><span class="sxs-lookup"><span data-stu-id="52ba6-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="52ba6-108">詳細については、[SendGrid - 取引先担当者を管理する](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52ba6-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="52ba6-109">対象者に関するインサイトで [セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="52ba6-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="52ba6-110">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="52ba6-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="52ba6-111">SendGrid へ接続する</span><span class="sxs-lookup"><span data-stu-id="52ba6-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="52ba6-112">**管理** > **エクスポート先** へと移動します。</span><span class="sxs-lookup"><span data-stu-id="52ba6-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="52ba6-113">**SendGrid** で **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="52ba6-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="52ba6-114">**表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="52ba6-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid エクスポート設定ペイン。":::

1. <span data-ttu-id="52ba6-116">**SendGrid API キー** [SendGrid APIキー](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)を入力します。</span><span class="sxs-lookup"><span data-stu-id="52ba6-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="52ba6-117">**[SendGrid リスト ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** を入力します。</span><span class="sxs-lookup"><span data-stu-id="52ba6-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="52ba6-118">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="52ba6-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="52ba6-119">**接続** を選択して、SendGrid への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="52ba6-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="52ba6-120">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="52ba6-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="52ba6-121">**次へ** を選択してエクスポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="52ba6-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="52ba6-122">コネクタの構成</span><span class="sxs-lookup"><span data-stu-id="52ba6-122">Configure the connector</span></span>

1. <span data-ttu-id="52ba6-123">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="52ba6-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="52ba6-124">**名**、**姓**、**国/リージョン**、**州**、**市町村**、および **郵便番号** などの、他のオプション フィールドについても同じ手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="52ba6-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="52ba6-125">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="52ba6-125">Select the segments you want to export.</span></span> <span data-ttu-id="52ba6-126">SendGrid に対しては **合計で 10 万件を超える顧客プロファイルは、エクスポートしないことをお勧めします**。</span><span class="sxs-lookup"><span data-stu-id="52ba6-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="52ba6-127">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="52ba6-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="52ba6-128">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="52ba6-128">Export the data</span></span>

<span data-ttu-id="52ba6-129">[オンデマンドでデータをエクスポート](export-destinations.md) できます。</span><span class="sxs-lookup"><span data-stu-id="52ba6-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="52ba6-130">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="52ba6-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="52ba6-131">既知の制限</span><span class="sxs-lookup"><span data-stu-id="52ba6-131">Known limitations</span></span>

- <span data-ttu-id="52ba6-132">SendGrid に合計で最大 10 万件のプロファイル。</span><span class="sxs-lookup"><span data-stu-id="52ba6-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="52ba6-133">SendGrid へのエクスポートはセグメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="52ba6-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="52ba6-134">最大 10 万件のプロファイルを SendGrid にエクスポートすると、完了するまでに最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="52ba6-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="52ba6-135">SendGrid にエクスポートできるプロファイルの数は、SendGrid との契約に依存し、制限されています。</span><span class="sxs-lookup"><span data-stu-id="52ba6-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="52ba6-136">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="52ba6-136">Data privacy and compliance</span></span>

<span data-ttu-id="52ba6-137">Dynamics 365 Customer Insights による SendGrid へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="52ba6-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="52ba6-138">Microsoft ではこのようなデータをお客様の指示により転送しますが、SendGrid がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="52ba6-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="52ba6-139">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52ba6-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="52ba6-140">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="52ba6-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]