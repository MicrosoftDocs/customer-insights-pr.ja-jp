---
title: Power BI コネクタ
description: Power BI で Dynamics 365 Customer Insights コネクタの使用方法を学びます。
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406154"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="faf0c-103">Power BI のコネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="faf0c-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="faf0c-104">Power BI Desktop を使用してデータをビジュアル化します。</span><span class="sxs-lookup"><span data-stu-id="faf0c-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="faf0c-105">統合された顧客データを使用して、追加のインサイトを生成し、レポートをビルドします。</span><span class="sxs-lookup"><span data-stu-id="faf0c-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="faf0c-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="faf0c-106">Prerequisites</span></span>

- <span data-ttu-id="faf0c-107">統合顧客プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="faf0c-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="faf0c-108">[Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/)の最新バージョンがコンピュータにインストールされている。</span><span class="sxs-lookup"><span data-stu-id="faf0c-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="faf0c-109">[Power BI Desktop の詳細](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)</span><span class="sxs-lookup"><span data-stu-id="faf0c-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="faf0c-110">Power BI のコネクタの構成</span><span class="sxs-lookup"><span data-stu-id="faf0c-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="faf0c-111">Power BI Desktop で、**ファイル** > **データの取得** を選択します。</span><span class="sxs-lookup"><span data-stu-id="faf0c-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="faf0c-112">**詳細を表示** を選択して、**Dynamics 365 Customer Insights** を検索します</span><span class="sxs-lookup"><span data-stu-id="faf0c-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="faf0c-113">結果を選択して、**接続** を選択します。</span><span class="sxs-lookup"><span data-stu-id="faf0c-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="faf0c-114">Customer Insightsに使用するのと同じ組織アカウントを使用して **サインイン** して、**接続** を選択します。</span><span class="sxs-lookup"><span data-stu-id="faf0c-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="faf0c-115">この手順で指定するアカウントは、Customer Insights からデータをフェッチするために使用され、Power BI にサインインしているものと同じである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="faf0c-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="faf0c-116">データの取得に使用されるアカウントをリセットするには、Power BI を開き、**ファイル** > **オプション** > **設定** > **データ ソース設定** に移動します。</span><span class="sxs-lookup"><span data-stu-id="faf0c-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="faf0c-117">データ ソースの一覧で、**Dynamics 365 Customer Insights へのログイン** を選択し、**アクセス許可のクリア** を選択します。</span><span class="sxs-lookup"><span data-stu-id="faf0c-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="faf0c-118">**検索** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="faf0c-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="faf0c-119">アクセス可能なすべての環境を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="faf0c-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="faf0c-120">環境を展開し、任意のフォルダー (エンティティ、メジャー、セグメント、エンリッチメント) を開きます。</span><span class="sxs-lookup"><span data-stu-id="faf0c-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="faf0c-121">たとえば、**エンティティ** フォルダを開き、インポートできるすべてのエンティティを表示します。</span><span class="sxs-lookup"><span data-stu-id="faf0c-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="faf0c-122">![Power BIコネクタ ナビゲータ](media/power-bi-navigator.png "Power BI コネクタ ナビゲーター")</span><span class="sxs-lookup"><span data-stu-id="faf0c-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="faf0c-123">含めるエンティティの横にあるチェックボックスを選択して、**読み込みます**。</span><span class="sxs-lookup"><span data-stu-id="faf0c-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="faf0c-124">複数の環境から複数のエンティティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="faf0c-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="faf0c-125">エンティティがロードされている間、ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="faf0c-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="faf0c-126">選択したエンティティをすべて読み込むと、Power BI の機能を使用して、データを視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="faf0c-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="faf0c-127">大規模なデータセット</span><span class="sxs-lookup"><span data-stu-id="faf0c-127">Large data sets</span></span>

<span data-ttu-id="faf0c-128">Power BI の Customer Insights コネクタは、最大 100 万の顧客プロファイルを含むデータセットで機能するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="faf0c-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="faf0c-129">大きなデータセットのインポートは出来る可能性がありますが、時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="faf0c-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="faf0c-130">さらに、Power BI 制限によりプロセスがタイムアウトになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="faf0c-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="faf0c-131">詳細については、[Power BI : 大きなデータセットの推奨事項](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faf0c-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="faf0c-132">データのサブセットを使用する</span><span class="sxs-lookup"><span data-stu-id="faf0c-132">Work with a subset of data</span></span>

<span data-ttu-id="faf0c-133">データのサブセットを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="faf0c-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="faf0c-134">たとえば、すべての顧客レコードを Power BI にエクスポートする代わりに、[セグメント](segments.md) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="faf0c-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
