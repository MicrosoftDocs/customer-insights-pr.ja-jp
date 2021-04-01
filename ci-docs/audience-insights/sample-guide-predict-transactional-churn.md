---
title: トランザクション解約予測サンプル ガイド
description: このサンプル ガイドを使用して、既成のトランザクション解約予測モデルを試してください。
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 251bc26246cee16952e8e4cb08e2ed7aa4d18488
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595432"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="667fa-103">トランザクション解約予測 (プレビュー) サンプル ガイド</span><span class="sxs-lookup"><span data-stu-id="667fa-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="667fa-104">このガイドでは、以下のデータを使用して、Customer Insights でのトランザクション解約予測のエンドツーエンドの例について説明します。</span><span class="sxs-lookup"><span data-stu-id="667fa-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="667fa-105">このガイドで使用されているすべてのデータは、実際の顧客データではなく、Customer Insights サブスクリプション内の *デモ* 環境にある Contoso データセットの一部です。</span><span class="sxs-lookup"><span data-stu-id="667fa-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="667fa-106">シナリオ</span><span class="sxs-lookup"><span data-stu-id="667fa-106">Scenario</span></span>

<span data-ttu-id="667fa-107">Contoso は、高品質のコーヒーとコーヒー メーカーを製造し、Contoso Coffee の Web サイトで販売している会社です。</span><span class="sxs-lookup"><span data-stu-id="667fa-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="667fa-108">彼らの目標は、製品を通常定期的に購入している顧客のうち、どの顧客が今後 60 日以内にアクティブな顧客でなくなるかを把握することです。</span><span class="sxs-lookup"><span data-stu-id="667fa-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="667fa-109">どの顧客が **解約する可能性がある** かを把握することは、顧客をつなぎ止めることに集中することで、マーケティング活動を軽減するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="667fa-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="667fa-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="667fa-110">Prerequisites</span></span>

- <span data-ttu-id="667fa-111">少なくとも Customer Insights の[共同作成者権限](permissions.md) があること。</span><span class="sxs-lookup"><span data-stu-id="667fa-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="667fa-112">[新しい環境で](manage-environments.md) 次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="667fa-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="667fa-113">タスク 1 - データの取り込み</span><span class="sxs-lookup"><span data-stu-id="667fa-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="667fa-114">特に [データの取り込み](data-sources.md) と [Power Query コネクタを使用したデータ ソースのインポート](connect-power-query.md) についての記事を確認します。</span><span class="sxs-lookup"><span data-stu-id="667fa-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="667fa-115">以下の情報は、一般的なデータの取り込みに精通していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="667fa-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="667fa-116">顧客データを eコマース プラットフォームから取り込む</span><span class="sxs-lookup"><span data-stu-id="667fa-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="667fa-117">**eコマース** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="667fa-118">eコマースの連絡先の URL https://aka.ms/ciadclasscontacts を入力します。</span><span class="sxs-lookup"><span data-stu-id="667fa-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="667fa-119">データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="667fa-120">以下にリストされている列のデータ型を更新します:</span><span class="sxs-lookup"><span data-stu-id="667fa-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="667fa-121">**DateOfBirth**: 日付</span><span class="sxs-lookup"><span data-stu-id="667fa-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="667fa-122">**CreatedOn**: 日付/時刻/タイムゾーン</span><span class="sxs-lookup"><span data-stu-id="667fa-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="667fa-123">![生年月日を日付に変換](media/ecommerce-dob-date.PNG "生年月日を日付に変換する")</span><span class="sxs-lookup"><span data-stu-id="667fa-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="667fa-124">右側のペインにある **名前** フィールドで、データ ソースの名前を **クエリ** から **eCommerceContacts** に変更します</span><span class="sxs-lookup"><span data-stu-id="667fa-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="667fa-125">データ ソースを保存します。</span><span class="sxs-lookup"><span data-stu-id="667fa-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="667fa-126">オンライン購入データを取り込む</span><span class="sxs-lookup"><span data-stu-id="667fa-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="667fa-127">同じ **eコマース** データ ソースに別のデータ セットを追加します。</span><span class="sxs-lookup"><span data-stu-id="667fa-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="667fa-128">**テキスト/CSV** コネクタをもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="667fa-129">**オンライン購入** データ の URL https://aka.ms/ciadclassonline を入力します。</span><span class="sxs-lookup"><span data-stu-id="667fa-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="667fa-130">データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="667fa-131">以下にリストされている列のデータ型を更新します:</span><span class="sxs-lookup"><span data-stu-id="667fa-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="667fa-132">**PurchasedOn**: 日付/時刻</span><span class="sxs-lookup"><span data-stu-id="667fa-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="667fa-133">**TotalPrice**: 通貨</span><span class="sxs-lookup"><span data-stu-id="667fa-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="667fa-134">右側のペインにある **名前** フィールドで、データ ソースの名前を **クエリ** から **eCommercePurchases** に変更します。</span><span class="sxs-lookup"><span data-stu-id="667fa-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="667fa-135">データ ソースを保存します。</span><span class="sxs-lookup"><span data-stu-id="667fa-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="667fa-136">ロイヤルティ スキームから顧客データを取り込む</span><span class="sxs-lookup"><span data-stu-id="667fa-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="667fa-137">**LoyaltyScheme** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="667fa-138">eコマースの連絡先の URL https://aka.ms/ciadclasscustomerloyalty を入力します。</span><span class="sxs-lookup"><span data-stu-id="667fa-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="667fa-139">データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="667fa-140">以下にリストされている列のデータ型を更新します:</span><span class="sxs-lookup"><span data-stu-id="667fa-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="667fa-141">**DateOfBirth**: 日付</span><span class="sxs-lookup"><span data-stu-id="667fa-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="667fa-142">**RewardsPoints**: 整数</span><span class="sxs-lookup"><span data-stu-id="667fa-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="667fa-143">**CreatedOn**: 日付/時刻</span><span class="sxs-lookup"><span data-stu-id="667fa-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="667fa-144">右側のペインにある **名前** フィールドで、データ ソースの名前を **クエリ** から **loyCustomers** に変更します。</span><span class="sxs-lookup"><span data-stu-id="667fa-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="667fa-145">データ ソースを保存します。</span><span class="sxs-lookup"><span data-stu-id="667fa-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="667fa-146">タスク 2 - データの統合</span><span class="sxs-lookup"><span data-stu-id="667fa-146">Task 2 - Data unification</span></span>

<span data-ttu-id="667fa-147">データを取り込んだ後、**マップ、照合、マージ** のプロセスを開始して、統一顧客プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="667fa-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="667fa-148">詳細については、[データの統合](data-unification.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="667fa-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="667fa-149">マップ</span><span class="sxs-lookup"><span data-stu-id="667fa-149">Map</span></span>

1. <span data-ttu-id="667fa-150">データを取り込んだ後、連絡先を eコマースおよびロイヤルティ データから共通のデータ型にマップします。</span><span class="sxs-lookup"><span data-stu-id="667fa-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="667fa-151">**データ** > **統合** > **マップ** に移動します。</span><span class="sxs-lookup"><span data-stu-id="667fa-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="667fa-152">顧客プロファイルを表すエンティティ - **eCommerceContacts** および **loyCustomers** を選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="eコマースとロイヤルティ データソースを統合します。":::

1. <span data-ttu-id="667fa-154">**eCommerceContacts** の主キーとして **ContactId**、**loyCustomers** の主キーとして **LoyaltyID** を選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="LoyaltyId を主キーとして統合します。":::

### <a name="match"></a><span data-ttu-id="667fa-156">照合</span><span class="sxs-lookup"><span data-stu-id="667fa-156">Match</span></span>

1. <span data-ttu-id="667fa-157">**照合** タブに移動して、**順序の設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="667fa-158">**プライマリ** ドロップダウン リストで、**eCommerceContacts : eCommerce** をプライマリ ソースとして選択し、すべてのレコードを含めます。</span><span class="sxs-lookup"><span data-stu-id="667fa-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="667fa-159">**エンティティ 2** ドロップダウン リストで、**loyCustomers : LoyaltyScheme** を選択し、すべてのレコードを含めます。</span><span class="sxs-lookup"><span data-stu-id="667fa-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="eコマースとロイヤルティの一致を統合します。":::

1. <span data-ttu-id="667fa-161">**新しいルールの作成** を選択します</span><span class="sxs-lookup"><span data-stu-id="667fa-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="667fa-162">FullName を使用して最初の条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="667fa-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="667fa-163">eCommerceContacts の場合は、ドロップダウンで **FullName** を選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="667fa-164">loyCustomers の場合は、ドロップダウンで **FullName** を選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="667fa-165">**正規化** ドロップダウンを選択して、**種類 (電話、名前、住所、...)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="667fa-166">**精度レベル** の設定: **基本** と **値**: **高い**。</span><span class="sxs-lookup"><span data-stu-id="667fa-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="667fa-167">新しいルールに **FullName, Email** という名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="667fa-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="667fa-168">**条件の追加** を選択し、メール アドレスの 2 番目の条件を追加します</span><span class="sxs-lookup"><span data-stu-id="667fa-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="667fa-169">エンティティ eCommerceContacts の場合、ドロップダウンで **電子メール** を選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="667fa-170">エンティティ loyCustomers の場合、ドロップダウンで **電子メール** を選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="667fa-171">正規化を空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="667fa-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="667fa-172">**精度レベル** の設定: **基本** と **値**: **高い**。</span><span class="sxs-lookup"><span data-stu-id="667fa-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="名前とメールの照合ルールを統一します。":::

7. <span data-ttu-id="667fa-174">**保存** と **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="667fa-175">マージ</span><span class="sxs-lookup"><span data-stu-id="667fa-175">Merge</span></span>

1. <span data-ttu-id="667fa-176">**マージ** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="667fa-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="667fa-177">**loyCustomers** エンティティの **ContactId** で、表示名を **ContactIdLOYALTY** に変更して、取り込まれた別の ID とは区別されるようにします。</span><span class="sxs-lookup"><span data-stu-id="667fa-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="ロイヤルティ ID から contactid に名前を変更します。":::

1. <span data-ttu-id="667fa-179">**保存** と **実行** を選択し、マージ プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="667fa-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="667fa-180">タスク 3 - トランザクション解約予測を構成する</span><span class="sxs-lookup"><span data-stu-id="667fa-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="667fa-181">統合顧客プロファイルが整ったら、サブスクリプション解約予測を実行できます。</span><span class="sxs-lookup"><span data-stu-id="667fa-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="667fa-182">詳細な手順については、[サブスクリプション解約予測 (プレビュー)](predict-subscription-churn.md) の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="667fa-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="667fa-183">**インテリジェンス** > **検出** に移動し、**顧客離反モデル** の使用を選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="667fa-184">**トランザクション** オプションを選択し、**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="667fa-185">モデルに **OOB eコマース トランザクション解約予測**、出力エンティティに **OOBeCommerceChurnPrediction** という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="667fa-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="667fa-186">離反モデルの 2 つの条件を定義します:</span><span class="sxs-lookup"><span data-stu-id="667fa-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="667fa-187">**予測ウィンドウ**: **少なくとも 60** 日。</span><span class="sxs-lookup"><span data-stu-id="667fa-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="667fa-188">この設定では、顧客離れをどの程度先まで予測するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="667fa-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="667fa-189">**解約定義**: **少なくとも 60** 日。</span><span class="sxs-lookup"><span data-stu-id="667fa-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="667fa-190">顧客が解約されたと見なされるまでの購入なしの期間。</span><span class="sxs-lookup"><span data-stu-id="667fa-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="モデル レバーの予測ウィンドウと解約定義を選択します。":::

1. <span data-ttu-id="667fa-192">**購入履歴 (必須)** を選択し、購入履歴に対して **データの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="667fa-193">**eCommercePurchases : eCommerce** エンティティを追加し、eコマースのフィールドをモデルに必要な対応するフィールドにマップします。</span><span class="sxs-lookup"><span data-stu-id="667fa-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="667fa-194">**eCommercePurchases : eCommerce** エンティティを **eCommerceContacts : eCommerce** と結合します。</span><span class="sxs-lookup"><span data-stu-id="667fa-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="eコマース エンティティを結合します。":::

1. <span data-ttu-id="667fa-196">**次へ** を選択し、モデル スケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="667fa-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="667fa-197">新しいデータが取り込まれた場合、モデルは新しいパターンを学習するために定期的にトレーニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="667fa-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="667fa-198">この例では、**月** を選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="667fa-199">すべての詳細を確認した後、**保存と実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="667fa-200">タスク 4 - モデルの結果と説明を確認する</span><span class="sxs-lookup"><span data-stu-id="667fa-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="667fa-201">モデルにデータのトレーニングとスコアリングを完了させます。</span><span class="sxs-lookup"><span data-stu-id="667fa-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="667fa-202">これで、サブスクリプション解約モデルの説明を確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="667fa-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="667fa-203">詳細については、[予測の状態と結果の確認](predict-subscription-churn.md#review-a-prediction-status-and-results) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="667fa-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="667fa-204">タスク5 - 解約リスクの高い顧客のセグメントを作成する</span><span class="sxs-lookup"><span data-stu-id="667fa-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="667fa-205">運用モデルを実行すると、**データ** > **エンティティ** に表示される新しいエンティティが作成されます。</span><span class="sxs-lookup"><span data-stu-id="667fa-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="667fa-206">モデルによって作成されたエンティティに基づいて、新しいセグメントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="667fa-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="667fa-207">**セグメント** に移動します。</span><span class="sxs-lookup"><span data-stu-id="667fa-207">Go to **Segments**.</span></span> <span data-ttu-id="667fa-208">**新規** を選択し、**作成元** > **インテリジェンス** と選択します。</span><span class="sxs-lookup"><span data-stu-id="667fa-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="モデル出力を使用してセグメントを作成しています。":::

1. <span data-ttu-id="667fa-210">**OOBSubscriptionChurnPrediction** エンドポイントを選択して、セグメントを定義します:</span><span class="sxs-lookup"><span data-stu-id="667fa-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="667fa-211">フィールド: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="667fa-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="667fa-212">演算子: より大きい</span><span class="sxs-lookup"><span data-stu-id="667fa-212">Operator: greater than</span></span>
   - <span data-ttu-id="667fa-213">値: 0.6</span><span class="sxs-lookup"><span data-stu-id="667fa-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="サブスクリプション解約セグメントを設定します。":::

<span data-ttu-id="667fa-215">これで、このサブスクリプション ビジネスの解約リスクの高い顧客を識別するセグメントが動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="667fa-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="667fa-216">詳細については、[セグメントの作成と管理](segments.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="667fa-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]