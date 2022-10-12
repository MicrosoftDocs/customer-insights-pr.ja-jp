---
title: カスタム機械学習モデル | Microsoft Docs
description: Dynamics 365 Customer Insights で Azure Machine Learning で作成したカスタマイズ モデルで作業する。
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609752"
---
# <a name="custom-machine-learning-models"></a>カスタム機械学習モデル

> [!NOTE]
> Machine Learning Studio (クラシック) のサポートは、2024 年 8 月 31 日に終了します。 その日までに、[Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) に移行することをお薦めします。
>
> 2021 年 12 月 1 日以降、新しい Machine Learning Studio (クラシック) のリソースは作成できません。 2024 年 8 月 31 日まで、既存の Machine Learning Studio (クラシック) リソースを引き続き使用できます。 詳細については、[Azure Machine Learning に移行する](/azure/machine-learning/migrate-overview)を参照してください。

カスタム モデルでは、Azure Machine Learning モデルに基づいてワークフローを管理できます。 ワークフローは、インサイトを生成するデータを選択し、その結果を統合顧客データにマップするのに役立ちます。 カスタム ML モデルの構築の詳細については、[ Azure Machine Learning ベースのモデルを使用する](azure-machine-learning-experiments.md) を参照してください。

## <a name="prerequisites"></a>前提条件

- [Azure Machine Learning バッチ パイプライン](/azure/machine-learning/concept-ml-pipelines) で公開された Web サービス。
- パイプラインは、[パイプライン エンドポイント](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) の下で公開されている必要があります。
- Azure Studio インスタンスに関連付けられた [Azure Data Lake Gen2 ストレージ アカウント](/azure/storage/blobs/data-lake-storage-quickstart-create-account)。
- パイプラインを含む Azure Machine Learning ワークスペースの場合、Azure Machine Learning ワークスペースに対する所有者またはユーザー アクセス管理者権限。

  > [!NOTE]
  > データは、Customer Insights インスタンスと、ワークフローで選択した Azure Web サービスまたはパイプラインの間で転送されます。 Azure サービスにデータを転送する場合は、必要な方法と場所でデータを処理するようにサービスを構成し、組織のデータに関する法律や規制の要件に準拠していることをご確認ください。

## <a name="add-a-new-workflow"></a>新しいワークフローを追加します

1. **インテリジェンス** > **カスタム モデル** に移動し、**新規ワークフロー** を選択します。

1. 認識可能な **名前** を入力します。

   :::image type="content" source="media/new-workflowv2.png" alt-text="新規ワークフロー ウィンドウのスクリーンショット。":::

1. **Web サービスを含むテナント** にて、Webサービスを含む組織を選択します。

1. Azure Machine Learning のサブスクリプションが Customer Insights とは異なるテナントにある場合は、選択した組織の資格情報を使用して **サイン インする** を選択します。

1. Web サービスに関連付けられている **ワークスペース** を選択します。

1. **モデルを含む Web サービス** ドロップダウンで、Azure Machine Learning パイプラインを選択します。 続いて、**次へ** を選択します。
   [デザイナーを使用した Azure Machine Learning でのパイプラインの公開](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) または [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) の詳細。

1. 各 **Web サービスの入力** に対して、 Customer Insights から一致する **エンティティ** を選択し、 次へ を選択します。 続いて、**次へ** を選択します。
   > [!NOTE]
   > カスタム モデル ワークフローは、ヒューリスティックを適用して、フィールドの名前とデータ型に基づいて Web サービス入力フィールドをエンティティ属性にマッピングします。 Web サービス フィールドをエンティティにマップできない場合は、エラーが表示されます。

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="ワークフローの構成。":::

1. **モデル出力パラメーター** の場合、次のプロパティを設定します:
   - パイプライン出力結果の **エンティティ名**
   - バッチ パイプラインの **出力データ ストア パラメーター名**
   - バッチ パイプラインの **出力パス パラメーター名**

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="モデル出力パラメーター ペイン。":::

1. 顧客を特定する **結果に含まれる顧客 ID** から一致する属性を選択し、**保存** を選択します。

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="結果と顧客データの関連付けペイン。":::

   **ワークフローの保存** 画面では、ワークフローの詳細が表示されます。 Azure 機械学習パイプラインのワークフローを構成した場合、Customer Insights はパイプラインを含むワークスペースに接続します。 Customer Insights は Azure ワークスペースで **共同作成者** の役割を取得します。

1. **完了** を選択します。 **カスタム モデル** ページが表示されます。

1. ワークフローの垂直方向の省略記号 (&vellip;) を選択し、**実行** を選択します。 また、ワークフローは [スケジュールされている更新](schedule-refresh.md) のたびに自動的に実行されます。

## <a name="manage-an-existing-workflow"></a>既存ワークフローの管理

**インテリジェンス** > **カスタム モデル** に移動し、作成したワークフローを表示します。

ワークフローを選択して、使用可能なアクションを表示します。

- ワークフローの **編集**
- ワークフローの **実行**
- ワークフローの [**削除**](#delete-a-workflow)

### <a name="edit-a-workflow"></a>ワークフローの編集

1. **インテリジェンス** > **カスタム モデル** に移動します。

1. 更新するワークフローの横にある垂直方向の省略記号 (&vellip;) を選択して、**編集** を選択します。

1. 必要に応じて **表示名** を変更し、**次へ** を選択します。

1. **Web サービスの入力** ごとに、必要に応じて Customer Insights から一致する **エンティティ** を更新します。 続いて、**次へ** を選択します。

1. **モデル出力パラメーター** の場合、次のいずれかを変更します:
   - パイプライン出力結果の **エンティティ名**
   - バッチ パイプラインの **出力データ ストア パラメーター名**
   - バッチ パイプラインの **出力パス パラメーター名**

1. **結果に含まれる顧客 ID** から一致する属性を変更し、顧客を特定します。 顧客エンティティの顧客 ID 列に類似した値を持つ属性を、推論出力から選択します。 データ セットにそのような列がない場合は、行を一意に識別する属性を選択してください。

1. **保存** を選択します

### <a name="delete-a-workflow"></a>ワークフローを削除する

1. **インテリジェンス** > **カスタム モデル** に移動します。

1. 削除するワークフローの横にある垂直方向の省略記号 (&vellip;) を選択して、**削除** を選択します。

1. 削除を確認します。

ワークフローが削除されます。 ワークフローの作成時に作成された [エンティティ](entities.md) は保持されており、**データ** > **エンティティ** ページで確認することができます。

## <a name="view-the-results"></a>結果の表示

ワークフローの結果は、**モデル出力パラメーター** に定義されたエンティティに保存されます。 このデータには、[**データ** > **エンティティ** ページ](entities.md) から、または [API アクセス](apis.md) を使用してアクセスします。

### <a name="api-access"></a>API アクセス

カスタム モデル エンティティからデータを取得するための特定の OData クエリには、次の形式を使用します:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. `<your instance id>` を、Customer Insights にアクセスするときに、ブラウザーのアドレス バーに表示される Customer Insights 環境の ID に置き換えます。

1. `<custom model output entity>` を **モデル出力パラメーター** に指定したエンティティ名に置き換えます。

1. `<guid value>` をアクセスする顧客の顧客 ID に置き換えます。 この ID は [顧客プロファイル ページ](customer-profiles.md) の CustomerID フィールドに表示されます。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

- カスタム モデル ワークフローを設定するときに、パイプラインが表示されないのはなぜですか?
  この問題は、パイプラインの構成の問題が原因で発生することがよくあります。 [入力パラメータが構成](azure-machine-learning-experiments.md#dataset-configuration) され、[出力データストアとパス パラメータ](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) も構成されていることを確認します。

- 「インテリジェンス ワークフローを保存できませんでした」というエラーは何を意味していますか? 
  ユーザーが、ワークスペースに対する所有者またはユーザー アクセス管理者権限がない場合、通常、このエラー メッセージが表示されます。 ユーザーは、Customer Insights がワークフローをサービスとして処理できるようにするために、ワークフローの後続の実行にユーザー資格情報を使用するのではなく、より高いレベルの権限を必要とします。

- カスタム モデル ワークフローのプライベート エンドポイント / プライベート リンクはサポートされていますか?
  Customer Insights は現在、すぐに使えるカスタム モデルのプライベート エンドポイントをサポートしていませんが、手動の回避策を利用できます。 詳細についてサポートにお問い合わせください。

## <a name="responsible-ai"></a>責任ある AI

予測は、より良い顧客体験を生み出し、ビジネス能力と収益ストリームを改善する機能を提供します。 予測の価値と、それが持つ影響や倫理的な方法で導入される可能性のあるバイアスとのバランスを取ることを強くお勧めします。 Microsoft の [責任ある AI への対応](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) の詳細を確認してください。 また、Azure Machine Learning に固有の [責任ある機械学習の技術とプロセス](/azure/machine-learning/concept-responsible-ml) についても確認できます。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
