---
title: Machine Learning Studio (クラシック) の実験
description: Dynamics 365 Customer Insights で Machine Learning Studio (クラシック) モデルを使用します。
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b979dd177b7c6de1971c02a69748006d041e4d2c3e49a3639dba03212bd7acf9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033729"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Azure Machine Learning Studio (クラシック) に基づくモデルを使用する

Dynamics 365 Customer Insights の統合データは、追加のビジネス インサイトを生成できる機械学習モデルを構築するためのソースです。 Customer Insights は、Machine Learning Studio (クラシック) と統合して、独自のカスタム モデルを使用します。 Azure Machine Learning で開発されたモデルが Customer Insights とどのように統合されているかを確認するには、[Azure Machine Learning の実験](azure-machine-learning-experiments.md) を参照してください。

## <a name="prerequisites"></a>前提条件

- Customer Insights を使用する
- アクティブな Azure Enterprise のサブスクリプション
- [統合顧客プロファイル](data-unification.md)
- [Azure Blob Storage へのエンティティのエクスポート](export-azure-blob-storage.md)の設定

## <a name="set-up-machine-learning-studio-classic"></a>Machine Learning Studio クラシックの設定

最初のステップでは、Machine Learning Studio (クラシック) のワークスペースを作成して開く必要があります。

1. [https://www.portal.azure.com](https://www.portal.azure.com/) に移動してサインインします。

1. **リソースの作成** を選択します。

1. **Machine Learning Studio ワークスペース** を選択し、**作成** を選択します。

1. 必要な詳細を入力して[ワークスペースを作成します](/azure/machine-learning/studio/create-workspace)。 インポートする予定のデータの量に基づき、**Web サービス プランの価格レベル** を選択します。 最良のパフォーマンスを得るために、地理的に最も近い **場所** を選択します。

1. リソースを作成すると、Machine Learning Studio ワークスペースのダッシュボードが表示されます。 **Machine Learning Studio** を選択します。

   ![Azure Machine Learning Studio ユーザー インターフェイス。](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Azure Machine Learning Studio で作業する

これで、新たな実験を作成したり、サンプル ギャラリーから既存の実験テンプレートをインポートしたりできます。 3 つの標準シナリオのサンプル実験があります:

- [チャーン予測](#churn-analysis)

- [顧客の生涯価値](#customer-lifetime-value-prediction)

- [製品の推奨または次善の策](#productrecommendation-or-next-best-action)

1. 新たな実験を作成するか、ギャラリーから実験のテンプレートを使用する場合は、**データをインポートする** プロパティを構成する必要があります。 ガイド付きエクスペリエンスを使用するか、詳細を直接入力して、データを含む Azure Blob Storage にアクセスします。  

   ![Azure Machine Learning Studio で実験する。](media/azure-machine-learning-studio-experiment.png)

1. ここまでの手順で、カスタム処理パイプラインを構築して、データのクリーンアップと前処理、機能の抽出、適切なモデルのトレーニングを行うことができます。

1. モデルの性能をテストし、最適化します。

1. モデルの品質が満足いくものであれば、**Webサービスを設定する** > **予測 Web サービス** を選択します。 このオプションは、トレーニング済みのモデルと機能化パイプラインをトレーニング実験から予測サービスにインポートします。 予測サービスは、予測を行うためにトレーニングの実験で使用されたスキーマを使用して、別の入力データのセットを取得することができます。

   ![予測 Web サービスを設定する。](media/predictive-webservice-control.png)

1. 予測 Web サービスの実験が成功したら、自動スケジューリング用にデプロイすることができます。 Web サービスを Customer Insights と連携させるには、**Web サービスのデプロイ** > **Web サービスのデプロイ [新規] プレビュー** を選択します。 [Web サービスのデプロイの詳細](/azure/machine-learning/studio/deploy-a-machine-learning-web-service)。

   ![予測 Web サービスをデプロイする。](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>ギャラリーのサンプル モデル

今回のモデルでは、Contoso ホテルという架空のシナリオを使用します。 Contoso ホテルは次のデータを収集します:

- ホテルの滞在活動で構成される CRM データ。 データセットには、登録されている顧客ごとの宿泊日に関する情報が含まれています。 また、予約情報、部屋タイプ、支出の詳細などに関する詳細も含まれています。 データは、2014 年 1 月から 2018 年 1 月までの 4 年間です。
- ホテルのゲストの顧客プロファイル。 これらのプロファイルには、名前、生年月日、住所、性別、電話番号など、それぞれの顧客に関する情報が含まれています。
- スパ、ランドリー、Wi-Fi、宅配便など、ホテルが提供するサービスの使用率。 この情報は、登録された顧客ごとに記録されます。 通常、サービスの用は宿泊と連動しています。 ホテルに宿泊なくても、顧客がサービスを利用できる場合があります。

## <a name="churn-analysis"></a>チャーン分析

チャーン分析は、さまざまなビジネスの領域に適用されます。 この例では、特に上記のホテル サービスのコンテキストで、サービス チャーンについて説明します。 他のタイプのチャーン モデルの開始点として使用できるエンドツーエンド モデル パイプラインの実用例を提供します。

### <a name="definition-of-churn"></a>チャーンの定義

チャーンの定義は、シナリオによって異なる場合があります。 この例では、過去 1 年間ホテルを利用していないゲストには、チャーンのラベルが表示されているはずです。  

実験のテンプレートは、ギャラリーからインポートできます。 まず、**ホテル滞在アクティビティ**、**顧客データ**、**サービス利用データ** のデータを Azure Blob Storage からインポートしていることを確認します。

   ![チャーンのモデルに使用するデータをインポートする。](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>特性付け

チャーンの定義に基づいて、まずラベルに影響を与える生の特徴を特定します。 そして、これらの原素材の特徴を機械学習モデルで利用できる数値特徴に加工します。 データ統合は、Customer Insights で行われるため、*顧客 ID* を使用して、これらのテーブルを結合できます。

   ![インポートされたレコードの結合。](media/join-imported-data.png)

チャーン分析のモデルを構築するための特性付けには、少し注意が必要です。 データは時間の関数であり、新しいホテルのアクティビティが毎日記録されます。 特性付けの際には、動的データから静的機能を生成する必要があります。 この場合、1 年のスライディング ウィンドウを使用して、ホテルの活動から複数の機能を生成します。 また、部屋タイプや予約タイプなどのカテゴリ機能を、ワンホット エンコーディングを使用してで別の機能に拡張します。  

機能の最終リスト :

| **番号**  | **Original_Column**          | **派生機能**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | 部屋タイプ                    | RoomTypeLargeCount、RoomTypeSmallCount                                                                                                    |
| 2           | 予約の種類                 | BookingTypeOnlineCount、BookingTypePhoneCallCount                                                                                         |
| 3           | 旅行カテゴリー              | TravelCategoryBusinessCount、TravelCategoryLeisureCount                                                                                   |
| 4           | 使用されたドル                | TotalDollarSpent                                                                                                                          |
| 5           | チェックイン日付とチェックアウト日付  | StayDayCount、StayDayCount2016、StayDayCount2015、StayDayCount2014、StayCount、StayCount2016。 StayCount2015、StayCount2014                |
| 6           | サービスの使用率                | UsageTenure、ConciergeUsage、CourierUsage、DryCleaningUsage、GymUsage、PhoneUsage、RestaurantUsage、SpaUsage、TelevisionUsage、WifiUsage  |

### <a name="model-selection"></a>モデルの選択

次に、使用する最適なアルゴリズムを選択する必要があります。 この場合、ほとんどの機能はカテゴリの機能に基づいています。 通常、デシジョン ツリー ベースのモデルがうまく機能します。 数値的特徴しかない場合は、ニューラル ネットワークの方が良いかもしれません。 このような状況では、サポート ベクター マシン (SVM) も適していますが、最高のパフォーマンスを引き出すためには、多くのチューニングが必要となります。 第 1 の選択モデルとして **2 クラスの増幅デシジョン ツリー** を選択し、第 2 の選択モデルとして **2 クラスの SVM** を選択します。 Azure Machine Learning Studio を使用すると、A/B テストを実行できるため、1 つではなく 2 つのモデルから開始することを推奨します。

次の画像は、Azure Machine Learning Studio におけるモデルのトレーニングと評価のパイプラインを示しています :

![Azure Machine Learning Studio のチャーン モデル。](media/azure-machine-learning-model.png)

また、モデル最適化の重要な側面である **順列の特徴量の重要度** と呼ばれる手法を適用します。 組み込みモデルは、最終的な予測に対する特定の特徴量の影響についての分析情報をほとんど有しません。 特徴量の重要度計算機は、特定のモデルの結果に対する個々の特徴量の影響を計算するためにカスタム アルゴリズムを使用しています。 特徴量の重要度は +1 から -1 の範囲で正規化されます。 マイナスの影響は、対応する特徴量が結果に反直観的な影響を及ぼしており、モデルから削除する必要があることを意味します。 ポジティブな影響は、特徴量が予測に大きく貢献していることを示します。 これらの値は異なるメトリックであるため、相関係数とは見なされません。 詳細については、[順列の特徴量の重要度](/azure/machine-learning/studio-module-reference/permutation-feature-importance) を参照してください。

全体的な [チャーンの実験は Azure AI Gallery で利用できます](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp)。

## <a name="customer-lifetime-value-prediction"></a>顧客の生涯価値予測

顧客の生涯価値 (CLTV) の算出は、企業が顧客を評価し、セグメント化するにあたっての重要なメトリックの 1 つです。 ホテル ビジネスでは、顧客を知ることが重要となります。 たとえば、良い顧客を構成する要素を理解することは重要な情報です。 これにより、ホテルの経営者が、高い金額を払ってくれる顧客を満足させるためにどの機能に焦点を当て、改善する必要があるかを評価する際に役立ちます。 これらの決定は、売上と収益に直接影響を与える可能性があります。  

### <a name="definition-of-cltv"></a>CLTV の定義

この例では、顧客の CLTV を、顧客が今後 365 日間に消費すると予想される総ドル額と定義しています。 過去 3 年分のデータを使って、すべての顧客に対するこの価値を予測します。

### <a name="featurization"></a>特性付け

この場合、特徴付けはチャーンのシナリオと非常に共通しています。 ただし、ラベルと予測値は上記で定義したものとは異なります。

### <a name="model-selection"></a>モデルの選択

CLTV の予測は、予測値が正の値の連続型変数であるため、回帰問題となります。 機能のプロパティに基づいて、モデルをトレーニングするための、1 つのアルゴリズムとして **増幅デシジョン ツリー回帰** を、もう 1 つのアルゴリズムとして **ニューラル ネットワーク回帰** を選択します。

## <a name="product-recommendation-or-next-best-action"></a>製品推奨、または次のベスト アクション

ホテルのシナリオにおける製品の推奨は、ホテルが顧客に提供する推奨サービスとして解釈されます。 目的は、顧客に最適なサービスを選択して、その利用を最大化することです。 これは、ビデオ ストリーミング サービスのユーザーに向けて、映画を推薦することに似ています。

### <a name="definition-of-product-recommendation-or-next-best-action"></a>製品の推奨、または次善の策についての定義

目的に応じて、ホテルの顧客に最適なマッチング サービスを提供することで、サービスの利用額を最大化することを目標としています。

### <a name="featurization"></a>特性付け

チャーンモデルと同様に、ホテルの ServiceCustomerID と CustomerID を結合し、CustomerID ごとに一貫した推奨事項を構築しています。

![レコメンデーション モデルの特性付け。](media/azure-machine-learning-model-featurization.png)

データは 3 つの異なるエンティティをソースにしており、そこから特徴を派生させています。 推奨の問題に対する特徴付けは、チャーンや CLTV のシナリオとは異なります。 推奨モデルには、3 つの機能セットの形式で入力データが必要となります。

### <a name="model-selection"></a>モデルの選択

**マッチボックス レコメンダーのトレーニング** と呼ばれるアルゴリズムを用いて、製品やサービスを予測し、推奨モデルをトレーニングします。

![製品レコメンデーションのアルゴリズム。](media/azure-machine-learning-model-recommendation-algorithm.png)

**マッチボックス レコメンダーのトレーニング** モデルに使用されるの 3 つの入力ポートは、トレーニング サービスの利用データ、顧客説明 (オプション)、サービス説明を取り込みます。 モデルのスコアリングには 3 つの方法があります。 1 つは、正規化された割引累積ゲイン (NDCG) スコアを計算して、評価されたアイテムをランク付けするモデル評価用です。 この実験では、NDCG スコアは 0.97 となっています。 その他 2 つのオプションは、推奨可能なサービス カタログ全体でモデルを採点するか、ユーザーが以前に使用したことのない項目のみを採点するものです。

さらにサービス カタログ全体での推奨分布を見てみると、電話、WiFi、宅配便が推奨度の上位を占めていることがわかります。 これは、サービスの消費データの分布から得られるものと一致しています。

![レコメンデーション モデルの結果。](media/azure-machine-learning-model-output.png)

全体的な [製品推奨の実験は、Azure AI Gallery でアクセスできます。](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>カスタム モデルの統合

Customer Insights でこれらの予測を使用するには、顧客 ID と共に予測値を **エクスポート** する必要があります。 ソース データをエクスポートするのと [同じ Azure Blob Storage の場所にエクスポート](/azure/storage/common/storage-import-export-data-from-blobs) します。 予測 Webサービスは、定期的に実行してスコアを更新するようにスケジュール設定することができます。

カスタム モデルで生成されたデータを使用して、顧客データをさらに強化させることができます。 詳細については、[カスタム機械学習モデル](custom-models.md) を参照してください。


[!INCLUDE[footer-include](../includes/footer-banner.md)]