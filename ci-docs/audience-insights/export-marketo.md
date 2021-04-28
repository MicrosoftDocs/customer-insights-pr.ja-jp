---
title: Customer Insights のデータを Marketo にエクスポートする
description: Marketo への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759827"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="1e7f5-103">セグメントを Marketo にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="1e7f5-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="1e7f5-104">統合顧客プロファイルのセグメントをエクスポートして、キャンペーンを生成し、電子メール マーケティングを提供して Marketo で特定の顧客グループを使用します。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="1e7f5-105">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="1e7f5-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="1e7f5-106">[Marketo アカウント](https://login.marketo.com/) と対応する管理者資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1e7f5-107">Marketo に既存のリストと対応する ID があります。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="1e7f5-108">詳細については、[Marketo リスト](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="1e7f5-109">[セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="1e7f5-110">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1e7f5-111">既知の制限</span><span class="sxs-lookup"><span data-stu-id="1e7f5-111">Known limitations</span></span>

- <span data-ttu-id="1e7f5-112">Marketo へのエクスポートごとに 100 万プロファイルまで。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="1e7f5-113">Marketo へのエクスポートはセグメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="1e7f5-114">合計 100 万のプロファイルを持つセグメントのエクスポートには、最大 3 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="1e7f5-115">Marketo にエクスポートできるプロファイルの数は、Marketo との契約に依存し、制限されています。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="1e7f5-116">Marketo への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="1e7f5-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="1e7f5-117">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1e7f5-118">**つながりの追加** を選択し、**Marketo** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="1e7f5-119">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1e7f5-120">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1e7f5-121">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1e7f5-122">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-122">Choose who can use this connection.</span></span> <span data-ttu-id="1e7f5-123">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1e7f5-124">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1e7f5-125">**[Marketo クライアント ID、クライアント シークレット、REST エンドポイントのホスト名](https://developers.marketo.com/rest-api/authentication/)** を入力します。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="1e7f5-126">**同意する** を選択して、**データのプライバシーとコンプライアンス** を確認し、**接続** を選択して、Marketo への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="1e7f5-127">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1e7f5-128">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1e7f5-129">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="1e7f5-129">Configure an export</span></span>

<span data-ttu-id="1e7f5-130">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1e7f5-131">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1e7f5-132">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1e7f5-133">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1e7f5-134">**エクスポートの接続** フィールドで、Marketo セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="1e7f5-135">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1e7f5-136">**[Marketo リスト ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** を入力します</span><span class="sxs-lookup"><span data-stu-id="1e7f5-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="1e7f5-137">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="1e7f5-138">オプションで、**名**、**姓**、**市**、**都道府県**、**国/地域** をエクスポートし、パーソナライズされたメールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="1e7f5-139">**属性の追加** を選択し、これらのフィールドをマップします。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="1e7f5-140">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-140">Select the segments you want to export.</span></span> <span data-ttu-id="1e7f5-141">合計で最大 100 万の顧客プロファイルを Marketo にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="1e7f5-142">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-142">Select **Save**.</span></span>

<span data-ttu-id="1e7f5-143">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1e7f5-144">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1e7f5-145">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="1e7f5-146">Marketo では、セグメントが [Marketo リスト](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) の下に表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1e7f5-147">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="1e7f5-147">Data privacy and compliance</span></span>

<span data-ttu-id="1e7f5-148">Dynamics 365 Customer Insights による Marketo へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1e7f5-149">Microsoft ではこのようなデータをお客様の指示により転送しますが、Marketo がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1e7f5-150">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1e7f5-151">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="1e7f5-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]