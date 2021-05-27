---
title: Customer Insights のデータを Dynamics 365 Marketing にエクスポートする
description: Dynamics 365 Marketing への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976806"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="22962-103">Dynamics 365 Marketing でセグメントを使用する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="22962-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="22962-104">[セグメント](segments.md) を使用してキャンペーンを生成し、Dynamics 365 Marketing を使用して特定の顧客グループに連絡します。</span><span class="sxs-lookup"><span data-stu-id="22962-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="22962-105">詳しくは、[Dynamics 365 Marketing で Dynamics 365 Customer Insights のセグメントを使用する](/dynamics365/marketing/customer-insights-segments)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22962-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="22962-106">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="22962-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="22962-107">Customer Insights から Marketing にセグメントをエクスポートする前に、取引先担当者レコードが Dynamics 365 Marketing に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="22962-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="22962-108">取引先担当者を取り込む方法の詳細については、[Common Data Services を使った Dynamics 365 Marketing](connect-power-query.md) を読んでください。</span><span class="sxs-lookup"><span data-stu-id="22962-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="22962-109">対象者インサイトから Marketing にセグメントをエクスポートしても、Marketing インスタンスに新しい取引先担当者レコードは作成されません。</span><span class="sxs-lookup"><span data-stu-id="22962-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="22962-110">Marketing からの取引先担当者レコードは、対象者インサイトに取り込まれ、データ ソースとして使用される必要があります。</span><span class="sxs-lookup"><span data-stu-id="22962-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="22962-111">また、セグメントをエクスポートする前に、顧客 ID を取引先担当者 ID にマッピングするために、統合された顧客エンティティに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="22962-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="22962-112">Marketing への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="22962-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="22962-113">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="22962-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="22962-114">**つながりの追加** を選択し、**Dynamics 365 Marketing** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="22962-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="22962-115">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="22962-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="22962-116">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="22962-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="22962-117">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="22962-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="22962-118">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="22962-118">Choose who can use this connection.</span></span> <span data-ttu-id="22962-119">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="22962-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="22962-120">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22962-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="22962-121">**サーバー アドレス** フィールドに組織の Marketing URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="22962-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="22962-122">**サーバー管理者アカウント** セクションで、**サインイン** を選択し、Dynamics 365 Marketing アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="22962-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="22962-123">顧客 ID フィールドを Dynamics 365 取引先担当者 ID にマップします。</span><span class="sxs-lookup"><span data-stu-id="22962-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="22962-124">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="22962-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="22962-125">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="22962-125">Configure an export</span></span>

<span data-ttu-id="22962-126">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="22962-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="22962-127">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22962-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="22962-128">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="22962-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="22962-129">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="22962-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="22962-130">**エクスポートの接続** フィールドで、Dynamics 365 Marketing セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="22962-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="22962-131">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="22962-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="22962-132">1つ、または複数のセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="22962-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="22962-133">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="22962-133">Select **Save**.</span></span>

<span data-ttu-id="22962-134">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="22962-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="22962-135">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="22962-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="22962-136">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="22962-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
