---
title: Customer Insights データを Campaign Monitor にエクスポート
description: Campaign Monitor への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124187"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="05bce-103">セグメントを Campaign Monitor にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="05bce-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="05bce-104">統合顧客プロファイルのセグメントを Campaign Monitor にエクスポートし、マーケティング活動に使用します。</span><span class="sxs-lookup"><span data-stu-id="05bce-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="05bce-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="05bce-105">Prerequisites</span></span>

-   <span data-ttu-id="05bce-106">[Campaign Monitor アカウント](https://www.campaignmonitor.com/) と対応する管理者資格情報がある。</span><span class="sxs-lookup"><span data-stu-id="05bce-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="05bce-107">対象者に関するインサイトで [セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="05bce-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="05bce-108">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="05bce-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="05bce-109">既知の制限</span><span class="sxs-lookup"><span data-stu-id="05bce-109">Known limitations</span></span>

- <span data-ttu-id="05bce-110">Campaign Monitor には、1 回のエクスポートにつき 100 万プロファイルまでエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="05bce-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="05bce-111">Campaign Monitor へのエクスポートはセグメントに限定されます。</span><span class="sxs-lookup"><span data-stu-id="05bce-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="05bce-112">最大 100 万のプロファイルを Campaign Monitor にエクスポートすると、完了するまでに最大 20 分かかります。</span><span class="sxs-lookup"><span data-stu-id="05bce-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="05bce-113">Campaign Monitor にエクスポートできるプロファイルの数は、Campaign Monitor との契約によって異なり、制限されます。</span><span class="sxs-lookup"><span data-stu-id="05bce-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="05bce-114">Campaign Monitor への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="05bce-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="05bce-115">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="05bce-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="05bce-116">**つながりの追加** を選択し、**Campaign Monitor** を選択して接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="05bce-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="05bce-117">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="05bce-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="05bce-118">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="05bce-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="05bce-119">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="05bce-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="05bce-120">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="05bce-120">Choose who can use this connection.</span></span> <span data-ttu-id="05bce-121">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="05bce-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="05bce-122">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05bce-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="05bce-123">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="05bce-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="05bce-124">**接続** を選択して、Campaign Monitor への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="05bce-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="05bce-125">**Campaign Monitor による認証** を選択して、Campaign Monitor の管理者資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="05bce-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="05bce-126">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="05bce-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="05bce-127">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="05bce-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="05bce-128">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="05bce-128">Configure an export</span></span>

<span data-ttu-id="05bce-129">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="05bce-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="05bce-130">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05bce-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="05bce-131">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="05bce-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="05bce-132">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="05bce-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="05bce-133">**エクスポートの接続** フィールドで、Campaign Monitor セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="05bce-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="05bce-134">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="05bce-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="05bce-135">[**Campaign Monitor リスト ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id) を入力します。</span><span class="sxs-lookup"><span data-stu-id="05bce-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="05bce-136">Campaign Monitor の **アカウント設定** から最初に [API キーを生成](https://www.campaignmonitor.com/api/getting-started/) し、API リスト ID を表示します。</span><span class="sxs-lookup"><span data-stu-id="05bce-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="05bce-137">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="05bce-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="05bce-138">セグメントを Campaign Monitor にエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="05bce-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="05bce-139">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="05bce-139">Select **Save**.</span></span>

<span data-ttu-id="05bce-140">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="05bce-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="05bce-141">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="05bce-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="05bce-142">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="05bce-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="05bce-143">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="05bce-143">Data privacy and compliance</span></span>

<span data-ttu-id="05bce-144">Dynamics 365 Customer Insights による Campaign Monitor へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンスの境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可することになります。</span><span class="sxs-lookup"><span data-stu-id="05bce-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="05bce-145">Microsoft ではこのようなデータをお客様の指示により転送しますが、Campaign Monitor がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="05bce-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="05bce-146">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05bce-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="05bce-147">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="05bce-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
