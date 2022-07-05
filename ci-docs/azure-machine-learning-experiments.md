---
title: Azure Machine Learning ベースのモデルを使用する
description: Dynamics 365 Customer Insights で Azure Machine Learning ベースのモデルを使用します。
ms.date: 12/02/2021
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a1efad2887a02a92ee2960b07b066edc331f3665
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081316"
---
# <a name="use-azure-machine-learning-based-models"></a>Azure Machine Learning ベースのモデルを使用する

Dynamics 365 Customer Insights の統合データは、追加のビジネス インサイトを生成できる機械学習モデルを構築するためのソースです。 Customer Insights は Azure Machine Learning と統合し、独自のカスタム モデルを使用します。

## <a name="prerequisites"></a>前提条件

- Customer Insights を使用する
- アクティブな Azure Enterprise のサブスクリプション
- [統合顧客プロファイル](data-unification.md)
- [Azure Blob Storage へのエンティティのエクスポート](export-azure-blob-storage.md) 構成済み

## <a name="set-up-azure-machine-learning-workspace"></a>Azure Machine Learning ワークスペースの設定

1. ワークスペースを作成するためのさまざまなオプションについては、[Azure Machine Learning ワークスペースの作成](/azure/machine-learning/concept-workspace#-create-a-workspace) を参照してください。 最適なパフォーマンスを得るには、Customer Insights 環境に地理的に最も近い Azure リージョンにワークスペースを作成します。

1. [Azure Machine Learning Studio](https://ml.azure.com/) からワークスペースにアクセスします。 ワークスペースを [操作する方法](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) はいくつかあります。

## <a name="work-with-azure-machine-learning-designer"></a>Azure Machine Learning デザイナーと連携する

Azure Machine Learning デザイナーは、データセットとモジュールをドラッグ アンド ドロップできるビジュアル キャンバスを提供します。 デザイナーから作成されたバッチ パイプラインは、適切に構成されていれば、Customer Insights に統合できます。 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Azure Machine Learning SDK との連携

データ サイエンティストと AI 開発者は、[Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) を使用して、機械学習ワークフローを構築します。 現在、SDK を使用してトレーニングされたモデルは、Customer Insights と直接統合することはできません。 このモデルを使用するバッチ推論パイプラインは、Customer Insights との統合に必要です。

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Customer Insights と統合するためのバッチ パイプラインの要件

### <a name="dataset-configuration"></a>データセットの構成

Customer Insights のエンティティ データをバッチ推論パイプラインに使用するには、データセットを作成する必要があります。 これらのデータセットは、ワークスペースに登録する必要があります。 現在、.csv 形式の [表形式データセット](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) のみをサポートしています。 エンティティ データに対応するデータセットは、パイプライン パラメーターとしてパラメーター化する必要があります。
   
* デザイナーのデータセット パラメーター
   
     デザイナーで、**データセットで列を選択** を開き、**パイプライン パラメーターとして設定** を選択して、パラメーターの名前を指定します。

     > [!div class="mx-imgBorder"]
     > ![デザイナーでのデータセットのパラメーター化。](media/intelligence-designer-dataset-parameters.png "デザイナーでのデータセットのパラメーター化")
   
* SDK (Python) のデータセット パラメーター
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>バッチ推論パイプライン
  
* デザイナーでは、トレーニング パイプラインを使用して、推論パイプラインを作成または更新できます。 現在、バッチ推論パイプラインのみがサポートされています。

* SDK を使用して、パイプラインをエンドポイントに公開できます。 現在、Customer Insightsは、Machine Learning ワークスペースにあるバッチ パイプライン エンドポイントの、既定のパイプラインと統合されています。
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>パイプライン データ を Customer Insights にインポートする

* デザイナーは、パイプラインの出力を Azure Storage にエクスポートできる [データ エクスポート モジュール](/azure/machine-learning/algorithm-module-reference/export-data) を提供します。 現在、モジュールはデータストア型の **Azure Blob Storage** を使用し、**データストア** と 相対 **パス** をパラメータ化する必要があります。 Customer Insights は、パイプラインの実行中に、製品にアクセス可能なデータストアとパスを使用して、これら両方のパラメーターを上書きします。
   > [!div class="mx-imgBorder"]
   > ![データ モジュール構成のエクスポート。](media/intelligence-designer-importdata.png "データ モジュール構成のエクスポート")
   
* コードを使用して推論出力を作成する場合、ワークスペースで *登録済みデータストア* 内のパスに出力をアップロードできます。 パスとデータストアがパイプラインでパラメーター化されている場合、Customer insights は推論出力を読み込んでインポートできます。 現在、csv 形式の 1 つの表形式の出力がサポートされています。 パスには、ディレクトリとファイル名が含まれている必要があります。

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


[!INCLUDE [footer-include](includes/footer-banner.md)]