---
title: 製品のレコメンデーション予測サンプル ガイド
description: このサンプル ガイドを使用して、既成の製品レコメンデーション予測モデルを試してください。
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270506"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="7414f-103">製品のレコメンデーション予測 (プレビュー) サンプル ガイド</span><span class="sxs-lookup"><span data-stu-id="7414f-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="7414f-104">以下に示すサンプル データを使用して、製品レコメンデーション予測のエンドツーエンドの例について説明します。</span><span class="sxs-lookup"><span data-stu-id="7414f-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="7414f-105">シナリオ</span><span class="sxs-lookup"><span data-stu-id="7414f-105">Scenario</span></span>

<span data-ttu-id="7414f-106">Contoso は、高品質のコーヒーとコーヒー メーカーを製造し、Contoso Coffee の Web サイトで販売している会社です。</span><span class="sxs-lookup"><span data-stu-id="7414f-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="7414f-107">その目標は、定期的な顧客にどの製品を推奨すべきかを理解することです。</span><span class="sxs-lookup"><span data-stu-id="7414f-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="7414f-108">顧客が **購入する可能性が高い** ことを把握することで、特定のアイテムに焦点を当ててマーケティングの労力を軽減できます。</span><span class="sxs-lookup"><span data-stu-id="7414f-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7414f-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="7414f-109">Prerequisites</span></span>

- <span data-ttu-id="7414f-110">少なくとも Customer Insights の[共同作成者権限](permissions.md) があること。</span><span class="sxs-lookup"><span data-stu-id="7414f-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="7414f-111">[新しい環境で](manage-environments.md) 次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7414f-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="7414f-112">タスク 1 - データの取り込み</span><span class="sxs-lookup"><span data-stu-id="7414f-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="7414f-113">特に [データの取り込み](data-sources.md) と [Power Query コネクタを使用したデータ ソースのインポート](connect-power-query.md) についての記事を確認します。</span><span class="sxs-lookup"><span data-stu-id="7414f-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="7414f-114">以下の情報は、一般的なデータの取り込みに精通していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="7414f-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="7414f-115">顧客データを eコマース プラットフォームから取り込む</span><span class="sxs-lookup"><span data-stu-id="7414f-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="7414f-116">**eコマース** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="7414f-117">eコマースの連絡先の URL https://aka.ms/ciadclasscontacts を入力します。</span><span class="sxs-lookup"><span data-stu-id="7414f-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="7414f-118">データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7414f-119">以下にリストされている列のデータ型を更新します:</span><span class="sxs-lookup"><span data-stu-id="7414f-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="7414f-120">**DateOfBirth**: 日付</span><span class="sxs-lookup"><span data-stu-id="7414f-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="7414f-121">**CreatedOn**: 日付/時刻/タイムゾーン</span><span class="sxs-lookup"><span data-stu-id="7414f-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="生年月日を日付に変換します。":::

5. <span data-ttu-id="7414f-123">右側のペインにある '名前' フィールドで、データ ソースの名前を **クエリ** から **eCommerceContacts** に変更します</span><span class="sxs-lookup"><span data-stu-id="7414f-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="7414f-124">データ ソースを **保存** します。</span><span class="sxs-lookup"><span data-stu-id="7414f-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="7414f-125">オンライン購入データを取り込む</span><span class="sxs-lookup"><span data-stu-id="7414f-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="7414f-126">同じ **eコマース** データ ソースに別のデータ セットを追加します。</span><span class="sxs-lookup"><span data-stu-id="7414f-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="7414f-127">**テキスト/CSV** コネクタをもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="7414f-128">**オンライン購入** データ の URL https://aka.ms/ciadclassonline を入力します。</span><span class="sxs-lookup"><span data-stu-id="7414f-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="7414f-129">データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7414f-130">以下にリストされている列のデータ型を更新します:</span><span class="sxs-lookup"><span data-stu-id="7414f-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="7414f-131">**PurchasedOn**: 日付/時刻</span><span class="sxs-lookup"><span data-stu-id="7414f-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="7414f-132">**TotalPrice**: 通貨</span><span class="sxs-lookup"><span data-stu-id="7414f-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="7414f-133">サイド ペインの **名前** フィールドで、データ ソースの名前を **クエリ** から **eCommercePurchases** に変更します。</span><span class="sxs-lookup"><span data-stu-id="7414f-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="7414f-134">データ ソースを保存します。</span><span class="sxs-lookup"><span data-stu-id="7414f-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="7414f-135">ロイヤルティ スキームから顧客データを取り込む</span><span class="sxs-lookup"><span data-stu-id="7414f-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="7414f-136">**LoyaltyScheme** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="7414f-137">eコマースの連絡先の URL https://aka.ms/ciadclasscustomerloyalty を入力します。</span><span class="sxs-lookup"><span data-stu-id="7414f-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="7414f-138">データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7414f-139">以下にリストされている列のデータ型を更新します:</span><span class="sxs-lookup"><span data-stu-id="7414f-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="7414f-140">**DateOfBirth**: 日付</span><span class="sxs-lookup"><span data-stu-id="7414f-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="7414f-141">**RewardsPoints**: 整数</span><span class="sxs-lookup"><span data-stu-id="7414f-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="7414f-142">**CreatedOn**: 日付/時刻</span><span class="sxs-lookup"><span data-stu-id="7414f-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="7414f-143">右側のペインにある **名前** フィールドで、データ ソースの名前を **クエリ** から **loyCustomers** に変更します。</span><span class="sxs-lookup"><span data-stu-id="7414f-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="7414f-144">データ ソースを保存します。</span><span class="sxs-lookup"><span data-stu-id="7414f-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="7414f-145">タスク 2 - データの統合</span><span class="sxs-lookup"><span data-stu-id="7414f-145">Task 2 - Data unification</span></span>

<span data-ttu-id="7414f-146">データを取り込んだ後、**マップ、照合、マージ** のプロセスを開始して、統一顧客プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7414f-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="7414f-147">詳細については、[データの統合](data-unification.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7414f-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="7414f-148">マップ</span><span class="sxs-lookup"><span data-stu-id="7414f-148">Map</span></span>

1. <span data-ttu-id="7414f-149">データを取り込んだ後、連絡先を eコマースおよびロイヤルティ データから共通のデータ型にマップします。</span><span class="sxs-lookup"><span data-stu-id="7414f-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="7414f-150">**データ** > **統合** > **マップ** に移動します。</span><span class="sxs-lookup"><span data-stu-id="7414f-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="7414f-151">顧客プロファイルを表すエンティティ - **eCommerceContacts** および **loyCustomers** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![eコマースとロイヤルティ データソースを統合します。](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="7414f-153">**eCommerceContacts** の主キーとして **ContactId**、**loyCustomers** の主キーとして **LoyaltyID** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![LoyaltyId を主キーとして統合します。](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="7414f-155">照合</span><span class="sxs-lookup"><span data-stu-id="7414f-155">Match</span></span>

1. <span data-ttu-id="7414f-156">**照合** タブに移動して、**順序の設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="7414f-157">**プライマリ** ドロップダウン リストで、**eCommerceContacts : eCommerce** をプライマリ ソースとして選択し、すべてのレコードを含めます。</span><span class="sxs-lookup"><span data-stu-id="7414f-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="7414f-158">**エンティティ 2** ドロップダウン リストで、**loyCustomers : LoyaltyScheme** を選択し、すべてのレコードを含めます。</span><span class="sxs-lookup"><span data-stu-id="7414f-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![eコマースとロイヤルティの一致を統合します。](media/unify-match-order.png)

4. <span data-ttu-id="7414f-160">**新しいルールの作成** を選択します</span><span class="sxs-lookup"><span data-stu-id="7414f-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="7414f-161">FullName を使用して最初の条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="7414f-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="7414f-162">eCommerceContacts の場合は、ドロップダウンで **FullName** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="7414f-163">loyCustomers の場合は、ドロップダウンで **FullName** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="7414f-164">**正規化** ドロップダウンを選択して、**種類 (電話、名前、住所、...)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="7414f-165">**精度レベル** の設定: **基本** と **値**: **高い**。</span><span class="sxs-lookup"><span data-stu-id="7414f-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="7414f-166">新しいルールに **FullName, Email** という名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7414f-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="7414f-167">**条件の追加** を選択し、メール アドレスの 2 番目の条件を追加します</span><span class="sxs-lookup"><span data-stu-id="7414f-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="7414f-168">エンティティ eCommerceContacts の場合、ドロップダウンで **電子メール** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="7414f-169">エンティティ loyCustomers の場合、ドロップダウンで **電子メール** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="7414f-170">正規化を空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="7414f-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="7414f-171">**精度レベル** の設定: **基本** と **値**: **高い**。</span><span class="sxs-lookup"><span data-stu-id="7414f-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![名前とメールの照合ルールを統一します。](media/unify-match-rule.png)

7. <span data-ttu-id="7414f-173">**保存** と **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="7414f-174">マージ</span><span class="sxs-lookup"><span data-stu-id="7414f-174">Merge</span></span>

1. <span data-ttu-id="7414f-175">**マージ** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="7414f-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="7414f-176">**loyCustomers** エンティティの **ContactId** で、表示名を **ContactIdLOYALTY** に変更して、取り込まれた別の ID とは区別されるようにします。</span><span class="sxs-lookup"><span data-stu-id="7414f-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![ロイヤルティ ID から contactid に名前を変更します。](media/unify-merge-contactid.png)

1. <span data-ttu-id="7414f-178">**保存** と **実行** を選択し、マージ プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="7414f-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="7414f-179">タスク 3 - 製品レコメンデーション予測を構成する</span><span class="sxs-lookup"><span data-stu-id="7414f-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="7414f-180">統合顧客プロファイルが整ったら、サブスクリプション解約予測を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7414f-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="7414f-181">**インテリジェンス** > **予測** に移動して、**製品レコメンデーション** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="7414f-182">**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-182">Select **Get started**.</span></span>

1. <span data-ttu-id="7414f-183">モデルに **OOB 製品レコメンデーション モデル予測**、出力エンティティには **OOBProductRecommendationModelPrediction** という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="7414f-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="7414f-184">モデルの 3 つの条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="7414f-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="7414f-185">**製品数**: この値を **5** に設定します。</span><span class="sxs-lookup"><span data-stu-id="7414f-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="7414f-186">この設定は、顧客に推奨する製品の数を定義します。</span><span class="sxs-lookup"><span data-stu-id="7414f-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="7414f-187">**顧客が最近購入した製品を提案しますか?**: **はい** を選択して、顧客が以前に購入したレコメンデーションに製品を含めることを示します。</span><span class="sxs-lookup"><span data-stu-id="7414f-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="7414f-188">**ウィンドウを見返す:** 少なくとも **365 日** を選択してください。</span><span class="sxs-lookup"><span data-stu-id="7414f-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="7414f-189">この設定で、レコメンデーションへの入力として顧客のアクティビティをさかのぼって振り返る期間が定義されます。</span><span class="sxs-lookup"><span data-stu-id="7414f-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="製品レコメンデーション モデルモデル マッピングです。":::

1. <span data-ttu-id="7414f-191">**必要なデータ** を選択し、購入履歴に対して **データの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="7414f-192">**eCommercePurchases : eCommerce** エンティティを追加し、eコマースのフィールドをモデルに必要な対応するフィールドにマップします。</span><span class="sxs-lookup"><span data-stu-id="7414f-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="7414f-193">**eCommercePurchases : eCommerce** エンティティを **eCommerceContacts : eCommerce** と結合します。</span><span class="sxs-lookup"><span data-stu-id="7414f-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![eコマース エンティティを結合します。](media/model-purchase-join.png)

1. <span data-ttu-id="7414f-195">**次へ** を選択し、モデル スケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="7414f-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="7414f-196">新しいデータが取り込まれた場合、モデルは新しいパターンを学習するために定期的にトレーニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7414f-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="7414f-197">この例では、**月** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="7414f-198">すべての詳細を確認した後、**保存と実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="7414f-199">タスク 4 - モデルの結果と説明を確認する</span><span class="sxs-lookup"><span data-stu-id="7414f-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="7414f-200">モデルにデータのトレーニングとスコアリングを完了させます。</span><span class="sxs-lookup"><span data-stu-id="7414f-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="7414f-201">これで、製品レコメンデーション モデルの説明を確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7414f-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="7414f-202">詳細については、[予測の状態と結果の確認](predict-subscription-churn.md#review-a-prediction-status-and-results) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7414f-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="7414f-203">タスク 5 - 購入数の多い製品のセグメントを作成する</span><span class="sxs-lookup"><span data-stu-id="7414f-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="7414f-204">運用モデルを実行すると、**データ** > **エンティティ** に表示される新しいエンティティが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7414f-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="7414f-205">モデルによって作成されたエンティティに基づいて、新しいセグメントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7414f-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="7414f-206">**セグメント** に移動します。</span><span class="sxs-lookup"><span data-stu-id="7414f-206">Go to **Segments**.</span></span> <span data-ttu-id="7414f-207">**新規** を選択し、**作成元** > **インテリジェンス** と選択します。</span><span class="sxs-lookup"><span data-stu-id="7414f-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![モデル出力を使用してセグメントを作成しています。](media/segment-intelligence.png)

1. <span data-ttu-id="7414f-209">**OOBProductRecommendationModelPrediction** エンドポイントを選択して、セグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="7414f-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="7414f-210">フィールド: ProductID</span><span class="sxs-lookup"><span data-stu-id="7414f-210">Field: ProductID</span></span>
   - <span data-ttu-id="7414f-211">演算子: 値</span><span class="sxs-lookup"><span data-stu-id="7414f-211">Operator: Value</span></span>
   - <span data-ttu-id="7414f-212">値: 上位 3 つの製品 ID を選択する</span><span class="sxs-lookup"><span data-stu-id="7414f-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="モデルの結果からセグメントを作成します。":::

<span data-ttu-id="7414f-214">これで、最も推奨される 3 つの製品を購入する意欲のある顧客を識別する、動的に更新されるセグメントができました</span><span class="sxs-lookup"><span data-stu-id="7414f-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="7414f-215">詳細については、[セグメントの作成と管理](segments.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7414f-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]