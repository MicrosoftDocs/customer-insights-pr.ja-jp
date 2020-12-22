---
title: カスタム機械学習モデル | Microsoft Docs
description: Dynamics 365 Customer Insights で Azure Machine Learning で作成したカスタマイズ モデルで作業する。
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668909"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="e2cd2-103">カスタム機械学習モデル</span><span class="sxs-lookup"><span data-stu-id="e2cd2-103">Custom machine learning models</span></span>

<span data-ttu-id="e2cd2-104">**インテリジェンス** > **カスタム モデル** を使用すると、Azure Machine Learning モデルに基づいてワークフローを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="e2cd2-105">ワークフローは、インサイトを生成するデータを選択し、その結果を統合顧客データにマップするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="e2cd2-106">カスタム ML モデルの構築の詳細については、[ Azure Machine Learning ベースのモデルを使用する](azure-machine-learning-experiments.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="e2cd2-107">責任ある AI</span><span class="sxs-lookup"><span data-stu-id="e2cd2-107">Responsible AI</span></span>

<span data-ttu-id="e2cd2-108">予測は、より良い顧客体験を生み出し、ビジネス能力と収益ストリームを改善する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="e2cd2-109">予測の価値と、それが持つ影響や倫理的な方法で導入される可能性のあるバイアスとのバランスを取ることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="e2cd2-110">Microsoft の [責任ある AI への対応](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) の詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="e2cd2-111">また、Azure Machine Learning に固有の [責任ある機械学習の技術とプロセス](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) についても確認できます。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e2cd2-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="e2cd2-112">Prerequisites</span></span>

- <span data-ttu-id="e2cd2-113">現在、この機能は、[Machine Learning Studio (クラシック)](https://studio.azureml.net) と [Azure Machine Learning バッチ パイプライン](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) を通じて公開された Web サービスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="e2cd2-114">この機能を使用するには、Azure Studio インスタンスに関連付けられている Azure Data Lake Gen2 ストレージ アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="e2cd2-115">詳細については、[Azure Data Lake Storage Gen2ストレージアカウントの作成](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account) を参照してください</span><span class="sxs-lookup"><span data-stu-id="e2cd2-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="e2cd2-116">新しいワークフローを追加します</span><span class="sxs-lookup"><span data-stu-id="e2cd2-116">Add a new workflow</span></span>

1. <span data-ttu-id="e2cd2-117">**インテリジェンス** > **カスタム モデル** に移動し、**新規ワークフロー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="e2cd2-118">**名前** フィールドで、カスタム モデルにわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2cd2-119">![新規ワークフロー ウィンドウのスクリーンショット](media/new-workflowv2.png "新規ワークフロー ウィンドウのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="e2cd2-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="e2cd2-120">**Web サービスを含むテナント** にて、Webサービスを含む組織を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="e2cd2-121">Azure Machine Learning のサブスクリプションが Customer Insights とは異なるテナントにある場合は、選択した組織の資格情報を使用して **サイン インする** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="e2cd2-122">Web サービスに関連付けられている **ワークスペース** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="e2cd2-123">リストされているセクションは 2 つあり、Azure Machine Learning v1 (Machine Learning Studio (クラシック)) と Azure Machine Learning v2 (Azure Machine Learning) です。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="e2cd2-124">どのワークスペースが Machine Learning Studio (クラシック) Web サービスに適しているかわからない場合は、**任意** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="e2cd2-125">**モデルを含む Web サービス** ドロップダウンで、Machine Learning Studio (クラシック) Web サービスまたは Azure Machine Learning パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="e2cd2-126">続いて、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="e2cd2-127">[Machine Learning Studio (クラシック) での Web サービスの公開](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service) の詳細</span><span class="sxs-lookup"><span data-stu-id="e2cd2-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="e2cd2-128">[デザイナーを使用した Azure Machine Learning でのパイプラインの公開](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) または [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) の詳細。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="e2cd2-129">パイプラインは、[パイプライン エンドポイント](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) で公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="e2cd2-130">**Web サービスの入力** ごとに、対象者に関するインサイトから一致する **エンティティ** を選択して、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2cd2-131">![ワークフローの構成](media/intelligence-screen2-updated.png "ワークフローの構成")</span><span class="sxs-lookup"><span data-stu-id="e2cd2-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="e2cd2-132">**モデル出力パラメーター** のステップで、次のプロパティを設定します:</span><span class="sxs-lookup"><span data-stu-id="e2cd2-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="e2cd2-133">Machine Learning Studio (クラシック)</span><span class="sxs-lookup"><span data-stu-id="e2cd2-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="e2cd2-134">Web サービス出力結果のフロー先となる、出力 **エンティティ名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="e2cd2-135">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="e2cd2-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="e2cd2-136">パイプライン出力結果のフロー先となる、出力 **エンティティ名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="e2cd2-137">ドロップダウンからバッチ パイプラインの **出力データ ストア パラメーター名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="e2cd2-138">ドロップダウンからバッチ パイプラインの **出力パス パラメーター名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="e2cd2-139">![モデル出力パラメーター ペイン](media/intelligence-screen3-outputparameters.png "モデル出力パラメーター ペイン")</span><span class="sxs-lookup"><span data-stu-id="e2cd2-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="e2cd2-140">顧客を識別する **結果に含まれる顧客 ID** ドロップダウン リストから一致する属性を選択し、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2cd2-141">![結果と顧客データの関連付けペイン](media/intelligence-screen4-relatetocustomer.png "結果と顧客データの関連付けペイン")</span><span class="sxs-lookup"><span data-stu-id="e2cd2-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="e2cd2-142">ワークフローの詳細が表示された、**保存されたワークフロー** 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="e2cd2-143">Azure Machine Learning パイプラインのワークフローを構成した場合、対象者に関するインサイトは、パイプラインを含むワークスペースに添付されます。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="e2cd2-144">対象者に関するインサイトは、Azure ワークスペースで **共同作成者** ロールを取得します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="e2cd2-145">**完了** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-145">Select **Done**.</span></span>

1. <span data-ttu-id="e2cd2-146">これで、**カスタム モデル** ページからワークフローを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="e2cd2-147">ワークフローの編集</span><span class="sxs-lookup"><span data-stu-id="e2cd2-147">Edit a workflow</span></span>

1. <span data-ttu-id="e2cd2-148">**カスタム モデル** ページで、以前に作成したワークフローの横にある **アクション** 列で縦方向の省略記号を選択して、**編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="e2cd2-149">**表示名** フィールドでワークフローの認識可能な名前を更新できますが、構成済みの Web サービスやパイプラインを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="e2cd2-150">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-150">Select **Next**.</span></span>

1. <span data-ttu-id="e2cd2-151">**Web サービスの入力** ごとに、対象者に関するインサイトから一致する **エンティティ** を更新できます。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="e2cd2-152">続いて、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="e2cd2-153">**モデル出力パラメーター** のステップで、次のプロパティを設定します:</span><span class="sxs-lookup"><span data-stu-id="e2cd2-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="e2cd2-154">Machine Learning Studio (クラシック)</span><span class="sxs-lookup"><span data-stu-id="e2cd2-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="e2cd2-155">Web サービス出力結果のフロー先となる、出力 **エンティティ名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="e2cd2-156">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="e2cd2-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="e2cd2-157">パイプライン出力結果のフロー先となる、出力 **エンティティ名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="e2cd2-158">テスト パイプラインの **出力データ ストア パラメーター名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="e2cd2-159">テスト パイプラインの **出力パス パラメーター名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="e2cd2-160">顧客を識別する **結果に含まれる顧客 ID** ドロップダウン リストから一致する属性を選択し、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="e2cd2-161">推論出力から、顧客エンティティの顧客 ID 列に類似した値を持つ属性を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="e2cd2-162">データ セットにそのような列がない場合は、行を一意に識別する属性を選択してください。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="e2cd2-163">ワークフローの実行</span><span class="sxs-lookup"><span data-stu-id="e2cd2-163">Run a workflow</span></span>

1. <span data-ttu-id="e2cd2-164">**カスタム モデル** ページで、以前に作成したワークフローの横にある **アクション** 列で縦方向の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="e2cd2-165">**実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-165">Select **Run**.</span></span>

<span data-ttu-id="e2cd2-166">ワークフローは、更新がスケジュールされるたびに自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="e2cd2-167">詳細については、 [スケジュールされた更新を設定する](system.md#schedule-tab) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="e2cd2-168">ワークフローを削除する</span><span class="sxs-lookup"><span data-stu-id="e2cd2-168">Delete a workflow</span></span>

1. <span data-ttu-id="e2cd2-169">**カスタム モデル** ページで、以前に作成したワークフローの横にある **アクション** 列で縦方向の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="e2cd2-170">**削除** を選び、削除内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="e2cd2-171">ワークフローが削除されます。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-171">Your workflow will be deleted.</span></span> <span data-ttu-id="e2cd2-172">ワークフローの作成時に作成された [エンティティ](entities.md)は保持されており、これらは **エンティティ** ページで確認することができます。</span><span class="sxs-lookup"><span data-stu-id="e2cd2-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
