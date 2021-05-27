---
title: Customer Insights データを Azure Blob Storage にエクスポートする
description: Blob Storage への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976187"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="7fb73-103">セグメント リストとその他のデータを Azure Blob Storage にエクスポートする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7fb73-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="7fb73-104">Customer Insights データを Blob Storage に保存するか、それを使用してユーザーのデータを他のアプリケーションに転送します。</span><span class="sxs-lookup"><span data-stu-id="7fb73-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="7fb73-105">Blob Storage への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="7fb73-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="7fb73-106">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="7fb73-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7fb73-107">**つながりの追加** を選択し、**Azure Blob Storage** を選択して接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="7fb73-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="7fb73-108">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="7fb73-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7fb73-109">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="7fb73-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7fb73-110">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7fb73-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7fb73-111">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7fb73-111">Choose who can use this connection.</span></span> <span data-ttu-id="7fb73-112">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="7fb73-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7fb73-113">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fb73-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7fb73-114">Blob Storage アカウントに **アカウント名**、**アカウント キー**、**コンテナー** を入力します。</span><span class="sxs-lookup"><span data-stu-id="7fb73-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="7fb73-115">Blob Storage アカウント名とアカウント キーを検索する方法の詳細については、[Azure ポータルでストレージ アカウントの設定を管理する](/azure/storage/common/storage-account-manage) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fb73-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="7fb73-116">コンテナの作成方法については、[コンテナを作成する](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fb73-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="7fb73-117">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="7fb73-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="7fb73-118">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="7fb73-118">Configure an export</span></span>

<span data-ttu-id="7fb73-119">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7fb73-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7fb73-120">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fb73-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7fb73-121">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="7fb73-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7fb73-122">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fb73-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7fb73-123">**エクスポートの接続** フィールドで、Azure Blob Storage セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fb73-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="7fb73-124">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="7fb73-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7fb73-125">エクスポートの出力先とする各エンティティの横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="7fb73-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="7fb73-126">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fb73-126">Select **Save**.</span></span>

<span data-ttu-id="7fb73-127">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="7fb73-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7fb73-128">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="7fb73-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="7fb73-129">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="7fb73-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="7fb73-130">エクスポート データは、構成した Blob Storage コンテナーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="7fb73-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="7fb73-131">以下のフォルダー パスが自動的にコンテナーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="7fb73-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="7fb73-132">システムによって生成されたソース エンティティとエンティティの場合: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="7fb73-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="7fb73-133">例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="7fb73-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="7fb73-134">エクスポートされたエンティティの model.json は、%ExportDestinationName% レベルです</span><span class="sxs-lookup"><span data-stu-id="7fb73-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="7fb73-135">例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="7fb73-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
