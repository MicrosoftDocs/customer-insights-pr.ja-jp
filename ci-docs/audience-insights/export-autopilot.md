---
title: Customer Insights のデータを Autopilot にエクスポートする
description: Autopilot への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760149"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="eb6ea-103">セグメントを AutoPilot にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="eb6ea-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="eb6ea-104">統合された顧客プロファイルのセグメントを Autopilot にエクスポートし、Autopilot での E メール マーケティングに使用します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="eb6ea-105">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="eb6ea-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="eb6ea-106">[Autopilot 広告アカウント](https://www.autopilothq.com/) と対応する管理者資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="eb6ea-107">対象者に関するインサイトで [セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="eb6ea-108">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="eb6ea-109">既知の制限</span><span class="sxs-lookup"><span data-stu-id="eb6ea-109">Known limitations</span></span>

- <span data-ttu-id="eb6ea-110">合計で最大 10 万の顧客プロファイルを Autopilot にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="eb6ea-111">Autopilot へのエクスポートはセグメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="eb6ea-112">最大 10 万件のプロファイルを Autopilot にエクスポートすると、完了するまでに最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="eb6ea-113">Autopilot にエクスポートできるプロファイルの数は、Autopilot との契約に依存し、制限されています。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="eb6ea-114">Autopilot への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="eb6ea-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="eb6ea-115">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="eb6ea-116">**つながりの追加** を選択し、**Autopilot** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="eb6ea-117">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="eb6ea-118">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="eb6ea-119">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="eb6ea-120">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-120">Choose who can use this connection.</span></span> <span data-ttu-id="eb6ea-121">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="eb6ea-122">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="eb6ea-123">[Autopilot API キー](https://autopilot.docs.apiary.io/#) を入力します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="eb6ea-124">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="eb6ea-125">**接続** を選択して、Autopilot への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="eb6ea-126">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="eb6ea-127">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="eb6ea-128">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="eb6ea-128">Configure an export</span></span>

<span data-ttu-id="eb6ea-129">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="eb6ea-130">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="eb6ea-131">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="eb6ea-132">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="eb6ea-133">**エクスポートの接続** フィールドで、Autopilot セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="eb6ea-134">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="eb6ea-135">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="eb6ea-136">**名**、**姓** など、他の任意フィールドに同じ手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="eb6ea-137">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-137">Select the segments you want to export.</span></span> <span data-ttu-id="eb6ea-138">Autopilot に対しては **合計で 10 万件を超える顧客プロファイルは、エクスポートしないことをお勧めします**。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="eb6ea-139">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-139">Select **Save**.</span></span>

<span data-ttu-id="eb6ea-140">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="eb6ea-141">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="eb6ea-142">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="eb6ea-143">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="eb6ea-143">Data privacy and compliance</span></span>

<span data-ttu-id="eb6ea-144">Dynamics 365 Customer Insights による Autopilot へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="eb6ea-145">Microsoft ではこのようなデータをお客様の指示により転送しますが、Autopilot がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="eb6ea-146">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="eb6ea-147">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="eb6ea-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
