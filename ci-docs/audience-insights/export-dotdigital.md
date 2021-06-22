---
title: Customer Insights のデータを DotDigital にエクスポートする
description: DotDigital への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124417"
---
# <a name="export-segments-to-dotdigital-preview"></a><span data-ttu-id="5204b-103">セグメントを DotDigital にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="5204b-103">Export segments to DotDigital (preview)</span></span>

<span data-ttu-id="5204b-104">統合顧客プロファイルのセグメントを DotDigital のアドレス帳にエクスポートし、キャンペーン、電子メール マーケティング、および DotDigital で顧客セグメントを構築するために使用します。</span><span class="sxs-lookup"><span data-stu-id="5204b-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="5204b-105">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="5204b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="5204b-106">[DotDigital アカウント](https://dotdigital.com/) と対応する管理者資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="5204b-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5204b-107">DotDigital には既存のアドレス帳と対応する ID があります。</span><span class="sxs-lookup"><span data-stu-id="5204b-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="5204b-108">アドレス帳を選択して開くと、URL に ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5204b-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="5204b-109">詳細については、[DotDigital アドレス帳](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5204b-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="5204b-110">対象者に関するインサイトで [セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="5204b-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5204b-111">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5204b-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5204b-112">既知の制限</span><span class="sxs-lookup"><span data-stu-id="5204b-112">Known limitations</span></span>

- <span data-ttu-id="5204b-113">DotDigital へのエクスポートごとに 100 万プロファイルまで。</span><span class="sxs-lookup"><span data-stu-id="5204b-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="5204b-114">DotDigital へのエクスポートはセグメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="5204b-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="5204b-115">プロバイダー側の制限により、合計 100 万のプロファイルを持つセグメントのエクスポートには最大 3 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5204b-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="5204b-116">DotDigital にエクスポートできるプロファイルの数は、DotDigital との契約に依存し、制限されています。</span><span class="sxs-lookup"><span data-stu-id="5204b-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="5204b-117">DotDigital への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="5204b-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="5204b-118">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="5204b-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5204b-119">**つながりの追加** を選択し、**DotDigital** を選択して接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="5204b-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="5204b-120">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="5204b-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5204b-121">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="5204b-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5204b-122">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5204b-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5204b-123">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="5204b-123">Choose who can use this connection.</span></span> <span data-ttu-id="5204b-124">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="5204b-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5204b-125">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5204b-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5204b-126">**DotDigital のユーザー名とパスワード** を入力します。</span><span class="sxs-lookup"><span data-stu-id="5204b-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="5204b-127">**[DotDigital アドレス帳 ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** を入力します。</span><span class="sxs-lookup"><span data-stu-id="5204b-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="5204b-128">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5204b-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5204b-129">**接続** を選択して、DotDigital への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="5204b-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="5204b-130">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="5204b-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5204b-131">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="5204b-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="5204b-132">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="5204b-132">Configure an export</span></span>

<span data-ttu-id="5204b-133">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5204b-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5204b-134">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5204b-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5204b-135">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="5204b-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5204b-136">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5204b-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5204b-137">**エクスポートの接続** フィールドで、DotDigital セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="5204b-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="5204b-138">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="5204b-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="5204b-139">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="5204b-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5204b-140">**名**、**姓**、**氏名**、**性別**、**郵便番号** などの、他のオプション フィールドについても同じ手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5204b-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="5204b-141">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="5204b-141">Select the segments you want to export.</span></span> <span data-ttu-id="5204b-142">合計で最大 100 万の顧客プロファイルを DotDigital にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="5204b-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="5204b-143">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5204b-143">Select **Save**.</span></span>

<span data-ttu-id="5204b-144">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="5204b-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5204b-145">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="5204b-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5204b-146">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="5204b-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="5204b-147">DotDigital では、セグメントを [DotDigital アドレス帳](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) で検索できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5204b-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5204b-148">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="5204b-148">Data privacy and compliance</span></span>

<span data-ttu-id="5204b-149">Dynamics 365 Customer Insights による DotDigital へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="5204b-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5204b-150">Microsoft ではこのようなデータをお客様の指示により転送しますが、DotDigital がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="5204b-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="5204b-151">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5204b-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5204b-152">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="5204b-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
