---
title: Customer Insights データを Azure Synapse Analytics にエクスポート
description: Azure Synapse Analytics への接続を構成する方法について説明します。
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977383"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="a2cdb-103">データを Azure Synapse Analytics にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="a2cdb-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="a2cdb-104">Azure Synapse は、データ ウェアハウスやビッグ データ システムにおいて分析時間を短縮する分析サービスです。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="a2cdb-105">[Azure Synapse](/azure/synapse-analytics/overview-what-is) では、Customer Insights のデータを取り込んで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a2cdb-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="a2cdb-106">Prerequisites</span></span>

<span data-ttu-id="a2cdb-107">Customer Insights から Azure Synapse への接続を構成するには、次の前提条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="a2cdb-108">すべての **ロールの割り当て** を説明どおりに設定してください。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="a2cdb-109">Customer Insights の前提条件</span><span class="sxs-lookup"><span data-stu-id="a2cdb-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="a2cdb-110">対象者に関するインサイトで **管理者** ロールを持っていること。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="a2cdb-111">詳細については、[対象者に関するインサイトでのユーザー アクセス許可の設定](permissions.md#assign-roles-and-permissions) を参照してください</span><span class="sxs-lookup"><span data-stu-id="a2cdb-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="a2cdb-112">Azure の場合:</span><span class="sxs-lookup"><span data-stu-id="a2cdb-112">In Azure:</span></span> 

- <span data-ttu-id="a2cdb-113">有効な Azure サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-113">An active Azure subscription.</span></span>

- <span data-ttu-id="a2cdb-114">新しい Azure Data Lake Storage Gen2 アカウントを使用する場合、*対象者に関するインサイトのサービス プリンシパル* には、**ストレージ Blob データ共同作成者** アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="a2cdb-115">詳細は、[対象者に関するインサイトの Azure サービス プリンシパルを持つ Azure Data Lake Storage Gen2 アカウントへの接続](connect-service-principal.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="a2cdb-116">Data Lake Storage Gen2 では、[階層型名前空間](/azure/storage/blobs/data-lake-storage-namespace) を有効にすることが **必要** です。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="a2cdb-117">Azure Synapse ワークスペースが配置されているリソース グループでは、*サービス プリンシパル* と *対象者に関するインサイトのユーザー* に、少なくとも **閲覧者** のアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="a2cdb-118">詳細については、[Azure ポータルを使用した Azure ロールの割り当て](/azure/role-based-access-control/role-assignments-portal) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="a2cdb-119">*ユーザー* には、データが配置され、Azure Synapse ワークスペースにリンクされている Azure Data Lake Storage Gen2 アカウントの **ストレージ BLOB データ共同作成者** アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="a2cdb-120">詳細については、[Azure ポータルを使用した BLOB およびキュー データへのアクセスのための Azure ロールの割り当て](/azure/storage/common/storage-auth-aad-rbac-portal) と [ストレージ BLOB データ共同作成者のアクセス許可](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="a2cdb-121">*[Azure Synapse ワークスペース マネージド ID](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* には、データが配置され、Azure Synapse ワークスペースにリンクされている Azure Data Lake Storage Gen2 アカウントの **ストレージ BLOB データ共同作成者** アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="a2cdb-122">詳細は、[Azure ポータルを使用した BLOB およびキュー データへのアクセスのための Azure ロールの割り当て](/azure/storage/common/storage-auth-aad-rbac-portal) と [ストレージ BLOB データ共同作成者のアクセス許可](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="a2cdb-123">Azure Synapse ワークスペースでは、*対象者に関するインサイトのサービス プリンシパル* に **Synapse 管理者** ロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="a2cdb-124">詳細については、[Synapse ワークスペースのアクセス制御を設定する方法](/azure/synapse-analytics/security/how-to-set-up-access-control) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="a2cdb-125">Azure Synapse への接続とエクスポートを設定する</span><span class="sxs-lookup"><span data-stu-id="a2cdb-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="a2cdb-126">接続の構成</span><span class="sxs-lookup"><span data-stu-id="a2cdb-126">Configure a connection</span></span>

1. <span data-ttu-id="a2cdb-127">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a2cdb-128">**つながりの追加** を選択し、**Azure Synapse Analytics** を選択するか、**Azure Synapse Analytics** タイルで **設定** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="a2cdb-129">接続にわかりやすい名前を 表示名 フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="a2cdb-130">接続名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="a2cdb-131">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a2cdb-132">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-132">Choose who can use this connection.</span></span> <span data-ttu-id="a2cdb-133">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a2cdb-134">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a2cdb-135">Customer Insights のデータを使用するサブスクリプションを選択または検索します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="a2cdb-136">サブスクリプションが選択されると、**ワークスペース**、**ストレージ アカウント**、**コンテナー** も選択できます。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="a2cdb-137">**保存** を選択して、接続を保存します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="a2cdb-138">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="a2cdb-138">Configure an export</span></span>

<span data-ttu-id="a2cdb-139">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a2cdb-140">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a2cdb-141">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a2cdb-142">新しいエクスポートを作成するには、**エクスポートの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="a2cdb-143">**エクスポートの接続** フィールドで、**Azure Synapse Analytics** セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="a2cdb-144">このセクション名が表示されない場合、この種類の [接続](connections.md) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="a2cdb-145">エクスポートの識別可能な **表示名** と **データベース名** を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="a2cdb-146">Azure Synapse Analytics にエクスポートするエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="a2cdb-147">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-147">Select **Save**.</span></span>

<span data-ttu-id="a2cdb-148">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a2cdb-149">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a2cdb-150">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="a2cdb-151">エクスポートの更新</span><span class="sxs-lookup"><span data-stu-id="a2cdb-151">Update an export</span></span>

1. <span data-ttu-id="a2cdb-152">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a2cdb-153">更新するエクスポートで **編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="a2cdb-154">選択からエンティティを **追加** または **削除** します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="a2cdb-155">エンティティを選択から削除しても、Synapse Analytics データベースからは削除されません。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="a2cdb-156">ただし、今後データを更新しても、そのデータベース内の削除されたエンティティは更新されません。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="a2cdb-157">**データベース名を変更** すると、新しい Synapse Analytics データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="a2cdb-158">以前に構成された名前のデータベースは、今後の更新では更新が行われません。</span><span class="sxs-lookup"><span data-stu-id="a2cdb-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
