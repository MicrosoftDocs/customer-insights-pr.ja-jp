---
title: カスタム機械学習モデル | Microsoft Docs
description: Dynamics 365 Customer Insights で Azure Machine Learning で作成したカスタマイズ モデルで作業する。
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267240"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="b05bc-103">カスタム機械学習モデル</span><span class="sxs-lookup"><span data-stu-id="b05bc-103">Custom machine learning models</span></span>

<span data-ttu-id="b05bc-104">**インテリジェンス** > **カスタム モデル** を使用すると、Azure Machine Learning モデルに基づいてワークフローを管理できます。</span><span class="sxs-lookup"><span data-stu-id="b05bc-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="b05bc-105">ワークフローは、インサイトを生成するデータを選択し、その結果を統合顧客データにマップするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b05bc-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="b05bc-106">カスタム ML モデルの構築の詳細については、[ Azure Machine Learning ベースのモデルを使用する](azure-machine-learning-experiments.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b05bc-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="b05bc-107">責任ある AI</span><span class="sxs-lookup"><span data-stu-id="b05bc-107">Responsible AI</span></span>

<span data-ttu-id="b05bc-108">予測は、より良い顧客体験を生み出し、ビジネス能力と収益ストリームを改善する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="b05bc-109">予測の価値と、それが持つ影響や倫理的な方法で導入される可能性のあるバイアスとのバランスを取ることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b05bc-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="b05bc-110">Microsoft の [責任ある AI への対応](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) の詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b05bc-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="b05bc-111">また、Azure Machine Learning に固有の [責任ある機械学習の技術とプロセス](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) についても確認できます。</span><span class="sxs-lookup"><span data-stu-id="b05bc-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b05bc-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="b05bc-112">Prerequisites</span></span>

- <span data-ttu-id="b05bc-113">現在、この機能は、[Machine Learning Studio (クラシック)](https://studio.azureml.net) と [Azure Machine Learning バッチ パイプライン](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) を通じて公開された Web サービスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b05bc-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="b05bc-114">この機能を使用するには、Azure Studio インスタンスに関連付けられている Azure Data Lake Gen2 ストレージ アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="b05bc-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="b05bc-115">詳細については、[Azure Data Lake Storage Gen2ストレージアカウントの作成](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account) を参照してください</span><span class="sxs-lookup"><span data-stu-id="b05bc-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="b05bc-116">新しいワークフローを追加します</span><span class="sxs-lookup"><span data-stu-id="b05bc-116">Add a new workflow</span></span>

1. <span data-ttu-id="b05bc-117">**インテリジェンス** > **カスタム モデル** に移動し、**新規ワークフロー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="b05bc-118">**名前** フィールドで、カスタム モデルにわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="b05bc-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b05bc-119">![新規ワークフロー ウィンドウのスクリーンショット](media/new-workflowv2.png "新規ワークフロー ウィンドウのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="b05bc-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="b05bc-120">**Web サービスを含むテナント** にて、Webサービスを含む組織を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="b05bc-121">Azure Machine Learning のサブスクリプションが Customer Insights とは異なるテナントにある場合は、選択した組織の資格情報を使用して **サイン インする** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="b05bc-122">Web サービスに関連付けられている **ワークスペース** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="b05bc-123">リストされているセクションは 2 つあり、Azure Machine Learning v1 (Machine Learning Studio (クラシック)) と Azure Machine Learning v2 (Azure Machine Learning) です。</span><span class="sxs-lookup"><span data-stu-id="b05bc-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="b05bc-124">どのワークスペースが Machine Learning Studio (クラシック) Web サービスに適しているかわからない場合は、**任意** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="b05bc-125">**モデルを含む Web サービス** ドロップダウンで、Machine Learning Studio (クラシック) Web サービスまたは Azure Machine Learning パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="b05bc-126">続いて、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="b05bc-127">[Machine Learning Studio (クラシック) での Web サービスの公開](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service) の詳細</span><span class="sxs-lookup"><span data-stu-id="b05bc-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="b05bc-128">[デザイナーを使用した Azure Machine Learning でのパイプラインの公開](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) または [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) の詳細。</span><span class="sxs-lookup"><span data-stu-id="b05bc-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="b05bc-129">パイプラインは、[パイプライン エンドポイント](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) で公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b05bc-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="b05bc-130">**Web サービスの入力** ごとに、対象者に関するインサイトから一致する **エンティティ** を選択して、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="b05bc-131">カスタム モデル ワークフローは、ヒューリスティックを適用して、フィールドの名前とデータ型に基づいて Web サービス入力フィールドをエンティティ属性にマッピングします。</span><span class="sxs-lookup"><span data-stu-id="b05bc-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="b05bc-132">Web サービス フィールドをエンティティにマップできない場合は、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b05bc-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b05bc-133">![ワークフローの構成](media/intelligence-screen2-updated.png "ワークフローの構成")</span><span class="sxs-lookup"><span data-stu-id="b05bc-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="b05bc-134">**モデル出力パラメーター** のステップで、次のプロパティを設定します:</span><span class="sxs-lookup"><span data-stu-id="b05bc-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="b05bc-135">Machine Learning Studio (クラシック)</span><span class="sxs-lookup"><span data-stu-id="b05bc-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="b05bc-136">Web サービス出力結果のフロー先となる、出力 **エンティティ名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="b05bc-137">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="b05bc-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="b05bc-138">パイプライン出力結果のフロー先となる、出力 **エンティティ名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="b05bc-139">ドロップダウンからバッチ パイプラインの **出力データ ストア パラメーター名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="b05bc-140">ドロップダウンからバッチ パイプラインの **出力パス パラメーター名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="b05bc-141">![モデル出力パラメーター ペイン](media/intelligence-screen3-outputparameters.png "モデル出力パラメーター ペイン")</span><span class="sxs-lookup"><span data-stu-id="b05bc-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="b05bc-142">顧客を識別する **結果に含まれる顧客 ID** ドロップダウン リストから一致する属性を選択し、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b05bc-143">![結果と顧客データの関連付けペイン](media/intelligence-screen4-relatetocustomer.png "結果と顧客データの関連付けペイン")</span><span class="sxs-lookup"><span data-stu-id="b05bc-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="b05bc-144">ワークフローの詳細が表示された、**保存されたワークフロー** 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b05bc-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="b05bc-145">Azure Machine Learning パイプラインのワークフローを構成した場合、対象者に関するインサイトは、パイプラインを含むワークスペースに添付されます。</span><span class="sxs-lookup"><span data-stu-id="b05bc-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="b05bc-146">対象者に関するインサイトは、Azure ワークスペースで **共同作成者** ロールを取得します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="b05bc-147">**完了** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-147">Select **Done**.</span></span>

1. <span data-ttu-id="b05bc-148">これで、**カスタム モデル** ページからワークフローを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b05bc-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="b05bc-149">ワークフローの編集</span><span class="sxs-lookup"><span data-stu-id="b05bc-149">Edit a workflow</span></span>

1. <span data-ttu-id="b05bc-150">**カスタム モデル** ページで、以前に作成したワークフローの横にある **アクション** 列で縦方向の省略記号を選択して、**編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="b05bc-151">**表示名** フィールドでワークフローの認識可能な名前を更新できますが、構成済みの Web サービスやパイプラインを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="b05bc-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="b05bc-152">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-152">Select **Next**.</span></span>

1. <span data-ttu-id="b05bc-153">**Web サービスの入力** ごとに、対象者に関するインサイトから一致する **エンティティ** を更新できます。</span><span class="sxs-lookup"><span data-stu-id="b05bc-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="b05bc-154">続いて、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="b05bc-155">**モデル出力パラメーター** のステップで、次のプロパティを設定します:</span><span class="sxs-lookup"><span data-stu-id="b05bc-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="b05bc-156">Machine Learning Studio (クラシック)</span><span class="sxs-lookup"><span data-stu-id="b05bc-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="b05bc-157">Web サービス出力結果のフロー先となる、出力 **エンティティ名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="b05bc-158">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="b05bc-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="b05bc-159">パイプライン出力結果のフロー先となる、出力 **エンティティ名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="b05bc-160">テスト パイプラインの **出力データ ストア パラメーター名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="b05bc-161">テスト パイプラインの **出力パス パラメーター名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="b05bc-162">顧客を識別する **結果に含まれる顧客 ID** ドロップダウン リストから一致する属性を選択し、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="b05bc-163">推論出力から、顧客エンティティの顧客 ID 列に類似した値を持つ属性を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b05bc-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="b05bc-164">データ セットにそのような列がない場合は、行を一意に識別する属性を選択してください。</span><span class="sxs-lookup"><span data-stu-id="b05bc-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="b05bc-165">ワークフローの実行</span><span class="sxs-lookup"><span data-stu-id="b05bc-165">Run a workflow</span></span>

1. <span data-ttu-id="b05bc-166">**カスタム モデル** ページで、以前に作成したワークフローの横にある **アクション** 列で縦方向の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="b05bc-167">**実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-167">Select **Run**.</span></span>

<span data-ttu-id="b05bc-168">ワークフローは、更新がスケジュールされるたびに自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="b05bc-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="b05bc-169">詳細については、 [スケジュールされた更新を設定する](system.md#schedule-tab) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b05bc-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="b05bc-170">ワークフローを削除する</span><span class="sxs-lookup"><span data-stu-id="b05bc-170">Delete a workflow</span></span>

1. <span data-ttu-id="b05bc-171">**カスタム モデル** ページで、以前に作成したワークフローの横にある **アクション** 列で縦方向の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="b05bc-172">**削除** を選び、削除内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="b05bc-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="b05bc-173">ワークフローが削除されます。</span><span class="sxs-lookup"><span data-stu-id="b05bc-173">Your workflow will be deleted.</span></span> <span data-ttu-id="b05bc-174">ワークフローの作成時に作成された [エンティティ](entities.md)は保持されており、これらは **エンティティ** ページで確認することができます。</span><span class="sxs-lookup"><span data-stu-id="b05bc-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]