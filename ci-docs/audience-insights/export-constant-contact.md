---
title: Customer Insights データを Constant Contact にエクスポート
description: Constant Contact への接続とエクスポートを構成する方法を説明します。
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760566"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="8bd9d-103">セグメント リストを Constant Contact にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="8bd9d-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="8bd9d-104">統合顧客プロファイルのセグメントを Constant Contact にエクスポートし、マーケティング活動に使用します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="8bd9d-105">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="8bd9d-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="8bd9d-106">[Constant Contact アカウント](https://www.constantcontact.com/account-home) と対応する管理者資格情報がある。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8bd9d-107">対象者に関するインサイトで [セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8bd9d-108">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8bd9d-109">既知の制限</span><span class="sxs-lookup"><span data-stu-id="8bd9d-109">Known limitations</span></span>

- <span data-ttu-id="8bd9d-110">Constant Contact には、1 回のエクスポートにつき 100 万プロファイルまでエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="8bd9d-111">Constant Contact へのエクスポートはセグメントに限定されています。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="8bd9d-112">最大 100 万のプロファイルを Constant Contact にエクスポートすると、完了するまでに最大 1 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="8bd9d-113">Constant Contact にエクスポートできるプロファイルの数は、Constant Contact との契約によって異なり、制限されます。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="8bd9d-114">Constant Contact への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="8bd9d-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="8bd9d-115">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8bd9d-116">**つながりの追加** を選択し、**Constant Contact** を選択して接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="8bd9d-117">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8bd9d-118">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8bd9d-119">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8bd9d-120">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-120">Choose who can use this connection.</span></span> <span data-ttu-id="8bd9d-121">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8bd9d-122">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8bd9d-123">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8bd9d-124">**接続** を選択して、Constant Contact への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="8bd9d-125">**AdRoll による認証** を選択して、Constant Contact の管理者資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="8bd9d-126">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8bd9d-127">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8bd9d-128">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="8bd9d-128">Configure an export</span></span>

<span data-ttu-id="8bd9d-129">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8bd9d-130">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8bd9d-131">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8bd9d-132">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8bd9d-133">**エクスポートの接続** フィールドで、Constant Contact セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="8bd9d-134">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8bd9d-135">[**Constant Contact リスト ID**](https://app.constantcontact.com/pages/contacts/ui#lists) を入力します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="8bd9d-136">Constant Contact でリストを開き、URL でリスト ID を検索します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="8bd9d-137">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8bd9d-138">セグメントを Constant Contact にエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="8bd9d-139">オプションで、名 と 姓 を追加フィールドとしてエクスポートし、よりパーソナライズされた電子メールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="8bd9d-140">**属性の追加** を選択し、これらのフィールドをマップします。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="8bd9d-141">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="8bd9d-142">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-142">Select **Save**.</span></span>

<span data-ttu-id="8bd9d-143">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8bd9d-144">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8bd9d-145">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8bd9d-146">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="8bd9d-146">Data privacy and compliance</span></span>

<span data-ttu-id="8bd9d-147">Dynamics 365 Customer Insights による Constant Contact へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンスの境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可することになります。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8bd9d-148">Microsoft ではこのようなデータをお客様の指示により転送しますが、Constant Contact がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8bd9d-149">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="8bd9d-150">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
