---
title: サードパーティのエンリッチメント Experian によるエンリッチメント
description: Experian サードパーティのエンリッチメントに関する一般情報。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309826"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="abc94-103">Experian からの人口統計情報で顧客プロファイルをエンリッチする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="abc94-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="abc94-104">Experian は、消費者および企業のクレジットのレポートおよびマーケティング サービスにおけるグローバル リーダーです。</span><span class="sxs-lookup"><span data-stu-id="abc94-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="abc94-105">Experian のデータ エンリッチメント サービスを使用して、世帯規模、収入などの人口統計データで顧客プロファイルのエンリッチメントを行うことで、顧客をより深く理解していくことができます。</span><span class="sxs-lookup"><span data-stu-id="abc94-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="abc94-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="abc94-106">Prerequisites</span></span>

<span data-ttu-id="abc94-107">Experian を構成するには、次の前提条件が満たされている必要があります:</span><span class="sxs-lookup"><span data-stu-id="abc94-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="abc94-108">有効な Experian サブスクリプションを所有していること。</span><span class="sxs-lookup"><span data-stu-id="abc94-108">You have an active Experian subscription.</span></span> <span data-ttu-id="abc94-109">サブスクリプションを取得するには、[Experian へのお問い合わせ](https://www.experian.com/marketing-services/contact) から直接お問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="abc94-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="abc94-110">[Experian データ エンリッチメントの詳細](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。</span><span class="sxs-lookup"><span data-stu-id="abc94-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="abc94-111">Experian 接続は既に管理者によって構成されている、*または* [管理者](permissions.md#administrator) 権限を所有していること。</span><span class="sxs-lookup"><span data-stu-id="abc94-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="abc94-112">また、Experian がユーザーのために作成した、SSH 対応セキュア トランスポート (ST) アカウントのユーザー ID、パーティ ID、およびモデル番号も必要です。</span><span class="sxs-lookup"><span data-stu-id="abc94-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="abc94-113">サポートされている国/地域</span><span class="sxs-lookup"><span data-stu-id="abc94-113">Supported countries/regions</span></span>

<span data-ttu-id="abc94-114">現在、米国でのみ顧客プロファイルのエンリッチメントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="abc94-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="abc94-115">エンリッチメントの構成</span><span class="sxs-lookup"><span data-stu-id="abc94-115">Configure the enrichment</span></span>

1. <span data-ttu-id="abc94-116">**データ** > **エンリッチメント** に移動し、**検出** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="abc94-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="abc94-117">Experian タイルで、**データのエンリッチメント** を選択します。</span><span class="sxs-lookup"><span data-stu-id="abc94-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="abc94-118">![Experian タイルを](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="abc94-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="abc94-119">ドロップダウン リストから [接続](connections.md) を選択してください。</span><span class="sxs-lookup"><span data-stu-id="abc94-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="abc94-120">接続できない場合は、管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="abc94-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="abc94-121">管理者の場合は、**接続の追加** を選択して、ドロップダウン リストから Experian を選択することで、接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="abc94-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="abc94-122">選択した接続を確定するには、**Experian に接続** を選択します。</span><span class="sxs-lookup"><span data-stu-id="abc94-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="abc94-123">**次へ** を選択し、Experian からの人口統計データでエンリッチメントしたい **顧客データ セット** を選択します。</span><span class="sxs-lookup"><span data-stu-id="abc94-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="abc94-124">**顧客** エンティティを選択してすべての顧客プロファイルをエンリッチするか、セグメント エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="abc94-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="顧客データ セットを選択するときのスクリーンショット。":::

1. <span data-ttu-id="abc94-126">**次へ** を選択し、統合されたプロファイルのどの種類のフィールドを使用して、Experian の一致する人口統計データを検索するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="abc94-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="abc94-127">**名前と住所**、**電話**、または **メール** フィールドの少なくとも 1 つが必要です。</span><span class="sxs-lookup"><span data-stu-id="abc94-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="abc94-128">一致精度を高めるために、他に最大 2 つのフィールドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="abc94-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="abc94-129">この選択は、次の手順でアクセスできるマッピング フィールドに影響します。</span><span class="sxs-lookup"><span data-stu-id="abc94-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="abc94-130">Experian に送信される、その他のキー識別子属性の一致率が高くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="abc94-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="abc94-131">**次へ** を選択し、フィールド マッピングを開始します。</span><span class="sxs-lookup"><span data-stu-id="abc94-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="abc94-132">統合されたプロファイルのどの種類のフィールドを使用して、Experian の一致する人口統計データを検索するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="abc94-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="abc94-133">必須フィールドはマークされます。</span><span class="sxs-lookup"><span data-stu-id="abc94-133">Required fields are marked.</span></span>

1. <span data-ttu-id="abc94-134">エンリッチメントの名前と出力エンティティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="abc94-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="abc94-135">選択内容を確認した後、**エンリッチメントの保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="abc94-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="abc94-136">Experian の接続を構成する</span><span class="sxs-lookup"><span data-stu-id="abc94-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="abc94-137">接続を構成するには、管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="abc94-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="abc94-138">エンリッチメントを構成するときに **接続の追加** 選択するか、*または*、Experian タイルで、**管理者** > **接続** に移動し、**設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="abc94-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="abc94-139">**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="abc94-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="abc94-140">**表示名** ボックスに接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="abc94-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="abc94-141">Experian のセキュア トランスポート アカウントの、有効なユーザー ID、パーティ ID、モデル番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="abc94-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="abc94-142">確認して、**同意する** を選択して、**データのプライバシーとコンプライアンス** に同意します。</span><span class="sxs-lookup"><span data-stu-id="abc94-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="abc94-143">**検証** を選択して、構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="abc94-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="abc94-144">検証が完了したら、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="abc94-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian 接続の構成ペイン。":::

## <a name="enrichment-results"></a><span data-ttu-id="abc94-146">強化の結果</span><span class="sxs-lookup"><span data-stu-id="abc94-146">Enrichment results</span></span>

<span data-ttu-id="abc94-147">エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="abc94-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="abc94-148">[スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。</span><span class="sxs-lookup"><span data-stu-id="abc94-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="abc94-149">処理時間は、顧客データのサイズと、Experian でアカウントに設定されたエンリッチメント プロセスによって異なります。</span><span class="sxs-lookup"><span data-stu-id="abc94-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="abc94-150">エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイル データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="abc94-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="abc94-151">さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="abc94-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="abc94-152">**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="abc94-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="abc94-153">次の手順</span><span class="sxs-lookup"><span data-stu-id="abc94-153">Next steps</span></span>

<span data-ttu-id="abc94-154">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="abc94-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="abc94-155">[セグメント](segments.md) および [メジャー](measures.md) を作成し、さらに [データのエクスポート](export-destinations.md) を行って、パーソナライズされたエクスペリエンスを顧客に提供します。</span><span class="sxs-lookup"><span data-stu-id="abc94-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="abc94-156">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="abc94-156">Data privacy and compliance</span></span>

<span data-ttu-id="abc94-157">Dynamics 365 Customer Insights から Experian へのデータ送信を可能にすると、Dynamics 365 Customer Insights のコンプライアンスの範囲を越えて、個人情報などの機密性の高い情報が潜在的に含まれるデータの転送を許可することになります。</span><span class="sxs-lookup"><span data-stu-id="abc94-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="abc94-158">Microsoft はお客様の指示でそのようなデータを送信することがありますが、Experian が関係するプライバシーまたはセキュリティのすべての義務を満たすよう見届ける責任はお客様にあります。</span><span class="sxs-lookup"><span data-stu-id="abc94-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="abc94-159">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abc94-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="abc94-160">Dynamics 365 Customer Insights 管理者は、いつでもエンリッチメントを削除して、この機能の使用を中止することができます。</span><span class="sxs-lookup"><span data-stu-id="abc94-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
