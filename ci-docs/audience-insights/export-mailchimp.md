---
title: Customer Insights のデータを Mailchimp にエクスポートする
description: Mailchimp への接続を構成する方法を説明します。
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406155"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="1d6be-103">Mailchimp 用コネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="1d6be-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="1d6be-104">統合顧客プロファイルのセグメントを Mailchimp にエクスポートして、ニュースレターと電子メール キャンペーンを作成します。</span><span class="sxs-lookup"><span data-stu-id="1d6be-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1d6be-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="1d6be-105">Prerequisites</span></span>

-   <span data-ttu-id="1d6be-106">[Mailchimp アカウント](https://mailchimp.com/) と対応する管理者資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="1d6be-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1d6be-107">Mailchimp に既存のオーディエンスと対応する ID があります。</span><span class="sxs-lookup"><span data-stu-id="1d6be-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="1d6be-108">詳細については、[Mailchimp オーディエンス](https://mailchimp.com/help/create-audience/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d6be-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="1d6be-109">[セグメントを構成](segments.md) しました</span><span class="sxs-lookup"><span data-stu-id="1d6be-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="1d6be-110">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d6be-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="1d6be-111">Mailchimp に接続する</span><span class="sxs-lookup"><span data-stu-id="1d6be-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="1d6be-112">**管理** > **エクスポート先** へと移動します。</span><span class="sxs-lookup"><span data-stu-id="1d6be-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1d6be-113">**Mailchimp** で **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d6be-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="1d6be-114">**表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="1d6be-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="1d6be-115">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1d6be-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1d6be-116">**[Mailchimp オーディエンス ID](https://mailchimp.com/help/find-audience-id/)** を入力して、**接続** を選択し、Mailchimp への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="1d6be-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="1d6be-117">**Mailchimp による認証** を選択し、Mailchimp の認証情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1d6be-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="1d6be-118">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1d6be-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Mailchimp 接続のスクリーンショットをエクスポートする":::

1. <span data-ttu-id="1d6be-120">**次へ** を選択してエクスポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="1d6be-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="1d6be-121">コネクタの構成</span><span class="sxs-lookup"><span data-stu-id="1d6be-121">Configure the connector</span></span>

1. <span data-ttu-id="1d6be-122">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="1d6be-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="1d6be-123">オプションで、**名** と **姓** を追加フィールドとしてエクスポートし、よりパーソナライズされた電子メールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1d6be-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="1d6be-124">**属性の追加** を選択し、これらのフィールドをマップします。</span><span class="sxs-lookup"><span data-stu-id="1d6be-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="1d6be-125">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="1d6be-125">Select the segments you want to export.</span></span> <span data-ttu-id="1d6be-126">合計で最大 100 万の顧客プロファイルを Mailchimp にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="1d6be-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="フィールドとセグメントを選択して、Mailchimp にエクスポートする":::

1. <span data-ttu-id="1d6be-128">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d6be-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1d6be-129">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="1d6be-129">Export the data</span></span>

<span data-ttu-id="1d6be-130">[オンデマンドでデータをエクスポート](export-destinations.md) できます。</span><span class="sxs-lookup"><span data-stu-id="1d6be-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="1d6be-131">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="1d6be-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1d6be-132">Mailchimp では、セグメントが [Mailchimp オーディエンス](https://mailchimp.com/help/create-audience/) の下に表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1d6be-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1d6be-133">既知の制限</span><span class="sxs-lookup"><span data-stu-id="1d6be-133">Known limitations</span></span>

- <span data-ttu-id="1d6be-134">Mailchimp へのエクスポートごとに 100 万プロファイルまで。</span><span class="sxs-lookup"><span data-stu-id="1d6be-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="1d6be-135">Mailchimp へのエクスポートはセグメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="1d6be-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="1d6be-136">プロバイダー側の制限により、合計 100 万のプロファイルを持つセグメントのエクスポートには最大 3 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1d6be-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="1d6be-137">Mailchimp にエクスポートできるプロファイルの数は、Mailchimp との契約に依存し、制限されています。</span><span class="sxs-lookup"><span data-stu-id="1d6be-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1d6be-138">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="1d6be-138">Data privacy and compliance</span></span>

<span data-ttu-id="1d6be-139">Dynamics 365 Customer Insights による Mailchimp へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="1d6be-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1d6be-140">Microsoft ではこのようなデータをお客様の指示により転送しますが、Mailchimp がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="1d6be-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1d6be-141">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d6be-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1d6be-142">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="1d6be-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
