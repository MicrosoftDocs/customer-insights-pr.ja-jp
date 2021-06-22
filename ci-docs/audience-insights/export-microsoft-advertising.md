---
title: Customer Insights データを Microsoft Advertising にエクスポートする
description: Microsoft Advertising への接続とエクスポートを構成する方法を説明します。
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124510"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="d17ac-103">セグメントを MicrosoftAdvertising にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d17ac-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="d17ac-104">Customer Insights セグメントを Microsoft Advertising にエクスポートして、カスタマー マッチの対象者を作成します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="d17ac-105">これらの対象者を広告キャンペーンに使用します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d17ac-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="d17ac-106">Prerequisites</span></span>

-   <span data-ttu-id="d17ac-107">[Microsoft Advertising アカウント](https://ads.microsoft.com/) と対応する管理者資格情報。</span><span class="sxs-lookup"><span data-stu-id="d17ac-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d17ac-108">カスタマー マッチの使用条件に同意しました。</span><span class="sxs-lookup"><span data-stu-id="d17ac-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="d17ac-109">対象者に関するインサイトの [構成済みセグメント](segments.md)。</span><span class="sxs-lookup"><span data-stu-id="d17ac-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d17ac-110">エクスポートされたセグメントの統合された顧客プロファイルには、メール アドレスのあるフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d17ac-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d17ac-111">既知の制限</span><span class="sxs-lookup"><span data-stu-id="d17ac-111">Known limitations</span></span>

- <span data-ttu-id="d17ac-112">Microsoft Advertising には、エクスポートごとに 50 万プロファイルまでエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="d17ac-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="d17ac-113">Microsoft Advertising へのエクスポートはセグメントに限定されています。</span><span class="sxs-lookup"><span data-stu-id="d17ac-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="d17ac-114">最大 50 万のプロファイルを Microsoft Advertising にエクスポートすると、完了するまでに最大 10 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d17ac-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="d17ac-115">Microsoft Advertising への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="d17ac-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="d17ac-116">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d17ac-117">**つながりの追加** を選択し、**Microsoft Advertising** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="d17ac-118">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="d17ac-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d17ac-119">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d17ac-120">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d17ac-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d17ac-121">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-121">Choose who can use this connection.</span></span> <span data-ttu-id="d17ac-122">既定は管理者です。</span><span class="sxs-lookup"><span data-stu-id="d17ac-122">The default is administrators.</span></span> <span data-ttu-id="d17ac-123">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d17ac-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d17ac-124">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d17ac-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d17ac-125">**接続** を選択して、Microsoft Advertising への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="d17ac-126">**Microsoft Advertising による認証** を選択して、Microsoft Advertising の管理者資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="d17ac-127">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d17ac-128">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d17ac-129">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="d17ac-129">Configure an export</span></span>

<span data-ttu-id="d17ac-130">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d17ac-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d17ac-131">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d17ac-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d17ac-132">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d17ac-133">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d17ac-134">**エクスポートの接続** フィールドで、Microsoft Advertising セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="d17ac-135">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="d17ac-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d17ac-136">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-136">Select the segments to export.</span></span> <span data-ttu-id="d17ac-137">Microsoft Advertising のカスタマー マッチの対象者は、エクスポート用に選択されたセグメントの名前で自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d17ac-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="d17ac-138">各セグメントは、個別のカスタマー マッチの対象者になります。</span><span class="sxs-lookup"><span data-stu-id="d17ac-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="d17ac-139">**Microsoft Advertising の顧客 ID とアカウントID** を入力します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="d17ac-140">顧客 ID (`cid`) とアカウントID (`aid`) は、Microsoft Advertising にサインインしているときに URL のパラメーターで確認できます。</span><span class="sxs-lookup"><span data-stu-id="d17ac-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="d17ac-141">**データ一致** セクションの **メール** フィールドで、顧客のメール アドレスを持つ統合された顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="d17ac-142">セグメントを Microsoft Advertising にエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d17ac-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="d17ac-143">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d17ac-143">Select **Save**.</span></span>

<span data-ttu-id="d17ac-144">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="d17ac-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d17ac-145">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="d17ac-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d17ac-146">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="d17ac-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d17ac-147">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="d17ac-147">Data privacy and compliance</span></span>

<span data-ttu-id="d17ac-148">Dynamics 365 Customer Insights による Microsoft Advertising へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンスの境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可することになります。</span><span class="sxs-lookup"><span data-stu-id="d17ac-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d17ac-149">Microsoft ではこのようなデータをお客様の指示により転送しますが、Microsoft Advertising がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="d17ac-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d17ac-150">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d17ac-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d17ac-151">Dynamics 365 Customer Insights の管理者は、このエクスポート先を、この機能の使用を停止するために、いつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="d17ac-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
