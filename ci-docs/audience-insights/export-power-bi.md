---
title: Power BI コネクタ
description: Power BI で Dynamics 365 Customer Insights コネクタの使用方法を学びます。
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596045"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="4c3ed-103">Power BI のコネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="4c3ed-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="4c3ed-104">Power BI Desktop を使用してデータをビジュアル化します。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="4c3ed-105">統合された顧客データを使用して、追加のインサイトを生成し、レポートをビルドします。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4c3ed-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="4c3ed-106">Prerequisites</span></span>

- <span data-ttu-id="4c3ed-107">統合顧客プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="4c3ed-108">最新バージョンの [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) がコンピュータにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="4c3ed-109">[Power BI Desktop の詳細](/power-bi/desktop-what-is-desktop)</span><span class="sxs-lookup"><span data-stu-id="4c3ed-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="4c3ed-110">Power BI のコネクタの構成</span><span class="sxs-lookup"><span data-stu-id="4c3ed-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="4c3ed-111">Power BI Desktop で、**ファイル** > **データの取得** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="4c3ed-112">**詳細を表示** を選択して、**Dynamics 365 Customer Insights** を検索します</span><span class="sxs-lookup"><span data-stu-id="4c3ed-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="4c3ed-113">**接続** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-113">Select **Connect**.</span></span>

1. <span data-ttu-id="4c3ed-114">Customer Insightsに使用するのと同じ組織アカウントを使用して **サインイン** して、**接続** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="4c3ed-115">この手順で指定するアカウントは、Customer Insights からデータをフェッチするために使用され、Power BI にサインインしているものと同じである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="4c3ed-116">データの取得に使用されるアカウントをリセットするには、Power BI を開き、**ファイル** > **オプション** > **設定** > **データ ソース設定** に移動します。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="4c3ed-117">データ ソースの一覧で、**Dynamics 365 Customer Insights へのログイン** を選択し、**アクセス許可のクリア** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="4c3ed-118">**検索** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="4c3ed-119">アクセス可能なすべての環境を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="4c3ed-120">環境を展開し、任意のフォルダー (エンティティ、メジャー、セグメント、エンリッチメント) を開きます。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="4c3ed-121">たとえば、**エンティティ** フォルダを開き、インポートできるすべてのエンティティを表示します。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="4c3ed-122">![Power BIコネクタ ナビゲータ](media/power-bi-navigator.png "Power BI コネクタ ナビゲーター")</span><span class="sxs-lookup"><span data-stu-id="4c3ed-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="4c3ed-123">含めるエンティティの横にあるチェックボックスを選択して、**読み込みます**。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="4c3ed-124">複数の環境から複数のエンティティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="4c3ed-125">エンティティがロードされている間、ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="4c3ed-126">選択したエンティティをすべて読み込むと、Power BI の機能を使用して、データを視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="4c3ed-127">大規模なデータセット</span><span class="sxs-lookup"><span data-stu-id="4c3ed-127">Large data sets</span></span>

<span data-ttu-id="4c3ed-128">Power BI の Customer Insights コネクタは、最大 100 万の顧客プロファイルを含むデータセットで機能するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="4c3ed-129">大きなデータセットのインポートは出来る可能性がありますが、時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="4c3ed-130">さらに、Power BI 制限によりプロセスがタイムアウトになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="4c3ed-131">詳細については、[Power BI : 大きなデータセットの推奨事項](/power-bi/admin/service-premium-what-is#large-datasets)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="4c3ed-132">データのサブセットを使用する</span><span class="sxs-lookup"><span data-stu-id="4c3ed-132">Work with a subset of data</span></span>

<span data-ttu-id="4c3ed-133">データのサブセットを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="4c3ed-134">たとえば、すべての顧客レコードを Power BI にエクスポートする代わりに、[セグメント](segments.md) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="4c3ed-135">トラブルシューティング​​</span><span class="sxs-lookup"><span data-stu-id="4c3ed-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="4c3ed-136">Power BI に Customer Insights 環境はに表示されません</span><span class="sxs-lookup"><span data-stu-id="4c3ed-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="4c3ed-137">対象者に関するインサイトの 2 つの同一エンティティ間で定義された[リレーションシップ](relationships.md)が複数ある環境は、Power BI コネクタでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="4c3ed-138">重複したリレーションシップは特定して削除できます。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="4c3ed-139">Power BI にない環境の対象者インサイトで、**データ** > **リレーションシップ** に進みます。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="4c3ed-140">重複したリレーションシップを特定します。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="4c3ed-141">同じ 2 つのエンティティ間に複数のリレーションシップが定義されているかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="4c3ed-142">統合プロセスに含まれる 2 つのエンティティ間に作成されたリレーションシップがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="4c3ed-143">統合プロセスに含まれるすべてのエンティティ間に定義された暗黙のリレーションシップがあります。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="4c3ed-144">識別された重複するリレーションシップをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="4c3ed-145">重複したリレーションシップを削除した後、Power BI コネクタに再接続してみます。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="4c3ed-146">これで環境が利用可能になりました。</span><span class="sxs-lookup"><span data-stu-id="4c3ed-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]