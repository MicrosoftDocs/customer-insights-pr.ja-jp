---
title: カスタム機械学習モデル | Microsoft Docs
description: Dynamics 365 Customer Insights で Azure Machine Learning で作成したカスタマイズ モデルで作業する。
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 82f6f363497f8f1b45fa84acd49bcaed332e60e8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305644"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="0da56-103">カスタム機械学習モデル</span><span class="sxs-lookup"><span data-stu-id="0da56-103">Custom machine learning models</span></span>

<span data-ttu-id="0da56-104">**インテリジェンス** > **カスタム モデル** を使用すると、Azure Machine Learning モデルに基づいてワークフローを管理できます。</span><span class="sxs-lookup"><span data-stu-id="0da56-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="0da56-105">ワークフローは、インサイトを生成するデータを選択し、その結果を統合顧客データにマップするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0da56-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="0da56-106">カスタム ML モデルの構築の詳細については、[ Azure Machine Learning ベースのモデルを使用する](azure-machine-learning-experiments.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0da56-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="0da56-107">責任ある AI</span><span class="sxs-lookup"><span data-stu-id="0da56-107">Responsible AI</span></span>

<span data-ttu-id="0da56-108">予測は、より良い顧客体験を生み出し、ビジネス能力と収益ストリームを改善する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="0da56-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="0da56-109">予測の価値と、それが持つ影響や倫理的な方法で導入される可能性のあるバイアスとのバランスを取ることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0da56-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="0da56-110">Microsoft の [責任ある AI への対応](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) の詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="0da56-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="0da56-111">また、Azure Machine Learning に固有の [責任ある機械学習の技術とプロセス](/azure/machine-learning/concept-responsible-ml) についても確認できます。</span><span class="sxs-lookup"><span data-stu-id="0da56-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0da56-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="0da56-112">Prerequisites</span></span>

- <span data-ttu-id="0da56-113">現在、この機能は、[Machine Learning Studio (クラシック)](https://studio.azureml.net) と [Azure Machine Learning バッチ パイプライン](/azure/machine-learning/concept-ml-pipelines) を通じて公開された Web サービスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0da56-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="0da56-114">この機能を使用するには、Azure Studio インスタンスに関連付けられている Azure Data Lake Gen2 ストレージ アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="0da56-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="0da56-115">詳細については、[Azure Data Lake Storage Gen2 ストレージ アカウントの作成](/azure/storage/blobs/data-lake-storage-quickstart-create-account) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0da56-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="0da56-116">パイプラインを含む Azure Machine Learning ワークスペースの場合、Azure Machine Learning ワークスペースに対する所有者またはユーザー アクセス管理者アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="0da56-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0da56-117">データは、Customer Insights インスタンスと、ワークフローで選択した Azure Web サービスまたはパイプラインの間で転送されます。</span><span class="sxs-lookup"><span data-stu-id="0da56-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="0da56-118">Azure サービスにデータを転送する場合は、必要な方法と場所でデータを処理するようにサービスを構成し、組織のデータに関する法律や規制の要件に準拠していることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="0da56-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="0da56-119">新しいワークフローを追加します</span><span class="sxs-lookup"><span data-stu-id="0da56-119">Add a new workflow</span></span>

1. <span data-ttu-id="0da56-120">**インテリジェンス** > **カスタム モデル** に移動し、**新規ワークフロー** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="0da56-121">**名前** フィールドで、カスタム モデルにわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="0da56-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0da56-122">![新規ワークフロー ウィンドウのスクリーンショット](media/new-workflowv2.png "新規ワークフロー ウィンドウのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="0da56-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="0da56-123">**Web サービスを含むテナント** にて、Webサービスを含む組織を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="0da56-124">Azure Machine Learning のサブスクリプションが Customer Insights とは異なるテナントにある場合は、選択した組織の資格情報を使用して **サイン インする** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="0da56-125">Web サービスに関連付けられている **ワークスペース** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="0da56-126">リストされているセクションは 2 つあり、Azure Machine Learning v1 (Machine Learning Studio (クラシック)) と Azure Machine Learning v2 (Azure Machine Learning) です。</span><span class="sxs-lookup"><span data-stu-id="0da56-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="0da56-127">どのワークスペースが Machine Learning Studio (クラシック) Web サービスに適しているかわからない場合は、**任意** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="0da56-128">**モデルを含む Web サービス** ドロップダウンで、Machine Learning Studio (クラシック) Web サービスまたは Azure Machine Learning パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="0da56-129">続いて、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="0da56-130">[Machine Learning Studio (クラシック) での Web サービスの公開](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service) の詳細</span><span class="sxs-lookup"><span data-stu-id="0da56-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="0da56-131">[デザイナーを使用した Azure Machine Learning でのパイプラインの公開](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) または [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) の詳細。</span><span class="sxs-lookup"><span data-stu-id="0da56-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="0da56-132">パイプラインは、[パイプライン エンドポイント](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) で公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0da56-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="0da56-133">**Web サービスの入力** ごとに、対象者に関するインサイトから一致する **エンティティ** を選択して、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="0da56-134">カスタム モデル ワークフローは、ヒューリスティックを適用して、フィールドの名前とデータ型に基づいて Web サービス入力フィールドをエンティティ属性にマッピングします。</span><span class="sxs-lookup"><span data-stu-id="0da56-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="0da56-135">Web サービス フィールドをエンティティにマップできない場合は、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0da56-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0da56-136">![ワークフローの構成](media/intelligence-screen2-updated.png "ワークフローの構成")</span><span class="sxs-lookup"><span data-stu-id="0da56-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="0da56-137">**モデル出力パラメーター** のステップで、次のプロパティを設定します:</span><span class="sxs-lookup"><span data-stu-id="0da56-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="0da56-138">Machine Learning Studio (クラシック)</span><span class="sxs-lookup"><span data-stu-id="0da56-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="0da56-139">Web サービス出力結果のフロー先となる、出力 **エンティティ名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="0da56-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="0da56-140">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="0da56-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="0da56-141">パイプライン出力結果のフロー先となる、出力 **エンティティ名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="0da56-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="0da56-142">ドロップダウンからバッチ パイプラインの **出力データ ストア パラメーター名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="0da56-143">ドロップダウンからバッチ パイプラインの **出力パス パラメーター名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="0da56-144">![モデル出力パラメーター ペイン](media/intelligence-screen3-outputparameters.png "モデル出力パラメーター ペイン")</span><span class="sxs-lookup"><span data-stu-id="0da56-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="0da56-145">顧客を特定するには、**結果内の顧客 ID** ドロップダウン リストから一致する属性を選択し、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-145">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0da56-146">![結果と顧客データの関連付けペイン](media/intelligence-screen4-relatetocustomer.png "結果と顧客データの関連付けペイン")</span><span class="sxs-lookup"><span data-stu-id="0da56-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="0da56-147">ワークフローの詳細が表示された、**保存されたワークフロー** 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0da56-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="0da56-148">Azure Machine Learning パイプラインのワークフローを構成した場合、対象者に関するインサイトは、パイプラインを含むワークスペースに添付されます。</span><span class="sxs-lookup"><span data-stu-id="0da56-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="0da56-149">対象者に関するインサイトは、Azure ワークスペースで **共同作成者** ロールを取得します。</span><span class="sxs-lookup"><span data-stu-id="0da56-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="0da56-150">**完了** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-150">Select **Done**.</span></span>

1. <span data-ttu-id="0da56-151">これで、**カスタム モデル** ページからワークフローを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0da56-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="0da56-152">ワークフローの編集</span><span class="sxs-lookup"><span data-stu-id="0da56-152">Edit a workflow</span></span>

1. <span data-ttu-id="0da56-153">**カスタム モデル** ページで、以前に作成したワークフローの横にある **アクション** 列で縦方向の省略記号を選択して、**編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="0da56-154">**表示名** フィールドでワークフローの認識可能な名前を更新できますが、構成済みの Web サービスやパイプラインを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0da56-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="0da56-155">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-155">Select **Next**.</span></span>

1. <span data-ttu-id="0da56-156">**Web サービスの入力** ごとに、対象者に関するインサイトから一致する **エンティティ** を更新できます。</span><span class="sxs-lookup"><span data-stu-id="0da56-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="0da56-157">続いて、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="0da56-158">**モデル出力パラメーター** のステップで、次のプロパティを設定します:</span><span class="sxs-lookup"><span data-stu-id="0da56-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="0da56-159">Machine Learning Studio (クラシック)</span><span class="sxs-lookup"><span data-stu-id="0da56-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="0da56-160">Web サービス出力結果のフロー先となる、出力 **エンティティ名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="0da56-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="0da56-161">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="0da56-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="0da56-162">パイプライン出力結果のフロー先となる、出力 **エンティティ名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="0da56-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="0da56-163">テスト パイプラインの **出力データ ストア パラメーター名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="0da56-164">テスト パイプラインの **出力パス パラメーター名** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="0da56-165">顧客を特定するには、**結果内の顧客 ID** ドロップダウン リストから一致する属性を選択し、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-165">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="0da56-166">顧客エンティティの顧客 ID 列に類似した値を持つ属性を、推論出力から選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="0da56-167">データ セットにそのような列がない場合は、行を一意に識別する属性を選択してください。</span><span class="sxs-lookup"><span data-stu-id="0da56-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="0da56-168">ワークフローの実行</span><span class="sxs-lookup"><span data-stu-id="0da56-168">Run a workflow</span></span>

1. <span data-ttu-id="0da56-169">**カスタム モデル** ページで、以前に作成したワークフローの横にある **アクション** 列で縦方向の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="0da56-170">**実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-170">Select **Run**.</span></span>

<span data-ttu-id="0da56-171">ワークフローは、更新がスケジュールされるたびに自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="0da56-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="0da56-172">詳細については、 [スケジュールされた更新を設定する](system.md#schedule-tab) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0da56-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="0da56-173">ワークフローを削除する</span><span class="sxs-lookup"><span data-stu-id="0da56-173">Delete a workflow</span></span>

1. <span data-ttu-id="0da56-174">**カスタム モデル** ページで、以前に作成したワークフローの横にある **アクション** 列で縦方向の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="0da56-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="0da56-175">**削除** を選び、削除内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="0da56-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="0da56-176">ワークフローが削除されます。</span><span class="sxs-lookup"><span data-stu-id="0da56-176">Your workflow will be deleted.</span></span> <span data-ttu-id="0da56-177">ワークフローの作成時に作成された [エンティティ](entities.md)は保持されており、これらは **エンティティ** ページで確認することができます。</span><span class="sxs-lookup"><span data-stu-id="0da56-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="0da56-178">結果​​</span><span class="sxs-lookup"><span data-stu-id="0da56-178">Results</span></span>

<span data-ttu-id="0da56-179">ワークフローの結果は、モデル出力パラメーター フェーズで構成されたエンティティに保存されます。</span><span class="sxs-lookup"><span data-stu-id="0da56-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="0da56-180">このデータには、[エンティティ ページ](entities.md) から、または [API アクセス](apis.md) を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0da56-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="0da56-181">API アクセス</span><span class="sxs-lookup"><span data-stu-id="0da56-181">API Access</span></span>

<span data-ttu-id="0da56-182">カスタム モデル エンティティからデータを取得するための特定の OData クエリには、次の形式を使用します:</span><span class="sxs-lookup"><span data-stu-id="0da56-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="0da56-183">`<your instance id>` を、Customer Insights にアクセスするときに、ブラウザーのアドレス バーに表示される Customer Insights 環境の ID に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0da56-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="0da56-184">`<custom model output entity>` を、カスタム モデル構成のモモデル出力パラメーター ステップで指定したエンティティ名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0da56-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="0da56-185">`<guid value>` を、レコードにアクセスする顧客の顧客 ID に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0da56-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="0da56-186">通常、この ID は [顧客プロファイル ページ](customer-profiles.md) の CustomerID フィールドにあります。</span><span class="sxs-lookup"><span data-stu-id="0da56-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="0da56-187">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="0da56-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="0da56-188">カスタム モデル ワークフローを設定するときに、パイプラインが表示されないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="0da56-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="0da56-189">この問題は、パイプラインの構成の問題が原因で発生することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="0da56-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="0da56-190">[入力パラメータが構成](azure-machine-learning-experiments.md#dataset-configuration) され、[出力データストアとパス パラメータ](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) も構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0da56-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="0da56-191">「インテリジェンス ワークフローを保存できませんでした」というエラーは何を意味していますか?</span><span class="sxs-lookup"><span data-stu-id="0da56-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="0da56-192">ユーザーが、ワークスペースに対する所有者またはユーザー アクセス管理者権限がない場合、通常、このエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0da56-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="0da56-193">ユーザーは、Customer Insights がワークフローをサービスとして処理できるようにするために、ワークフローの後続の実行にユーザー資格情報を使用するのではなく、より高いレベルの権限を必要とします。</span><span class="sxs-lookup"><span data-stu-id="0da56-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
