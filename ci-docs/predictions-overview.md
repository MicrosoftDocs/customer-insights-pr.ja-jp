---
title: 予測の概要
description: Dynamics 365 Customer Insights アプリケーションで対応する予測シナリオとオプション。
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610196"
---
# <a name="predictions-overview"></a>予測の概要

Dynamics 365 Customer Insights には、AI や機械学習を活用してデータを予測するさまざまなオプションが用意されています。

## <a name="out-of-box-models"></a>標準モデル

データの予測を開始する最も簡単な方法は、事前定義されたモデルであり、多くの場合、標準モデルと呼ばれます。 特定のデータと構造があれば、インサイトをすばやく生成することができます。 以下のモデルが使用可能です:

# <a name="individual-consumers-b-to-c"></a>[個人消費者 (B2C)](#tab/b2c)

- [顧客の生涯価値](predict-customer-lifetime-value.md): ビジネスとのやり取り全体を通じて、顧客の潜在的な売上を予測します。
- [製品推奨](predict-product-recommendation.md): 購入行動や類似の購入パターンを持つ顧客に基づいて、予測製品推奨セットを提案します。
- [サブスクリプション離反](predict-subscription-churn.md): 顧客が自社のサブスクリプション製品やサービスを使用しなくなるリスクがあるかどうかを予測します。
- [トランザクション離反](predict-transactional-churn.md): 個々の顧客が一定期間内に製品やサービスを購入しなくなるかどうかを予測します。
- [感情分析](sentiment-analysis.md): 顧客のフィードバックの感情を分析し、頻繁に言及されるビジネスに関する意見を特定します。

# <a name="business-accounts-b-to-b"></a>[事業取引先企業 (B2B)](#tab/b2b)

- [トランザクション離反](predict-transactional-churn.md): 顧客取引先企業が一定期間内に製品やサービスを購入しなくなるかどうかを予測します。

---

> [!TIP]
> 更新されたデータを使用してすぐに使用できるモデルを定期的に更新し、ビジネスのユース ケースを正確に通知することをお勧めします。 システムが新しいデータ ソースや更新されたデータ ソースを取り込むと、データはアドホックに更新されます。 ただし、モデルはこの場合にのみ再スコアリングし、既存のトレーニング データを引き続き使用します。
>
> **更新スケジュール** を構成するには、構成時にモデルの再トレーニング スケジュールを設定します。 モデルはこのスケジュールで再トレーニングと再スコアリングを行います。このスケジュールはいつでも変更できます。

## <a name="azure-machine-learning-integration"></a>Azure Machine Learning 統合

組織が既に Azure Machine Learning の実験に基づく機械学習シナリオを使用している場合、Customer Insights のカスタム モデル機能はドットを関連付けるのに役立ちます。 インサイトを生成するデータの選択に役立つワークフローを作成し、結果を統合された顧客プロファイルにマップします。 詳細については、[カスタム機械学習モデル](custom-models.md) を参照してください。

## <a name="manage-existing-predictions"></a>既存の予測の管理

**インテリジェンス** > **予測** ページに移動します。 **自分の予測** タブで、作成した予測、その予測タイプ、出力エンティティ名、状態、予測が最後に編集された時刻、データが最後に更新された時刻を表示します。 予測のリストは任意の列で並べ替えることができます。

予測を選択して、使用可能なアクションを表示します。

:::image type="content" source="media/predictions.png" alt-text="自分の予測ページ。":::

- プロパティを変更する予測を **編集** します。
- 最新のデータを含むように予測を [**更新**](#refresh-a-prediction) します。
- 予測の詳細を **表示** します。
- エラー、警告、推奨事項を表示する [**入力データ ユーザビリティ レポート**](#view-the-input-data-usability-report)。
- 予測を **削除** します。

### <a name="refresh-a-prediction"></a>予測を更新する

予測は、自動スケジュールで更新することも、オンデマンドで手動で更新することもできます。 すべての予測を手動で更新するには、**すべて更新** を選択します。 予測を手動で更新するには、予測を選択して **更新** を選択します。 [自動更新をスケジュールする](schedule-refresh.md)には、**管理者** > **システム** > **スケジュール** に移動します。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>入力データ ユーザビリティ レポートの表示

入力データのユーザビリティ レポートは、すぐに使用できる予測で生成される可能性のあるエラーと警告の統合ビューを提供します。 また、モデルのパフォーマンスを向上させる方法に関する推奨事項も含まれます。

レポートは、モデルがトレーニング プロセスを完了した後で利用できます。 正常にトレーニングが完了したかどうかに関係なく、モデルごとに個別に作成されます。

**自分の予測** タブで予測を選択し、**入力データ ユーザビリティ レポート** を選択します。 または、予測の詳細ビューから、**入力データ ユーザビリティ レポート** を選択します。

:::image type="content" source="media/input-data-usability-report.png" alt-text="エラー、警告、および推奨事項を含むテーブルを示す入力データ ユーザビリティ レポートの例。":::

レポートの内容は次のとおりです:

- **名前:** エラー、警告、または推奨事項の内容を示す名前。
- **ステップ:** 情報が参照するモデル フェーズ、トレーニングまたはスコア。
- **状態:** 情報の重要度 (エラー、警告、推奨事項)。
- **列名:** モデルのパフォーマンスを向上させるために変更が必要なエンティティの列。
- **エンティティ名:** モデルのパフォーマンスを向上させるために変更が必要なエンティティの名前。
- **詳細:** エラー、警告、または推奨事項に関する詳細。

[!INCLUDE [footer-include](includes/footer-banner.md)]
