---
title: リアルタイム データ インジェストと制限
description: 対象者に関するインサイトのリアルタイム機能に関する一般情報。
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598575"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="270b9-103">リアルタイム データ インジェスト (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="270b9-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="270b9-104">ほぼリアルタイムの機能により、顧客が製品やサービスに対して行った最新の対話を数秒で確認できます。</span><span class="sxs-lookup"><span data-stu-id="270b9-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="270b9-105">[スケジュールされた更新](system.md#schedule-tab) には、多数のレコードといくつかの複雑な操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="270b9-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="270b9-106">まず、データはデータ ソースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="270b9-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="270b9-107">次に、データが統合され、追加情報が追加されます。</span><span class="sxs-lookup"><span data-stu-id="270b9-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="270b9-108">このプロセスを実行するたびに、数分から数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="270b9-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="270b9-109">リアルタイム機能は、後続のスケジュールされた更新が、このデータをデータ ソースから取得するまで、データを即座に使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="270b9-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="270b9-110">リアルタイムの更新には有効期限があり、その後はデータ ソースからの値を上書きしなくなります。</span><span class="sxs-lookup"><span data-stu-id="270b9-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="270b9-111">プロファイルの更新は 4 時間保持されます</span><span class="sxs-lookup"><span data-stu-id="270b9-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="270b9-112">アクティビティは 30 日間保持されます</span><span class="sxs-lookup"><span data-stu-id="270b9-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="270b9-113">これらの値は、変更可能な API 呼び出しパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="270b9-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="270b9-114">これらは、ソース データの内容が変更されていないことを保証することを目指しています。</span><span class="sxs-lookup"><span data-stu-id="270b9-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="270b9-115">リアルタイムの更新をより長く含める場合は、データ ソースに追加して、次のスケジュールされた更新時に取得されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="270b9-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="270b9-116">統合された顧客プロファイル フィールドのリアルタイム更新</span><span class="sxs-lookup"><span data-stu-id="270b9-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="270b9-117">更新されたプロファイルは、数秒以内に顧客カード ビューまたはその他のビジュアル化で表示されます。</span><span class="sxs-lookup"><span data-stu-id="270b9-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="270b9-118">データの統合が行われた後にリアルタイムの操作が行われるため、統合された顧客プロファイルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="270b9-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="270b9-119">したがって、リアルタイムのプロファイル変更は、メジャー、セグメント メンバーシップ、またはエンリッチメントを更新しません。</span><span class="sxs-lookup"><span data-stu-id="270b9-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="270b9-120">制限</span><span class="sxs-lookup"><span data-stu-id="270b9-120">Limitations</span></span>

- <span data-ttu-id="270b9-121">顧客プロファイルは更新できますが、作成または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="270b9-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="270b9-122">Power BI のような外部システムへのリアルタイム更新のエクスポートは、現時点では不可能です。</span><span class="sxs-lookup"><span data-stu-id="270b9-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="270b9-123">活動のリアルタイム作成</span><span class="sxs-lookup"><span data-stu-id="270b9-123">Real-time creation of activities</span></span>

<span data-ttu-id="270b9-124">リアルタイム API を使用すると、ソース システム (個々のソース レコード) から統合顧客プロファイルに、新しい活動を公開できます。</span><span class="sxs-lookup"><span data-stu-id="270b9-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="270b9-125">新しいアクティビティは、その統合された顧客プロファイルのタイムラインで、数秒で統合されたアクティビティとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="270b9-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="270b9-126">タイムラインは、顧客カード ビューまたは構成したその他のタイムライン統合で確認できます。</span><span class="sxs-lookup"><span data-stu-id="270b9-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="270b9-127">活動は不変です。</span><span class="sxs-lookup"><span data-stu-id="270b9-127">Activities are immutable.</span></span> <span data-ttu-id="270b9-128">いったん作成されると、変更されません。</span><span class="sxs-lookup"><span data-stu-id="270b9-128">They don't change once created.</span></span>
> - <span data-ttu-id="270b9-129">現在、セグメントとメジャーは新しいアクティビティに基づいて更新されません。</span><span class="sxs-lookup"><span data-stu-id="270b9-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="270b9-130">リアルタイム API を介してのみ追加された活動はエクスポートの一部ではなく、PowerBI に表示されません。</span><span class="sxs-lookup"><span data-stu-id="270b9-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="270b9-131">リアルタイム API に接続する方法は 2 つあります:</span><span class="sxs-lookup"><span data-stu-id="270b9-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="270b9-132">[Dynamics 365 Customer Insights コネクタ](/connectors/customerinsights/)を使用して[間接的に](#connect-via-the-dynamics-365-customer-insights-connector)</span><span class="sxs-lookup"><span data-stu-id="270b9-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)</span></span>
- <span data-ttu-id="270b9-133">コードを使用して[直接](#connect-directly-to-the-real-time-api)</span><span class="sxs-lookup"><span data-stu-id="270b9-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="270b9-134">どちらの方法でも次の前提条件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="270b9-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="270b9-135">Customer Insights 環境</span><span class="sxs-lookup"><span data-stu-id="270b9-135">A Customer Insights environment</span></span>
- <span data-ttu-id="270b9-136">統合顧客プロファイル</span><span class="sxs-lookup"><span data-stu-id="270b9-136">Unified customer profiles</span></span>
- <span data-ttu-id="270b9-137">構成および実行される活動</span><span class="sxs-lookup"><span data-stu-id="270b9-137">Activities configured and run</span></span>
- <span data-ttu-id="270b9-138">アカウントを認証する共同作成者または管理者アクセス許可</span><span class="sxs-lookup"><span data-stu-id="270b9-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="270b9-139">Dynamics 365 Customer Insights コネクタ経由で接続</span><span class="sxs-lookup"><span data-stu-id="270b9-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="270b9-140">リアルタイム API は、専用 Power Platform コネクタ、[Dynamics 365 Customer Insights コネクタ](/connectors/customerinsights/) からデータを取り込むことができます。コードを記述してデプロイする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="270b9-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="270b9-141">コネクタは、API と同じリアルタイム アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="270b9-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="270b9-142">プレミアム コネクタの有効なライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="270b9-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="270b9-143">詳細については、[Power Apps と Power Automate のライセンスの FAQ](/power-platform/admin/powerapps-flow-licensing-faq)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="270b9-143">For more information, see [Power Apps and Power Automate licensing FAQs](/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="270b9-144">Power Platform [Power Apps や Power Automate](/connectors/)</span><span class="sxs-lookup"><span data-stu-id="270b9-144">Power Platform [Power Apps and/or Power Automate](/connectors/)</span></span>
- <span data-ttu-id="270b9-145">Azure [Logic Apps](/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="270b9-145">Azure [Logic Apps](/azure/connectors/apis-list)</span></span>

<span data-ttu-id="270b9-146">フローの作成の詳細については、[Power Automate ドキュメンテーション](/power-automate/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="270b9-146">For details about creating flows, see the [Power Automate documentation](/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="270b9-147">リアルタイム API に直接接続する</span><span class="sxs-lookup"><span data-stu-id="270b9-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="270b9-148">独自のパイプラインを構築し、リアルタイム API に直接接続することで、リアルタイム機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="270b9-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="270b9-149">ソース システムの形式または UnifiedActivity 形式で活動を投稿できます。</span><span class="sxs-lookup"><span data-stu-id="270b9-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="270b9-150">/api/instances/{instanceId}/manage/entities/UnifiedActivity への API 呼び出しを行って形式を取得します。</span><span class="sxs-lookup"><span data-stu-id="270b9-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="270b9-151">パラメーターや応答など、この API の詳細については、[Customer Insights API リファレンス](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) の **EntityData** のセクションにあります。</span><span class="sxs-lookup"><span data-stu-id="270b9-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="270b9-152">詳細については、[Customer Insights API の使用](apis.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="270b9-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="270b9-153">テレメトリを使用してリアルタイムの使用状況を把握する</span><span class="sxs-lookup"><span data-stu-id="270b9-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="270b9-154">リアルタイム API への要求の量の概要と、システムで発生する可能性のある問題に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="270b9-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="270b9-155">[リアルタイム テレメトリにアクセス](system.md#api-usage-tab)できます。</span><span class="sxs-lookup"><span data-stu-id="270b9-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]