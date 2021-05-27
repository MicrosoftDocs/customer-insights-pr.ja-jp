---
title: Dynamics 365 アプリ用顧客カード アドイン
description: このアドインを使用して、Dynamics 365 アプリに対象者に関するインサイトのデータを表示します。
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059594"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="5fed0-103">顧客カード アドイン (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="5fed0-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="5fed0-104">Dynamics 365 アプリで直接、顧客を全方位から確認します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="5fed0-105">サポートされている Dynamics 365 アプリにインストールされた顧客カード アドインを使用すると、人口統計、インサイト、活動タイムラインの表示を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="5fed0-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="5fed0-106">アドインは、接続されている Dynamics 365 アプリのデータに影響を与えることなく、Customer Insights からデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="5fed0-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="5fed0-107">Prerequisites</span></span>

- <span data-ttu-id="5fed0-108">アドインは、Sales や Customer Service など、Dynamics 365 モデル駆動型アプリ 9.0 以降でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="5fed0-109">Dynamics 365 のデータを対象者に関するインサイトの顧客プロファイルにマップするには、[Common Data Service コネクタを使用して Dynamics 365 アプリから取り込む](connect-power-query.md) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fed0-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="5fed0-110">顧客カード アドインのすべての Dynamics 365 ユーザーは、データを表示するために対象者に関するインサイトの [ユーザーとして追加](permissions.md) されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fed0-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="5fed0-111">データの検索を機能させるには、対象者に関するインサイトの [検索およびフィルター機能を構成](search-filter-index.md) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fed0-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="5fed0-112">各アドイン コントロールは、対象者に関するインサイトの特定のデータに依存します:</span><span class="sxs-lookup"><span data-stu-id="5fed0-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="5fed0-113">メジャー制御: [構成済みメジャー](measures.md) が必要です。</span><span class="sxs-lookup"><span data-stu-id="5fed0-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="5fed0-114">インテリジェンス制御: [予測](predictions.md) または [カスタム モデル](custom-models.md) を使用して生成されたデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="5fed0-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="5fed0-115">人口統計コントロール: 人口統計フィールド (年齢や性別など) は、統合顧客プロファイルで利用できます。</span><span class="sxs-lookup"><span data-stu-id="5fed0-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="5fed0-116">エンリッチメント制御 : 顧客プロファイルに適用されるアクティブな[エンリッチメント](enrichment-hub.md)が必要です。</span><span class="sxs-lookup"><span data-stu-id="5fed0-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="5fed0-117">タイムライン コントロール: [構成済みアクティビティ](activities.md) が必要です。</span><span class="sxs-lookup"><span data-stu-id="5fed0-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="5fed0-118"> 顧客カード アドイン のインストール</span><span class="sxs-lookup"><span data-stu-id="5fed0-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="5fed0-119">カスタマー カード アドインは、Dynamics 365 の Customer Engagement アプリのソリューションです。</span><span class="sxs-lookup"><span data-stu-id="5fed0-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="5fed0-120">ソリューションをインストールするには、AppSource に移動し、**Dynamics 顧客カード** を検索します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="5fed0-121">[AppSource で顧客カードアドイン](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) を選択して、**今すぐ入手** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="5fed0-122">ソリューションをインストールするには、Dynamics 365 アプリの管理者の資格情報でログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fed0-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="5fed0-123">ソリューションが環境にインストールされるまでに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5fed0-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="5fed0-124">顧客カードアドインの構成</span><span class="sxs-lookup"><span data-stu-id="5fed0-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="5fed0-125">管理者は、 Dynamics 365の **設定** セクションに移動し、**ソリューション** を選択してください。</span><span class="sxs-lookup"><span data-stu-id="5fed0-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="5fed0-126">**Dynamics 365 Customer Insights 顧客カード アドイン (プレビュー)** ソリューションの **表示名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5fed0-127">![表示名の選択](media/select-display-name.png "表示名の選択")</span><span class="sxs-lookup"><span data-stu-id="5fed0-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="5fed0-128">**サインイン** を選択し、Customer Insights の構成に使用する管理者アカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5fed0-129">**サインイン** ボタンを選択する場合に、ブラウザのポップアップ ブロッカーが認証ウィンドウをブロックしないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="5fed0-130">データを取得する Customer Insights 環境を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="5fed0-131">Dynamics 365 アプリでレコードへのフィールド マッピングを定義します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="5fed0-132">Customer Insights のデータに応じて、次のオプションのマップを選択できます:</span><span class="sxs-lookup"><span data-stu-id="5fed0-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="5fed0-133">取引先担当者とマップするには、取引先担当者エンティティの ID と一致する顧客エンティティのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="5fed0-134">取引先企業とマップするには、取引先企業エンティティの ID と一致する顧客エンティティのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5fed0-135">![取引先担当者 ID フィールド](media/contact-id-field.png "取引先担当者 ID フィールド")</span><span class="sxs-lookup"><span data-stu-id="5fed0-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="5fed0-136">設定を保存するには、**構成を保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="5fed0-137">次に、Dynamics 365 でセキュリティ ロールを割り当てて、ユーザーが顧客カードをカスタマイズして表示できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fed0-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="5fed0-138">Dynamics 365 で、**設定** > **セキュリティ** > **ユーザー** に移動します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="5fed0-139">ユーザー ロールを編集するユーザーを選択し、**役割を管理する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="5fed0-140">組織全体で使用するカードに表示されているコンテンツをカスタマイズするユーザーに **Customer Insights カード カスタマイザ** のロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5fed0-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="5fed0-141">フォームに顧客カード コントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="5fed0-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="5fed0-142">顧客カードコントロールを連絡先フォームに追加するには、**設定** > **カスタマイズ** Dynamics 365 の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="5fed0-143">**システムのカスタマイズ** を選択。</span><span class="sxs-lookup"><span data-stu-id="5fed0-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="5fed0-144">**取引先担当者** エンティティを参照し、メニューを展開して、**フォーム** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="5fed0-145">顧客カード管理を追加したい取引先担当者フォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5fed0-146">![取引先担当者フォームを選択する](media/contact-active-forms.png "取引先担当者フォームを選択する")</span><span class="sxs-lookup"><span data-stu-id="5fed0-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="5fed0-147">人口統計コントロールを追加するには、フォーム エディターで、任意のフィールドを **フィールド エクスプローラー** から人口統計コントロールを配置する場所にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="5fed0-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="5fed0-148">今追加したフォームのフィールドを選択し、**プロパティの変更** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="5fed0-149">**コントロール** タブに移動し、**コントロールの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="5fed0-150">利用可能なカスタム コントロールの 1 つを選択し、**追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="5fed0-151">**フィールドのプロパティ** ダイアログで、**フォームにラベルを表示する** チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5fed0-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="5fed0-152">**Web** オプションをコントロールに選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="5fed0-153">エンリッチメント制御で、**enrichmentType** フィールドを設定して、表示するエンリッチメントのタイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="5fed0-154">エンリッチメントのタイプごとに個別のエンリッチメント コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="5fed0-155">**保存** そして **公開** を選択して、更新された問い合わせフォームを公開します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="5fed0-156">公開されている取引先担当者フォームに移動します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-156">Go to the published contact form.</span></span> <span data-ttu-id="5fed0-157">新しく追加されたコントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fed0-157">You'll see the newly added control.</span></span> <span data-ttu-id="5fed0-158">初めて使用するときはサインインする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="5fed0-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="5fed0-159">カスタム コントロールで表示したいものをカスタマイズするには、右上隅の編集ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="5fed0-160">顧客カード アドインのアップグレード</span><span class="sxs-lookup"><span data-stu-id="5fed0-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="5fed0-161">顧客カード アドインは自動的にアップグレードされません。</span><span class="sxs-lookup"><span data-stu-id="5fed0-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="5fed0-162">最新バージョンにアップグレードするには、アドインがインストールされている Dynamics 365 アプリでこの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5fed0-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="5fed0-163">Dynamics 365 アプリで、**設定** > **カスタマイズ**、そして **ソリューション** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="5fed0-164">アドインの表で、**CustomerInsightsCustomerCard** を探して、行を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="5fed0-165">アクションバーで **ソリューションのアップグレードを適用する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fed0-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Dynamics 365 アプリのカスタマイズ領域でソリューションをアップグレードする":::

1. <span data-ttu-id="5fed0-167">アップグレード プロセスを開始すると、アップグレードが完了するまで読み込みインジケータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fed0-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="5fed0-168">新しいバージョンがない場合、アップグレードでエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fed0-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
