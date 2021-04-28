---
title: Customer Insights のデータを Azure Data Lake Storage Gen2 にエクスポートする
description: Azure Data Lake Storage Gen2 への接続を構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760057"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="26fad-103">Azure Data Lake Storage Gen2 への接続を設定する (preview)</span><span class="sxs-lookup"><span data-stu-id="26fad-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="26fad-104">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="26fad-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="26fad-105">**つながりの追加** を選択し、**Azure Data Lake Storage Gen2** を選択して接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="26fad-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="26fad-106">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="26fad-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="26fad-107">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="26fad-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="26fad-108">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="26fad-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="26fad-109">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="26fad-109">Choose who can use this connection.</span></span> <span data-ttu-id="26fad-110">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="26fad-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="26fad-111">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26fad-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="26fad-112">Azure Data Lake Storage Gen2 の **アカウント名**、**アカウント キー**、および **コンテナ** を入力します。</span><span class="sxs-lookup"><span data-stu-id="26fad-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="26fad-113">Azure Data Lake Storage Gen2 で使うストレージ アカウントを作成する方法を学ぶには、[ストレージアカウントを作成する](/azure/storage/blobs/create-data-lake-storage-account)を参照します。</span><span class="sxs-lookup"><span data-stu-id="26fad-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="26fad-114">Azure Data Lake Gen2 のストレージ アカウント名とアカウント キーの詳細については、[Azure ポータルでストレージ アカウントの設定を管理する](/azure/storage/common/storage-account-manage) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26fad-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="26fad-115">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="26fad-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="26fad-116">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="26fad-116">Configure an export</span></span>

<span data-ttu-id="26fad-117">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="26fad-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="26fad-118">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26fad-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="26fad-119">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="26fad-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="26fad-120">新しいエクスポートを作成するには、**エクスポートの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="26fad-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="26fad-121">**エクスポートの接続** フィールドで、**Azure Data Lake** セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="26fad-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="26fad-122">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="26fad-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="26fad-123">エクスポートの出力先とする各エンティティの横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="26fad-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="26fad-124">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="26fad-124">Select **Save**.</span></span>

<span data-ttu-id="26fad-125">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="26fad-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="26fad-126">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="26fad-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="26fad-127">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="26fad-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="26fad-128">エクスポート データは、構成した Azure Data Lake Gen 2 のストレージ コンテナーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="26fad-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
