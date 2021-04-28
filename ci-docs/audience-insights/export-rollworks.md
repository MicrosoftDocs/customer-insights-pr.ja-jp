---
title: Customer Insights データを RollWorks にエクスポート
description: RollWorks への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760568"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="7c9f1-103">セグメント リストを RollWorks にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7c9f1-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="7c9f1-104">統合顧客プロファイルのセグメントを RollWorks にエクスポートし、広告に使用します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="7c9f1-105">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="7c9f1-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="7c9f1-106">[RollWorks アカウント](https://www.rollworks.com/) と対応する管理者資格情報がある。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7c9f1-107">対象者に関するインサイトで [セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="7c9f1-108">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7c9f1-109">既知の制限</span><span class="sxs-lookup"><span data-stu-id="7c9f1-109">Known limitations</span></span>

- <span data-ttu-id="7c9f1-110">RollWorks には、1 回のエクスポートで 250'000 プロファイルまでエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="7c9f1-111">プロファイルが 100 未満のセグメントを RollWorks にエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="7c9f1-112">RollWorks へのエクスポートはセグメントに限定されています。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="7c9f1-113">最大 250'000 件のプロファイルを RollWorks にエクスポートすると、完了するまでに最大 10 分かかります。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="7c9f1-114">RollWorks にエクスポートできるプロファイルの数は、RollWorks との契約によって異なり、制限されます。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="7c9f1-115">RollWorks への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="7c9f1-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="7c9f1-116">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7c9f1-117">**つながりの追加** を選択し、**RollWorks** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="7c9f1-118">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7c9f1-119">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7c9f1-120">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7c9f1-121">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-121">Choose who can use this connection.</span></span> <span data-ttu-id="7c9f1-122">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7c9f1-123">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7c9f1-124">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7c9f1-125">**接続** を選択して、RollWorks への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="7c9f1-126">**RollWorks による認証** を選択して、RollWorks の管理者資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="7c9f1-127">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7c9f1-128">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="7c9f1-129">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="7c9f1-129">Configure an export</span></span>

<span data-ttu-id="7c9f1-130">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7c9f1-131">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7c9f1-132">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7c9f1-133">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7c9f1-134">**エクスポートの接続** フィールドで、RollWorks セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="7c9f1-135">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7c9f1-136">**RollWorks 広告者 ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles) を入力します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="7c9f1-137">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7c9f1-138">セグメントを RollWorks にエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="7c9f1-139">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-139">Select the segments you want to export.</span></span> <span data-ttu-id="7c9f1-140">メンバー数が 100 以上のセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="7c9f1-141">小さいセグメントをエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-141">You can't export smaller segments.</span></span> <span data-ttu-id="7c9f1-142">さらに、エクスポートするセグメントの最大サイズは、エクスポートごとに 250'000 メンバーです。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="7c9f1-143">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-143">Select **Save**.</span></span>

<span data-ttu-id="7c9f1-144">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7c9f1-145">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7c9f1-146">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7c9f1-147">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="7c9f1-147">Data privacy and compliance</span></span>

<span data-ttu-id="7c9f1-148">Dynamics 365 Customer Insights による RollWorks へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンスの境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可することになります。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7c9f1-149">Microsoft ではこのようなデータをお客様の指示により転送しますが、RollWorks がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7c9f1-150">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="7c9f1-151">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="7c9f1-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
