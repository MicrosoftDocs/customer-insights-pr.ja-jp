---
title: Customer Insights のデータを SendGrid にエクスポートする
description: SendGrid への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976922"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="db790-103">セグメントを SendGrid にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="db790-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="db790-104">統合された顧客プロファイルのセグメントを SendGrid 取引先担当者リストにエクスポートし、SendGrid でのキャンペーンと E メール マーケティングに使用します。</span><span class="sxs-lookup"><span data-stu-id="db790-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="db790-105">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="db790-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="db790-106">[SendGrid アカウント](https://sendgrid.com/) と対応する管理者資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="db790-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="db790-107">SendGrid に既存取引先担当者リストと対応する ID があります。</span><span class="sxs-lookup"><span data-stu-id="db790-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="db790-108">詳細については、[SendGrid - 取引先担当者を管理する](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db790-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="db790-109">対象者に関するインサイトで [セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="db790-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="db790-110">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="db790-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="db790-111">既知の制限</span><span class="sxs-lookup"><span data-stu-id="db790-111">Known limitations</span></span>

- <span data-ttu-id="db790-112">SendGrid に合計で最大 10 万件のプロファイル。</span><span class="sxs-lookup"><span data-stu-id="db790-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="db790-113">SendGrid へのエクスポートはセグメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="db790-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="db790-114">最大 10 万件のプロファイルを SendGrid にエクスポートすると、完了するまでに最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="db790-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="db790-115">SendGrid にエクスポートできるプロファイルの数は、SendGrid との契約に依存し、制限されています。</span><span class="sxs-lookup"><span data-stu-id="db790-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="db790-116">SendGrid への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="db790-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="db790-117">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="db790-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="db790-118">**つながりの追加** を選択し、**SendGrid** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="db790-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="db790-119">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="db790-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="db790-120">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="db790-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="db790-121">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="db790-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="db790-122">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="db790-122">Choose who can use this connection.</span></span> <span data-ttu-id="db790-123">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="db790-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="db790-124">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db790-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="db790-125">**SendGrid API キー** [SendGrid APIキー](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)を入力します。</span><span class="sxs-lookup"><span data-stu-id="db790-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="db790-126">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="db790-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="db790-127">**接続** を選択して、SendGrid への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="db790-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="db790-128">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="db790-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="db790-129">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="db790-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="db790-130">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="db790-130">Configure an export</span></span>

<span data-ttu-id="db790-131">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="db790-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="db790-132">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db790-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="db790-133">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="db790-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="db790-134">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="db790-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="db790-135">**エクスポートの接続** フィールドで、SendGrid セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="db790-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="db790-136">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="db790-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="db790-137">**[SendGrid リスト ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** を入力します。</span><span class="sxs-lookup"><span data-stu-id="db790-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="db790-138">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="db790-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="db790-139">**名**、**姓**、**国/リージョン**、**州**、**市町村**、および **郵便番号** などの、他のオプション フィールドについても同じ手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="db790-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="db790-140">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="db790-140">Select the segments you want to export.</span></span> <span data-ttu-id="db790-141">SendGrid に対しては **合計で 10 万件を超える顧客プロファイルは、エクスポートしないことをお勧めします**。</span><span class="sxs-lookup"><span data-stu-id="db790-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="db790-142">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="db790-142">Select **Save**.</span></span>

<span data-ttu-id="db790-143">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="db790-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="db790-144">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="db790-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="db790-145">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="db790-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="db790-146">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="db790-146">Data privacy and compliance</span></span>

<span data-ttu-id="db790-147">Dynamics 365 Customer Insights による SendGrid へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="db790-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="db790-148">Microsoft ではこのようなデータをお客様の指示により転送しますが、SendGrid がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="db790-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="db790-149">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db790-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="db790-150">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="db790-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]