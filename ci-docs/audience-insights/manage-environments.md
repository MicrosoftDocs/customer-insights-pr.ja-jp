---
title: 環境の作成および管理
description: サービスにサインアップする方法と環境を管理する方法について説明します。
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644139"
---
# <a name="manage-environments"></a><span data-ttu-id="2c3ee-103">環境の管理</span><span class="sxs-lookup"><span data-stu-id="2c3ee-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="2c3ee-104">この記事では、新しい組織を作成する方法と環境をプロビジョニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="2c3ee-105">サインアップと組織の作成</span><span class="sxs-lookup"><span data-stu-id="2c3ee-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="2c3ee-106">[Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) Web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="2c3ee-107">**使用開始** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="2c3ee-108">お好みの新規登録のシナリオを選択し、該当のリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="2c3ee-109">利用条件に同意して、**続行** を選択し、組織の作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="2c3ee-110">環境が作成されると、[Customer Insights](https://home.ci.ai.dynamics.com) にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="2c3ee-111">デモ環境を使用してアプリを探索するか、次のセクションに示す手順に従って新しい環境を作成してください。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="2c3ee-112">環境の設定を指定した後、**作成する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="2c3ee-113">環境が正常に作成された後、サインインします。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="2c3ee-114">既存の組織で環境を作成する</span><span class="sxs-lookup"><span data-stu-id="2c3ee-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="2c3ee-115">新規環境を作成するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="2c3ee-116">まったく新たな構成を指定することも、既存の環境から一部の構成設定をコピーすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="2c3ee-117">環境の作成方法 :</span><span class="sxs-lookup"><span data-stu-id="2c3ee-117">To create an environment:</span></span>

1. <span data-ttu-id="2c3ee-118">アプリのヘッダーから **設定** 記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="2c3ee-119">**新しい環境** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2c3ee-120">![環境の設定](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="2c3ee-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="2c3ee-121">**新しい環境の作成** ダイアログで **新しい環境** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="2c3ee-122">[現在の環境からデータをコピー](#additional-considerations-for-copy-configuration-preview) する場合は、**既存の環境からコピー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="2c3ee-123">データのコピー元となる組織の、利用可能なすべての環境のリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="2c3ee-124">次の詳細を入力します:</span><span class="sxs-lookup"><span data-stu-id="2c3ee-124">Provide the following details:</span></span>
   - <span data-ttu-id="2c3ee-125">**名前**: この環境の名前。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="2c3ee-126">既存の環境からコピーする場合は、このフィールドには既にに入力されていますが、変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="2c3ee-127">**リージョン** : サービスが展開、ホストされるリージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="2c3ee-128">**タイプ**: 実稼働環境、またはサンドボックス環境のどちらを作成するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="2c3ee-129">オプションで、**詳細設定** を選択できます:</span><span class="sxs-lookup"><span data-stu-id="2c3ee-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="2c3ee-130">**すべてのデータを保存する** : Customer Insights から生成された出力データを保存する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="2c3ee-131">次の2つの選択肢があります: **Customer Insights ストレージ** (Customer Insights チームが管理する Azure Data Lake) と **Azure Data Lake Storage Gen2** (ユーザーが管理する Azure Data Lake Storage) です。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="2c3ee-132">既定では、Customer Insights のストレージが選択されています。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2c3ee-133">Azure Data Lake Storage にデータを保存することで、その Azure Storage のアカウントに対して適切な地理的位置にデータが転送され、保存されることに同意したことになります。これは、 Dynamics 365 Customer Insights におけるデータの保存場所とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="2c3ee-134">Microsoft Trust Center を詳しく知る。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="2c3ee-135">現在、取り込まれたエンティティは常に Customer Insights が管理するデータレイクに保存されます。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="2c3ee-136">環境の作成時に選択したのと同じ Azure リージョンの Azure Data Lake Gen2 ストレージ アカウントのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="2c3ee-137">Azure Data Lake Gen2 Hierarchical Name Space (HNS) が有効となっているストレージ アカウントのみに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="2c3ee-138">Azure Data Lake Storage Gen2 オプションの場合、認証にリソース ベースのオプションとサブスクリプション ベースのオプションのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="2c3ee-139">詳細については、[対象者に関するインサイトを Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="2c3ee-140">**コンテナー** 名は変更できず、"customerinsights" になります。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="2c3ee-141">[予測](predictions.md) を使用する場合は、**予測の使用** の下の **サーバー アドレス** フィールドに Common Data Service インスタンスの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="2c3ee-142">データ インジェストやセグメントの作成などのプロセスを実行すると、対応するフォルダーが上記で指定したストレージ アカウントに作成されます。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="2c3ee-143">データ ファイルと model.json ファイルが作成され、実行するプロセスに基づいてそれぞれのサブ フォルダーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="2c3ee-144">Customer Insights の複数の環境を作成し、それらの環境からの出力エンティティをストレージ アカウントに保存することを選択した場合、コンテナーに ci_<environmentid> が含まれる環境ごとに個別のフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="2c3ee-145">コピー構成に関する追加の考慮事項 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2c3ee-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="2c3ee-146">以下の構成設定がコピーされます：</span><span class="sxs-lookup"><span data-stu-id="2c3ee-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="2c3ee-147">機能の構成</span><span class="sxs-lookup"><span data-stu-id="2c3ee-147">Feature configurations</span></span>
- <span data-ttu-id="2c3ee-148">統合/インポートされたデータソース</span><span class="sxs-lookup"><span data-stu-id="2c3ee-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="2c3ee-149">データ統合 (マッピング、一致、マージ) の構成</span><span class="sxs-lookup"><span data-stu-id="2c3ee-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="2c3ee-150">セグメント</span><span class="sxs-lookup"><span data-stu-id="2c3ee-150">Segments</span></span>
- <span data-ttu-id="2c3ee-151">メジャー</span><span class="sxs-lookup"><span data-stu-id="2c3ee-151">Measures</span></span>
- <span data-ttu-id="2c3ee-152">顧客間関係</span><span class="sxs-lookup"><span data-stu-id="2c3ee-152">Relationships</span></span>
- <span data-ttu-id="2c3ee-153">活動 </span><span class="sxs-lookup"><span data-stu-id="2c3ee-153">Activities</span></span>
- <span data-ttu-id="2c3ee-154">検索/フィルターのインデックス</span><span class="sxs-lookup"><span data-stu-id="2c3ee-154">Search & filter Index</span></span>
- <span data-ttu-id="2c3ee-155">エクスポート先</span><span class="sxs-lookup"><span data-stu-id="2c3ee-155">Export destinations</span></span>
- <span data-ttu-id="2c3ee-156">スケジュールされた更新</span><span class="sxs-lookup"><span data-stu-id="2c3ee-156">Scheduled refresh</span></span>
- <span data-ttu-id="2c3ee-157">エンリッチメント</span><span class="sxs-lookup"><span data-stu-id="2c3ee-157">Enrichments</span></span>
- <span data-ttu-id="2c3ee-158">モデル管理</span><span class="sxs-lookup"><span data-stu-id="2c3ee-158">Model management</span></span>
- <span data-ttu-id="2c3ee-159">ロールの割り当て</span><span class="sxs-lookup"><span data-stu-id="2c3ee-159">Role assignments</span></span>

<span data-ttu-id="2c3ee-160">以下の構成設定はコピー *されません*：</span><span class="sxs-lookup"><span data-stu-id="2c3ee-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="2c3ee-161">顧客のプロファイル。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-161">Customer profiles.</span></span>
- <span data-ttu-id="2c3ee-162">データ ソースの資格情報。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-162">Data source credentials.</span></span> <span data-ttu-id="2c3ee-163">すべてのデータ ソースの認証情報を提供し、データソースを手動で更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="2c3ee-164">Common Data Model フォルダーのデータソース、および Common Data Service マネージド レイク。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="2c3ee-165">これらのデータ ソースは、ソース環境と同じ名前で手動で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="2c3ee-166">環境をコピーすると、新たな環境が作成されたことを示す確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="2c3ee-167">**データソースに移動する** を選択してデータ ソースのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="2c3ee-168">すべてのデータソースの状態が **資格情報が必須** となっています。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="2c3ee-169">データソースを編集し、資格情報を入力して更新します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2c3ee-170">![コピーされたデータ ソース](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="2c3ee-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="2c3ee-171">データソースの更新後、**データ** > **統一** に移動します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="2c3ee-172">ここには、ソース環境に由来する設定があります。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="2c3ee-173">必要に応じて編集するか、**実行** を選択してデータ統合プロセスを開始し、統合された顧客エンティティを作成します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="2c3ee-174">データ統合の完了後は、**計測** と **セグメント** に移動し、それらを更新します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="2c3ee-175">既存の環境を編集する</span><span class="sxs-lookup"><span data-stu-id="2c3ee-175">Edit an existing environment</span></span>

<span data-ttu-id="2c3ee-176">既存の環境について詳細な部分を編集できます。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="2c3ee-177">**管理** > **システム** > **詳細** に移動します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="2c3ee-178">**編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-178">Select **Edit**.</span></span>

3. <span data-ttu-id="2c3ee-179">環境の **表示名称** を更新できますが、**リージョン** または **タイプ** の変更はできません。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="2c3ee-180">環境がデータを Azure Data Lake Storage Gen2 に保存するように構成されている場合は、 **アカウントキー** を更新することができます。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="2c3ee-181">ただし、**アカウント名** または **コンテナー** 名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="2c3ee-182">オプションで、アカウント キー ベースの接続から、リソース ベースまたはサブスクリプション ベースの接続に更新できます。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="2c3ee-183">一度アップグレードすると、アップグレード後にアカウント キーに戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="2c3ee-184">詳細については、[対象者に関するインサイトを Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="2c3ee-185">接続の更新時に、**コンテナー** 情報を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="2c3ee-186">既存の環境のリセット</span><span class="sxs-lookup"><span data-stu-id="2c3ee-186">Reset an existing environment</span></span>

<span data-ttu-id="2c3ee-187">すべての構成を削除し、取り込んだデータを削除する場合は、環境を空の状態にリセットできます。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="2c3ee-188">**管理** > **システム** > **詳細** に移動します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="2c3ee-189">**リセット** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="2c3ee-190">削除を確認するには、環境名を入力して、**リセット** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="2c3ee-191">既存の環境を削除する</span><span class="sxs-lookup"><span data-stu-id="2c3ee-191">Delete an existing environment</span></span>

1. <span data-ttu-id="2c3ee-192">**管理** > **システム** > **詳細** に移動します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="2c3ee-193">**削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-193">Select **Delete**.</span></span>

1. <span data-ttu-id="2c3ee-194">削除の確認をするには、当該環境の名前を入力して **削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
