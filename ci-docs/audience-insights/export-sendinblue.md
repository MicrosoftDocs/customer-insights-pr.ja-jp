---
title: Customer Insights データを Sendinblue にエクスポートする
description: 接続を構成して、Sendinblue にエクスポートする方法を学びます。
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314634"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="e62e8-103">セグメントを Sendinblue にエクスポートする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e62e8-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="e62e8-104">統合された顧客プロファイルのセグメントをエクスポートして、キャンペーンを生成したり、電子メール マーケティングを行ったり、Sendinblue で特定の顧客グループを使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e62e8-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e62e8-105">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="e62e8-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="e62e8-106">[Sendinblue アカウント](https://www.sendinblue.com/) および対応する管理者資格情報を所有していること。</span><span class="sxs-lookup"><span data-stu-id="e62e8-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e62e8-107">Sendinblue には既存のリストと対応する ID があること。</span><span class="sxs-lookup"><span data-stu-id="e62e8-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="e62e8-108">[セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="e62e8-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="e62e8-109">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれていること。</span><span class="sxs-lookup"><span data-stu-id="e62e8-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e62e8-110">既知の制限</span><span class="sxs-lookup"><span data-stu-id="e62e8-110">Known limitations</span></span>

- <span data-ttu-id="e62e8-111">Sendinblue へのエクスポートごとに最大 100 万のプロファイルです。</span><span class="sxs-lookup"><span data-stu-id="e62e8-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="e62e8-112">Sendinblue へのエクスポートはセグメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="e62e8-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="e62e8-113">合計 100 万のプロファイルを持つセグメントのエクスポートには、最大 90 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e62e8-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="e62e8-114">Sendinblue にエクスポートできるプロファイルの数は、Sendinblue との契約内容に制限されます。</span><span class="sxs-lookup"><span data-stu-id="e62e8-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="e62e8-115">Sendinblue への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="e62e8-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="e62e8-116">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e62e8-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e62e8-117">**接続の追加** を選択し、**Sendinblue** を選んで、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="e62e8-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="e62e8-118">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="e62e8-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e62e8-119">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="e62e8-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e62e8-120">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e62e8-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e62e8-121">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e62e8-121">Choose who can use this connection.</span></span> <span data-ttu-id="e62e8-122">既定では、管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="e62e8-122">By default it's only administrators.</span></span> <span data-ttu-id="e62e8-123">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e62e8-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e62e8-124">**[Sendinblue API キー](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)** を入力します。</span><span class="sxs-lookup"><span data-stu-id="e62e8-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="e62e8-125">**同意する** を選択して、**データのプライバシーとコンプライアンス** を確認し、**接続** を選択して、Sendinblue への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="e62e8-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="e62e8-126">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e62e8-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e62e8-127">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="e62e8-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e62e8-128">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="e62e8-128">Configure an export</span></span>

<span data-ttu-id="e62e8-129">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e62e8-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e62e8-130">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e62e8-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e62e8-131">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e62e8-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e62e8-132">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e62e8-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e62e8-133">**エクスポート用の接続** フィールドで、Sendinblue セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="e62e8-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="e62e8-134">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="e62e8-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e62e8-135">**Sendinblue リスト ID** を入力します</span><span class="sxs-lookup"><span data-stu-id="e62e8-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="e62e8-136">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="e62e8-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e62e8-137">オプションで、**姓**、**名**、および **電話番号** をエクスポートして、よりパーソナライズされた電子メールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e62e8-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="e62e8-138">**属性の追加** を選択し、これらのフィールドをマップします。</span><span class="sxs-lookup"><span data-stu-id="e62e8-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e62e8-139">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="e62e8-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="e62e8-140">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e62e8-140">Select **Save**.</span></span>

<span data-ttu-id="e62e8-141">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="e62e8-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e62e8-142">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="e62e8-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e62e8-143">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="e62e8-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e62e8-144">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="e62e8-144">Data privacy and compliance</span></span>

<span data-ttu-id="e62e8-145">Dynamics 365 Customer Insights から Sendinblue へのデータ送信を可能にすると、Dynamics 365 Customer Insights のコンプライアンスの範囲を越えて、個人情報などの機密性の高い情報が潜在的に含まれるデータの転送を許可することになります。</span><span class="sxs-lookup"><span data-stu-id="e62e8-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e62e8-146">Microsoft はお客様の指示でそのようなデータを送信することがありますが、Sendinblue が関係するプライバシーまたはセキュリティのすべての義務を満たすよう見届ける責任はお客様にあります。</span><span class="sxs-lookup"><span data-stu-id="e62e8-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e62e8-147">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e62e8-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e62e8-148">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="e62e8-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
