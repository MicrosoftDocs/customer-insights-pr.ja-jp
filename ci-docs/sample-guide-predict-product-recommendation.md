---
title: 製品のレコメンデーション予測サンプル ガイド
description: このサンプル ガイドを使用して、既成の製品レコメンデーション予測モデルを試してください。
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610150"
---
# <a name="product-recommendation-prediction-sample-guide"></a>製品のレコメンデーション予測サンプル ガイド

このガイドはサンプル データを使用して、製品レコメンデーション予測のエンドツーエンドの例について説明します。 [新しい環境で](manage-environments.md) この予測を実行することをお勧めします。

## <a name="scenario"></a>シナリオ

Contoso は、高品質のコーヒーとコーヒー マシンを製造する会社です。 Contoso Coffee の Web サイトで製品を販売しています。 その目標は、定期的な顧客にどの製品を推奨すべきかを理解することです。 顧客が **購入する可能性が高い** ことを把握することで、特定のアイテムに焦点を当ててマーケティングの労力を軽減できます。

## <a name="prerequisites"></a>前提条件

- 少なくとも Customer Insights の[共同作成者権限](permissions.md) があること。

## <a name="task-1---ingest-data"></a>タスク 1 - データの取り込み

[データ インジェスト](data-sources.md) と [Power Query データ ソースへの接続](connect-power-query.md) に関する記事をご確認ください。 以下の情報は、一般的なデータの取り込みに精通していることを前提としています。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>顧客データを eコマース プラットフォームから取り込む

1. **eコマース** という名前の Power Query データ ソースを作成し、**テキスト/CSV** コネクタを選択します。

1. e コマースの連絡先の URL https://aka.ms/ciadclasscontacts を入力します。

1. データの編集中に、**変換** を選択して、その後 **1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **DateOfBirth**: 日付
   - **CreatedOn**: 日付/時刻/タイムゾーン

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="生年月日を日付に変換します。":::

1. 右側のペインにある **名前** フィールドで、データ ソースの名前を  **eCommerceContacts** に変更します

1. データ ソースを **保存** します。

### <a name="ingest-online-purchase-data"></a>オンライン購入データを取り込む

1. 同じ **eコマース** データ ソースに別のデータ セットを追加します。 **テキスト/CSV** コネクタをもう一度選択します。

1. オンライン購入データ https://aka.ms/ciadclassonline の URL を入力します。

1. データの編集中に、**変換** を選択して、その後 **1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **PurchasedOn**: 日付/時刻
   - **TotalPrice**: 通貨

1. サイド ペインの **名前** フィールドで、データ ソースの名前を **eCommercePurchases** に変更します。

1. データ ソースを **保存** します。

### <a name="ingest-customer-data-from-loyalty-schema"></a>ロイヤルティ スキームから顧客データを取り込む

1. **LoyaltyScheme** という名前のデータ ソースを作成し、**テキスト/CSV** コネクタを選択します。

1. 優良顧客の URL https://aka.ms/ciadclasscustomerloyalty を入力します。

1. データの編集中に、**変換** を選択して、その後 **1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **DateOfBirth**: 日付
   - **RewardsPoints**: 整数
   - **CreatedOn**: 日付/時刻

1. 右側のペインにある **名前** フィールドで、データ ソースの名前を クエリ から **loyCustomers** に変更します。

1. データ ソースを **保存** します。

## <a name="task-2---data-unification"></a>タスク 2 - データの統合

[データ統合に関する](data-unification.md) 記事をレビューします。 以下の情報は、一般的なデータ統合の取り込みに精通していることを前提としています。

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>タスク 3 - トランザクション履歴の活動

[お客様の活動に関する](activities.md) 記事をレビューする。 以下の情報は、一般的な活動作成に精通していることを前提としています。

1. *eCommercePurchases:eCommerce* エンティティとその主キー、**PurchaseId** ともに **eCommercePurchases** と呼ばれる活動を作成します。

1. *eCommercePurchases:eCommerce* と *eCommerceContacts:eCommerce* との間と、2 つのエンティティを接続するための外部キーとしての **ContactID** との関係を作成します。

1. **EventActivity** に対しては **TotalPrice**、そして **TimeStamp** に対して **PurchasedOn** を選択します。

1. **活動の種類** に対して **SalesOrderLine** を選択して活動データを意味的にマッピングします。

1. この活動を実行します。

## <a name="task-4---configure-product-recommendation-prediction"></a>タスク 4 - 製品レコメンデーション予測を構成する

統合顧客プロファイルが配置され、活動が作成されたので、製品レコメンデーション予測を実行できます。

1. **インテリジェンス** > **予測** に移動します。

1. **作成** タブで、**製品レコメンデーション (プレビュー)** タイルで **モデルを使用する** を選択します。

1. **開始する** を選択します。

1. モデルに **OOB 製品レコメンデーション モデル予測**、出力エンティティには **OOBProductRecommendationModelPrediction** という名前を付けます。

1. **次へ** を選択します。

1. モデルの基本設定を定義します:
   - **製品の数**: 顧客に推奨する製品の数を定義するには **5**。
   - **リピート購入期待**: 以前に購入した製品をレコメンデーションに含めるには **はい**。
   - **振り返るウィンドウ:** 製品を再度推奨する前に、モデルがどの程度振り返るかを定義するには **365 日**。

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="製品レコメンデーション モデルモデル マッピングです。":::

1. **次へ** を選択します。

1. **購入履歴の追加** 手順で、**データを追加する** を選択します。

1. **SalesOrderLine** と eCommercePurchases エンティティを選択して、**次へ** を選択します。 必要なデータはアクティビティから自動的に入力されます。 **保存**、**次へ** の順に選択します。

1. 製品情報データがないため、**製品情報の追加** と **製品フィルター** 手順をスキップします。

1. **データ更新** 手順で、モデル スケジュールに対して **月次** を選択します。

1. **次へ** を選択します。

1. すべての詳細を確認した後、**保存と実行** を選択します。

## <a name="task-5---review-model-results-and-explanations"></a>タスク 5 - モデルの結果と説明を確認する

モデルにデータのトレーニングとスコアリングを完了させます。 [製品レコメンデーション モデルの説明](predict-transactional-churn.md#view-prediction-results) をレビューします。

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>タスク 6 - 購入数の多い製品のセグメントを作成する

モデルを実行すると、新しいエンティティが作成され、**データ** > **エンティティ** に一覧表示されます。 モデルによって作成されたエンティティに基づいて、新しいセグメントを作成できます。

1. 結果ページで **セグメントの作成** を選択します。

1. **OOBProductRecommendationModelPrediction** エンティティを使ってルールを作成して、セグメントを定義します。
   - **フィールド**: ProductID
   - **値**: 上位 3 つの製品 ID を選択する

1. **保存** を選択し、セグメントを **実行** します。

これで、動的に更新されるセグメントができました。これは、最も推奨される 5 つの製品の購入に関心がある可能性のある顧客を識別します。 詳細については、[セグメントの作成と管理](segments.md) をご覧ください。

> [!TIP]
> **新規** を選択して、**作成元** > **インテリジェンス** を選ぶことで、**セグメント** ページから予測モデルに対してセグメントも作成できます。 詳細については、[クイック セグメントで新規セグメントを作成する](segment-quick.md) を参照してください。

[!INCLUDE [footer-include](includes/footer-banner.md)]
