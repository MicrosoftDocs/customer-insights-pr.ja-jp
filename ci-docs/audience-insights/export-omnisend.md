---
title: Customer Insights データを Omnisend にエクスポート
description: Omnisend への接続とエクスポートを構成する方法を説明します。
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124511"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="0f042-103">セグメントを Omnisend にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="0f042-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="0f042-104">統合された顧客プロファイルのセグメントを Omnisend にエクスポートし、マーケティング活動に使用します。</span><span class="sxs-lookup"><span data-stu-id="0f042-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f042-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="0f042-105">Prerequisites</span></span>

-   <span data-ttu-id="0f042-106">[Omnisend アカウント](https://www.omnisend.com/) と対応する管理者資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="0f042-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0f042-107">対象者に関するインサイトで [セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="0f042-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0f042-108">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0f042-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0f042-109">既知の制限</span><span class="sxs-lookup"><span data-stu-id="0f042-109">Known limitations</span></span>

- <span data-ttu-id="0f042-110">Omnisend には、エクスポートごとに 100 万プロファイルまでエクスポートでき、完了するまでに最大 4 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f042-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="0f042-111">Omnisend へのエクスポートはセグメントに限定されています。</span><span class="sxs-lookup"><span data-stu-id="0f042-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="0f042-112">Omnisend にエクスポートできるプロファイルの数は、Omnisend との契約によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0f042-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="0f042-113">Omnisend への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="0f042-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="0f042-114">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0f042-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0f042-115">**つながりの追加** を選択し、**Omnisend** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="0f042-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="0f042-116">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="0f042-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0f042-117">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="0f042-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0f042-118">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0f042-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0f042-119">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f042-119">Choose who can use this connection.</span></span> <span data-ttu-id="0f042-120">既定では、管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="0f042-120">By default it's only administrators.</span></span> <span data-ttu-id="0f042-121">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f042-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0f042-122">[Omnisend API キー](https://support.omnisend.com/en/articles/1061890-generating-api-key) を入力します。</span><span class="sxs-lookup"><span data-stu-id="0f042-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="0f042-123">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f042-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0f042-124">**接続** を選択して、Omnisend への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="0f042-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="0f042-125">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="0f042-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0f042-126">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="0f042-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0f042-127">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="0f042-127">Configure an export</span></span>

<span data-ttu-id="0f042-128">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0f042-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0f042-129">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f042-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0f042-130">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0f042-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0f042-131">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f042-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0f042-132">**エクスポートの接続** フィールドで、Omnisend セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f042-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="0f042-133">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="0f042-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0f042-134">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f042-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0f042-135">セグメントを Omnisend にエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f042-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="0f042-136">必要に応じて、名、姓、住所、国/地域、都道府県、市区町村、郵便番号をエクスポートし、パーソナライズされたメールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0f042-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="0f042-137">**属性の追加** を選択し、これらのフィールドをマップします。</span><span class="sxs-lookup"><span data-stu-id="0f042-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0f042-138">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f042-138">Select **Save**.</span></span>

<span data-ttu-id="0f042-139">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="0f042-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0f042-140">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="0f042-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0f042-141">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="0f042-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0f042-142">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="0f042-142">Data privacy and compliance</span></span>

<span data-ttu-id="0f042-143">Dynamics 365 Customer Insights による Ommisend へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンスの境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可することになります。</span><span class="sxs-lookup"><span data-stu-id="0f042-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0f042-144">Microsoft ではこのようなデータをお客様の指示により転送しますが、Omnisend がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="0f042-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0f042-145">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f042-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="0f042-146">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="0f042-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
