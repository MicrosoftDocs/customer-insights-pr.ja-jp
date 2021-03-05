---
title: Customer Insights のデータを DotDigital にエクスポートする
description: DotDigital への接続を構成する方法を説明します。
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269106"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="9cdcc-103">DotDigital 用コネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9cdcc-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="9cdcc-104">統合顧客プロファイルのセグメントを DotDigital のアドレス帳にエクスポートし、キャンペーン、電子メール マーケティング、および DotDigital で顧客セグメントを構築するために使用します。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="9cdcc-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="9cdcc-105">Prerequisites</span></span>

-   <span data-ttu-id="9cdcc-106">[DotDigital アカウント](https://dotdigital.com/) と対応する管理者資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9cdcc-107">DotDigital には既存のアドレス帳と対応する ID があります。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="9cdcc-108">アドレス帳を選択して開くと、URL に ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="9cdcc-109">詳細については、[DotDigital アドレス帳](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="9cdcc-110">対象者に関するインサイトで [セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="9cdcc-111">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="9cdcc-112">DotDigital への接続</span><span class="sxs-lookup"><span data-stu-id="9cdcc-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="9cdcc-113">**管理** > **エクスポート先** へと移動します。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9cdcc-114">**DotDigital** で **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="9cdcc-115">**表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="DotDigital エクスポート の構成ペイン。":::

1. <span data-ttu-id="9cdcc-117">**DotDigital のユーザー名とパスワード** を入力します。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="9cdcc-118">**[DotDigital アドレス帳 ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** を入力します。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="9cdcc-119">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9cdcc-120">**接続** を選択して、DotDigital への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="9cdcc-121">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9cdcc-122">**次へ** を選択してエクスポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="9cdcc-123">コネクタの構成</span><span class="sxs-lookup"><span data-stu-id="9cdcc-123">Configure the connector</span></span>

1. <span data-ttu-id="9cdcc-124">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="9cdcc-125">**名**、**姓**、**氏名**、**性別**、**郵便番号** などの、他のオプション フィールドについても同じ手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="9cdcc-126">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-126">Select the segments you want to export.</span></span> <span data-ttu-id="9cdcc-127">合計で最大 100 万の顧客プロファイルを DotDigital にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="9cdcc-128">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9cdcc-129">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="9cdcc-129">Export the data</span></span>

<span data-ttu-id="9cdcc-130">[オンデマンドでデータをエクスポート](export-destinations.md) できます。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9cdcc-131">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9cdcc-132">DotDigital では、セグメントを [DotDigital アドレス帳](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) で検索できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9cdcc-133">既知の制限</span><span class="sxs-lookup"><span data-stu-id="9cdcc-133">Known limitations</span></span>

- <span data-ttu-id="9cdcc-134">DotDigital へのエクスポートごとに 100 万プロファイルまで。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="9cdcc-135">DotDigital へのエクスポートはセグメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="9cdcc-136">プロバイダー側の制限により、合計 100 万のプロファイルを持つセグメントのエクスポートには最大 3 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="9cdcc-137">DotDigital にエクスポートできるプロファイルの数は、DotDigital との契約に依存し、制限されています。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9cdcc-138">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="9cdcc-138">Data privacy and compliance</span></span>

<span data-ttu-id="9cdcc-139">Dynamics 365 Customer Insights による DotDigital へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9cdcc-140">Microsoft ではこのようなデータをお客様の指示により転送しますが、DotDigital がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="9cdcc-141">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9cdcc-142">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="9cdcc-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]