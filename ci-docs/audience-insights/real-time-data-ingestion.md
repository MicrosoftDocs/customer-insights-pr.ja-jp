---
title: リアルタイム データ インジェストと制限
description: 対象者に関するインサイトのリアルタイム機能に関する一般情報。
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00a72e6a67e33c8e70ccc6139c5e62020f9d3e1
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689181"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="6e016-103">リアルタイム データ インジェスト (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="6e016-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="6e016-104">ほぼリアルタイムの機能により、顧客が製品やサービスに対して行った最新の対話を数秒で確認できます。</span><span class="sxs-lookup"><span data-stu-id="6e016-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="6e016-105">[スケジュールされた更新](system.md#schedule-tab) には、多数のレコードといくつかの複雑な操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6e016-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="6e016-106">まず、データはデータ ソースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="6e016-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="6e016-107">次に、データが統合され、追加情報が追加されます。</span><span class="sxs-lookup"><span data-stu-id="6e016-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="6e016-108">このプロセスを実行するたびに、数分から数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="6e016-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="6e016-109">リアルタイム機能は、後続のスケジュールされた更新が、このデータをデータ ソースから取得するまで、データを即座に使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6e016-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="6e016-110">リアルタイムの更新には有効期限があり、その後はデータ ソースからの値を上書きしなくなります。</span><span class="sxs-lookup"><span data-stu-id="6e016-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="6e016-111">プロファイルの更新は 4 時間保持されます</span><span class="sxs-lookup"><span data-stu-id="6e016-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="6e016-112">アクティビティは 30 日間保持されます</span><span class="sxs-lookup"><span data-stu-id="6e016-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="6e016-113">これらの値は、変更可能な API 呼び出しパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="6e016-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="6e016-114">これらは、ソース データの内容が変更されていないことを保証することを目指しています。</span><span class="sxs-lookup"><span data-stu-id="6e016-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="6e016-115">リアルタイムの更新をより長く含める場合は、データ ソースに追加して、次のスケジュールされた更新時に取得されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e016-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="6e016-116">統合された顧客プロファイル フィールドのリアルタイム更新</span><span class="sxs-lookup"><span data-stu-id="6e016-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="6e016-117">更新されたプロファイルは、数秒以内に顧客カード ビューまたはその他のビジュアル化で表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e016-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="6e016-118">データの統合が行われた後にリアルタイムの操作が行われるため、統合された顧客プロファイルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6e016-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="6e016-119">したがって、リアルタイムのプロファイル変更は、メジャー、セグメント メンバーシップ、またはエンリッチメントを更新しません。</span><span class="sxs-lookup"><span data-stu-id="6e016-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="6e016-120">制限</span><span class="sxs-lookup"><span data-stu-id="6e016-120">Limitations</span></span>

- <span data-ttu-id="6e016-121">顧客プロファイルは更新できますが、作成または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="6e016-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="6e016-122">Power BI のような外部システムへのリアルタイム更新のエクスポートは、現時点では不可能です。</span><span class="sxs-lookup"><span data-stu-id="6e016-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="6e016-123">活動のリアルタイム作成</span><span class="sxs-lookup"><span data-stu-id="6e016-123">Real-time creation of activities</span></span>

<span data-ttu-id="6e016-124">リアルタイム API を使用すると、ソース システム (個々のソース レコード) から統合顧客プロファイルに、新しい活動を公開できます。</span><span class="sxs-lookup"><span data-stu-id="6e016-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="6e016-125">新しい活動は、統合された顧客プロファイルのタイムラインで統合された活動として数秒以内に利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="6e016-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="6e016-126">タイムラインは、顧客カード ビューまたは構成したその他のタイムライン統合で確認できます。</span><span class="sxs-lookup"><span data-stu-id="6e016-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="6e016-127">活動は不変です。</span><span class="sxs-lookup"><span data-stu-id="6e016-127">Activities are immutable.</span></span> <span data-ttu-id="6e016-128">いったん作成されると、変更されません。</span><span class="sxs-lookup"><span data-stu-id="6e016-128">They don't change once created.</span></span>
> - <span data-ttu-id="6e016-129">現在、セグメントとメジャーは新しいアクティビティに基づいて更新されません。</span><span class="sxs-lookup"><span data-stu-id="6e016-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="6e016-130">リアルタイム API を介してのみ追加された活動はエクスポートの一部ではなく、PowerBI に表示されません。</span><span class="sxs-lookup"><span data-stu-id="6e016-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="6e016-131">リアルタイム API に接続する方法は 2 つあります:</span><span class="sxs-lookup"><span data-stu-id="6e016-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="6e016-132">[Dynamics 365 Customer Insights コネクタ](https://docs.microsoft.com/connectors/customerinsights/)を使用して[間接的に](#connect-via-the-dynamics-365-customer-insights-connector)</span><span class="sxs-lookup"><span data-stu-id="6e016-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="6e016-133">コードを使用して[直接](#connect-directly-to-the-real-time-api)</span><span class="sxs-lookup"><span data-stu-id="6e016-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="6e016-134">どちらの方法でも次の前提条件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="6e016-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="6e016-135">Customer Insights 環境</span><span class="sxs-lookup"><span data-stu-id="6e016-135">A Customer Insights environment</span></span>
- <span data-ttu-id="6e016-136">統合顧客プロファイル</span><span class="sxs-lookup"><span data-stu-id="6e016-136">Unified customer profiles</span></span>
- <span data-ttu-id="6e016-137">構成および実行される活動</span><span class="sxs-lookup"><span data-stu-id="6e016-137">Activities configured and run</span></span>
- <span data-ttu-id="6e016-138">アカウントを認証する共同作成者または管理者アクセス許可</span><span class="sxs-lookup"><span data-stu-id="6e016-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="6e016-139">Dynamics 365 Customer Insights コネクタ経由で接続</span><span class="sxs-lookup"><span data-stu-id="6e016-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="6e016-140">リアルタイム API は、専用 Power Platform コネクタ、[Dynamics 365 Customer Insights コネクタ](https://docs.microsoft.com/connectors/customerinsights/) からデータを取り込むことができます。コードを記述してデプロイする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6e016-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="6e016-141">コネクタは、API と同じリアルタイム アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6e016-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="6e016-142">プレミアム コネクタの有効なライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="6e016-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="6e016-143">詳細については、[Power Apps と Power Automate のライセンスの FAQ](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e016-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="6e016-144">Power Platform [Power Apps や Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="6e016-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="6e016-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="6e016-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="6e016-146">フローの作成の詳細については、[Power Automate ドキュメンテーション](https://docs.microsoft.com/power-automate/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e016-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="6e016-147">リアルタイム API に直接接続する</span><span class="sxs-lookup"><span data-stu-id="6e016-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="6e016-148">独自のパイプラインを構築し、リアルタイム API に直接接続することで、リアルタイム機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e016-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="6e016-149">ソース システムの形式または UnifiedActivity 形式で活動を投稿できます。</span><span class="sxs-lookup"><span data-stu-id="6e016-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="6e016-150">/api/instances/{instanceId}/manage/entities/UnifiedActivity への API 呼び出しを行って形式を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e016-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="6e016-151">パラメーターや応答など、この API の詳細については、[Customer Insights API リファレンス](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) の **EntityData** のセクションにあります。</span><span class="sxs-lookup"><span data-stu-id="6e016-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="6e016-152">詳細については、[Customer Insights API の使用](apis.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e016-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="6e016-153">テレメトリを使用してリアルタイムの使用状況を把握する</span><span class="sxs-lookup"><span data-stu-id="6e016-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="6e016-154">リアルタイム API への要求の量の概要と、システムで発生する可能性のある問題に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e016-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="6e016-155">[リアルタイム テレメトリにアクセス](system.md#api-usage-tab) するには、**管理** > **システム** > **API の使用** に移動します。</span><span class="sxs-lookup"><span data-stu-id="6e016-155">You can [access the real-time telemetry](system.md#api-usage-tab) by going to **Admin** > **System** > **API usage**.</span></span> <span data-ttu-id="6e016-156">**操作** テーブルでは、リアルタイム メソッドを使用する API 操作の行に、リアルタイム API の使用状況を表示するボタンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e016-156">In the **Operations** table, rows for API operations which use the real-time methods contain a button to view real-time API usage.</span></span> <span data-ttu-id="6e016-157">ボタンは双眼鏡マークで視覚化されています。</span><span class="sxs-lookup"><span data-stu-id="6e016-157">The button is visualized with a binocular symbol.</span></span> <span data-ttu-id="6e016-158">ボタンを選択して、現在の環境でリアルタイム API の使用状況の詳細を含むサイド ペインを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e016-158">Select the button to open a side pane containing usage details for the real-time API usage in the current environment.</span></span>

<span data-ttu-id="6e016-159">**グループ化** セレクターを使用して、過去 24 時間から過去 30 日間までのタイムライン上でリアルタイムのインタラクションを最適に表示する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e016-159">Use the **Group by** selector to choose how to best present your real-time interactions on a timeline ranging from the last 24 hours to the last 30 days.</span></span> <span data-ttu-id="6e016-160">API メソッド、エンティティー修飾名 (取り込んだエンティティー)、作成者 (イベントのソース)、結果 (成功または失敗)、またはエラー コード別にデータをグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="6e016-160">You can group the data by API method, entity qualified name (ingested entity), created by (source of the event), result (success or failure) or error codes.</span></span> <span data-ttu-id="6e016-161">データは履歴グラフおよびテーブルとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="6e016-161">The data is available as a history chart and as a table.</span></span>
