---
title: カスタム機械学習モデル | Microsoft Docs
description: Dynamics 365 Customer Insights で Azure Machine Learning で作成したカスタマイズ モデルで作業する。
ms.date: 12/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 460b68e1e65b3033af0a03d1bcc27e718c79d7aa
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355081"
---
# <a name="custom-machine-learning-models"></a>カスタム機械学習モデル

> [!NOTE]
> Machine Learning Studio (クラシック) のサポートは、2024 年 8 月 31 日に終了します。 その日までに、[Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) に移行することをお薦めします。
>
> 2021 年 12 月 1 日以降、新しい Machine Learning Studio (クラシック) のリソースは作成できません。 2024 年 8 月 31 日まで、既存の Machine Learning Studio (クラシック) リソースを引き続き使用できます。 詳細については、[Azure Machine Learning に移行する](/azure/machine-learning/migrate-overview)を参照してください。


**インテリジェンス** > **カスタム モデル** を使用すると、Azure Machine Learning モデルに基づいてワークフローを管理できます。 ワークフローは、インサイトを生成するデータを選択し、その結果を統合顧客データにマップするのに役立ちます。 カスタム ML モデルの構築の詳細については、[ Azure Machine Learning ベースのモデルを使用する](azure-machine-learning-experiments.md) を参照してください。

## <a name="responsible-ai"></a>責任ある AI

予測は、より良い顧客体験を生み出し、ビジネス能力と収益ストリームを改善する機能を提供します。 予測の価値と、それが持つ影響や倫理的な方法で導入される可能性のあるバイアスとのバランスを取ることを強くお勧めします。 Microsoft の [責任ある AI への対応](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) の詳細を確認してください。 また、Azure Machine Learning に固有の [責任ある機械学習の技術とプロセス](/azure/machine-learning/concept-responsible-ml) についても確認できます。

## <a name="prerequisites"></a>前提条件

- この機能は、[Azure Machine Learning バッチ パイプライン](/azure/machine-learning/concept-ml-pipelines)を通じて公開された Web サービスをサポートします。

- この機能を使用するには、Azure Studio インスタンスに関連付けられている Azure Data Lake Gen2 ストレージ アカウントが必要です。 詳細については、[Azure Data Lake Storage Gen2 ストレージ アカウントの作成](/azure/storage/blobs/data-lake-storage-quickstart-create-account) を参照してください。

- パイプラインを含む Azure Machine Learning ワークスペースの場合、Azure Machine Learning ワークスペースに対する所有者またはユーザー アクセス管理者アクセス許可が必要です。

   > [!NOTE]
   > データは、Customer Insights インスタンスと、ワークフローで選択した Azure Web サービスまたはパイプラインの間で転送されます。 Azure サービスにデータを転送する場合は、必要な方法と場所でデータを処理するようにサービスを構成し、組織のデータに関する法律や規制の要件に準拠していることをご確認ください。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

## <a name="add-a-new-workflow"></a>新しいワークフローを追加します

1. **インテリジェンス** > **カスタム モデル** に移動し、**新規ワークフロー** を選択します。

1. **名前** フィールドで、カスタム モデルにわかりやすい名前を付けます。

   > [!div class="mx-imgBorder"]
   > ![新規ワークフロー ウィンドウのスクリーンショット。](media/new-workflowv2.png "新規ワークフロー ウィンドウのスクリーンショット")

1. **Web サービスを含むテナント** にて、Webサービスを含む組織を選択します。

1. Azure Machine Learning のサブスクリプションが Customer Insights とは異なるテナントにある場合は、選択した組織の資格情報を使用して **サイン インする** を選択します。

1. Web サービスに関連付けられている **ワークスペース** を選択します。 

1. **モデルを含む Web サービス** ドロップダウンで、Azure Machine Learning パイプラインを選択します。 続いて、**次へ** を選択します。    
   [デザイナーを使用した Azure Machine Learning でのパイプラインの公開](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) または [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) の詳細。 パイプラインは、[パイプライン エンドポイント](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) で公開する必要があります。

1. **Web サービスの入力** ごとに、対象者に関するインサイトから一致する **エンティティ** を選択して、**次へ** を選択します。
   > [!NOTE]
   > カスタム モデル ワークフローは、ヒューリスティックを適用して、フィールドの名前とデータ型に基づいて Web サービス入力フィールドをエンティティ属性にマッピングします。 Web サービス フィールドをエンティティにマップできない場合は、エラーが表示されます。

   > [!div class="mx-imgBorder"]
   > ![ワークフローの構成。](media/intelligence-screen2-updated.png "ワークフローの構成")

1. **モデル出力パラメーター** のステップで、次のプロパティを設定します:
      1. パイプライン出力結果のフロー先となる、出力 **エンティティ名** を入力します。
      1. ドロップダウンからバッチ パイプラインの **出力データ ストア パラメーター名** を選択します。
      1. ドロップダウンからバッチ パイプラインの **出力パス パラメーター名** を選択します。

      > [!div class="mx-imgBorder"]
      > ![モデル出力パラメーター ペイン。](media/intelligence-screen3-outputparameters.png "モデル出力パラメーター ペイン")

1. 顧客を特定するには、**結果内の顧客 ID** ドロップダウン リストから一致する属性を選択し、**保存** を選択します。

   > [!div class="mx-imgBorder"]
   > ![結果と顧客データの関連付けペイン。](media/intelligence-screen4-relatetocustomer.png "結果と顧客データの関連付けペイン")

1. ワークフローの詳細が表示された、**保存されたワークフロー** 画面が表示されます。    
   Azure Machine Learning パイプラインのワークフローを構成した場合、対象者に関するインサイトは、パイプラインを含むワークスペースに添付されます。 対象者に関するインサイトは、Azure ワークスペースで **共同作成者** ロールを取得します。

1. **完了** を選択します。

1. これで、**カスタム モデル** ページからワークフローを実行できます。

## <a name="edit-a-workflow"></a>ワークフローの編集

1. **カスタム モデル** ページで、以前に作成したワークフローの横にある **アクション** 列で縦方向の省略記号を選択して、**編集** を選択します。

1. **表示名** フィールドでワークフローの認識可能な名前を更新できますが、構成済みの Web サービスやパイプラインを変更することはできません。 **次へ** を選択します。

1. **Web サービスの入力** ごとに、対象者に関するインサイトから一致する **エンティティ** を更新できます。 続いて、**次へ** を選択します。

1. **モデル出力パラメーター** のステップで、次のプロパティを設定します:
      1. パイプライン出力結果のフロー先となる、出力 **エンティティ名** を入力します。
      1. テスト パイプラインの **出力データ ストア パラメーター名** を選択します。
      1. テスト パイプラインの **出力パス パラメーター名** を選択します。

1. 顧客を特定するには、**結果内の顧客 ID** ドロップダウン リストから一致する属性を選択し、**保存** を選択します。
   顧客エンティティの顧客 ID 列に類似した値を持つ属性を、推論出力から選択します。 データ セットにそのような列がない場合は、行を一意に識別する属性を選択してください。

## <a name="run-a-workflow"></a>ワークフローの実行

1. **カスタム モデル** ページで、以前に作成したワークフローの横にある **アクション** 列で縦方向の省略記号を選択します。

1. **実行** を選択します。

ワークフローは、更新がスケジュールされるたびに自動的に実行されます。 詳細については、 [スケジュールされた更新を設定する](system.md#schedule-tab) を参照してください。

## <a name="delete-a-workflow"></a>ワークフローを削除する

1. **カスタム モデル** ページで、以前に作成したワークフローの横にある **アクション** 列で縦方向の省略記号を選択します。

1. **削除** を選び、削除内容を確認します。

ワークフローが削除されます。 ワークフローの作成時に作成された [エンティティ](entities.md)は保持されており、これらは **エンティティ** ページで確認することができます。

## <a name="results"></a>結果​​

ワークフローの結果は、モデル出力パラメーター フェーズで構成されたエンティティに保存されます。 このデータには、[エンティティ ページ](entities.md) から、または [API アクセス](apis.md) を使用してアクセスできます。

### <a name="api-access"></a>API アクセス

カスタム モデル エンティティからデータを取得するための特定の OData クエリには、次の形式を使用します:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. `<your instance id>` を、Customer Insights にアクセスするときに、ブラウザーのアドレス バーに表示される Customer Insights 環境の ID に置き換えます。

1. `<custom model output entity>` を、カスタム モデル構成のモモデル出力パラメーター ステップで指定したエンティティ名に置き換えます。

1. `<guid value>` を、レコードにアクセスする顧客の顧客 ID に置き換えます。 通常、この ID は [顧客プロファイル ページ](customer-profiles.md) の CustomerID フィールドにあります。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

- カスタム モデル ワークフローを設定するときに、パイプラインが表示されないのはなぜですか?    
  この問題は、パイプラインの構成の問題が原因で発生することがよくあります。 [入力パラメータが構成](azure-machine-learning-experiments.md#dataset-configuration) され、[出力データストアとパス パラメータ](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) も構成されていることを確認します。

- 「インテリジェンス ワークフローを保存できませんでした」というエラーは何を意味していますか?    
  ユーザーが、ワークスペースに対する所有者またはユーザー アクセス管理者権限がない場合、通常、このエラー メッセージが表示されます。 ユーザーは、Customer Insights がワークフローをサービスとして処理できるようにするために、ワークフローの後続の実行にユーザー資格情報を使用するのではなく、より高いレベルの権限を必要とします。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
