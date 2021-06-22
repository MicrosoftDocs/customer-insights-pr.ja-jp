---
title: 環境の作成および管理
description: サービスにサインアップする方法と環境を管理する方法について説明します。
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 06310ea6fc72f26e21e185a6abcb5d19d4b201f6
ms.sourcegitcommit: e5425f060c8d80f9510283dc610ce70a4e709b1e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2021
ms.locfileid: "6259105"
---
# <a name="manage-environments"></a><span data-ttu-id="36a61-103">環境の管理</span><span class="sxs-lookup"><span data-stu-id="36a61-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="36a61-104">この記事では、新しい組織を作成する方法と環境をプロビジョニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="36a61-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="36a61-105">サインアップと組織の作成</span><span class="sxs-lookup"><span data-stu-id="36a61-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="36a61-106">[Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) Web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="36a61-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="36a61-107">**使用開始** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a61-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="36a61-108">お好みの新規登録のシナリオを選択し、該当のリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="36a61-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="36a61-109">利用条件に同意して、**続行** を選択し、組織の作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="36a61-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="36a61-110">環境が作成されると、[Customer Insights](https://home.ci.ai.dynamics.com) にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="36a61-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="36a61-111">デモ環境を使用してアプリを探索するか、次のセクションに示す手順に従って新しい環境を作成してください。</span><span class="sxs-lookup"><span data-stu-id="36a61-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="36a61-112">環境の設定を指定した後、**作成する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a61-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="36a61-113">環境が正常に作成された後、サインインします。</span><span class="sxs-lookup"><span data-stu-id="36a61-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="36a61-114">既存の組織で環境を作成する</span><span class="sxs-lookup"><span data-stu-id="36a61-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="36a61-115">新規環境を作成するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="36a61-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="36a61-116">まったく新たな構成を指定することも、既存の環境から一部の構成設定をコピーすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="36a61-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

> [!NOTE]
> <span data-ttu-id="36a61-117">組織では、Customer Insights ライセンスごとに *2* つの環境を作成できます。</span><span class="sxs-lookup"><span data-stu-id="36a61-117">Organizations can create *two* environments for every Customer Insights license.</span></span> <span data-ttu-id="36a61-118">組織が複数のライセンスを購入する場合は、[サポート チームに連絡](https://go.microsoft.com/fwlink/?linkid=2079641) して利用可能な環境の数を増やしてください。</span><span class="sxs-lookup"><span data-stu-id="36a61-118">If your organization purchases more than once license, please [contact our support team](https://go.microsoft.com/fwlink/?linkid=2079641) to increase the number of available environments.</span></span> <span data-ttu-id="36a61-119">容量とアドオン容量の詳細については、[Dynamics 365 のライセンス ガイド](https://go.microsoft.com/fwlink/?LinkId=866544) をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="36a61-119">For more information about capacity and add-on capacity, download [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).</span></span>

<span data-ttu-id="36a61-120">環境の作成方法 :</span><span class="sxs-lookup"><span data-stu-id="36a61-120">To create an environment:</span></span>

1. <span data-ttu-id="36a61-121">アプリのヘッダーにある **環境** ピッカーを選択します。</span><span class="sxs-lookup"><span data-stu-id="36a61-121">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="36a61-122">**新規** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a61-122">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="36a61-123">![環境の設定](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="36a61-123">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="36a61-124">**新しい環境の作成** ダイアログで **新しい環境** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a61-124">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="36a61-125">[現在の環境からデータをコピー](#considerations-for-copy-configuration-preview) する場合は、**既存の環境からコピー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a61-125">If you want to [copy data from the current environment](#considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="36a61-126">データのコピー元となる組織の、利用可能なすべての環境のリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36a61-126">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="36a61-127">次の詳細を入力します:</span><span class="sxs-lookup"><span data-stu-id="36a61-127">Provide the following details:</span></span>
   - <span data-ttu-id="36a61-128">**名前**: この環境の名前。</span><span class="sxs-lookup"><span data-stu-id="36a61-128">**Name**: The name for this environment.</span></span> <span data-ttu-id="36a61-129">既存の環境からコピーする場合は、このフィールドには既にに入力されていますが、変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="36a61-129">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="36a61-130">**リージョン** : サービスが展開、ホストされるリージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="36a61-130">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="36a61-131">**タイプ**: 実稼働環境、またはサンドボックス環境のどちらを作成するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="36a61-131">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

1. <span data-ttu-id="36a61-132">オプションで、**詳細設定** を選択できます:</span><span class="sxs-lookup"><span data-stu-id="36a61-132">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="36a61-133">**すべてのデータを保存する** : Customer Insights から生成された出力データを保存する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="36a61-133">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="36a61-134">次の2つの選択肢があります: **Customer Insights ストレージ** (Customer Insights チームが管理する Azure Data Lake) と **Azure Data Lake Storage Gen2** (ユーザーが管理する Azure Data Lake Storage) です。</span><span class="sxs-lookup"><span data-stu-id="36a61-134">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="36a61-135">既定では、Customer Insights のストレージが選択されています。</span><span class="sxs-lookup"><span data-stu-id="36a61-135">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="36a61-136">Azure Data Lake Storage にデータを保存することで、その Azure Storage のアカウントに対して適切な地理的位置にデータが転送され、保存されることに同意したことになります。これは、 Dynamics 365 Customer Insights におけるデータの保存場所とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="36a61-136">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="36a61-137">Microsoft Trust Center を詳しく知る。</span><span class="sxs-lookup"><span data-stu-id="36a61-137">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="36a61-138">現在、取り込まれたエンティティは常に Customer Insights が管理するデータレイクに保存されます。</span><span class="sxs-lookup"><span data-stu-id="36a61-138">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="36a61-139">環境の作成時に選択したのと同じ Azure リージョンの Azure Data Lake Gen2 ストレージ アカウントのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="36a61-139">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="36a61-140">Azure Data Lake Gen2 Hierarchical Name Space (HNS) が有効となっているストレージ アカウントのみに対応しています。</span><span class="sxs-lookup"><span data-stu-id="36a61-140">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="36a61-141">Azure Data Lake Storage Gen2 オプションの場合、認証にリソース ベースのオプションとサブスクリプション ベースのオプションのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="36a61-141">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="36a61-142">詳細については、[対象者に関するインサイトを Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36a61-142">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="36a61-143">**コンテナー** 名は変更できず、`customerinsights` になります。</span><span class="sxs-lookup"><span data-stu-id="36a61-143">The **Container** name can't be changed and will be `customerinsights`.</span></span>
   
   - <span data-ttu-id="36a61-144">[予測](predictions.md) を使用したり、Microsoft Dataverse を使用したデータ共有を構成したり、あるいはオンプレミスのデータ ソースからのデータ インジェストを有効にしたりする場合は、**Microsoft Dataverse とのデータ共有を構成し、追加の機能を有効にする** の下にある Microsoft Dataverse 環境の URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="36a61-144">If you want to use [predictions](predictions.md), configure data sharing with Microsoft Dataverse, or enable data ingestion from on-premises data sources, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="36a61-145">**データ共有を有効にする** を選択して、Customer Insights 出力データを Microsoft Dataverse マネージド Data Lake と共有します。</span><span class="sxs-lookup"><span data-stu-id="36a61-145">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="36a61-146">Microsoft Dataverse マネージド Data Lake とのデータ共有は、すべてのデータを自分の Azure Data Lake Storage に保存する場合、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="36a61-146">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="36a61-147">[エンティティの欠落値の予測](predictions.md)は、Microsoft Dataverse マネージド Data Lake とのデータ共有を有効にした場合、現在はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="36a61-147">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="36a61-148">![Microsoft Dataverse](media/datasharing-with-DataverseMDL.png) とのデータ共有を可能にする構成オプション</span><span class="sxs-lookup"><span data-stu-id="36a61-148">![Configuration options to enable data sharing with Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="36a61-149">データ インジェストやセグメントの作成などのプロセスを実行すると、対応するフォルダーが上記で指定したストレージ アカウントに作成されます。</span><span class="sxs-lookup"><span data-stu-id="36a61-149">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="36a61-150">データ ファイルと model.json ファイルが作成され、プロセス名に基づいてフォルダーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="36a61-150">Data files and model.json files will be created and added to folders based on the process name.</span></span>

   <span data-ttu-id="36a61-151">Customer Insights の複数の環境を作成し、それらの環境からの出力エンティティをストレージ アカウントに保存することを選択した場合、コンテナーに ci_<environmentid> が含まれる環境ごとに個別のフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="36a61-151">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="considerations-for-copy-configuration-preview"></a><span data-ttu-id="36a61-152">コピー構成に関する考慮事項 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="36a61-152">Considerations for copy configuration (preview)</span></span>

<span data-ttu-id="36a61-153">以下の構成設定がコピーされます：</span><span class="sxs-lookup"><span data-stu-id="36a61-153">The following configuration settings are copied:</span></span>

- <span data-ttu-id="36a61-154">機能の構成</span><span class="sxs-lookup"><span data-stu-id="36a61-154">Feature configurations</span></span>
- <span data-ttu-id="36a61-155">取り込んだ/インポートされたデータ ソース</span><span class="sxs-lookup"><span data-stu-id="36a61-155">Ingested/imported data sources</span></span>
- <span data-ttu-id="36a61-156">データ統合 (マッピング、一致、マージ) の構成</span><span class="sxs-lookup"><span data-stu-id="36a61-156">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="36a61-157">セグメント</span><span class="sxs-lookup"><span data-stu-id="36a61-157">Segments</span></span>
- <span data-ttu-id="36a61-158">メジャー</span><span class="sxs-lookup"><span data-stu-id="36a61-158">Measures</span></span>
- <span data-ttu-id="36a61-159">顧客間関係</span><span class="sxs-lookup"><span data-stu-id="36a61-159">Relationships</span></span>
- <span data-ttu-id="36a61-160">活動 </span><span class="sxs-lookup"><span data-stu-id="36a61-160">Activities</span></span>
- <span data-ttu-id="36a61-161">検索/フィルターのインデックス</span><span class="sxs-lookup"><span data-stu-id="36a61-161">Search & filter Index</span></span>
- <span data-ttu-id="36a61-162">エクスポート先</span><span class="sxs-lookup"><span data-stu-id="36a61-162">Export destinations</span></span>
- <span data-ttu-id="36a61-163">スケジュールされた更新</span><span class="sxs-lookup"><span data-stu-id="36a61-163">Scheduled refresh</span></span>
- <span data-ttu-id="36a61-164">エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="36a61-164">Enrichments</span></span>
- <span data-ttu-id="36a61-165">モデル管理</span><span class="sxs-lookup"><span data-stu-id="36a61-165">Model management</span></span>
- <span data-ttu-id="36a61-166">ロールの割り当て</span><span class="sxs-lookup"><span data-stu-id="36a61-166">Role assignments</span></span>

<span data-ttu-id="36a61-167">以下の構成設定はコピー *されません*：</span><span class="sxs-lookup"><span data-stu-id="36a61-167">The following settings are *not* copied:</span></span>

- <span data-ttu-id="36a61-168">顧客のプロファイル。</span><span class="sxs-lookup"><span data-stu-id="36a61-168">Customer profiles.</span></span>
- <span data-ttu-id="36a61-169">データ ソースの資格情報。</span><span class="sxs-lookup"><span data-stu-id="36a61-169">Data source credentials.</span></span> <span data-ttu-id="36a61-170">すべてのデータ ソースの認証情報を提供し、データソースを手動で更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36a61-170">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="36a61-171">Common Data Model フォルダーのデータソース、および Common Data Service マネージド レイク。</span><span class="sxs-lookup"><span data-stu-id="36a61-171">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="36a61-172">これらのデータ ソースは、ソース環境と同じ名前で手動で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36a61-172">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="36a61-173">環境をコピーすると、新たな環境が作成されたことを示す確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36a61-173">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="36a61-174">**データソースに移動する** を選択してデータ ソースのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="36a61-174">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="36a61-175">すべてのデータソースの状態が **資格情報が必須** となっています。</span><span class="sxs-lookup"><span data-stu-id="36a61-175">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="36a61-176">データソースを編集し、資格情報を入力して更新します。</span><span class="sxs-lookup"><span data-stu-id="36a61-176">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="36a61-177">![コピーされたデータ ソース](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="36a61-177">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="36a61-178">データソースの更新後、**データ** > **統一** に移動します。</span><span class="sxs-lookup"><span data-stu-id="36a61-178">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="36a61-179">ここには、ソース環境に由来する設定があります。</span><span class="sxs-lookup"><span data-stu-id="36a61-179">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="36a61-180">必要に応じて編集するか、**実行** を選択してデータ統合プロセスを開始し、統合された顧客エンティティを作成します。</span><span class="sxs-lookup"><span data-stu-id="36a61-180">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="36a61-181">データ統合の完了後は、**計測** と **セグメント** に移動し、それらを更新します。</span><span class="sxs-lookup"><span data-stu-id="36a61-181">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="36a61-182">既存の環境を編集する</span><span class="sxs-lookup"><span data-stu-id="36a61-182">Edit an existing environment</span></span>

<span data-ttu-id="36a61-183">既存の環境について詳細な部分を編集できます。</span><span class="sxs-lookup"><span data-stu-id="36a61-183">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="36a61-184">アプリのヘッダーにある **環境** ピッカーを選択します。</span><span class="sxs-lookup"><span data-stu-id="36a61-184">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="36a61-185">**編集** アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="36a61-185">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="36a61-186">**環境の編集** ボックスで、環境の **表示名** は更新できますが、**リージョン** または **タイプ** を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="36a61-186">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="36a61-187">環境がデータを Azure Data Lake Storage Gen2 に保存するように構成されている場合は、 **アカウントキー** を更新することができます。</span><span class="sxs-lookup"><span data-stu-id="36a61-187">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="36a61-188">ただし、**アカウント名** または **コンテナー** 名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="36a61-188">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="36a61-189">オプションで、アカウント キー ベースの接続から、リソース ベースまたはサブスクリプション ベースの接続に更新できます。</span><span class="sxs-lookup"><span data-stu-id="36a61-189">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="36a61-190">一度アップグレードすると、アップグレード後にアカウント キーに戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="36a61-190">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="36a61-191">詳細については、[対象者に関するインサイトを Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36a61-191">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="36a61-192">接続の更新時に、**コンテナー** 情報を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="36a61-192">You can't change **Container** information when updating the connection.</span></span>

6. <span data-ttu-id="36a61-193">オプションで、**Microsoft Dataverse とのデータ共有を構成し、追加の機能を有効にする** の下にある Microsoft Dataverse 環境の URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="36a61-193">Optionally, you can provide a Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="36a61-194">これらの機能には、Microsoft Dataverse に基づくアプリケーションおよびソリューションとのデータ共有、オンプレミスのデータ ソースからのデータ インジェスト、または使用 [予測](predictions.md) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="36a61-194">These capabilities include data sharing with applications and solutions based on Microsoft Dataverse, data ingestion from on-premises data sources, or the use [predictions](predictions.md).</span></span> <span data-ttu-id="36a61-195">**データ共有の有効化** を選択して、Customer Insights 出力データを Microsoft Dataverse Managed Data Lake と共有します。</span><span class="sxs-lookup"><span data-stu-id="36a61-195">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data lake.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="36a61-196">Microsoft Dataverse マネージド Data Lake とのデータ共有は、すべてのデータを自分の Azure Data Lake Storage に保存する場合、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="36a61-196">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
   > - <span data-ttu-id="36a61-197">Microsoft Dataverse Managed Data Lake を使用したデータ共有を有効にした場合、[エンティティでの不足値の予測](predictions.md) は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="36a61-197">[Prediction of missing values in an entity](predictions.md) is currently not supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

   <span data-ttu-id="36a61-198">Microsoft Dataverse でデータ共有を有効にすると、データ ソースやその他のプロセスの完全更新が開始されます。</span><span class="sxs-lookup"><span data-stu-id="36a61-198">After enabling data sharing with Microsoft Dataverse, a full refresh of your data sources and other processes starts.</span></span> <span data-ttu-id="36a61-199">プロセスが現在実行中の場合は、Microsoft Dataverse とのデータ共有を有効にするオプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="36a61-199">If processes are currently running, you don't see the option to enable data sharing with Microsoft Dataverse.</span></span> <span data-ttu-id="36a61-200">これらのプロセスが完了するのを待つか、キャンセルして、データ共有を有効にします。</span><span class="sxs-lookup"><span data-stu-id="36a61-200">Wait for those processes to complete or cancel them to enable data sharing.</span></span> 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Microsoft Dataverse とのデータ共有を有効にする構成オプション。":::
   
   <span data-ttu-id="36a61-202">データ インジェストやセグメントの作成などのプロセスを実行すると、対応するフォルダーが上記で指定したストレージ アカウントに作成されます。</span><span class="sxs-lookup"><span data-stu-id="36a61-202">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="36a61-203">実行するプロセスに応じて、データ ファイルと model.json ファイルが作成され、それぞれのサブフォルダーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="36a61-203">Data files and model.json files will be created and added to the respective subfolders, depending on the process you run.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="36a61-204">既存の環境のリセット</span><span class="sxs-lookup"><span data-stu-id="36a61-204">Reset an existing environment</span></span>

<span data-ttu-id="36a61-205">管理者の場合、すべての構成を削除し、取り込んだデータを削除する場合は、環境を空の状態にリセットできます。</span><span class="sxs-lookup"><span data-stu-id="36a61-205">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="36a61-206">アプリのヘッダーにある **環境** ピッカーを選択します。</span><span class="sxs-lookup"><span data-stu-id="36a61-206">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="36a61-207">リセットする環境を選択し、省略記号 **...** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a61-207">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="36a61-208">**リセット** オプションを選択してください。</span><span class="sxs-lookup"><span data-stu-id="36a61-208">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="36a61-209">削除を確認するには、環境名を入力して、**リセット** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a61-209">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="36a61-210">既存の環境を削除する (管理者のみ利用可能)</span><span class="sxs-lookup"><span data-stu-id="36a61-210">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="36a61-211">管理者の場合、管理している環境を削除できます。</span><span class="sxs-lookup"><span data-stu-id="36a61-211">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="36a61-212">アプリのヘッダーにある **環境** ピッカーを選択します。</span><span class="sxs-lookup"><span data-stu-id="36a61-212">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="36a61-213">リセットする環境を選択し、省略記号 **...** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a61-213">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="36a61-214">**削除** オプションを選択してください。</span><span class="sxs-lookup"><span data-stu-id="36a61-214">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="36a61-215">削除の確認をするには、当該環境の名前を入力して **削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a61-215">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
