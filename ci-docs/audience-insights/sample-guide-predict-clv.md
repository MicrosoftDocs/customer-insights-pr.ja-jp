---
title: 顧客の生涯価値予測サンプル ガイド
description: このサンプル ガイドを使用して、顧客の生涯価値予測モデルを試してください。
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129951"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="b1b1a-103">顧客の生涯価値 (CLV) 予測サンプル ガイド</span><span class="sxs-lookup"><span data-stu-id="b1b1a-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="b1b1a-104">このガイドでは、サンプル データを使用した Customer Insights での顧客の生涯価値 (CLV) 予測の例を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="b1b1a-105">シナリオ</span><span class="sxs-lookup"><span data-stu-id="b1b1a-105">Scenario</span></span>

<span data-ttu-id="b1b1a-106">Contoso は高品質のコーヒーとコーヒー メーカーを製造する会社です。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="b1b1a-107">Contoso Coffee の Web サイトで製品を販売しています。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="b1b1a-108">同社は、顧客が今後 12 か月で生み出す価値 (売上) を把握したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="b1b1a-109">今後 12 か月の顧客の期待値を知ることで、価値の高い顧客にマーケティング活動を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b1b1a-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="b1b1a-110">Prerequisites</span></span>

- <span data-ttu-id="b1b1a-111">少なくとも、対象者に関するインサイトで [共同作成者のアクセス許可](permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="b1b1a-112">[新しい環境で](manage-environments.md) 次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="b1b1a-113">タスク 1 - データの取り込み</span><span class="sxs-lookup"><span data-stu-id="b1b1a-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="b1b1a-114">[データ インジェストについて](data-sources.md) と [Power Query コネクタを使用したデータ ソースのインポート](connect-power-query.md) の記事を確認します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="b1b1a-115">以下の情報は、一般的なデータの取り込みに精通していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="b1b1a-116">顧客データを eコマース プラットフォームから取り込む</span><span class="sxs-lookup"><span data-stu-id="b1b1a-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="b1b1a-117">**eコマース** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b1b1a-118">eコマースの連絡先 URL [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts) を入力します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="b1b1a-119">データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b1b1a-120">以下にリストされている列のデータ型を更新します:</span><span class="sxs-lookup"><span data-stu-id="b1b1a-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="b1b1a-121">**DateOfBirth**: 日付</span><span class="sxs-lookup"><span data-stu-id="b1b1a-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="b1b1a-122">**CreatedOn**: 日付/時刻/タイムゾーン</span><span class="sxs-lookup"><span data-stu-id="b1b1a-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="生年月日を日付に変換します。":::

1. <span data-ttu-id="b1b1a-124">右側のペインにある '名前' フィールドで、データ ソースの名前を **クエリ** から **eCommerceContacts** に変更します</span><span class="sxs-lookup"><span data-stu-id="b1b1a-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="b1b1a-125">データ ソースを **保存** します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="b1b1a-126">オンライン購入データを取り込む</span><span class="sxs-lookup"><span data-stu-id="b1b1a-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="b1b1a-127">同じ **eコマース** データ ソースに別のデータ セットを追加します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="b1b1a-128">**テキスト/CSV** コネクタをもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="b1b1a-129">**オンライン購入** データ の URL https://aka.ms/ciadclassonline を入力します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="b1b1a-130">データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b1b1a-131">以下にリストされている列のデータ型を更新します:</span><span class="sxs-lookup"><span data-stu-id="b1b1a-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="b1b1a-132">**PurchasedOn**: 日付/時刻</span><span class="sxs-lookup"><span data-stu-id="b1b1a-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="b1b1a-133">**TotalPrice**: 通貨</span><span class="sxs-lookup"><span data-stu-id="b1b1a-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="b1b1a-134">サイド ペインの **名前** フィールドで、データ ソースの名前を **クエリ** から **eCommercePurchases** に変更します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="b1b1a-135">データ ソースを **保存** します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="b1b1a-136">ロイヤルティ スキームから顧客データを取り込む</span><span class="sxs-lookup"><span data-stu-id="b1b1a-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="b1b1a-137">**LoyaltyScheme** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b1b1a-138">eコマースの連絡先の URL https://aka.ms/ciadclasscustomerloyalty を入力します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="b1b1a-139">データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b1b1a-140">以下にリストされている列のデータ型を更新します:</span><span class="sxs-lookup"><span data-stu-id="b1b1a-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="b1b1a-141">**DateOfBirth**: 日付</span><span class="sxs-lookup"><span data-stu-id="b1b1a-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="b1b1a-142">**RewardsPoints**: 整数</span><span class="sxs-lookup"><span data-stu-id="b1b1a-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="b1b1a-143">**CreatedOn**: 日付/時刻</span><span class="sxs-lookup"><span data-stu-id="b1b1a-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="b1b1a-144">右側のペインにある **名前** フィールドで、データ ソースの名前を **クエリ** から **loyCustomers** に変更します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="b1b1a-145">データ ソースを **保存** します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="b1b1a-146">Web サイトのレビューから顧客データを取り込む</span><span class="sxs-lookup"><span data-stu-id="b1b1a-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="b1b1a-147">**Web サイト** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b1b1a-148">eコマースの連絡先の URL https://aka.ms/CI-ILT/WebReviews を入力します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="b1b1a-149">データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b1b1a-150">以下にリストされている列のデータ型を更新します:</span><span class="sxs-lookup"><span data-stu-id="b1b1a-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="b1b1a-151">**ReviewRating**: 10 進数</span><span class="sxs-lookup"><span data-stu-id="b1b1a-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="b1b1a-152">**ReviewDate**: 日付</span><span class="sxs-lookup"><span data-stu-id="b1b1a-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="b1b1a-153">右側のペインの '名前' フィールドで、データ ソースの名前を **Query** から **Reviews** に変更します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="b1b1a-154">データ ソースを **保存** します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="b1b1a-155">タスク 2 - データの統合</span><span class="sxs-lookup"><span data-stu-id="b1b1a-155">Task 2 - Data unification</span></span>

<span data-ttu-id="b1b1a-156">データを取り込んだ後、データ統合プロセスを開始して、統合された顧客プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="b1b1a-157">詳細については、[データの統合](data-unification.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="b1b1a-158">マップ</span><span class="sxs-lookup"><span data-stu-id="b1b1a-158">Map</span></span>

1. <span data-ttu-id="b1b1a-159">データを取り込んだ後、連絡先を eコマースおよびロイヤルティ データから共通のデータ型にマップします。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="b1b1a-160">**データ** > **統合** > **マップ** に移動します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="b1b1a-161">顧客プロファイルを表すエンティティ - **eCommerceContacts** および **loyCustomers** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="b1b1a-162">次に、**適用** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-162">Then, select **Apply**.</span></span>

   ![eコマースとロイヤルティ データソースを統合します。](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="b1b1a-164">**eCommerceContacts** の主キーとして **ContactId**、**loyCustomers** の主キーとして **LoyaltyID** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![LoyaltyId を主キーとして統合します。](media/unify-loyaltyid.png)

1. <span data-ttu-id="b1b1a-166">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="b1b1a-167">照合</span><span class="sxs-lookup"><span data-stu-id="b1b1a-167">Match</span></span>

1. <span data-ttu-id="b1b1a-168">**照合** タブに移動して、**順序の設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="b1b1a-169">**プライマリ** ドロップダウン リストで、**eCommerceContacts : eCommerce** をプライマリ ソースとして選択し、すべてのレコードを含めます。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="b1b1a-170">**エンティティ 2** ドロップダウン リストで、**loyCustomers : LoyaltyScheme** を選択し、すべてのレコードを含めます。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![eコマースとロイヤルティの一致を統合します。](media/unify-match-order.png)

1. <span data-ttu-id="b1b1a-172">**ルールの追加** を選択します</span><span class="sxs-lookup"><span data-stu-id="b1b1a-172">Select **Add rule**</span></span>

1. <span data-ttu-id="b1b1a-173">FullName を使用して最初の条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="b1b1a-174">eCommerceContacts の場合は、ドロップダウンで **FullName** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="b1b1a-175">loyCustomers の場合は、ドロップダウンで **FullName** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="b1b1a-176">**正規化** ドロップダウンを選択して、**種類 (電話、名前、住所、...)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="b1b1a-177">**精度レベル** の設定: **基本** と **値**: **高い**。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="b1b1a-178">新しいルールに **FullName, Email** という名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="b1b1a-179">**条件の追加** を選択し、メール アドレスの 2 番目の条件を追加します</span><span class="sxs-lookup"><span data-stu-id="b1b1a-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="b1b1a-180">エンティティ eCommerceContacts の場合、ドロップダウンで **電子メール** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="b1b1a-181">エンティティ loyCustomers の場合、ドロップダウンで **電子メール** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="b1b1a-182">正規化を空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="b1b1a-183">**精度レベル** の設定: **基本** と **値**: **高い**。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![名前とメールの照合ルールを統一します。](media/unify-match-rule.png)

1. <span data-ttu-id="b1b1a-185">**完了** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-185">Select **Done**.</span></span>

1. <span data-ttu-id="b1b1a-186">**保存** と **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="b1b1a-187">マージ</span><span class="sxs-lookup"><span data-stu-id="b1b1a-187">Merge</span></span>

1. <span data-ttu-id="b1b1a-188">**マージ** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="b1b1a-189">**loyCustomers** エンティティの **ContactId** で、表示名を **ContactIdLOYALTY** に変更して、取り込まれた別の ID とは区別されるようにします。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![ロイヤルティ ID から contactid に名前を変更します。](media/unify-merge-contactid.png)

1. <span data-ttu-id="b1b1a-191">**保存** と **マージおよびダウンストリーム プロセスを実行する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="b1b1a-192">タスク 3 - 顧客の生涯価値予測の構成</span><span class="sxs-lookup"><span data-stu-id="b1b1a-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="b1b1a-193">統合された顧客プロファイルが用意できたので、顧客の生涯価値予測を実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="b1b1a-194">詳細な手順については、[顧客の生涯価値予測 (プレビュー)](predict-customer-lifetime-value.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="b1b1a-195">**インテリジェンス**  > **予測** に移動し、**顧客の生涯価値モデル** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="b1b1a-196">サイド ペインの情報に目を通し、**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="b1b1a-197">モデルに **OOB eコマース CLV 予測**、出力エンティティに **OOBeCommerceCLVPrediction** という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="b1b1a-198">CLV モデルのモデルの基本設定を定義します:</span><span class="sxs-lookup"><span data-stu-id="b1b1a-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="b1b1a-199">**予測期間**: **12 か月間または 1 年**。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="b1b1a-200">この設定では、顧客の生涯価値をどのくらい先まで予測するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="b1b1a-201">**アクティブな顧客**: アクティブな顧客がビジネスにどのような意味を持つかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="b1b1a-202">顧客がアクティブであると見なされるには、少なくとも 1 件のトランザクションを持つ必要がある履歴期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="b1b1a-203">このモデルは、アクティブな顧客の CLV のみを予測します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="b1b1a-204">モデルでトランザクションの履歴データに基づいて期間を計算するか、特定の期間を指定するかのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="b1b1a-205">このサンプル ガイドでは、既定のオプションである **モデルで購入間隔を計算** します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="b1b1a-206">**価値の高い顧客**: 価値の高い顧客を上位支払顧客のパーセンタイルとして定義します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="b1b1a-207">モデルはこの入力を使用して、価値の高い顧客のビジネス定義に適合する結果を提供します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="b1b1a-208">モデルに価値の高い顧客を定義させることもできます。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="b1b1a-209">パーセンタイルを算出する発見的規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="b1b1a-210">価値の高い顧客を今後の上位支払顧客のパーセンタイルとして定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="b1b1a-211">このサンプル ガイドでは、価値の高い顧客を **アクティブな支払顧客の上位 30%** として手動で定義し、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV モデルのガイド付きエクスペリエンスの基本設定ステップ。":::

1. <span data-ttu-id="b1b1a-213">**必須データ** ステップで、**データの追加** を選択し、トランザクション履歴データを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="b1b1a-214">**eCommercePurchases : eCommerce** エンティティを追加し、モデルに必要な属性をマップします:</span><span class="sxs-lookup"><span data-stu-id="b1b1a-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="b1b1a-215">トランザクション ID: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="b1b1a-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="b1b1a-216">トランザクションの日付: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="b1b1a-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="b1b1a-217">トランザクション金額: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="b1b1a-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="b1b1a-218">製品 ID: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="b1b1a-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="b1b1a-219">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-219">Select **Next**.</span></span>

1. <span data-ttu-id="b1b1a-220">**eCommercePurchases : eCommerce** エンティティと **eCommerceContacts : eCommerce** の関係を設定します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="b1b1a-221">**追加データ (オプション)** ステップでは、顧客活動データをさらに追加できます。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="b1b1a-222">このデータは、顧客のビジネスとのやり取りについてより多くのインサイトを得るのに役立ち、CLV に貢献する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="b1b1a-223">Web ログ、顧客サービス ログ、特典プログラム履歴などの、顧客との重要なやり取りを追加すると、予測の精度を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="b1b1a-224">**データの追加** を選択し、より多くの顧客活動データを追加します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="b1b1a-225">顧客活動エンティティを追加し、そのフィールド名をモデルに必要な対応するフィールドにマップします:</span><span class="sxs-lookup"><span data-stu-id="b1b1a-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="b1b1a-226">顧客活動エンティティ: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="b1b1a-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="b1b1a-227">主キー: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="b1b1a-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="b1b1a-228">タイムスタンプ: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="b1b1a-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="b1b1a-229">イベント (活動名): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="b1b1a-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="b1b1a-230">詳細 (金額または値): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="b1b1a-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="b1b1a-231">**次へ** を選択し、活動およびトランザクション データと顧客データの関係を構成します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="b1b1a-232">活動の種類: 既存を選択</span><span class="sxs-lookup"><span data-stu-id="b1b1a-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="b1b1a-233">活動ラベル: Review</span><span class="sxs-lookup"><span data-stu-id="b1b1a-233">Activity label: Review</span></span>
   - <span data-ttu-id="b1b1a-234">対応するラベル: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="b1b1a-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="b1b1a-235">顧客エンティティ: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="b1b1a-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="b1b1a-236">関連付け: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="b1b1a-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="b1b1a-237">**次へ** を選択し、モデル スケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="b1b1a-238">新しいデータが取り込まれたときに、モデルは新しいパターンを学習するために、定期的にトレーニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="b1b1a-239">この例では、**月単位** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="b1b1a-240">すべての詳細を確認した後、**保存と実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="b1b1a-241">タスク 4 - モデルの結果と説明を確認する</span><span class="sxs-lookup"><span data-stu-id="b1b1a-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="b1b1a-242">モデルにデータのトレーニングとスコアリングを完了させます。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="b1b1a-243">次に、CLV モデルの結果と説明を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="b1b1a-244">詳細については、[予測の状態と結果の確認](predict-customer-lifetime-value.md#review-prediction-status-and-results) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="b1b1a-245">タスク 5 - 価値の高い顧客のセグメントの作成</span><span class="sxs-lookup"><span data-stu-id="b1b1a-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="b1b1a-246">モデルを実行すると、新しいエンティティが作成され、**データ** > **エンティティ** に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="b1b1a-247">モデルによって作成されたエンティティに基づいて、新しい顧客セグメントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="b1b1a-248">**セグメント** に移動します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="b1b1a-249">**新規** を選択し、**作成元** > **インテリジェンス** と選択します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![モデル出力を使用してセグメントを作成しています。](media/segment-intelligence.png)

1. <span data-ttu-id="b1b1a-251">**OOBeCommerceCLVPrediction** エンティティを選択し、セグメントを定義します:</span><span class="sxs-lookup"><span data-stu-id="b1b1a-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="b1b1a-252">フィールド: CLVScore</span><span class="sxs-lookup"><span data-stu-id="b1b1a-252">Field: CLVScore</span></span>
  - <span data-ttu-id="b1b1a-253">演算子: より大きい</span><span class="sxs-lookup"><span data-stu-id="b1b1a-253">Operator: greater than</span></span>
  - <span data-ttu-id="b1b1a-254">値: 1500</span><span class="sxs-lookup"><span data-stu-id="b1b1a-254">Value: 1500</span></span>

1. <span data-ttu-id="b1b1a-255">**レビュー** を選択し、セグメントを **保存** します。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="b1b1a-256">これで、今後 12 か月間で $1500 を超える売上を生み出すと予測される顧客を識別するセグメントができました。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="b1b1a-257">より多くのデータが取り込まれると、このセグメントは動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="b1b1a-258">詳細については、[セグメントの作成と管理](segments.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b1b1a-258">For more information, see [Create and manage segments](segments.md).</span></span>
