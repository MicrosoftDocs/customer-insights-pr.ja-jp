---
title: サブスクリプション解約予測サンプル ガイド
description: このサンプル ガイドを使用して、既成のサブスクリプション解約予測モデルを試してください。
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269842"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="bfa06-103">サブスクリプション解約予測 (プレビュー) サンプル ガイド</span><span class="sxs-lookup"><span data-stu-id="bfa06-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="bfa06-104">以下に示すサンプル データを使用して、サブスクリプション解約予測のエンドツーエンドの例について説明します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="bfa06-105">シナリオ</span><span class="sxs-lookup"><span data-stu-id="bfa06-105">Scenario</span></span>

<span data-ttu-id="bfa06-106">Contoso は、高品質のコーヒーとコーヒー メーカーを製造し、Contoso Coffee の Web サイトで販売している会社です。</span><span class="sxs-lookup"><span data-stu-id="bfa06-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="bfa06-107">彼らは最近、定期的にコーヒーを飲む顧客のためにサブスクリプション ビジネスを始めた。</span><span class="sxs-lookup"><span data-stu-id="bfa06-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="bfa06-108">彼らの目標は、どの加入した顧客が今後数か月以内にサブスクリプションをキャンセルする可能性があるかを把握することです。</span><span class="sxs-lookup"><span data-stu-id="bfa06-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="bfa06-109">どの顧客が **解約する可能性がある** かを把握することは、顧客をつなぎ止めることに集中することで、マーケティング活動を軽減するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bfa06-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bfa06-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="bfa06-110">Prerequisites</span></span>

- <span data-ttu-id="bfa06-111">少なくとも Customer Insights の[共同作成者権限](permissions.md) があること。</span><span class="sxs-lookup"><span data-stu-id="bfa06-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="bfa06-112">[新しい環境で](manage-environments.md) 次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bfa06-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="bfa06-113">タスク 1 - データの取り込み</span><span class="sxs-lookup"><span data-stu-id="bfa06-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="bfa06-114">特に [データの取り込み](data-sources.md) と [Power Query コネクタを使用したデータ ソースのインポート](connect-power-query.md) についての記事を確認します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="bfa06-115">以下の情報は、一般的なデータの取り込みに精通していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="bfa06-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="bfa06-116">顧客データを eコマース プラットフォームから取り込む</span><span class="sxs-lookup"><span data-stu-id="bfa06-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="bfa06-117">**eコマース** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="bfa06-118">eコマースの連絡先の URL https://aka.ms/ciadclasscontacts を入力します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="bfa06-119">データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="bfa06-120">以下にリストされている列のデータ型を更新します:</span><span class="sxs-lookup"><span data-stu-id="bfa06-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="bfa06-121">**DateOfBirth**: 日付</span><span class="sxs-lookup"><span data-stu-id="bfa06-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="bfa06-122">**CreatedOn**: 日付/時刻/タイムゾーン</span><span class="sxs-lookup"><span data-stu-id="bfa06-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="生年月日を日付に変換します。":::

1. <span data-ttu-id="bfa06-124">右側のペインにある **名前** フィールドで、データ ソースの名前を **クエリ** から **eCommerceContacts** に変更します</span><span class="sxs-lookup"><span data-stu-id="bfa06-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="bfa06-125">データ ソースを保存します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="bfa06-126">ロイヤルティ スキームから顧客データを取り込む</span><span class="sxs-lookup"><span data-stu-id="bfa06-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="bfa06-127">**LoyaltyScheme** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="bfa06-128">eコマースの連絡先の URL https://aka.ms/ciadclasscustomerloyalty を入力します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="bfa06-129">データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="bfa06-130">以下にリストされている列のデータ型を更新します:</span><span class="sxs-lookup"><span data-stu-id="bfa06-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="bfa06-131">**DateOfBirth**: 日付</span><span class="sxs-lookup"><span data-stu-id="bfa06-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="bfa06-132">**RewardsPoints**: 整数</span><span class="sxs-lookup"><span data-stu-id="bfa06-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="bfa06-133">**CreatedOn**: 日付/時刻</span><span class="sxs-lookup"><span data-stu-id="bfa06-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="bfa06-134">右側のペインにある **名前** フィールドで、データ ソースの名前を **クエリ** から **loyCustomers** に変更します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="bfa06-135">データ ソースを保存します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="bfa06-136">サブスクリプション情報の取り込み</span><span class="sxs-lookup"><span data-stu-id="bfa06-136">Ingest subscription information</span></span>

1. <span data-ttu-id="bfa06-137">**SubscriptionHistory** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="bfa06-138">eコマースの連絡先の URL https://aka.ms/ciadchurnsubscriptionhistory を入力します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="bfa06-139">データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="bfa06-140">以下にリストされている列のデータ型を更新します:</span><span class="sxs-lookup"><span data-stu-id="bfa06-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="bfa06-141">**SubscriptioID**: 整数</span><span class="sxs-lookup"><span data-stu-id="bfa06-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="bfa06-142">**SubscriptionAmount**: 通貨</span><span class="sxs-lookup"><span data-stu-id="bfa06-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="bfa06-143">**SubscriptionEndDate**: 日付/時刻</span><span class="sxs-lookup"><span data-stu-id="bfa06-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="bfa06-144">**SubscriptionStartDate**: 日付/時刻</span><span class="sxs-lookup"><span data-stu-id="bfa06-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="bfa06-145">**TransactionDate**: 日付/時刻</span><span class="sxs-lookup"><span data-stu-id="bfa06-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="bfa06-146">**IsRecurring**: True/False</span><span class="sxs-lookup"><span data-stu-id="bfa06-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="bfa06-147">**Is_auto_renew**: True/False</span><span class="sxs-lookup"><span data-stu-id="bfa06-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="bfa06-148">**RecurringFrequencyInMonths**: 整数</span><span class="sxs-lookup"><span data-stu-id="bfa06-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="bfa06-149">右側のペインにある **名前** フィールドで、データ ソースの名前を **クエリ** から **SubscriptionHistory** に変更します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="bfa06-150">データ ソースを保存します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="bfa06-151">Web サイトのレビューから顧客データを取り込む</span><span class="sxs-lookup"><span data-stu-id="bfa06-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="bfa06-152">**Web サイト** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="bfa06-153">eコマースの連絡先の URL https://aka.ms/ciadclasswebsite を入力します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="bfa06-154">データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="bfa06-155">以下にリストされている列のデータ型を更新します:</span><span class="sxs-lookup"><span data-stu-id="bfa06-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="bfa06-156">**ReviewRating**: 整数</span><span class="sxs-lookup"><span data-stu-id="bfa06-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="bfa06-157">**ReviewDate**: 日付</span><span class="sxs-lookup"><span data-stu-id="bfa06-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="bfa06-158">右側のペインにある '名前' フィールドで、データ ソースの名前を **クエリ** から **webReviews** に変更します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="bfa06-159">タスク 2 - データの統合</span><span class="sxs-lookup"><span data-stu-id="bfa06-159">Task 2 - Data unification</span></span>

<span data-ttu-id="bfa06-160">データを取り込んだ後、**マップ、照合、マージ** のプロセスを開始して、統一顧客プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="bfa06-161">詳細については、[データの統合](data-unification.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfa06-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="bfa06-162">マップ</span><span class="sxs-lookup"><span data-stu-id="bfa06-162">Map</span></span>

1. <span data-ttu-id="bfa06-163">データを取り込んだ後、連絡先を eコマースおよびロイヤルティ データから共通のデータ型にマップします。</span><span class="sxs-lookup"><span data-stu-id="bfa06-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="bfa06-164">**データ** > **統合** > **マップ** に移動します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="bfa06-165">顧客プロファイルを表すエンティティ - **eCommerceContacts** および **loyCustomers** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="eコマースとロイヤルティ データソースを統合します。":::

1. <span data-ttu-id="bfa06-167">**eCommerceContacts** の主キーとして **ContactId**、**loyCustomers** の主キーとして **LoyaltyID** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="LoyaltyId を主キーとして統合します。":::

### <a name="match"></a><span data-ttu-id="bfa06-169">照合</span><span class="sxs-lookup"><span data-stu-id="bfa06-169">Match</span></span>

1. <span data-ttu-id="bfa06-170">**照合** タブに移動して、**順序の設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="bfa06-171">**プライマリ** ドロップダウン リストで、**eCommerceContacts : eCommerce** をプライマリ ソースとして選択し、すべてのレコードを含めます。</span><span class="sxs-lookup"><span data-stu-id="bfa06-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="bfa06-172">**エンティティ 2** ドロップダウン リストで、**loyCustomers : LoyaltyScheme** を選択し、すべてのレコードを含めます。</span><span class="sxs-lookup"><span data-stu-id="bfa06-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="eコマースとロイヤルティの一致を統合します。":::

1. <span data-ttu-id="bfa06-174">**新しいルールの作成** を選択します</span><span class="sxs-lookup"><span data-stu-id="bfa06-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="bfa06-175">FullName を使用して最初の条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="bfa06-176">eCommerceContacts の場合は、ドロップダウンで **FullName** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="bfa06-177">loyCustomers の場合は、ドロップダウンで **FullName** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="bfa06-178">**正規化** ドロップダウンを選択して、**種類 (電話、名前、住所、...)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="bfa06-179">**精度レベル** の設定: **基本** と **値**: **高い**。</span><span class="sxs-lookup"><span data-stu-id="bfa06-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="bfa06-180">新しいルールに **FullName, Email** という名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="bfa06-181">**条件の追加** を選択し、メール アドレスの 2 番目の条件を追加します</span><span class="sxs-lookup"><span data-stu-id="bfa06-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="bfa06-182">エンティティ eCommerceContacts の場合、ドロップダウンで **電子メール** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="bfa06-183">エンティティ loyCustomers の場合、ドロップダウンで **電子メール** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="bfa06-184">正規化を空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="bfa06-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="bfa06-185">**精度レベル** の設定: **基本** と **値**: **高い**。</span><span class="sxs-lookup"><span data-stu-id="bfa06-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="名前とメールの照合ルールを統一します。":::

7. <span data-ttu-id="bfa06-187">**保存** と **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="bfa06-188">マージ</span><span class="sxs-lookup"><span data-stu-id="bfa06-188">Merge</span></span>

1. <span data-ttu-id="bfa06-189">**マージ** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="bfa06-190">**loyCustomers** エンティティの **ContactId** で、表示名を **ContactIdLOYALTY** に変更して、取り込まれた別の ID とは区別されるようにします。</span><span class="sxs-lookup"><span data-stu-id="bfa06-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="ロイヤルティ ID から contactid に名前を変更します。":::

1. <span data-ttu-id="bfa06-192">**保存** と **実行** を選択し、マージ プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="bfa06-193">タスク 3 - サブスクリプション解約予測を構成する</span><span class="sxs-lookup"><span data-stu-id="bfa06-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="bfa06-194">統合顧客プロファイルが整ったら、サブスクリプション解約予測を実行できます。</span><span class="sxs-lookup"><span data-stu-id="bfa06-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="bfa06-195">詳細な手順については、[サブスクリプション解約予測 (プレビュー)](predict-subscription-churn.md) の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfa06-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="bfa06-196">**インテリジェンス** > **検出** に移動し、**顧客離反モデル** の使用を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="bfa06-197">**サブスクリプション** オプションを選択し、**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="bfa06-198">モデルに **OOB サブスクリプション解約予測**、出力エンティティに **OOBSubscriptionChurnPrediction** という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="bfa06-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="bfa06-199">離反モデルの 2 つの条件を定義します:</span><span class="sxs-lookup"><span data-stu-id="bfa06-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="bfa06-200">**サブスクリプションが終了してからの日数**: **少なくとも 60** 日。</span><span class="sxs-lookup"><span data-stu-id="bfa06-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="bfa06-201">サブスクリプション終了後、顧客がこの期間に更新しなかった場合は、解約されたとみなされます。</span><span class="sxs-lookup"><span data-stu-id="bfa06-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="bfa06-202">**解約定義**: **少なくとも 93** 日。</span><span class="sxs-lookup"><span data-stu-id="bfa06-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="bfa06-203">モデルが解約する可能性のある顧客を予測する期間。</span><span class="sxs-lookup"><span data-stu-id="bfa06-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="bfa06-204">先のことを考えれば考えるほど、結果の精度は低くなります。</span><span class="sxs-lookup"><span data-stu-id="bfa06-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="モデル レバーの予測ウィンドウと解約定義を選択します。":::

1. <span data-ttu-id="bfa06-206">**必要なデータの追加** を選択し、サブスクリプション履歴の **データの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="bfa06-207">**Subscription : SubscriptionHistory** エンティティを追加し、eコマースのフィールドをモデルに必要な対応するフィールドにマップします。</span><span class="sxs-lookup"><span data-stu-id="bfa06-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="bfa06-208">**Subscription : SubscriptionHistory** エンティテと **eCommerceContacts : eCommerce** を結合し、関連付けに **eCommerceSubscription** という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="bfa06-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="eコマース エンティティを結合します。":::

1. <span data-ttu-id="bfa06-210">顧客アクティビティで、**webReviews : Website** エンティティを追加し、webReviews のフィールドをモデルに必要な対応するフィールドにマップします。</span><span class="sxs-lookup"><span data-stu-id="bfa06-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="bfa06-211">主キー: ReviewId</span><span class="sxs-lookup"><span data-stu-id="bfa06-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="bfa06-212">タイムスタンプ: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="bfa06-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="bfa06-213">イベント: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="bfa06-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="bfa06-214">Web サイトレ ビューのアクティビティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="bfa06-215">アクティビティ **レビュー** を選択し、**webReviews : Website** エンティティを **eCommerceContacts : eCommerce** と結合します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="bfa06-216">**次へ** を選択し、モデル スケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="bfa06-217">新しいデータが取り込まれた場合、モデルは新しいパターンを学習するために定期的にトレーニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfa06-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="bfa06-218">この例では、**月** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="bfa06-219">すべての詳細を確認した後、**保存と実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="bfa06-220">タスク 4 - モデルの結果と説明を確認する</span><span class="sxs-lookup"><span data-stu-id="bfa06-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="bfa06-221">モデルにデータのトレーニングとスコアリングを完了させます。</span><span class="sxs-lookup"><span data-stu-id="bfa06-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="bfa06-222">これで、サブスクリプション解約モデルの説明を確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="bfa06-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="bfa06-223">詳細については、[予測の状態と結果の確認](predict-subscription-churn.md#review-a-prediction-status-and-results) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfa06-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="bfa06-224">タスク5 - 解約リスクの高い顧客のセグメントを作成する</span><span class="sxs-lookup"><span data-stu-id="bfa06-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="bfa06-225">運用モデルを実行すると、**データ** > **エンティティ** に表示される新しいエンティティが作成されます。</span><span class="sxs-lookup"><span data-stu-id="bfa06-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="bfa06-226">モデルによって作成されたエンティティに基づいて、新しいセグメントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bfa06-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="bfa06-227">**セグメント** に移動します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-227">Go to **Segments**.</span></span> <span data-ttu-id="bfa06-228">**新規** を選択し、**作成元** > **インテリジェンス** と選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa06-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="モデル出力を使用してセグメントを作成しています。":::

1. <span data-ttu-id="bfa06-230">**OOBSubscriptionChurnPrediction** エンドポイントを選択して、セグメントを定義します:</span><span class="sxs-lookup"><span data-stu-id="bfa06-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="bfa06-231">フィールド: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="bfa06-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="bfa06-232">演算子: より大きい</span><span class="sxs-lookup"><span data-stu-id="bfa06-232">Operator: greater than</span></span>
   - <span data-ttu-id="bfa06-233">値: 0.6</span><span class="sxs-lookup"><span data-stu-id="bfa06-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="サブスクリプション解約セグメントを設定します。":::

<span data-ttu-id="bfa06-235">これで、このサブスクリプション ビジネスの解約リスクの高い顧客を識別するセグメントが動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="bfa06-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="bfa06-236">詳細については、[セグメントの作成と管理](segments.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bfa06-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]