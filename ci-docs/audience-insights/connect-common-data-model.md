---
title: Common Data Model データを Azure Data Lake アカウントに接続する
description: Azure Data Lake Storage を使用して、Common Data Model データを操作します。
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596551"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="4cf97-103">Azure Data Lake アカウントを使用して Common Data Model のフォルダーに接続する</span><span class="sxs-lookup"><span data-stu-id="4cf97-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="4cf97-104">この記事では、Azure Data Lake Storage Gen2 アカウントを使用して、Common Data Model フォルダーからデータを取り込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="4cf97-105">重要な考慮事項</span><span class="sxs-lookup"><span data-stu-id="4cf97-105">Important considerations</span></span>

- <span data-ttu-id="4cf97-106">Azure Data Lake のデータは、Common Data Model に準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cf97-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="4cf97-107">他のフォーマットは現在のところ対応していません。</span><span class="sxs-lookup"><span data-stu-id="4cf97-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="4cf97-108">データの取り込みは、Azure Data Lake *Gen2* ストレージ アカウントのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4cf97-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="4cf97-109">Azure Data Lake Gen1 ストレージ アカウントを使用してデータを取り込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="4cf97-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="4cf97-110">Azure サービス プリンシパルで認証するには、テナントで構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4cf97-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="4cf97-111">詳細については、[対象者に関するインサイトを Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cf97-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="4cf97-112">接続してデータを取り込む Azure Data Lake は、Dynamics 365 Customer Insights 環境と同じ Azure リージョンに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cf97-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="4cf97-113">別の Azure リージョンにあるデータ レイクから Common Data Model フォルダーへの接続はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4cf97-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="4cf97-114">環境の Azure リージョンを確認するには、対象者に関するインサイトで **管理** > **システム** > **詳細** に移動します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="4cf97-115">オンライン サービスに保存されたデータは、Dynamics 365 Customer Insights でデータが処理または保存される場所とは別の場所に保存される場合があります。</span><span class="sxs-lookup"><span data-stu-id="4cf97-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="4cf97-116">  オンライン サービスに保存されているデータをインポート、あるいは接続することで、 Dynamics 365 Customer Insights にデータの転送と保存がされることに同意するものとします。詳細については、 [Microsoft Trust Center](https://www.microsoft.com/trust-center) をご覧ください</span><span class="sxs-lookup"><span data-stu-id="4cf97-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="4cf97-117">Common Data Model フォルダーへの接続</span><span class="sxs-lookup"><span data-stu-id="4cf97-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="4cf97-118">対象者に関するインサイトで、**データ** > **データ ソース** に移動します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="4cf97-119">**データソースの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="4cf97-120">**Common Data Model フォルダーへの接続** を選択し、データ ソースの **名前** を入力して、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="4cf97-121">名前のガイドライン:</span><span class="sxs-lookup"><span data-stu-id="4cf97-121">Name guidelines:</span></span> 
   - <span data-ttu-id="4cf97-122">文字で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cf97-122">Start with a letter.</span></span>
   - <span data-ttu-id="4cf97-123">文字と数字のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="4cf97-123">Use letters and numbers only.</span></span> <span data-ttu-id="4cf97-124">特殊文字とスペースは使用できません。</span><span class="sxs-lookup"><span data-stu-id="4cf97-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="4cf97-125">3〜64 文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="4cf97-126">認証にリソース ベースのオプションとサブスクリプション ベースのオプションのどちらを使用するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4cf97-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="4cf97-127">詳細については、[対象者に関するインサイトを Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cf97-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="4cf97-128">**コンテナー** 情報を入力し、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4cf97-129">![Azure Data Lake の新しい接続の詳細を入力するためのダイアログ ボックス](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="4cf97-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="4cf97-130">データ ソースに接続して作成するには、上記のコンテナまたはストレージ アカウントのどちらかに次のうち 1 つのロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="4cf97-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="4cf97-131">ストレージ Blob データ閲覧者</span><span class="sxs-lookup"><span data-stu-id="4cf97-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="4cf97-132">ストレージ Blob データ所有者</span><span class="sxs-lookup"><span data-stu-id="4cf97-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="4cf97-133">ストレージ Blob データ共同作成者</span><span class="sxs-lookup"><span data-stu-id="4cf97-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="4cf97-134">**Common Data Model フォルダーの選択** ダイアログで、データをインポートする model.json または manifest.json ファイルを選択し、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="4cf97-135">環境内にある別のデータ ソースに関連付けられている model.json または manifest.json ファイルは一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="4cf97-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="4cf97-136">選択した model.json または manifest.json ファイルで利用可能なエンティティの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="4cf97-137">使用可能なエンティティのリストから、レビューと選択をし、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="4cf97-138">選択したエンティティのすべてが新しいデータ ソースから取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="4cf97-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4cf97-139">![ダイアログ ボックスに model.json ファイルのエンティティ リストが表示されます](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="4cf97-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="4cf97-140">データ プロファイルを有効にするデータ エンティティを指定し、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="4cf97-141">データ プロファイルによって分析とその他の機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="4cf97-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="4cf97-142">エンティティ全体を選択して、エンティティからすべての属性を選択するか、選択した特定の属性を選択できます。</span><span class="sxs-lookup"><span data-stu-id="4cf97-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="4cf97-143">既定では、データ プロファイルが有効になっているエンティティはありません。</span><span class="sxs-lookup"><span data-stu-id="4cf97-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4cf97-144">![データ プロファイルを表示するダイアログ ボックス](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="4cf97-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="4cf97-145">選択内容を保存した後、**データ ソース** のページが開きます。</span><span class="sxs-lookup"><span data-stu-id="4cf97-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="4cf97-146">以上で、データ ソースとして Common Data Model フォルダーの接続が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cf97-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="4cf97-147">model.json または manifest.json ファイルは、同じ環境内の 1 つのデータ ソースにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="4cf97-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="4cf97-148">ただし、同じ model.json または manifest.json ファイルを複数の環境のデータ ソースに使用できます。</span><span class="sxs-lookup"><span data-stu-id="4cf97-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="4cf97-149">共通データモデルフォルダーのデータ ソースを編集する</span><span class="sxs-lookup"><span data-stu-id="4cf97-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="4cf97-150">Common Data Model フォルダーを含むストレージ アカウントのアクセス キーを更新できます。</span><span class="sxs-lookup"><span data-stu-id="4cf97-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="4cf97-151">model.json または manifest.json ファイルを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="4cf97-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="4cf97-152">ご利用のストレージ アカウントとは異なるコンテナーに接続をする場合や、アカウント名を変更する場合は、[新しいデータ ソースの接続を作成してください](#connect-to-a-common-data-model-folder)。</span><span class="sxs-lookup"><span data-stu-id="4cf97-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="4cf97-153">対象者に関するインサイトで、**データ** > **データ ソース** に移動します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="4cf97-154">更新を行うデータ ソースの横にある省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="4cf97-155">リストから **編集** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="4cf97-156">任意で、 **アクセス キー** を更新し、 **次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![既存のデータ ソースのアクセス キーを編集、更新するダイアログ](media/edit-access-key.png)

5. <span data-ttu-id="4cf97-158">オプションで、アカウント キー接続からリソース ベースまたはサブスクリプション ベースの接続に更新できます。</span><span class="sxs-lookup"><span data-stu-id="4cf97-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="4cf97-159">詳細については、[対象者に関するインサイトを Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cf97-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="4cf97-160">接続の更新時に、**コンテナー** 情報を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="4cf97-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Azure Data Lake の既存のストレージ アカウントへの接続の詳細を入力するためのダイアログ ボックス](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="4cf97-162">データ ソースに接続して作成するには、上記のコンテナまたはストレージ アカウントのどちらかに次のうち 1 つのロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="4cf97-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="4cf97-163">ストレージ Blob データ閲覧者</span><span class="sxs-lookup"><span data-stu-id="4cf97-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="4cf97-164">ストレージ Blob データ所有者</span><span class="sxs-lookup"><span data-stu-id="4cf97-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="4cf97-165">ストレージ Blob データ共同作成者</span><span class="sxs-lookup"><span data-stu-id="4cf97-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="4cf97-166">必要に応じて、コンテナとは異なるエンティティのセットを含む別の model.json または manifest.json ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="4cf97-167">オプションで、取り込む追加のエンティティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4cf97-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="4cf97-168">依存関係がない場合は、選択済のエンティティを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="4cf97-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4cf97-169">既存の model.json または manifest.json ファイルとエンティティのセットに依存関係がある場合、エラー メッセージが表示され、別の model.json または manifest.json ファイルを選択できません。</span><span class="sxs-lookup"><span data-stu-id="4cf97-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="4cf97-170">model.json または manifest.json ファイルを変更する前にこれらの依存関係を削除するか、依存関係の削除を回避するために使用する model.json または manifest.json ファイルを使用して新しいデータ ソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="4cf97-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="4cf97-171">オプションで、追加の属性やエンティティを選択して、データ プロファイルを有効にしたり、すでに選択されているものを無効にしたりできます。</span><span class="sxs-lookup"><span data-stu-id="4cf97-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]