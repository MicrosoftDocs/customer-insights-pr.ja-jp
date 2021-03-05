---
title: 顧客カード アドインのインストールと構成
description: Dynamics 365 Customer Insights の顧客カード アドインのインストールと構成
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268050"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="1b0cb-103">顧客カード アドイン (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="1b0cb-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="1b0cb-104">Dynamics 365 アプリで直接、顧客を全方位から確認します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="1b0cb-105">顧客カード アドインを使用して、人口統計、インサイト、および活動のタイムラインを表示します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1b0cb-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="1b0cb-106">Prerequisites</span></span>

- <span data-ttu-id="1b0cb-107">Dynamics 365アプリ (営業ハブまたは顧客サービス ハブなど)、バージョン9.0以降、統一インターフェイスが有効化されていること。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="1b0cb-108">[Common Data Service を使用して Dynamics 365 アプリから取り込んだ](connect-power-query.md) 顧客プロファイル。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="1b0cb-109">顧客カード アドインのユーザーは、対象者に関するインサイトに [ユーザーとして追加](permissions.md) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="1b0cb-110">[構成された検索およびフィルター機能](search-filter-index.md)。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="1b0cb-111">人口統計コントロール: 人口統計フィールド (年齢や性別など) は、統合顧客プロファイルで利用できます。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="1b0cb-112">エンリッチメント制御 : 顧客プロファイルに適用されるアクティブな[エンリッチメント](enrichment-hub.md)が必要です。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="1b0cb-113">インテリジェンス制御: Azure Machine Learning ([予測](predictions.md) または [カスタム モデル](custom-models.md)) を使用して生成されたデータが必要です</span><span class="sxs-lookup"><span data-stu-id="1b0cb-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="1b0cb-114">メジャー制御: [構成済みメジャー](measures.md) が必要です。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="1b0cb-115">タイムライン コントロール: [構成済みアクティビティ](activities.md) が必要です。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="1b0cb-116"> 顧客カード アドイン のインストール</span><span class="sxs-lookup"><span data-stu-id="1b0cb-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="1b0cb-117">カスタマー カード アドインは、Dynamics 365 の Customer Engagement アプリのソリューションです。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="1b0cb-118">ソリューションをインストールするには、AppSource に移動し、**Dynamics 顧客カード** を検索します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="1b0cb-119">[AppSource で顧客カードアドイン](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) を選択して、**今すぐ入手** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="1b0cb-120">ソリューションをインストールするには、Dynamics 365 アプリの管理者の資格情報でログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="1b0cb-121">ソリューションが環境にインストールされるまでに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="1b0cb-122">顧客カードアドインの構成</span><span class="sxs-lookup"><span data-stu-id="1b0cb-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="1b0cb-123">管理者は、 Dynamics 365の **設定** セクションに移動し、**ソリューション** を選択してください。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="1b0cb-124">**Dynamics 365 Customer Insights 顧客カード アドイン (プレビュー)** ソリューションの **表示名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1b0cb-125">![表示名の選択](media/select-display-name.png "表示名の選択")</span><span class="sxs-lookup"><span data-stu-id="1b0cb-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="1b0cb-126">**サインイン** を選択し、Customer Insights の構成に使用する管理者アカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1b0cb-127">**サインイン** ボタンを選択する場合に、ブラウザのポップアップ ブロッカーが認証ウィンドウをブロックしないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="1b0cb-128">データを取り込む環境を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="1b0cb-129">Dynamics 365 アプリのレコードにマッピングするフィールドを定義します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="1b0cb-130">取引先担当者とマップするには、取引先担当者エンティティの ID と一致する顧客エンティティのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="1b0cb-131">取引先企業とマップするには、取引先企業エンティティの ID と一致する顧客エンティティのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1b0cb-132">![取引先担当者 ID フィールド](media/contact-id-field.png "取引先担当者 ID フィールド")</span><span class="sxs-lookup"><span data-stu-id="1b0cb-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="1b0cb-133">設定を保存するには、**構成を保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="1b0cb-134">次に、Dynamics 365 でセキュリティ ロールを割り当てて、ユーザーが顧客カードをカスタマイズして表示できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="1b0cb-135">Dynamics 365 で、**設定** > **セキュリティ** > **ユーザー** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="1b0cb-136">ユーザー ロールを編集するユーザーを選択し、**役割を管理する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="1b0cb-137">組織全体で使用するカードに表示されているコンテンツをカスタマイズするユーザーに **Customer Insights カード カスタマイザ** のロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="1b0cb-138">フォームに顧客カード コントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="1b0cb-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="1b0cb-139">顧客カードコントロールを連絡先フォームに追加するには、**設定** > **カスタマイズ** Dynamics 365 の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="1b0cb-140">**システムのカスタマイズ** を選択。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="1b0cb-141">**取引先担当者** エンティティを参照し、メニューを展開して、**フォーム** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="1b0cb-142">顧客カード管理を追加したい取引先担当者フォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1b0cb-143">![取引先担当者フォームを選択する](media/contact-active-forms.png "取引先担当者フォームを選択する")</span><span class="sxs-lookup"><span data-stu-id="1b0cb-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="1b0cb-144">人口統計コントロールを追加するには、フォーム エディターで、任意のフィールドを **フィールド エクスプローラー** から人口統計コントロールを配置する場所にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="1b0cb-145">今追加したフォームのフィールドを選択し、**プロパティの変更** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="1b0cb-146">**コントロール** タブに移動し、**コントロールの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="1b0cb-147">利用可能なカスタム コントロールの 1 つを選択し、**追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="1b0cb-148">**フィールドのプロパティ** ダイアログで、**フォームにラベルを表示する** チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="1b0cb-149">**Web** オプションをコントロールに選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="1b0cb-150">エンリッチメント制御で、**enrichmentType** フィールドを設定して、表示するエンリッチメントのタイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="1b0cb-151">エンリッチメントのタイプごとに個別のエンリッチメント コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="1b0cb-152">**保存** そして **公開** を選択して、更新された問い合わせフォームを公開します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="1b0cb-153">公開されている取引先担当者フォームに移動します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-153">Go to the published contact form.</span></span> <span data-ttu-id="1b0cb-154">新しく追加されたコントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-154">You'll see the newly added control.</span></span> <span data-ttu-id="1b0cb-155">初めて使用するときはサインインする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="1b0cb-156">カスタム コントロールで表示したいものをカスタマイズするには、右上隅の編集ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="1b0cb-157">顧客カード アドインのアップグレード</span><span class="sxs-lookup"><span data-stu-id="1b0cb-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="1b0cb-158">顧客カード アドインは自動的にアップグレードされません。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="1b0cb-159">最新バージョンにアップグレードするには、アドインがインストールされている Dynamics 365 アプリでこの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="1b0cb-160">Dynamics 365 アプリで、**設定** > **カスタマイズ**、そして **ソリューション** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="1b0cb-161">アドインの表で、**CustomerInsightsCustomerCard** を探して、行を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="1b0cb-162">アクションバーで **ソリューションのアップグレードを適用する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Dynamics 365 アプリのカスタマイズ領域でソリューションをアップグレードする":::

1. <span data-ttu-id="1b0cb-164">アップグレード プロセスを開始すると、アップグレードが完了するまで読み込みインジケータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="1b0cb-165">新しいバージョンがない場合、アップグレードでエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b0cb-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]