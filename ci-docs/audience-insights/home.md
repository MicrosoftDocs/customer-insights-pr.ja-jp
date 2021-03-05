---
title: 対象者に関するインサイトのホーム ページ
description: ホーム ページでアプリの詳細を確認します。
ms.date: 01/07/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7cc767f5d80b213a4c1bb5b2e8062bd44c15279b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477047"
---
# <a name="create-a-new-environment"></a><span data-ttu-id="04ba9-103">新しい環境の作成</span><span class="sxs-lookup"><span data-stu-id="04ba9-103">Create a new environment</span></span>

## <a name="create-a-trial-environment"></a><span data-ttu-id="04ba9-104">試用版環境の作成</span><span class="sxs-lookup"><span data-stu-id="04ba9-104">Create a trial environment</span></span>

<span data-ttu-id="04ba9-105">[試用版サインアップ ページ](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights) で試用版にサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="04ba9-105">You can sign up for a trial on the [trial sign up page](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span></span> 

> [!NOTE]
> <span data-ttu-id="04ba9-106">試用期間は 30 日後に終了します。</span><span class="sxs-lookup"><span data-stu-id="04ba9-106">Trials expire after 30 days.</span></span>

1. <span data-ttu-id="04ba9-107">**無料試用版へのサインアップ** オプションを選択し、**今すぐサインアップ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04ba9-107">Choose the **Sign up for a free trial** option and select **Sign up now**.</span></span>

1. <span data-ttu-id="04ba9-108">職場または学校のメール アドレスを入力し、ご自身の詳細を入力して、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04ba9-108">Provide your work or school email address, tell us a more about yourself and select **Next**.</span></span>

   :::image type="content" source="media/trial-signup-dialog.png" alt-text=" 無料の試用版にサインアップするためのダイアログ":::

1. <span data-ttu-id="04ba9-110">新しい環境の **名前** を入力します。</span><span class="sxs-lookup"><span data-stu-id="04ba9-110">Provide a **Name** for your new environment.</span></span> 

1. <span data-ttu-id="04ba9-111">試用版の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="04ba9-111">Select the trial type.</span></span>

1. <span data-ttu-id="04ba9-112">環境に応じた **リージョン** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04ba9-112">Choose the **Region** for your environment.</span></span>

1. <span data-ttu-id="04ba9-113">オプションで、Dynamics 365 組織の管理者の場合: **詳細設定** を選択し、顧客離反などの予測機能を使用する組織の URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="04ba9-113">Optionally, for admins of a Dynamics 365 organization: Select **Advanced settings** and provide the URL of your organization to use prediction features like customer churn.</span></span>

1. <span data-ttu-id="04ba9-114">**作成** を選びます。</span><span class="sxs-lookup"><span data-stu-id="04ba9-114">Select **Create**.</span></span> 

<span data-ttu-id="04ba9-115">環境が作成されると、架空のデータを使用してアプリを確認できる **デモ** 環境が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04ba9-115">After the environment was created, you'll see the **Demo** environment which lets you explore the app with fictitious data.</span></span> <span data-ttu-id="04ba9-116">業種に合わせてサンプル データを変更できます。</span><span class="sxs-lookup"><span data-stu-id="04ba9-116">You can change the sample data to match your industry.</span></span> <span data-ttu-id="04ba9-117">ヘッダーで、**設定** アイコンを選択し、**デモの設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04ba9-117">Select the **Settings** icon in the header and select **Demo settings**.</span></span> <span data-ttu-id="04ba9-118">さらに、視覚的なテーマを変更できます。</span><span class="sxs-lookup"><span data-stu-id="04ba9-118">Additionally, you can change the visual theme.</span></span> 

<span data-ttu-id="04ba9-119">サインアップ プロセス中に作成した [環境に切り替え](#switch-environments) て、独自のデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="04ba9-119">You [switch to the environment](#switch-environments) you created during the sign-up process to work with your own data.</span></span>

## <a name="create-a-new-production-or-sandbox-environment"></a><span data-ttu-id="04ba9-120">新しい運用環境またはサンドボックス環境の作成</span><span class="sxs-lookup"><span data-stu-id="04ba9-120">Create a new production or sandbox environment</span></span>

<span data-ttu-id="04ba9-121">ご使用の環境で、アプリヘッダーの **環境** ピッカーを選択し、**新規** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04ba9-121">In your environment, select the **Environments** picker in the app header and select **New**.</span></span>

<span data-ttu-id="04ba9-122">[試用版環境を作成](#create-a-trial-environment) する場合と同様に、手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="04ba9-122">Follow the steps as if you [create a trial environment](#create-a-trial-environment).</span></span> <span data-ttu-id="04ba9-123">既定では、データは Customer Insights の管理された Data Lake に保存されます。</span><span class="sxs-lookup"><span data-stu-id="04ba9-123">By default, data is stored in the Customer Insights managed data lake.</span></span> <span data-ttu-id="04ba9-124">**詳細設定** を選択して独自の Azure Data Lake にデータを保存すると、追加オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="04ba9-124">You get an additional option when selecting **Advanced settings** to store your data in your own Azure Data Lake.</span></span> <span data-ttu-id="04ba9-125">アカウント名とアカウント キーを入力して、Azure Data Lake への接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="04ba9-125">Provide your account name and account key to establish a connection to your Azure Data Lake.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="04ba9-126">Azure Data Lake Storage にデータを保存することで、データがその Azure Storage アカウントの適切な地理的位置に転送され保存されることに同意することになりますが、Dynamics 365 Customer Insights でデータが保存される場所とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="04ba9-126">By saving data to your Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="04ba9-127">Microsoft Trust Center を詳しく知る。</span><span class="sxs-lookup"><span data-stu-id="04ba9-127">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a><span data-ttu-id="04ba9-128">ホーム ページの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="04ba9-128">Explore the home page</span></span>

<span data-ttu-id="04ba9-129">[Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/)からの対象者インサイトへは、次の URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/) からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="04ba9-129">You can [access audience insights from Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) on the following URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span></span>
<span data-ttu-id="04ba9-130">**ホーム** ページには、[マップ](map-entities.md)、[一致](match-entities.md)、および[マージ](merge-entities.md) フェーズ完了後のセグメント、メジャー、およびエンリッチメント データ (構成されている場合) の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04ba9-130">The **Home** page shows an overview of segments, measures, and enrichment data (if configured)after completing the [map](map-entities.md), [match](match-entities.md), and [merge](merge-entities.md) phases.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="04ba9-131">![ホーム ページでのインサイト](media/home-page-insights.png "ホーム ページでのインサイト")</span><span class="sxs-lookup"><span data-stu-id="04ba9-131">![Insights on Home page](media/home-page-insights.png "Insights on Home page")</span></span>

<span data-ttu-id="04ba9-132">**最近のセグメント** 配下で、定義した人口統計、行動、またはトランザクションの属性に基づいた顧客のグループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="04ba9-132">Under **Recent segments**, you see groups of customers based on demographic, behavioral, or transactional attributes that you've defined.</span></span> <span data-ttu-id="04ba9-133">[セグメントの作成](segments.md)は、顧客ベースをグループ化し、ビジネス活動をより的確にターゲティングするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="04ba9-133">[Creating segments](segments.md) helps you to group your customer base and better target your business activities.</span></span>

<span data-ttu-id="04ba9-134">**最近のメジャー** には、定義した[主要業績評価指標 (KPI)](measures.md) がタイル表示されます。</span><span class="sxs-lookup"><span data-stu-id="04ba9-134">**Recent measures** show tiles with [key performance indicators (KPIs)](measures.md) that you've defined.</span></span> <span data-ttu-id="04ba9-135">たとえば、顧客が解約する平均的な可能性や、顧客ごとの平均オンライン支出などです。</span><span class="sxs-lookup"><span data-stu-id="04ba9-135">For example, average likelihood of a customer to churn or the average online spend per customer.</span></span>

<span data-ttu-id="04ba9-136">**最近のエンリッチメント** セクションには、最近完了したエンリッチメントの実行結果が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="04ba9-136">The **Recent enrichments** section lists the results of the enrichment runs that completed recently.</span></span> <span data-ttu-id="04ba9-137">[エンリッチメント](enrichment-hub.md)は、顧客ベースに基づく情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="04ba9-137">[Enrichments](enrichment-hub.md) add information about your customer base.</span></span> <span data-ttu-id="04ba9-138">これらは、例えば親しんでいる興味の対象をブランドを理解することで得られます。</span><span class="sxs-lookup"><span data-stu-id="04ba9-138">For example, by understanding the interests and brands that they have affinity for.</span></span>

## <a name="switch-environments"></a><span data-ttu-id="04ba9-139">環境の切り替え</span><span class="sxs-lookup"><span data-stu-id="04ba9-139">Switch environments</span></span>

<span data-ttu-id="04ba9-140">ページ右上隅にある **環境** コントロールを選択肢て、環境を変更します。</span><span class="sxs-lookup"><span data-stu-id="04ba9-140">Select the **Environment** control in the upper-right corner of the page to change environments.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="04ba9-141">![環境の切り替え](media/home-page-environment-switcher.png "環境の切り替え")</span><span class="sxs-lookup"><span data-stu-id="04ba9-141">![Switch environment](media/home-page-environment-switcher.png "Switch environment")</span></span>

<span data-ttu-id="04ba9-142">管理者は[複数の環境](manage-environments.md)を作成、管理できます。</span><span class="sxs-lookup"><span data-stu-id="04ba9-142">Administrators can create and manage [multiple environments](manage-environments.md).</span></span> <span data-ttu-id="04ba9-143">たとえば、組織が国際的に事業を展開していて、データや分析情報をさまざまな方法で分離する必要がある場合には、複数の環境を維持することが有効かもしれません。</span><span class="sxs-lookup"><span data-stu-id="04ba9-143">Maintaining more than one environment may be useful if, for example, your organization operates internationally and you need to segregate data and insights in different ways.</span></span>

## <a name="next-step"></a><span data-ttu-id="04ba9-144">次のステップ</span><span class="sxs-lookup"><span data-stu-id="04ba9-144">Next step</span></span>

<span data-ttu-id="04ba9-145">ホームページで自分の分析情報を見るには、まずデータに対して[データソースの追加](data-sources.md)と[統合](data-unification.md)を行い、顧客プロファイルを構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04ba9-145">To see your own insights on the home page, you'll first need to [add data sources](data-sources.md) and [unify](data-unification.md) your data to build customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]