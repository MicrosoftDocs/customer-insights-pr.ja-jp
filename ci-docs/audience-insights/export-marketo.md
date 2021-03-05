---
title: Customer Insights のデータを Marketo にエクスポートする
description: Marketo への接続を構成する方法を説明します。
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267087"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="e6da2-103">Marketo 用コネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e6da2-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="e6da2-104">統合顧客プロファイルのセグメントをエクスポートして、キャンペーンを生成し、電子メール マーケティングを提供して Marketo で特定の顧客グループを使用します。</span><span class="sxs-lookup"><span data-stu-id="e6da2-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6da2-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="e6da2-105">Prerequisites</span></span>

-   <span data-ttu-id="e6da2-106">[Marketo アカウント](https://login.marketo.com/) と対応する管理者資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="e6da2-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e6da2-107">Marketo に既存のリストと対応する ID があります。</span><span class="sxs-lookup"><span data-stu-id="e6da2-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="e6da2-108">詳細については、[Marketo リスト](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6da2-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="e6da2-109">[セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="e6da2-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="e6da2-110">エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e6da2-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="e6da2-111">Marketo への接続</span><span class="sxs-lookup"><span data-stu-id="e6da2-111">Connect to Marketo</span></span>

1. <span data-ttu-id="e6da2-112">**管理** > **エクスポート先** へと移動します。</span><span class="sxs-lookup"><span data-stu-id="e6da2-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e6da2-113">**Marketo** で **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6da2-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="e6da2-114">**表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="e6da2-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e6da2-115">**[Marketo クライアント ID、クライアント シークレット、REST エンドポイントのホスト名](https://developers.marketo.com/rest-api/authentication/)** を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6da2-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="e6da2-116">**[Marketo リスト ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** を入力します</span><span class="sxs-lookup"><span data-stu-id="e6da2-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="e6da2-117">**同意する** を選択して、**データのプライバシーとコンプライアンス** を確認し、**接続** を選択して、Marketo への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="e6da2-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="e6da2-118">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6da2-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Marketo 接続のスクリーンショットをエクスポートする":::

1. <span data-ttu-id="e6da2-120">**次へ** を選択してエクスポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="e6da2-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="e6da2-121">コネクタの構成</span><span class="sxs-lookup"><span data-stu-id="e6da2-121">Configure the connector</span></span>

1. <span data-ttu-id="e6da2-122">**データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6da2-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e6da2-123">オプションで、**名**、**姓**、**市**、**都道府県**、**国/地域** を追加フィールドとしてエクスポートし、よりパーソナライズされた電子メールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e6da2-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="e6da2-124">**属性の追加** を選択し、これらのフィールドをマップします。</span><span class="sxs-lookup"><span data-stu-id="e6da2-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e6da2-125">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6da2-125">Select the segments you want to export.</span></span> <span data-ttu-id="e6da2-126">合計で最大 100 万の顧客プロファイルを Marketo にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e6da2-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="フィールドとセグメントを選択して、Marketo にエクスポートする":::

1. <span data-ttu-id="e6da2-128">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6da2-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e6da2-129">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e6da2-129">Export the data</span></span>

<span data-ttu-id="e6da2-130">[オンデマンドでデータをエクスポート](export-destinations.md) できます。</span><span class="sxs-lookup"><span data-stu-id="e6da2-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e6da2-131">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="e6da2-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e6da2-132">Marketo では、セグメントが [Marketo リスト](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) の下に表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e6da2-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e6da2-133">既知の制限</span><span class="sxs-lookup"><span data-stu-id="e6da2-133">Known limitations</span></span>

- <span data-ttu-id="e6da2-134">Marketo へのエクスポートごとに 100 万プロファイルまで。</span><span class="sxs-lookup"><span data-stu-id="e6da2-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="e6da2-135">Marketo へのエクスポートはセグメントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="e6da2-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="e6da2-136">合計 100 万のプロファイルを持つセグメントのエクスポートには、最大 3 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e6da2-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="e6da2-137">Marketo にエクスポートできるプロファイルの数は、Marketo との契約に依存し、制限されています。</span><span class="sxs-lookup"><span data-stu-id="e6da2-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e6da2-138">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="e6da2-138">Data privacy and compliance</span></span>

<span data-ttu-id="e6da2-139">Dynamics 365 Customer Insights による Marketo へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="e6da2-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e6da2-140">Microsoft ではこのようなデータをお客様の指示により転送しますが、Marketo がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="e6da2-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e6da2-141">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6da2-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e6da2-142">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="e6da2-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]