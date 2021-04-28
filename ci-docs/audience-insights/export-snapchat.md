---
title: Customer Insights データを Snapchat にエクスポート
description: Snapchat への接続とエクスポートを構成する方法を説明します。
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760565"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="7422b-103">セグメント リストを Snapchat にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7422b-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="7422b-104">統合顧客プロファイルのセグメントを Snapchat にエクスポートし、広告に使用します。</span><span class="sxs-lookup"><span data-stu-id="7422b-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="7422b-105">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="7422b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="7422b-106">[Snapchat ビジネス アカウント](https://business.snapchat.com/)、[Snapchat Ads アカウント](https://ads.snapchat.com/)、および対応する管理者資格情報がある。</span><span class="sxs-lookup"><span data-stu-id="7422b-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7422b-107">対象者に関するインサイトで [セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="7422b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="7422b-108">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7422b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7422b-109">既知の制限</span><span class="sxs-lookup"><span data-stu-id="7422b-109">Known limitations</span></span>

- <span data-ttu-id="7422b-110">Snapchat へのエクスポートはセグメントに限定されています。</span><span class="sxs-lookup"><span data-stu-id="7422b-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="7422b-111">最大 100 万件のプロファイルを Snapchat にエクスポートすると、完了するまでに最大 15 分かかります。</span><span class="sxs-lookup"><span data-stu-id="7422b-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="7422b-112">Snapchat への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="7422b-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="7422b-113">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="7422b-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7422b-114">**つながりの追加** を選択し、**Snapchat** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="7422b-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="7422b-115">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="7422b-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7422b-116">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="7422b-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7422b-117">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7422b-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7422b-118">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7422b-118">Choose who can use this connection.</span></span> <span data-ttu-id="7422b-119">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="7422b-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7422b-120">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7422b-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7422b-121">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="7422b-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7422b-122">**接続** を選択して、Snapchat への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="7422b-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="7422b-123">**Snapchat による認証** を選択して、Snapchat の管理者資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="7422b-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="7422b-124">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="7422b-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7422b-125">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="7422b-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="7422b-126">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="7422b-126">Configure an export</span></span>

<span data-ttu-id="7422b-127">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7422b-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7422b-128">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7422b-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7422b-129">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="7422b-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7422b-130">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7422b-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7422b-131">**エクスポートの接続** フィールドで、Snapchat セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="7422b-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="7422b-132">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="7422b-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7422b-133">[**Snapchat 対象者 ID**](https://businesshelp.snapchat.com/s/article/custom-audiences) を入力します。</span><span class="sxs-lookup"><span data-stu-id="7422b-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="7422b-134">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="7422b-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7422b-135">セグメントを Snapchat にエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7422b-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="7422b-136">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="7422b-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="7422b-137">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7422b-137">Select **Save**.</span></span>

<span data-ttu-id="7422b-138">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="7422b-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7422b-139">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="7422b-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7422b-140">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="7422b-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7422b-141">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="7422b-141">Data privacy and compliance</span></span>

<span data-ttu-id="7422b-142">Dynamics 365 Customer Insights による Snapchat へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンスの境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可することになります。</span><span class="sxs-lookup"><span data-stu-id="7422b-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7422b-143">Microsoft ではこのようなデータをお客様の指示により転送しますが、Snapchat がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="7422b-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7422b-144">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7422b-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="7422b-145">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="7422b-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
