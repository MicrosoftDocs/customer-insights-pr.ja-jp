---
title: Customer Insights データを Adobe Campaign Standard にエクスポート
description: Adobe CampaignStandard で対象者に関するインサイト セグメントを使用する方法について説明します。
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305392"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="0edcf-103">Adobe CampaignStandard で Customer Insights セグメントの使用 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="0edcf-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="0edcf-104">Dynamics 365 Customer Insights の対象者に関するインサイトのユーザーとして、関連する対象ユーザーをターゲットにすることで、マーケティング キャンペーンをより効率的にするためのセグメントが作成された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0edcf-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="0edcf-105">Adobe Experience Platform および Adobe Campaign Standardなどのアプリケーションで対象者に関するインサイトのセグメントを使用するには、この記事で概説するいくつかの手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0edcf-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="この記事で概説されているステップのプロセス図。":::

## <a name="prerequisites"></a><span data-ttu-id="0edcf-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="0edcf-107">Prerequisites</span></span>

-   <span data-ttu-id="0edcf-108">Dynamics 365 Customer Insights ライセンス</span><span class="sxs-lookup"><span data-stu-id="0edcf-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="0edcf-109">Adobe Campaign Standard ライセンス</span><span class="sxs-lookup"><span data-stu-id="0edcf-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="0edcf-110">Azure Blob Storage アカウント</span><span class="sxs-lookup"><span data-stu-id="0edcf-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="0edcf-111">キャンペーン 概要</span><span class="sxs-lookup"><span data-stu-id="0edcf-111">Campaign overview</span></span>

<span data-ttu-id="0edcf-112">Adobe Experience Platform で対象者に関するインサイトのセグメントを使用する方法をよりよく理解するために、架空のサンプル キャンペーンを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="0edcf-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="0edcf-113">あなたの会社が、米国の顧客に月次サブスクリプション ベースのサービスを提供していると仮定します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="0edcf-114">今後 8 日以内にサブスクリプションの更新が予定されているが、サブスクリプションをまだ更新していない顧客を特定します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="0edcf-115">これらの顧客を維持するために、Adobe Campaign Standard を使用して、電子メールでプロモーション オファーを送信します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="0edcf-116">この例では、メールのプロモーション キャンペーンを 1 回実行します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="0edcf-117">この記事では、キャンペーンを複数回実行するユース ケースについては説明しません。</span><span class="sxs-lookup"><span data-stu-id="0edcf-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="0edcf-118">ただし、対象者に関するインサイトと Adobe Campaign Standard は、定期的なキャンペーン シナリオでも機能するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="0edcf-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="0edcf-119">対象ユーザーの特定</span><span class="sxs-lookup"><span data-stu-id="0edcf-119">Identify your target audience</span></span>

<span data-ttu-id="0edcf-120">このシナリオでは、顧客の電子メール アドレスが対象者に関するインサイトで利用可能であり、セグメントのメンバーを特定するために顧客のプロモーションの好みが分析されたと仮定します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="0edcf-121">[対象者に関するインサイトで定義したセグメント](segments.md) は **ChurnProneCustomers** と呼ばれ、これらの顧客に電子メール プロモーションを送信する予定です。</span><span class="sxs-lookup"><span data-stu-id="0edcf-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers セグメントが作成されたセグメント ページのスクリーンショット。":::

<span data-ttu-id="0edcf-123">送信するキャンペーン メールには、名、姓、顧客のサブスクリプション終了日が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0edcf-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="0edcf-124">サブスクリプションが終了する前に更新した場合に得られる割引について顧客に通知します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="0edcf-125">対象ユーザーのエクスポート</span><span class="sxs-lookup"><span data-stu-id="0edcf-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="0edcf-126">接続の構成</span><span class="sxs-lookup"><span data-stu-id="0edcf-126">Configure a connection</span></span>

<span data-ttu-id="0edcf-127">対象ユーザーを特定した上で、対象者に関するインサイトから Azure Blob Storage アカウントへのエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0edcf-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="0edcf-128">対象者に関するインサイトで、**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0edcf-129">接続を構成するには、**接続の追加** を選択し、**Adobe Campaign** を選ぶか、**Adobe Campaign** タイルで **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard の構成タイル。":::

1. <span data-ttu-id="0edcf-131">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="0edcf-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0edcf-132">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0edcf-133">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0edcf-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0edcf-134">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-134">Choose who can use this connection.</span></span> <span data-ttu-id="0edcf-135">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="0edcf-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0edcf-136">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0edcf-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0edcf-137">セグメントをエクスポートする Azure Blob Storage アカウントの **アカウント名**、**アカウント キー**、および **コンテナー** を入力します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="ストレージ アカウント構成のスクリーンショット。"::: 

   - <span data-ttu-id="0edcf-139">Azure Blob Storage アカウント名とアカウント キーを見つける方法の詳細については、[Azure portal でストレージ アカウント設定を管理する](/azure/storage/common/storage-account-manage) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0edcf-139">To learn more about how to find the Azure Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="0edcf-140">コンテナの作成方法については、[コンテナを作成する](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0edcf-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="0edcf-141">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="0edcf-142">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="0edcf-142">Configure an export</span></span>

<span data-ttu-id="0edcf-143">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0edcf-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0edcf-144">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0edcf-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0edcf-145">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0edcf-146">新しいエクスポートを作成するには、**エクスポートの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="0edcf-147">**エクスポートの接続** フィールドで、Adobe Campaign セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="0edcf-148">このセクション名が表示されない場合、この種類の接続は利用できません。</span><span class="sxs-lookup"><span data-stu-id="0edcf-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="0edcf-149">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="0edcf-150">この例では、**ChurnProneCustomers** です。</span><span class="sxs-lookup"><span data-stu-id="0edcf-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers セグメントが選択されたセグメント選択ユーザー インターフェイスのスクリーンショット。":::

1. <span data-ttu-id="0edcf-152">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-152">Select **Next**.</span></span>

1. <span data-ttu-id="0edcf-153">次に、対象者に関するインサイト セグメントの **ソース** フィールドを Adobe Campaign Standard プロファイル スキーマの **ターゲット** フィールド名にマップします。</span><span class="sxs-lookup"><span data-stu-id="0edcf-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard コネクタのフィールド マッピング。":::

   <span data-ttu-id="0edcf-155">属性をさらに追加する場合は、**属性の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="0edcf-156">ターゲット名はソース フィールド名と異なることがあるため、2 つのシステムでフィールド名が同じでない場合でも、対象者に関するインサイトからのセグメント出力を Adobe Campaign Standard にマップできます。</span><span class="sxs-lookup"><span data-stu-id="0edcf-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0edcf-157">メール アドレスは ID フィールドとして使用されますが、対象者に関するインサイトの顧客プロファイルからその他の識別子を使用して、データを Adobe Campaign Standard にマップできます。</span><span class="sxs-lookup"><span data-stu-id="0edcf-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="0edcf-158">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-158">Select **Save**.</span></span>

<span data-ttu-id="0edcf-159">エクスポート先を保存した後、**データ** > **エクスポート** に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0edcf-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="0edcf-160">これで、[セグメントをオンデマンドでエクスポート](export-destinations.md#run-exports-on-demand) できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0edcf-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="0edcf-161">エクスポートは、[スケジュールされた更新](system.md) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="0edcf-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0edcf-162">エクスポートされたセグメントのレコード数が、Adobe Campaign Standard ライセンスの許可された制限内にあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0edcf-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="0edcf-163">エクスポートされたデータは、上記で構成した Azure Blob Storage コンテナーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="0edcf-163">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="0edcf-164">次のフォルダー パスがコンテナーに自動的に作成されます:</span><span class="sxs-lookup"><span data-stu-id="0edcf-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="0edcf-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="0edcf-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="0edcf-166">例: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="0edcf-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="0edcf-167">Adobe Campaign Standard の構成</span><span class="sxs-lookup"><span data-stu-id="0edcf-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="0edcf-168">対象者に関するインサイトのセグメントをエクスポートすると、前の手順でエクスポート先を定義するときに選択した列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0edcf-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="0edcf-169">このデータを使用して、[Adobe Campaign Standard でプロファイルを作成](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles) できます。</span><span class="sxs-lookup"><span data-stu-id="0edcf-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="0edcf-170">Adobe Campaign Standard でセグメントを使用するには、Adobe Campaign Standard のプロファイル スキーマを拡張して、2 つの追加フィールドを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0edcf-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="0edcf-171">Adobe Campaign Standard の新しいフィールドを使用して [プロファイル リソースを拡張](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="0edcf-172">この例では、これらのフィールドは *セグメント名とセグメント日付 (オプション)* です。</span><span class="sxs-lookup"><span data-stu-id="0edcf-172">In our example, these fields are *Segment Name and Segment Date (optional)*.</span></span>

<span data-ttu-id="0edcf-173">これらのフィールドを使用して、このキャンペーンのターゲットとする Adobe Campaign Standard のプロファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="0edcf-174">インポートするもの以外に Adobe Campaign Standard に他のレコードがない場合は、この手順をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="0edcf-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="0edcf-175">Adobe Campaign Standard にデータをインポート</span><span class="sxs-lookup"><span data-stu-id="0edcf-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="0edcf-176">すべてが整ったので、準備した対象ユーザー データを対象者に関するインサイトから Adobe Campaign Standard にインポートして、プロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0edcf-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="0edcf-177">ワークフローを使用して、[Adobe Campaign Standard でプロファイルをインポートする方法](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) について説明します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="0edcf-178">以下の画像のインポート ワークフローは、8 時間ごとに実行され、エクスポートされた対象ユーザー分析セグメント (Azure Blob Storage の .csv ファイル) を探すように構成されています。</span><span class="sxs-lookup"><span data-stu-id="0edcf-178">The import workflow in the image below has been configured to run every eight hours and look for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="0edcf-179">ワークフローは、指定された列の順序で .csv ファイルのコンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="0edcf-180">このワークフローは、基本的なエラー処理を実行し、Adobe Campaign Standard でデータをハイドレートする前に、各レコードに電子メール アドレスがあることを確認するために構築されています。</span><span class="sxs-lookup"><span data-stu-id="0edcf-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="0edcf-181">ワークフローは、Adobe Campaign Standard プロファイル データにアップサートする前に、ファイル名からセグメント名も抽出します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-181">The workflow also extracts the segment name from the filename before upserting into Adobe Campaign Standard profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard ユーザー インターフェイスのインポート ワークフローのスクリーンショット。":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="0edcf-183">Adobe Campaign Standard で対象ユーザーの取得</span><span class="sxs-lookup"><span data-stu-id="0edcf-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="0edcf-184">データが Adobe Campaign Standard にインポートされると、[ワークフローを作成](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) し、*セグメント名* と *セグメント日付* に基づいて顧客に対して [クエリ](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) を実行し、サンプル キャンペーンで特定されたプロファイルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0edcf-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="0edcf-185">Adobe Campaign Standard を使用したメールの作成と送信</span><span class="sxs-lookup"><span data-stu-id="0edcf-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="0edcf-186">メール コンテンツを作成し、メールを [テストおよび送信](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) します。</span><span class="sxs-lookup"><span data-stu-id="0edcf-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard からの更新キャンペーンを含むサンプル メール。":::
