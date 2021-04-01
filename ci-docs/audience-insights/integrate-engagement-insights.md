---
title: エンゲージメント インサイトからの Web データを対象者インサイトと統合する
description: エンゲージメント インサイトから対象者インサイトまで顧客に関する Web 情報を提供します。
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 14ebff30d3ec7fc52dca6f86136309a3f454fa27
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597471"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="b3581-103">エンゲージメント インサイトからの Web データを対象者インサイトと統合する</span><span class="sxs-lookup"><span data-stu-id="b3581-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="b3581-104">顧客は多くの場合、Web サイトを使用してオンラインで日常的なトランザクションを行います。</span><span class="sxs-lookup"><span data-stu-id="b3581-104">Customers often do their day to day transactions online using web sites.</span></span> <span data-ttu-id="b3581-105">Dynamics 365 Customer Insights のエンゲージメント インサイト機能は、Web データをソースとして統合するための便利なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="b3581-105">The engagement insights capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="b3581-106">トランザクション、人口統計、または行動データに加えて、統一された顧客プロファイルで Web 上のアクティビティを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b3581-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="b3581-107">このプロファイルを使用して、対象者をアクティブ化するためのセグメント、メジャー、予測などのその他のインサイトを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="b3581-107">We can use this profile to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="b3581-108">この記事では、エンゲージメント インサイトから既存の対象者インサイト環境に顧客の Web アクティビティ データを取り込む手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3581-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="b3581-109">この例では、統一された顧客プロファイルを含む環境を想定しています。</span><span class="sxs-lookup"><span data-stu-id="b3581-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="b3581-110">プロファイルは、調査、小売販売、およびチケット システムからのソースと統合されています。</span><span class="sxs-lookup"><span data-stu-id="b3581-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="b3581-111">また、顧客の関連アクティビティも表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3581-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="b3581-112">ここで、顧客が当社の Web プロパティにアクセスして、そのアクティビティを理解しているかどうかを確認したいと思います。</span><span class="sxs-lookup"><span data-stu-id="b3581-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="b3581-113">アクティビティには、たとえば、メールで受信したリンクから Web サイトにアクセスしたり製品ページを表示したりすることが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b3581-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b3581-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="b3581-114">Prerequisites</span></span>

<span data-ttu-id="b3581-115">エンゲージメント インサイトからのデータを統合するには、いくつかの前提条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3581-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="b3581-116">エンゲージメント インサイト SDK を Web サイトに統合します。</span><span class="sxs-lookup"><span data-stu-id="b3581-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="b3581-117">詳細については、[Web SDK を開始する](../engagement-insights/instrument-website.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3581-117">For more information, see [Get started with the web SDK](../engagement-insights/instrument-website.md).</span></span>
- <span data-ttu-id="b3581-118">エンゲージメント インサイトから Web イベントをエクスポートするには、Web イベントデータを対象者インサイトに取り込むために使用される ADLS Gen 2 ストレージ アカウントにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3581-118">Exporting web events from engagement insights requires access to an ADLS Gen 2 storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="b3581-119">詳細については、[イベントのエクスポート](../engagement-insights/export-events.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3581-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="b3581-120">エンゲージメント インサイトで詳細なイベントを構成する</span><span class="sxs-lookup"><span data-stu-id="b3581-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="b3581-121">管理者がエンゲージメント インサイト SDK を使用して Web サイトをインストルメント化した後、ユーザーが Web ページを表示したり、どこかをクリックすると、*ベース イベント* が収集されます。</span><span class="sxs-lookup"><span data-stu-id="b3581-121">After an administrator instrumented a website with the engagement insights SDK, *base events* are gathered when a user views a web page or clicks somewhere.</span></span> <span data-ttu-id="b3581-122">基本イベントには多くの詳細が含まれる傾向があります。</span><span class="sxs-lookup"><span data-stu-id="b3581-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="b3581-123">ユース ケースに応じて、基本イベントにはデータのサブセットのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="b3581-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="b3581-124">エンゲージメント インサイトでは、選択した基本イベントのプロパティのみが含まれる *詳細なイベント* を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b3581-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="b3581-125">詳しくは、[詳細なイベントを作成および変更する](../engagement-insights/refined-events.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3581-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="b3581-126">詳細なイベントを作成する際の考慮事項:</span><span class="sxs-lookup"><span data-stu-id="b3581-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="b3581-127">詳細なイベントには意味のある名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="b3581-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="b3581-128">対象者インサイトでアクティビティ名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="b3581-128">It's be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="b3581-129">対象者インサイトでアクティビティを作成するには、少なくとも次のプロパティを選択してください。</span><span class="sxs-lookup"><span data-stu-id="b3581-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="b3581-130">Signal.Action.Name - アクティビティの詳細を示します</span><span class="sxs-lookup"><span data-stu-id="b3581-130">Signal.Action.Name - indicating the activity details</span></span>
    - <span data-ttu-id="b3581-131">Signal.User.Id - 顧客 ID でマッピングするために使用されます</span><span class="sxs-lookup"><span data-stu-id="b3581-131">Signal.User.Id - used to map with the customer ID</span></span>
    - <span data-ttu-id="b3581-132">Signal.View.Uri - セグメントまたはメジャーの基礎となる Web アドレスとして使用されます</span><span class="sxs-lookup"><span data-stu-id="b3581-132">Signal.View.Uri - used as a web address as a basis for segments or measures</span></span>
    - <span data-ttu-id="b3581-133">Signal.Export.Id - イベントの主キーとして使用します</span><span class="sxs-lookup"><span data-stu-id="b3581-133">Signal.Export.Id - to use as a primary key for events</span></span> <!-- system generated, do we need to list?-->
    - <span data-ttu-id="b3581-134">Signal.Timestamp - アクティビティの日時を決定します</span><span class="sxs-lookup"><span data-stu-id="b3581-134">Signal.Timestamp - to determine the date and time for the activity</span></span>

<span data-ttu-id="b3581-135">フィルターを選択して、ユース ケースにとって重要なイベントとページに焦点を合わせます。</span><span class="sxs-lookup"><span data-stu-id="b3581-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="b3581-136">この例では、「メール プロモーション」というアクション名を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3581-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="b3581-137">詳細な Web イベントをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b3581-137">Export the Refined Web Events</span></span> 

<span data-ttu-id="b3581-138">詳細なイベントを定義した後、イベント データの Azure Data Lake Storage へのエクスポートを構成する必要があります、これは、対象者インサイトで取り込むためのデータ ソースとして設定できます。</span><span class="sxs-lookup"><span data-stu-id="b3581-138">After defining the refined event is defined, you have to configure the export of the event data to an Azure Data Lake Storage, that can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="b3581-139">イベントが Web プロパティから流れるのと平行して、エクスポートは常時発生します。</span><span class="sxs-lookup"><span data-stu-id="b3581-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="b3581-140">詳細については、[イベントのエクスポート](../engagement-insights/export-events.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3581-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="b3581-141">イベント データを対象者インサイトに取り込む</span><span class="sxs-lookup"><span data-stu-id="b3581-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="b3581-142">詳細なイベントを定義し、そのエクスポートを構成したので、次にデータを対象者インサイトに取り込みます。</span><span class="sxs-lookup"><span data-stu-id="b3581-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="b3581-143">Common Data Model フォルダーに基づいて新しいデータ ソースを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3581-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="b3581-144">イベントのエクスポート先であるストレージ アカウントの詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="b3581-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="b3581-145">*default.cdm.json* ファイルで、詳細なイベントを選択して取り込み、対象者インサイトでエンティティを作成します。</span><span class="sxs-lookup"><span data-stu-id="b3581-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="b3581-146">詳細については、[Azure Data Lake アカウントを使用して Common Data Model フォルダーに接続する](connect-common-data-model.md)を参照してください</span><span class="sxs-lookup"><span data-stu-id="b3581-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md)</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="b3581-147">詳細なイベント データを顧客プロファイルのアクティビティとして関連付けます</span><span class="sxs-lookup"><span data-stu-id="b3581-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="b3581-148">エンティティの取り込みが完了したら、顧客プロファイルのアクティビティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b3581-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="b3581-149">詳細については、[顧客アクティビティ](activities.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3581-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="アクティビティの編集ペインが展開され、フィールドに値が入力されたアクティビティ ページ。":::

<span data-ttu-id="b3581-151">次のマッピングを使用して新しいアクティビティを構成します。</span><span class="sxs-lookup"><span data-stu-id="b3581-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="b3581-152">**主キー:** Signal.Export.Id、エンゲージメント インサイトのすべてのイベント レコードで使用できる一意の ID。</span><span class="sxs-lookup"><span data-stu-id="b3581-152">**Primary Key:** Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="b3581-153">このプロパティは自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="b3581-153">This property is automatically generated.</span></span>

- <span data-ttu-id="b3581-154">**タイムスタンプ:** イベント プロパティの Signal.Timestamp。</span><span class="sxs-lookup"><span data-stu-id="b3581-154">**Timestamp:** Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="b3581-155">**イベント:** 追跡するイベント名である Signal.Name。</span><span class="sxs-lookup"><span data-stu-id="b3581-155">**Event:** Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="b3581-156">**Web アドレス:** イベントを作成したページの URI を参照する Signal.View.Uri。</span><span class="sxs-lookup"><span data-stu-id="b3581-156">**Web address:** Signal.View.Uri referring to the uri of the page that created the event.</span></span>

- <span data-ttu-id="b3581-157">**詳細:** イベントに関連付ける情報を表す Signal.Action.Name。</span><span class="sxs-lookup"><span data-stu-id="b3581-157">**Details:** Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="b3581-158">このケースで選択されたプロパティは、イベントがメール プロモーション用であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="b3581-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="b3581-159">**アクティビティ タイプ:** この例では、既存のアクティビティ タイプである WebLog を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3581-159">**Activity type:** In this example, we choose the exsting activity type WebLog.</span></span> <span data-ttu-id="b3581-160">この選択は、予測モデルを実行したり、このアクティビティ タイプに基づいてセグメントを作成したりするための便利なフィルター オプションです。</span><span class="sxs-lookup"><span data-stu-id="b3581-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="b3581-161">**関係を設定する:** この重要な設定では、アクティビティを既存の顧客プロファイルに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="b3581-161">**Set up relationship:** This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="b3581-162">**Signal.User.Id** は、収集される SDK で構成された識別子であり、対象者インサイトで構成された他のデータ ソースのユーザー ID に関連しています。</span><span class="sxs-lookup"><span data-stu-id="b3581-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="b3581-163">この例では、Signal.User.Id と RetailCustomers:CustomerRetailId の間の関係を構成します。これは、データ統合プロセスのマップ ステップで定義された主キーです。</span><span class="sxs-lookup"><span data-stu-id="b3581-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was deinfed in the map step of the data unification process.</span></span>


<span data-ttu-id="b3581-164">アクティビティを処理した後、顧客レコードを確認し、顧客カードを開いて、タイムラインのエンゲージメント インサイトからアクティビティを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b3581-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="b3581-165">エンゲージメント インサイト アクティビティがある顧客 ID を見つけるには、**エンティティ** に移動して、UnifiedActivity エンティティのデータをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="b3581-165">To find a customer id that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="b3581-166">ActivityTypeDisplay = WebLog には、上記の例で構成されたエンゲージメント インサイト アクティビティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b3581-166">ActivityTypeDisplay = WebLog contain the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="b3581-167">これらのレコードの 1 つとその ID の顧客 ID を **顧客** ページにコピーします。</span><span class="sxs-lookup"><span data-stu-id="b3581-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b3581-168">次のステップ</span><span class="sxs-lookup"><span data-stu-id="b3581-168">Next Steps</span></span>

<span data-ttu-id="b3581-169">これで、[セグメント](segments.md)、[メジャー](measures.md)、および[予測](predictions.md)を作成して、顧客と有意義な関係を築くことができます。</span><span class="sxs-lookup"><span data-stu-id="b3581-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]