---
title: データ ソースを使用してデータを取り込む
description: さまざまなソースからデータをインポートする方法について説明します。
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595953"
---
# <a name="data-sources-overview"></a><span data-ttu-id="ec1a9-103">データ ソースの概要</span><span class="sxs-lookup"><span data-stu-id="ec1a9-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ec1a9-104">Dynamics 365 Customer Insights の対象者に関するインサイト機能は、幅広いソースからのデータに接続します。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="ec1a9-105">データ ソースへの接続は、多くの場合、*データ取り込み* のプロセスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="ec1a9-106">データを取り込んだ後、[統合](data-unification.md) およびアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="ec1a9-107">データ ソースの追加</span><span class="sxs-lookup"><span data-stu-id="ec1a9-107">Add a data source</span></span>

<span data-ttu-id="ec1a9-108">選択したオプションに応じて、データ ソースを追加する方法に関する詳細な記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="ec1a9-109">データ ソースは、主に次の 3 つの方法で追加できます:</span><span class="sxs-lookup"><span data-stu-id="ec1a9-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="ec1a9-110">多数の Power Query コネクタを使用して</span><span class="sxs-lookup"><span data-stu-id="ec1a9-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="ec1a9-111">Common Data Model フォルダーから</span><span class="sxs-lookup"><span data-stu-id="ec1a9-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="ec1a9-112">自分の Common Data Service レイク から</span><span class="sxs-lookup"><span data-stu-id="ec1a9-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="ec1a9-113">オンプレミスのデータ ソースからのデータはまだ追加できません。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="ec1a9-114">取り込んだデータのレビュー</span><span class="sxs-lookup"><span data-stu-id="ec1a9-114">Review ingested data</span></span>

<span data-ttu-id="ec1a9-115">取り込んだ各データ ソースの名前、状態、ソースのデータが最後に更新された時刻が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="ec1a9-116">データ ソースの一覧を列ごとに並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ec1a9-117">![追加されたデータ ソース](media/configure-data-datasource-added.png "追加されたデータ ソース")</span><span class="sxs-lookup"><span data-stu-id="ec1a9-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="ec1a9-118">ステータス</span><span class="sxs-lookup"><span data-stu-id="ec1a9-118">Status</span></span>  |<span data-ttu-id="ec1a9-119">内容</span><span class="sxs-lookup"><span data-stu-id="ec1a9-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="ec1a9-120">成功</span><span class="sxs-lookup"><span data-stu-id="ec1a9-120">Successful</span></span>   |<span data-ttu-id="ec1a9-121">**最終更新** 列に時間が記載されている場合、データ ソースは正常に取り込まれました。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="ec1a9-122">開始前</span><span class="sxs-lookup"><span data-stu-id="ec1a9-122">Not started</span></span>   |<span data-ttu-id="ec1a9-123">データ ソースには、まだデータが取り込まれていないか、ドラフト モードのままです。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="ec1a9-124">更新中</span><span class="sxs-lookup"><span data-stu-id="ec1a9-124">Refreshing</span></span>    |<span data-ttu-id="ec1a9-125">データ取り込みが進行中です。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-125">Data ingestion is in progress.</span></span> <span data-ttu-id="ec1a9-126">この操作をキャンセルするには、**アクション** 列で **更新を中止** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="ec1a9-127">データ ソースの更新を停止すると、そのデータ ソースは最後の更新状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="ec1a9-128">失敗</span><span class="sxs-lookup"><span data-stu-id="ec1a9-128">Failed</span></span>     |<span data-ttu-id="ec1a9-129">データの取り込みでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="ec1a9-130">任意のデータ ソースの **ステータス** 列でで値を選択して、詳細をレビューします。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="ec1a9-131">**進捗状況の詳細** ペインで、**データ ソース** を展開します。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="ec1a9-132">**詳細の表示** を選択し、エラーの詳細や下流プロセスの更新など、更新ステータスのその他の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="ec1a9-133">データの読み込みには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-133">Loading data can take some time.</span></span> <span data-ttu-id="ec1a9-134">正常に最新の情報に更新したら、**エンティティ** ページから取り込んだデータをレビューできます。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="ec1a9-135">詳細については、[エンティティ](entities.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="ec1a9-136">データ ソースの更新</span><span class="sxs-lookup"><span data-stu-id="ec1a9-136">Refresh a data source</span></span>

<span data-ttu-id="ec1a9-137">データ ソースは、自動スケジュールで更新することも、オンデマンドで手動で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="ec1a9-138">**管理** > **システム** > [**スケジュール**](system.md#schedule-tab) に移動し、取り込まれたデータ ソースすべてのスケジュール済みの更新を構成します。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="ec1a9-139">オンデマンドでデータ ソースを更新するには、次の手順を実行します:</span><span class="sxs-lookup"><span data-stu-id="ec1a9-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="ec1a9-140">対象者に関するインサイトで、**データ** > **データ ソース** に移動します</span><span class="sxs-lookup"><span data-stu-id="ec1a9-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="ec1a9-141">更新するデータ ソースの横にある縦の省略記号を選択して、ドロップダウンリストから **更新** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="ec1a9-142">これで、データ ソースが手動で更新されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="ec1a9-143">データ ソースを更新すると、エンティティ スキーマと、データ ソースで指定されているすべてのエンティティのデータの両方が更新されます。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="ec1a9-144">既存の更新をキャンセルし、データ ソースを最後の更新状態に戻す場合は、**更新の停止** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="ec1a9-145">データ ソースの削除</span><span class="sxs-lookup"><span data-stu-id="ec1a9-145">Delete a data source</span></span>

1. <span data-ttu-id="ec1a9-146">対象者に関するインサイトで、**データ** > **データ ソース** に移動します。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="ec1a9-147">削除するデータ ソースの横にある縦の省略記号を選択し、ドロップダウンメニューから **削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="ec1a9-148">削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="ec1a9-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]