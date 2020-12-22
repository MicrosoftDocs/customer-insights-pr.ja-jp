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
# <a name="custom-machine-learning-models"></a>カスタム機械学習モデル

**インテリジェンス** > **カスタム モデル** を使用すると、Azure Machine Learning モデルに基づいてワークフローを管理できます。 ワークフローは、インサイトを生成するデータを選択し、その結果を統合顧客データにマップするのに役立ちます。 カスタム ML モデルの構築の詳細については、[ Azure Machine Learning ベースのモデルを使用する](azure-machine-learning-experiments.md) を参照してください。

## <a name="responsible-ai"></a>責任ある AI

予測は、より良い顧客体験を生み出し、ビジネス能力と収益ストリームを改善する機能を提供します。 予測の価値と、それが持つ影響や倫理的な方法で導入される可能性のあるバイアスとのバランスを取ることを強くお勧めします。 Microsoft の [責任ある AI への対応](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) の詳細を確認してください。 また、Azure Machine Learning に固有の [責任ある機械学習の技術とプロセス](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) についても確認できます。

## <a name="prerequisites"></a>前提条件

- 現在、この機能は、[Machine Learning Studio (クラシック)](https://studio.azureml.net) と [Azure Machine Learning バッチ パイプライン](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) を通じて公開された Web サービスをサポートしています。

- この機能を使用するには、Azure Studio インスタンスに関連付けられている Azure Data Lake Gen2 ストレージ アカウントが必要です。 詳細については、[Azure Data Lake Storage Gen2ストレージアカウントの作成](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account) を参照してください

## <a name="add-a-new-workflow"></a>新しいワークフローを追加します

1. **インテリジェンス** > **カスタム モデル** に移動し、**新規ワークフロー** を選択します。

1. **名前** フィールドで、カスタム モデルにわかりやすい名前を付けます。

   > [!div class="mx-imgBorder"]
   > ![新規ワークフロー ウィンドウのスクリーンショット](media/new-workflowv2.png "新規ワークフロー ウィンドウのスクリーンショット")

1. **Web サービスを含むテナント** にて、Webサービスを含む組織を選択します。

1. Azure Machine Learning のサブスクリプションが Customer Insights とは異なるテナントにある場合は、選択した組織の資格情報を使用して **サイン インする** を選択します。

1. Web サービスに関連付けられている **ワークスペース** を選択します。 リストされているセクションは 2 つあり、Azure Machine Learning v1 (Machine Learning Studio (クラシック)) と Azure Machine Learning v2 (Azure Machine Learning) です。 どのワークスペースが Machine Learning Studio (クラシック) Web サービスに適しているかわからない場合は、**任意** を選択します。

1. **モデルを含む Web サービス** ドロップダウンで、Machine Learning Studio (クラシック) Web サービスまたは Azure Machine Learning パイプラインを選択します。 続いて、**次へ** を選択します。
   - [Machine Learning Studio (クラシック) での Web サービスの公開](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service) の詳細
   - [デザイナーを使用した Azure Machine Learning でのパイプラインの公開](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) または [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) の詳細。 
     > [!NOTE]
     > パイプラインは、[パイプライン エンドポイント](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) で公開する必要があります。

1. **Web サービスの入力** ごとに、対象者に関するインサイトから一致する **エンティティ** を選択して、**次へ** を選択します。

   > [!div class="mx-imgBorder"]
   > ![ワークフローの構成](media/intelligence-screen2-updated.png "ワークフローの構成")

1. **モデル出力パラメーター** のステップで、次のプロパティを設定します:
   - Machine Learning Studio (クラシック)
      1. Web サービス出力結果のフロー先となる、出力 **エンティティ名** を入力します。
   - Azure Machine Learning
      1. パイプライン出力結果のフロー先となる、出力 **エンティティ名** を入力します。
      1. ドロップダウンからバッチ パイプラインの **出力データ ストア パラメーター名** を選択します。
      1. ドロップダウンからバッチ パイプラインの **出力パス パラメーター名** を選択します。
      
      > [!div class="mx-imgBorder"]
      > ![モデル出力パラメーター ペイン](media/intelligence-screen3-outputparameters.png "モデル出力パラメーター ペイン")

1. 顧客を識別する **結果に含まれる顧客 ID** ドロップダウン リストから一致する属性を選択し、**保存** を選択します。
   
   > [!div class="mx-imgBorder"]
   > ![結果と顧客データの関連付けペイン](media/intelligence-screen4-relatetocustomer.png "結果と顧客データの関連付けペイン")

1. ワークフローの詳細が表示された、**保存されたワークフロー** 画面が表示されます。    
   Azure Machine Learning パイプラインのワークフローを構成した場合、対象者に関するインサイトは、パイプラインを含むワークスペースに添付されます。 対象者に関するインサイトは、Azure ワークスペースで **共同作成者** ロールを取得します。

1. **完了** を選択します。

1. これで、**カスタム モデル** ページからワークフローを実行できます。

## <a name="edit-a-workflow"></a>ワークフローの編集

1. **カスタム モデル** ページで、以前に作成したワークフローの横にある **アクション** 列で縦方向の省略記号を選択して、**編集** を選択します。

1. **表示名** フィールドでワークフローの認識可能な名前を更新できますが、構成済みの Web サービスやパイプラインを変更することはできません。 **次へ** を選択します。

1. **Web サービスの入力** ごとに、対象者に関するインサイトから一致する **エンティティ** を更新できます。 続いて、**次へ** を選択します。

1. **モデル出力パラメーター** のステップで、次のプロパティを設定します:
   - Machine Learning Studio (クラシック)
      1. Web サービス出力結果のフロー先となる、出力 **エンティティ名** を入力します。
   - Azure Machine Learning
      1. パイプライン出力結果のフロー先となる、出力 **エンティティ名** を入力します。
      1. テスト パイプラインの **出力データ ストア パラメーター名** を選択します。
      1. テスト パイプラインの **出力パス パラメーター名** を選択します。

1. 顧客を識別する **結果に含まれる顧客 ID** ドロップダウン リストから一致する属性を選択し、**保存** を選択します。
   推論出力から、顧客エンティティの顧客 ID 列に類似した値を持つ属性を選択する必要があります。 データ セットにそのような列がない場合は、行を一意に識別する属性を選択してください。

## <a name="run-a-workflow"></a>ワークフローの実行

1. **カスタム モデル** ページで、以前に作成したワークフローの横にある **アクション** 列で縦方向の省略記号を選択します。

1. **実行** を選択します。

ワークフローは、更新がスケジュールされるたびに自動的に実行されます。 詳細については、 [スケジュールされた更新を設定する](system.md#schedule-tab) を参照してください。

## <a name="delete-a-workflow"></a>ワークフローを削除する

1. **カスタム モデル** ページで、以前に作成したワークフローの横にある **アクション** 列で縦方向の省略記号を選択します。

1. **削除** を選び、削除内容を確認します。

ワークフローが削除されます。 ワークフローの作成時に作成された [エンティティ](entities.md)は保持されており、これらは **エンティティ** ページで確認することができます。
