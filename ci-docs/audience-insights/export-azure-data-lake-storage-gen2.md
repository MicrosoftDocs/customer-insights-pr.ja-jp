---
title: Customer Insights のデータを Azure Data Lake Storage Gen2 にエクスポートする
description: Azure Data Lake Storage Gen2 への接続を構成する方法を説明します。
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477185"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="80f66-103">Azure Data Lake Storage Gen2 用コネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="80f66-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="80f66-104">Customer Insights データを Azure Data Lake Storage Gen2 に保存するか、それを使用してユーザーのデータを他のアプリケーションに転送します。</span><span class="sxs-lookup"><span data-stu-id="80f66-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="80f66-105">Azure Data Lake Storage Gen2 のコネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="80f66-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="80f66-106">対象者に関するインサイトで、**管理** > **エクスポート先** に移動します。</span><span class="sxs-lookup"><span data-stu-id="80f66-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="80f66-107">**Azure Data Lake Storage Gen2** で **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="80f66-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="80f66-108">出力先となる **表示名称** フィールドにはわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="80f66-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="80f66-109">Azure Data Lake Storage Gen2 の **アカウント名**、**アカウント キー**、および **コンテナ** を入力します。</span><span class="sxs-lookup"><span data-stu-id="80f66-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="80f66-110">Azure Data Lake Storage Gen2 で使うストレージ アカウントを作成する方法を学ぶには、[ストレージアカウントを作成する](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account)を参照します。</span><span class="sxs-lookup"><span data-stu-id="80f66-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="80f66-111">Azure Data Lake Gen2 ストレージ アカウント名とアカウントキーを見つける方法の詳細については、[ Azure ポータルでストレージ アカウント設定を管理する](https://docs.microsoft.com/azure/storage/common/storage-account-manage)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80f66-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="80f66-112">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="80f66-112">Select **Next**.</span></span>

1. <span data-ttu-id="80f66-113">エクスポートの出力先とする各エンティティの横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="80f66-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="80f66-114">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="80f66-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="80f66-115">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="80f66-115">Export the data</span></span>

<span data-ttu-id="80f66-116">[オンデマンドでデータをエクスポート](export-destinations.md#export-data-on-demand) できます。</span><span class="sxs-lookup"><span data-stu-id="80f66-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="80f66-117">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="80f66-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
