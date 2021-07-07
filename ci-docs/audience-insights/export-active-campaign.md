---
title: Customer Insights データを ActiveCampaign にエクスポートする
description: 接続を構成して、ActiveCampaign にエクスポートする方法を学びます。
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314635"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="b6c15-103">セグメントを ActiveCampaign にエクスポートする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="b6c15-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="b6c15-104">統合された顧客プロファイルのセグメントを ActiveCampaign にエクスポートし、マーケティング活動に使用します。</span><span class="sxs-lookup"><span data-stu-id="b6c15-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b6c15-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="b6c15-105">Prerequisites</span></span>

-   <span data-ttu-id="b6c15-106">[ActiveCampaign アカウント](https://www.activecampaign.com/) および対応する管理者資格情報を所有していること。</span><span class="sxs-lookup"><span data-stu-id="b6c15-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b6c15-107">対象者に関するインサイトで [セグメントを構成](segments.md) したこと。</span><span class="sxs-lookup"><span data-stu-id="b6c15-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b6c15-108">エクスポートされたセグメントの統合された顧客プロファイルには、メール アドレスのあるフィールドが含まれていること。</span><span class="sxs-lookup"><span data-stu-id="b6c15-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b6c15-109">既知の制限</span><span class="sxs-lookup"><span data-stu-id="b6c15-109">Known limitations</span></span>

- <span data-ttu-id="b6c15-110">ActiveCampaign へのエクスポートごとに最大 100 万のプロファイルをエクスポートでき、完了するまでに最大 90 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6c15-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="b6c15-111">ActiveCampaign へのエクスポートはセグメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="b6c15-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="b6c15-112">ActiveCampaign にエクスポートできるプロファイルの数は、ActiveCampaign との契約によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b6c15-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="b6c15-113">ActiveCampaign への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="b6c15-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="b6c15-114">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="b6c15-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b6c15-115">**接続の追加** を選択し、**ActiveCampaign** を選んで、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="b6c15-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="b6c15-116">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="b6c15-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b6c15-117">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="b6c15-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b6c15-118">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b6c15-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b6c15-119">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b6c15-119">Choose who can use this connection.</span></span> <span data-ttu-id="b6c15-120">既定では、管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="b6c15-120">By default, it's only administrators.</span></span> <span data-ttu-id="b6c15-121">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6c15-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b6c15-122">[ActiveCampaign API キーおよび REST エンドポイント ホスト名](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) を入力してください。</span><span class="sxs-lookup"><span data-stu-id="b6c15-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="b6c15-123">REST エンドポイントのホスト名はホスト名のみで、https:// は含まれません。</span><span class="sxs-lookup"><span data-stu-id="b6c15-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="b6c15-124">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b6c15-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b6c15-125">ActiveCampaign への接続を開始するには、**接続** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b6c15-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="b6c15-126">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b6c15-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b6c15-127">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="b6c15-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b6c15-128">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="b6c15-128">Configure an export</span></span>

<span data-ttu-id="b6c15-129">この種類の接続にアクセスできる場合は、エクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b6c15-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="b6c15-130">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6c15-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b6c15-131">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="b6c15-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b6c15-132">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b6c15-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b6c15-133">**エクスポート用の接続** フィールドで、ActiveCampaign セクションから、接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="b6c15-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="b6c15-134">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="b6c15-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b6c15-135">[**ActiveCampaign リスト ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign) を入力します。</span><span class="sxs-lookup"><span data-stu-id="b6c15-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="b6c15-136">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="b6c15-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b6c15-137">ActiveCampaign へは、セグメントをエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6c15-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="b6c15-138">オプションで、姓、名、および電話番号をエクスポートして、よりパーソナライズされた電子メールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b6c15-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="b6c15-139">属性の追加 を選択し、これらのフィールドをマップします。</span><span class="sxs-lookup"><span data-stu-id="b6c15-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="b6c15-140">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b6c15-140">Select **Save**.</span></span>

<span data-ttu-id="b6c15-141">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="b6c15-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b6c15-142">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="b6c15-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b6c15-143">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="b6c15-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b6c15-144">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="b6c15-144">Data privacy and compliance</span></span>

<span data-ttu-id="b6c15-145">Dynamics 365 Customer Insights から ActiveCampaign へのデータ送信を可能にすると、Dynamics 365 Customer Insights のコンプライアンスの範囲を越えて、個人情報などの機密性の高い情報が潜在的に含まれるデータの転送を許可することになります。</span><span class="sxs-lookup"><span data-stu-id="b6c15-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b6c15-146">Microsoft はお客様の指示でそのようなデータを送信することがありますが、ActiveCampaign が関係するプライバシーまたはセキュリティのすべての義務を満たすよう見届ける責任はお客様にあります。</span><span class="sxs-lookup"><span data-stu-id="b6c15-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b6c15-147">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6c15-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="b6c15-148">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="b6c15-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
