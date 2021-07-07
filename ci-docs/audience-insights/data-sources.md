---
title: データ ソースを使用してデータを取り込む
description: さまざまなソースからデータをインポートする方法について説明します。
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304702"
---
# <a name="data-sources-overview"></a><span data-ttu-id="7dcd4-103">データ ソースの概要</span><span class="sxs-lookup"><span data-stu-id="7dcd4-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="7dcd4-104">Dynamics 365 Customer Insights の対象者に関するインサイト機能は、幅広いソースからのデータに接続します。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="7dcd4-105">データ ソースへの接続は、多くの場合、*データ取り込み* のプロセスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="7dcd4-106">データを取り込んだ後、[統合](data-unification.md) およびアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="7dcd4-107">データ ソースの追加</span><span class="sxs-lookup"><span data-stu-id="7dcd4-107">Add a data source</span></span>

<span data-ttu-id="7dcd4-108">選択したオプションに応じて、データ ソースを追加する方法に関する詳細な記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="7dcd4-109">データ ソースは、主に次の 3 つの方法で追加できます:</span><span class="sxs-lookup"><span data-stu-id="7dcd4-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="7dcd4-110">多数の Power Query コネクタを使用して</span><span class="sxs-lookup"><span data-stu-id="7dcd4-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="7dcd4-111">Common Data Model フォルダーから</span><span class="sxs-lookup"><span data-stu-id="7dcd4-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="7dcd4-112">自分の Microsoft Dataverse レイク から</span><span class="sxs-lookup"><span data-stu-id="7dcd4-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="7dcd4-113">オンプレミスのデータ ソースからデータを追加する</span><span class="sxs-lookup"><span data-stu-id="7dcd4-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="7dcd4-114">オンプレミスのデータ ソースから、対象ユーザー分析情報へのデータの取り込みは、Microsoft Power Platform データフローに基づいてサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="7dcd4-115">データフローは、環境を設定するときに [Microsoft Dataverse 環境 URL を指定](manage-environments.md#create-an-environment-in-an-existing-organization) することで、Customer Insights で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="7dcd4-116">Dataverse 環境を Customer Insights に関連付け後に作成されるデータ ソースは、既定で [Power Platform データフロー](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) を使用します。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="7dcd4-117">データフローは、データ ゲートウェイを使用したオンプレミス接続をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="7dcd4-118">Dataverse 環境が関連付けられる前に存在したデータ ソースを削除して再作成し、[オンプレミス データ ゲートウェイを使用](/data-integration/gateway/service-gateway-app.md) します。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="7dcd4-119">既存の Power BI または Power Apps 環境からのデータ ゲートウェイが表示され、Customer Insights で再利用できます。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="7dcd4-120">データ ソース ページには、Microsoft Power Platform 環境に移動するためのリンクが表示され、オンプレミスのデータ ゲートウェイを表示および構成することができます。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="7dcd4-121">取り込んだデータのレビュー</span><span class="sxs-lookup"><span data-stu-id="7dcd4-121">Review ingested data</span></span>

<span data-ttu-id="7dcd4-122">取り込んだ各データ ソースの名前、状態、ソースのデータが最後に更新された時刻が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="7dcd4-123">データ ソースの一覧を列ごとに並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7dcd4-124">![追加されたデータ ソース](media/configure-data-datasource-added.png "追加されたデータ ソース")</span><span class="sxs-lookup"><span data-stu-id="7dcd4-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="7dcd4-125">ステータス</span><span class="sxs-lookup"><span data-stu-id="7dcd4-125">Status</span></span>  |<span data-ttu-id="7dcd4-126">内容</span><span class="sxs-lookup"><span data-stu-id="7dcd4-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="7dcd4-127">成功</span><span class="sxs-lookup"><span data-stu-id="7dcd4-127">Successful</span></span>   |<span data-ttu-id="7dcd4-128">**最終更新** 列に時間が記載されている場合、データ ソースは正常に取り込まれました。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="7dcd4-129">開始前</span><span class="sxs-lookup"><span data-stu-id="7dcd4-129">Not started</span></span>   |<span data-ttu-id="7dcd4-130">データ ソースには、まだデータが取り込まれていないか、ドラフト モードのままです。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="7dcd4-131">更新中</span><span class="sxs-lookup"><span data-stu-id="7dcd4-131">Refreshing</span></span>    |<span data-ttu-id="7dcd4-132">データ取り込みが進行中です。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-132">Data ingestion is in progress.</span></span> <span data-ttu-id="7dcd4-133">この操作をキャンセルするには、**アクション** 列で **更新を中止** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="7dcd4-134">データ ソースの更新を停止すると、そのデータ ソースは最後の更新状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="7dcd4-135">失敗</span><span class="sxs-lookup"><span data-stu-id="7dcd4-135">Failed</span></span>     |<span data-ttu-id="7dcd4-136">データの取り込みでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="7dcd4-137">任意のデータ ソースの **ステータス** 列でで値を選択して、詳細をレビューします。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="7dcd4-138">**進捗状況の詳細** ペインで、**データ ソース** を展開します。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="7dcd4-139">**詳細の表示** を選択し、エラーの詳細や下流プロセスの更新など、更新ステータスのその他の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="7dcd4-140">データの読み込みには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-140">Loading data can take time.</span></span> <span data-ttu-id="7dcd4-141">正常に最新の情報に更新したら、**エンティティ** ページから取り込んだデータをレビューできます。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="7dcd4-142">詳細については、[エンティティ](entities.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="7dcd4-143">データ ソースの更新</span><span class="sxs-lookup"><span data-stu-id="7dcd4-143">Refresh a data source</span></span>

<span data-ttu-id="7dcd4-144">データ ソースは、自動スケジュールで更新することも、オンデマンドで手動で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="7dcd4-145">**管理** > **システム** > [**スケジュール**](system.md#schedule-tab) に移動し、取り込まれたデータ ソースすべてのスケジュール済みの更新を構成します。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="7dcd4-146">オンデマンドでデータ ソースを更新するには、次の手順を実行します:</span><span class="sxs-lookup"><span data-stu-id="7dcd4-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="7dcd4-147">対象者に関するインサイトで、**データ** > **データ ソース** に移動します。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="7dcd4-148">更新するデータ ソースの横にある縦の省略記号を選択し、ドロップダウン リストから **更新** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="7dcd4-149">これで、データ ソースが手動で更新されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="7dcd4-150">データ ソースを更新すると、データ ソースで指定されたすべてのエンティティのエンティティ スキーマとデータの両方が更新されます。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="7dcd4-151">既存の更新をキャンセルし、データ ソースを最後の更新状態に戻す場合は、**更新の停止** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="7dcd4-152">データ ソースの削除</span><span class="sxs-lookup"><span data-stu-id="7dcd4-152">Delete a data source</span></span>

1. <span data-ttu-id="7dcd4-153">対象者に関するインサイトで、**データ** > **データ ソース** に移動します。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="7dcd4-154">削除するデータ ソースの横にある縦の省略記号を選択し、ドロップダウン メニューから **削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="7dcd4-155">削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="7dcd4-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
