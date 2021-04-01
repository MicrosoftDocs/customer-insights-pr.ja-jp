---
title: Azure Machine Learning の実験
description: Dynamics 365 Customer Insights で Azure Machine Learning ベースのモデルを使用します。
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597425"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="cbe44-103">Azure Machine Learning ベースのモデルを使用する</span><span class="sxs-lookup"><span data-stu-id="cbe44-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="cbe44-104">Dynamics 365 Customer Insights の統合データは、追加のビジネス インサイトを生成できる機械学習モデルを構築するためのソースです。</span><span class="sxs-lookup"><span data-stu-id="cbe44-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="cbe44-105">Customer Insights は、Machine Learning Studio (クラシック) や Azure Machine Learning と統合して、独自のカスタム モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="cbe44-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="cbe44-106">Machine Learning Studio (クラシック) 上に構築された実験の例については、[Machine Learning Studio (クラシック) の実験](machine-learning-studio-experiments.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbe44-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="cbe44-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="cbe44-107">Prerequisites</span></span>

- <span data-ttu-id="cbe44-108">Customer Insights を使用する</span><span class="sxs-lookup"><span data-stu-id="cbe44-108">Access to Customer Insights</span></span>
- <span data-ttu-id="cbe44-109">アクティブな Azure Enterprise のサブスクリプション</span><span class="sxs-lookup"><span data-stu-id="cbe44-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="cbe44-110">統合顧客プロファイル</span><span class="sxs-lookup"><span data-stu-id="cbe44-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="cbe44-111">[Azure Blob Storage へのエンティティのエクスポート](export-azure-blob-storage.md) 構成済み</span><span class="sxs-lookup"><span data-stu-id="cbe44-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="cbe44-112">Azure Machine Learning ワークスペースの設定</span><span class="sxs-lookup"><span data-stu-id="cbe44-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="cbe44-113">ワークスペースを作成するためのさまざまなオプションについては、[Azure Machine Learning ワークスペースの作成](/azure/machine-learning/concept-workspace#-create-a-workspace) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbe44-113">See [create a Azure Machine Learning workspace](/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="cbe44-114">最適なパフォーマンスを得るには、Customer Insights 環境に地理的に最も近い Azure リージョンにワークスペースを作成します。</span><span class="sxs-lookup"><span data-stu-id="cbe44-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="cbe44-115">[Azure Machine Learning Studio](https://ml.azure.com/) からワークスペースにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cbe44-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="cbe44-116">ワークスペースを [操作する方法](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="cbe44-116">There are several [ways to interact](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="cbe44-117">Azure Machine Learning デザイナーと連携する</span><span class="sxs-lookup"><span data-stu-id="cbe44-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="cbe44-118">Azure Machine Learning デザイナーは、Machine Learning Studio (クラシック) と同様に、データセットとモジュールをドラッグ アンド ドロップできるビジュアル キャンバスを提供します。</span><span class="sxs-lookup"><span data-stu-id="cbe44-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="cbe44-119">デザイナーから作成されたバッチ パイプラインは、適切に構成されていれば、Customer Insights に統合できます。</span><span class="sxs-lookup"><span data-stu-id="cbe44-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="cbe44-120">Azure Machine Learning SDK との連携</span><span class="sxs-lookup"><span data-stu-id="cbe44-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="cbe44-121">データ サイエンティストと AI 開発者は、[Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) を使用して、機械学習ワークフローを構築します。</span><span class="sxs-lookup"><span data-stu-id="cbe44-121">Data scientists and AI developers use the [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) to build machine learning workflows.</span></span> <span data-ttu-id="cbe44-122">現在、SDK を使用してトレーニングされたモデルは、Customer Insights と直接統合することはできません。</span><span class="sxs-lookup"><span data-stu-id="cbe44-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="cbe44-123">このモデルを使用するバッチ推論パイプラインは、Customer Insights との統合に必要です。</span><span class="sxs-lookup"><span data-stu-id="cbe44-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="cbe44-124">Customer Insights と統合するためのバッチ パイプラインの要件</span><span class="sxs-lookup"><span data-stu-id="cbe44-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="cbe44-125">データセットの構成</span><span class="sxs-lookup"><span data-stu-id="cbe44-125">Dataset Configuration</span></span>

<span data-ttu-id="cbe44-126">Customer Insights のエンティティ データをバッチ推論パイプラインに使用するには、データセットを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbe44-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="cbe44-127">これらのデータセットは、ワークスペースに登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbe44-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="cbe44-128">現在、.csv 形式の [表形式データセット](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="cbe44-128">Currently, we only support [tabular datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="cbe44-129">エンティティ データに対応するデータセットは、パイプライン パラメーターとしてパラメーター化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbe44-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="cbe44-130">デザイナーのデータセット パラメーター</span><span class="sxs-lookup"><span data-stu-id="cbe44-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="cbe44-131">デザイナーで、**データセットで列を選択** を開き、**パイプライン パラメーターとして設定** を選択して、パラメーターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cbe44-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="cbe44-132">![デザイナーでのデータセットのパラメーター化](media/intelligence-designer-dataset-parameters.png "デザイナーでのデータセットのパラメーター化")</span><span class="sxs-lookup"><span data-stu-id="cbe44-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="cbe44-133">SDK (Python) のデータセット パラメーター</span><span class="sxs-lookup"><span data-stu-id="cbe44-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="cbe44-134">バッチ推論パイプライン</span><span class="sxs-lookup"><span data-stu-id="cbe44-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="cbe44-135">デザイナーでは、トレーニング パイプラインを使用して、推論パイプラインを作成または更新できます。</span><span class="sxs-lookup"><span data-stu-id="cbe44-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="cbe44-136">現在、バッチ推論パイプラインのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cbe44-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="cbe44-137">SDK を使用して、パイプラインをエンドポイントに公開できます。</span><span class="sxs-lookup"><span data-stu-id="cbe44-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="cbe44-138">現在、Customer Insightsは、Machine Learning ワークスペースにあるバッチ パイプライン エンドポイントの、既定のパイプラインと統合されています。</span><span class="sxs-lookup"><span data-stu-id="cbe44-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="cbe44-139">パイプライン データ を Customer Insights にインポートする</span><span class="sxs-lookup"><span data-stu-id="cbe44-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="cbe44-140">デザイナーは、パイプラインの出力を Azure Storage にエクスポートできる [データ エクスポート モジュール](/azure/machine-learning/algorithm-module-reference/export-data) を提供します。</span><span class="sxs-lookup"><span data-stu-id="cbe44-140">The designer provides the [Export Data module](/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="cbe44-141">現在、モジュールはデータストア型の **Azure Blob Storage** を使用し、**データストア** と 相対 **パス** をパラメータ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbe44-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="cbe44-142">Customer Insights は、パイプラインの実行中に、製品にアクセス可能なデータストアとパスを使用して、これら両方のパラメーターを上書きします。</span><span class="sxs-lookup"><span data-stu-id="cbe44-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cbe44-143">![データ モジュール構成のエクスポート](media/intelligence-designer-importdata.png "データ モジュール構成のエクスポート")</span><span class="sxs-lookup"><span data-stu-id="cbe44-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="cbe44-144">コードを使用して推論出力を作成する場合、ワークスペースで *登録済みデータストア* 内のパスに出力をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="cbe44-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="cbe44-145">パスとデータストアがパイプラインでパラメーター化されている場合、Customer insights は推論出力を読み込んでインポートできます。</span><span class="sxs-lookup"><span data-stu-id="cbe44-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="cbe44-146">現在、csv 形式の 1 つの表形式の出力がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cbe44-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="cbe44-147">パスには、ディレクトリとファイル名が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbe44-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]