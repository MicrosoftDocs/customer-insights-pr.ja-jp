---
title: Customer Insights データを Adobe Experience Platform にエクスポート
description: Adobe Experience Platform で対象者に関するインサイト セグメントを使用する方法について説明します。
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760107"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="a725a-103">Adobe Experience Platform で Customer Insights セグメントの使用 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="a725a-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="a725a-104">Dynamics 365 Customer Insights の対象者インサイトのユーザーとして、関連する対象ユーザーをターゲットにすることで、マーケティング キャンペーンをより効率的にするためのセグメントを作成している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a725a-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="a725a-105">Adobe Experience Platform および Adobe Campaign Standardなどのアプリケーションで対象者に関するインサイトのセグメントを使用するには、この記事で概説するいくつかの手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a725a-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="この記事で概説されているステップのプロセス図。":::

## <a name="prerequisites"></a><span data-ttu-id="a725a-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="a725a-107">Prerequisites</span></span>

-   <span data-ttu-id="a725a-108">Dynamics 365 Customer Insights ライセンス</span><span class="sxs-lookup"><span data-stu-id="a725a-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="a725a-109">Adobe Experience Platform ライセンス</span><span class="sxs-lookup"><span data-stu-id="a725a-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="a725a-110">Adobe Campaign Standard ライセンス</span><span class="sxs-lookup"><span data-stu-id="a725a-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="a725a-111">Azure Blob Storage アカウント</span><span class="sxs-lookup"><span data-stu-id="a725a-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="a725a-112">キャンペーン概要</span><span class="sxs-lookup"><span data-stu-id="a725a-112">Campaign Overview</span></span>

<span data-ttu-id="a725a-113">Adobe Experience Platform で対象者に関するインサイトのセグメントを使用する方法をよりよく理解するために、架空のサンプル キャンペーンを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="a725a-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="a725a-114">あなたの会社が、米国の顧客に月次サブスクリプション ベースのサービスを提供していると仮定します。</span><span class="sxs-lookup"><span data-stu-id="a725a-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="a725a-115">今後 8 日以内にサブスクリプションの更新が予定されているが、サブスクリプションをまだ更新していない顧客を特定します。</span><span class="sxs-lookup"><span data-stu-id="a725a-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="a725a-116">これらの顧客を維持するために、Adobe Experience Platform を使用して、電子メールでプロモーション オファーを送信します。</span><span class="sxs-lookup"><span data-stu-id="a725a-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="a725a-117">この例では、メールのプロモーション キャンペーンを 1 回実行します。</span><span class="sxs-lookup"><span data-stu-id="a725a-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="a725a-118">この記事では、キャンペーンを複数回実行するユース ケースについては説明しません。</span><span class="sxs-lookup"><span data-stu-id="a725a-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="a725a-119">対象ユーザーの特定</span><span class="sxs-lookup"><span data-stu-id="a725a-119">Identify your target audience</span></span>

<span data-ttu-id="a725a-120">このシナリオでは、顧客の電子メール アドレスが対象者に関するインサイトで利用可能であり、セグメントのメンバーを特定するために顧客のプロモーションの好みが分析されたと仮定します。</span><span class="sxs-lookup"><span data-stu-id="a725a-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="a725a-121">[対象者に関するインサイトで定義したセグメント](segments.md) は **ChurnProneCustomers** と呼ばれ、これらの顧客に電子メール プロモーションを送信する予定です。</span><span class="sxs-lookup"><span data-stu-id="a725a-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers セグメントが作成されたセグメント ページのスクリーンショット。":::

<span data-ttu-id="a725a-123">送信するキャンペーン メールには、名、姓、顧客のサブスクリプション終了日が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a725a-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="a725a-124">サブスクリプションが終了する前に更新した場合に得られる割引について顧客に通知します。</span><span class="sxs-lookup"><span data-stu-id="a725a-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="a725a-125">対象ユーザーのエクスポート</span><span class="sxs-lookup"><span data-stu-id="a725a-125">Export your target audience</span></span>

<span data-ttu-id="a725a-126">対象ユーザーを特定した上で、対象者に関するインサイトから Azure Blob Storage アカウントへのエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a725a-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="a725a-127">接続の構成</span><span class="sxs-lookup"><span data-stu-id="a725a-127">Configure a connection</span></span>

1. <span data-ttu-id="a725a-128">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="a725a-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a725a-129">**つながりの追加** を選択し、**Azure Blob Storage** を選択するか、**Azure Blob Storage** タイルで **設定** を選択します:</span><span class="sxs-lookup"><span data-stu-id="a725a-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob Storage の構成タイル。"::: <span data-ttu-id="a725a-131">接続を構成するには。</span><span class="sxs-lookup"><span data-stu-id="a725a-131">to configure the connection.</span></span>

1. <span data-ttu-id="a725a-132">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="a725a-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a725a-133">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="a725a-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a725a-134">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a725a-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a725a-135">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a725a-135">Choose who can use this connection.</span></span> <span data-ttu-id="a725a-136">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="a725a-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a725a-137">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a725a-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a725a-138">セグメントをエクスポートする Blob Storage アカウントの **アカウント名**、**アカウント キー**、および **コンテナー** を入力します。</span><span class="sxs-lookup"><span data-stu-id="a725a-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="ストレージ アカウント構成のスクリーンショット。"::: 
   
    - <span data-ttu-id="a725a-140">Blob Storage アカウント名とアカウント キーを検索する方法の詳細については、[Azure ポータルでストレージ アカウントの設定を管理する](/azure/storage/common/storage-account-manage) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a725a-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="a725a-141">コンテナの作成方法については、[コンテナを作成する](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a725a-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="a725a-142">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="a725a-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="a725a-143">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="a725a-143">Configure an export</span></span>

<span data-ttu-id="a725a-144">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a725a-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a725a-145">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a725a-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a725a-146">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="a725a-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a725a-147">新しいエクスポートを作成するには、**エクスポートの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a725a-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="a725a-148">**エクスポートの接続** フィールドで、Azure Blob Storage セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="a725a-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="a725a-149">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="a725a-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a725a-150">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="a725a-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="a725a-151">この例では、**ChurnProneCustomers** です。</span><span class="sxs-lookup"><span data-stu-id="a725a-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers セグメントが選択されたセグメント選択ユーザー インターフェイスのスクリーンショット。":::

1. <span data-ttu-id="a725a-153">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a725a-153">Select **Save**.</span></span>

<span data-ttu-id="a725a-154">エクスポート先を保存した後、**データ** > **エクスポート** に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a725a-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="a725a-155">これで、[セグメントをオンデマンドでエクスポート](export-destinations.md#run-exports-on-demand) できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a725a-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="a725a-156">エクスポートは、[スケジュールされた更新](system.md) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="a725a-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a725a-157">エクスポートされたセグメントのレコード数が、Adobe Campaign Standard ライセンスの許可された制限内にあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a725a-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="a725a-158">エクスポートされたデータは、上記で構成した Azure Blob Storage コンテナーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="a725a-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="a725a-159">次のフォルダー パスがコンテナーに自動的に作成されます:</span><span class="sxs-lookup"><span data-stu-id="a725a-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="a725a-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="a725a-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="a725a-161">例: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="a725a-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="a725a-162">エクスポートされたエンティティの *model.json* は、*%ExportDestinationName%* レベルにあります。</span><span class="sxs-lookup"><span data-stu-id="a725a-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="a725a-163">例: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="a725a-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="a725a-164">Adobe Experience Platform でのエクスペリエンス データ モデル (XDM) の定義</span><span class="sxs-lookup"><span data-stu-id="a725a-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="a725a-165">対象者に関するインサイトからエクスポートされたデータを Adobe Experience Platform 内で使用する前に、エクスペリエンス データ モデル スキーマを定義し、[リアルタイム顧客プロファイルのデータを構成](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a725a-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="a725a-166">[XDM とは何か](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) を学び、[スキーマ構成の基本](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) について理解します。</span><span class="sxs-lookup"><span data-stu-id="a725a-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="a725a-167">Adobe Experience Platform にデータをインポート</span><span class="sxs-lookup"><span data-stu-id="a725a-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="a725a-168">すべてが整ったので、準備した対象ユーザー データを対象者に関するインサイトから Adobe Experience Platform にインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a725a-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="a725a-169">まず、[Azure Blob Storage のソース接続を作成](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started) します。</span><span class="sxs-lookup"><span data-stu-id="a725a-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="a725a-170">ソース接続を定義した後、クラウド ストレージ バッチ接続の [データフローを構成](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) して、対象者に関するインサイトから Adobe Experience Platform にセグメント出力をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a725a-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="a725a-171">Adobe Campaign Standard での対象ユーザーの作成</span><span class="sxs-lookup"><span data-stu-id="a725a-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="a725a-172">このキャンペーンのメールを送信するには、Adobe Campaign Standard を使用します。</span><span class="sxs-lookup"><span data-stu-id="a725a-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="a725a-173">データを Adobe Experience Platform にインポートした後、Adobe Experience Platform のデータを使用して、Adobe Campaign Standard で[対象ユーザーを作成](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a725a-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="a725a-174">Adobe Campaign Standard [セグメント ビルダーを使用](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) して、Adobe Experience Platform のデータに基づいて対象ユーザーを定義する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a725a-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="a725a-175">Adobe Campaign Standard を使用したメールの作成と送信</span><span class="sxs-lookup"><span data-stu-id="a725a-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="a725a-176">メール コンテンツを作成し、メールを [テストおよび送信](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) します。</span><span class="sxs-lookup"><span data-stu-id="a725a-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard からの更新キャンペーンを含むサンプル メール。":::
