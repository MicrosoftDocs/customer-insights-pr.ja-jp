---
title: 顧客カード アドインのインストールと構成
description: Dynamics 365 Customer Insights の顧客カード アドインのインストールと構成
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644049"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="04590-103">顧客カード アドイン (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="04590-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="04590-104">Dynamics 365 アプリで直接、顧客を全方位から確認します。</span><span class="sxs-lookup"><span data-stu-id="04590-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="04590-105">顧客カード アドインを使用して、人口統計、インサイト、および活動のタイムラインを表示します。</span><span class="sxs-lookup"><span data-stu-id="04590-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="04590-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="04590-106">Prerequisites</span></span>

- <span data-ttu-id="04590-107">Dynamics 365アプリ (営業ハブまたは顧客サービス ハブなど)、バージョン9.0以降、統一インターフェイスが有効化されていること。</span><span class="sxs-lookup"><span data-stu-id="04590-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="04590-108">[Common Data Service を使用して Dynamics 365 アプリから取り込んだ](connect-power-query.md) 顧客プロファイル。</span><span class="sxs-lookup"><span data-stu-id="04590-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="04590-109">顧客カード アドインのユーザーは、対象者に関するインサイトに [ユーザーとして追加](permissions.md) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04590-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="04590-110">[構成された検索およびフィルター機能](search-filter-index.md)。</span><span class="sxs-lookup"><span data-stu-id="04590-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="04590-111">人口統計コントロール: 年齢や性別などの人口統計フィールドは、統合顧客プロファイルで利用できます。</span><span class="sxs-lookup"><span data-stu-id="04590-111">Demographic control: Demographic fields, such as age or gender are available in the unified customer profile.</span></span>
- <span data-ttu-id="04590-112">エンリッチメント制御 : 顧客プロファイルに適用されるアクティブな[エンリッチメント](enrichment-hub.md)が必要です。</span><span class="sxs-lookup"><span data-stu-id="04590-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="04590-113">インテリジェンス制御: Azure Machine Learning ([予測](predictions.md) または [カスタム モデル](custom-models.md)) を使用して生成されたデータが必要です</span><span class="sxs-lookup"><span data-stu-id="04590-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="04590-114">メジャー制御: [構成済みメジャー](measures.md) が必要です。</span><span class="sxs-lookup"><span data-stu-id="04590-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="04590-115">タイムライン コントロール: [構成済みアクティビティ](activities.md) が必要です。</span><span class="sxs-lookup"><span data-stu-id="04590-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="04590-116"> 顧客カード アドイン のインストール</span><span class="sxs-lookup"><span data-stu-id="04590-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="04590-117">カスタマー カード アドインは、Dynamics 365 の Customer Engagement アプリのソリューションです。</span><span class="sxs-lookup"><span data-stu-id="04590-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="04590-118">ソリューションをインストールするには、AppSource に移動し、**Dynamics 顧客カード** を検索します。</span><span class="sxs-lookup"><span data-stu-id="04590-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="04590-119">[AppSource で顧客カードアドイン](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) を選択して、**今すぐ入手** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04590-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="04590-120">ソリューションをインストールするには、Dynamics 365 アプリの管理者の資格情報でログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04590-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="04590-121">ソリューションが環境にインストールされるまでに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="04590-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="04590-122">顧客カードアドインの構成</span><span class="sxs-lookup"><span data-stu-id="04590-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="04590-123">管理者は、 Dynamics 365の **設定** セクションに移動し、**ソリューション** を選択してください。</span><span class="sxs-lookup"><span data-stu-id="04590-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="04590-124">**Dynamics 365 Customer Insights 顧客カード アドイン (プレビュー)** ソリューションの **表示名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04590-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="04590-125">![表示名の選択](media/select-display-name.png "表示名の選択")</span><span class="sxs-lookup"><span data-stu-id="04590-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="04590-126">**サインイン** を選択し、Customer Insights の構成に使用する管理者アカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="04590-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="04590-127">**サインイン** ボタンを選択する場合に、ブラウザのポップアップ ブロッカーが認証ウィンドウをブロックしないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="04590-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="04590-128">データを取り込む環境を選択します。</span><span class="sxs-lookup"><span data-stu-id="04590-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="04590-129">Dynamics 365 アプリのレコードにマッピングするフィールドを定義します。</span><span class="sxs-lookup"><span data-stu-id="04590-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="04590-130">取引先担当者とマップするには、取引先担当者エンティティの ID と一致する顧客エンティティのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="04590-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="04590-131">取引先企業とマップするには、取引先企業エンティティの ID と一致する顧客エンティティのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="04590-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="04590-132">![取引先担当者 ID フィールド](media/contact-id-field.png "取引先担当者 ID フィールド")</span><span class="sxs-lookup"><span data-stu-id="04590-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="04590-133">設定を保存するには、**構成を保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04590-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="04590-134">次に、Dynamics 365 でセキュリティ ロールを割り当てて、ユーザーが顧客カードをカスタマイズして表示できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04590-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="04590-135">Dynamics 365 で、**設定** > **セキュリティ** > **ユーザー** に移動します。</span><span class="sxs-lookup"><span data-stu-id="04590-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="04590-136">ユーザー ロールを編集するユーザーを選択し、**役割を管理する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04590-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="04590-137">組織全体で使用するカードに表示されているコンテンツをカスタマイズするユーザーに **Customer Insights カード カスタマイザ** のロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="04590-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="04590-138">フォームに顧客カード コントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="04590-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="04590-139">顧客カードコントロールを連絡先フォームに追加するには、**設定** > **カスタマイズ** Dynamics 365 の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="04590-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="04590-140">**システムのカスタマイズ** を選択。</span><span class="sxs-lookup"><span data-stu-id="04590-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="04590-141">**取引先担当者** エンティティを参照し、メニューを展開して、**フォーム** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04590-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="04590-142">顧客カード管理を追加したい取引先担当者フォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="04590-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04590-143">![取引先担当者フォームを選択する](media/contact-active-forms.png "取引先担当者フォームを選択する")</span><span class="sxs-lookup"><span data-stu-id="04590-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="04590-144">人口統計コントロールを追加するには、フォーム エディターで、任意のフィールドを **フィールド エクスプローラー** から人口統計コントロールを配置する場所にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="04590-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="04590-145">今追加したフォームのフィールドを選択し、**プロパティの変更** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04590-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="04590-146">**コントロール** タブに移動し、**コントロールの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04590-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="04590-147">利用可能なカスタム コントロールの 1 つを選択し、**追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04590-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="04590-148">**フィールドのプロパティ** ダイアログで、**フォームにラベルを表示する** チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="04590-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="04590-149">**Web** オプションをコントロールに選択します。</span><span class="sxs-lookup"><span data-stu-id="04590-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="04590-150">エンリッチメント制御で、**enrichmentType** フィールドを設定して、表示するエンリッチメントのタイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="04590-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="04590-151">エンリッチメントのタイプごとに個別のエンリッチメント制御を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04590-151">You need to add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="04590-152">**保存** そして **公開** を選択して、更新された問い合わせフォームを公開します。</span><span class="sxs-lookup"><span data-stu-id="04590-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="04590-153">公開されている取引先担当者フォームに移動します。</span><span class="sxs-lookup"><span data-stu-id="04590-153">Go to the published contact form.</span></span> <span data-ttu-id="04590-154">新しく追加されたコントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="04590-154">You'll see the newly added control.</span></span> <span data-ttu-id="04590-155">初めて使用するときはサインインする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="04590-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="04590-156">カスタム コントロールで表示したいものをカスタマイズするには、右上隅の編集ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="04590-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>
