---
title: Customer Insights のデータを Mailchimp にエクスポートする
description: Mailchimp への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124233"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="7727e-103">セグメントを Mailchimp にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7727e-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="7727e-104">統合顧客プロファイルのセグメントを Mailchimp にエクスポートして、ニュースレターと電子メール キャンペーンを作成します。</span><span class="sxs-lookup"><span data-stu-id="7727e-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="7727e-105">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="7727e-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="7727e-106">[Mailchimp アカウント](https://mailchimp.com/) と対応する管理者資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="7727e-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7727e-107">Mailchimp に既存のオーディエンスと対応する ID があります。</span><span class="sxs-lookup"><span data-stu-id="7727e-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="7727e-108">詳細については、[Mailchimp オーディエンス](https://mailchimp.com/help/create-audience/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7727e-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="7727e-109">[セグメントを構成](segments.md) しました</span><span class="sxs-lookup"><span data-stu-id="7727e-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="7727e-110">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7727e-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7727e-111">既知の制限</span><span class="sxs-lookup"><span data-stu-id="7727e-111">Known limitations</span></span>

- <span data-ttu-id="7727e-112">Mailchimp へのエクスポートごとに 100 万プロファイルまで。</span><span class="sxs-lookup"><span data-stu-id="7727e-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="7727e-113">Mailchimp へのエクスポートはセグメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="7727e-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="7727e-114">100 万件のプロファイルを持つセグメントのエクスポートには、最大 3 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="7727e-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="7727e-115">Mailchimp にエクスポートできるプロファイルの数は、Mailchimp との契約に依存し、制限されています。</span><span class="sxs-lookup"><span data-stu-id="7727e-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="7727e-116">Mailchimp への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="7727e-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="7727e-117">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="7727e-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7727e-118">**つながりの追加** を選択し、**Autopilot** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="7727e-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="7727e-119">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="7727e-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7727e-120">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="7727e-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7727e-121">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7727e-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7727e-122">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7727e-122">Choose who can use this connection.</span></span> <span data-ttu-id="7727e-123">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="7727e-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7727e-124">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7727e-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7727e-125">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="7727e-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7727e-126">**接続** を選択して、Mailchimp への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="7727e-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="7727e-127">**Mailchimp による認証** を選択し、Mailchimp の認証情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="7727e-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="7727e-128">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="7727e-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7727e-129">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="7727e-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="7727e-130">コネクタの構成</span><span class="sxs-lookup"><span data-stu-id="7727e-130">Configure the connector</span></span>

<span data-ttu-id="7727e-131">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7727e-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7727e-132">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7727e-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7727e-133">**データ**> **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="7727e-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="7727e-134">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7727e-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7727e-135">**エクスポートの接続** フィールドで、Mailchimp セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="7727e-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="7727e-136">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="7727e-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7727e-137">**[Mailchimp 対象者 ID](https://mailchimp.com/help/find-audience-id/)** を入力します</span><span class="sxs-lookup"><span data-stu-id="7727e-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="7727e-138">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="7727e-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="7727e-139">オプションで、**名** と **姓** をエクスポートし、パーソナライズされたメールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7727e-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="7727e-140">**属性の追加** を選択し、これらのフィールドをマップします。</span><span class="sxs-lookup"><span data-stu-id="7727e-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="7727e-141">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="7727e-141">Select the segments you want to export.</span></span> <span data-ttu-id="7727e-142">合計で最大 100 万の顧客プロファイルを Mailchimp にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="7727e-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="7727e-143">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7727e-143">Select **Save**.</span></span>

<span data-ttu-id="7727e-144">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="7727e-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7727e-145">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="7727e-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7727e-146">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="7727e-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7727e-147">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="7727e-147">Data privacy and compliance</span></span>

<span data-ttu-id="7727e-148">Dynamics 365 Customer Insights による Mailchimp へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="7727e-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7727e-149">Microsoft ではこのようなデータをお客様の指示により転送しますが、Mailchimp がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="7727e-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7727e-150">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7727e-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7727e-151">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="7727e-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
