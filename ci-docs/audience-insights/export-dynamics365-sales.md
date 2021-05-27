---
title: Customer Insights のデータを Dynamics 365 Sales にエクスポートする
description: Dynamics 365 Sales への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976232"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="5fb26-103">Dynamics 365 Sales でセグメントを使用する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="5fb26-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="5fb26-104">Dynamics 365 Sales で顧客データを使用して、マーケティング リストの作成、ワークフローのフォローアップ、プロモーションの送信を行います。</span><span class="sxs-lookup"><span data-stu-id="5fb26-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="5fb26-105">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="5fb26-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="5fb26-106">Customer Insights から Sales にセグメントをエクスポートする前に、取引先担当者レコードが Dynamics 365 Sales に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fb26-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="5fb26-107">取引先担当者を取り込む方法の詳細については、[Common Data Services を使った Dynamics 365 Sales](connect-power-query.md) を読んでください。</span><span class="sxs-lookup"><span data-stu-id="5fb26-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="5fb26-108">対象者インサイトから Sales にセグメントをエクスポートしても、Sales インスタンスに新しい取引先担当者レコードは作成されません。</span><span class="sxs-lookup"><span data-stu-id="5fb26-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="5fb26-109">Sales からの取引先担当者レコードは、対象者インサイトに取り込まれ、データ ソースとして使用される必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fb26-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="5fb26-110">また、セグメントをエクスポートする前に、顧客 ID を取引先担当者 ID にマッピングするために、統合された顧客エンティティに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fb26-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="5fb26-111">Sales への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="5fb26-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="5fb26-112">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="5fb26-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5fb26-113">**つながりの追加** を選択し、**Dynamics 365 Sales** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="5fb26-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="5fb26-114">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="5fb26-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5fb26-115">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="5fb26-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5fb26-116">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5fb26-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5fb26-117">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fb26-117">Choose who can use this connection.</span></span> <span data-ttu-id="5fb26-118">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="5fb26-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5fb26-119">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fb26-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5fb26-120">**サーバー アドレス** フィールドに組織の Sales URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="5fb26-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="5fb26-121">**サーバー管理者アカウント** セクションで、**サインイン** を選択し、Dynamics 365 Sales アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fb26-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="5fb26-122">顧客 ID フィールドを Dynamics 365 取引先担当者 ID にマップします。</span><span class="sxs-lookup"><span data-stu-id="5fb26-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="5fb26-123">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="5fb26-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="5fb26-124">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="5fb26-124">Configure an export</span></span>

<span data-ttu-id="5fb26-125">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5fb26-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5fb26-126">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fb26-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5fb26-127">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="5fb26-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5fb26-128">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fb26-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5fb26-129">**エクスポートの接続** フィールドで、Dynamics 365 Sales セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fb26-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="5fb26-130">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="5fb26-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5fb26-131">1つ、または複数のセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fb26-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="5fb26-132">**保存** を選択します</span><span class="sxs-lookup"><span data-stu-id="5fb26-132">Select **Save**</span></span>

<span data-ttu-id="5fb26-133">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="5fb26-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5fb26-134">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="5fb26-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5fb26-135">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="5fb26-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
