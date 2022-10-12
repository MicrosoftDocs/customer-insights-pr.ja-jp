---
title: 顧客の生涯価値 (CLV) 予測サンプル ガイド
description: このサンプル ガイドを使用して、顧客の生涯価値予測モデルを試してください。
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609644"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>顧客の生涯価値 (CLV) 予測サンプル ガイド

このガイドでは、サンプル データを使用した Customer Insights での顧客の生涯価値 (CLV) 予測の例を順を追って説明します。 [新しい環境で](manage-environments.md) この予測を実行することをお勧めします。

## <a name="scenario"></a>シナリオ

Contoso は、高品質のコーヒーとコーヒー マシンを製造する会社です。 Contoso Coffee の Web サイトで製品を販売しています。 同社は、顧客が今後 12 か月で生み出す価値 (売上) を把握したいと考えています。 今後 12 か月の顧客の期待値を知ることで、価値の高い顧客にマーケティング活動を行うことができます。

## <a name="prerequisites"></a>前提条件

- 少なくとも [共同作成者のアクセス許可](permissions.md)。

## <a name="task-1---ingest-data"></a>タスク 1 - データの取り込み

[データ インジェスト](data-sources.md) と [Power Query データ ソースへの接続](connect-power-query.md) に関する記事をご確認ください。 以下の情報は、一般的なデータの取り込みに精通していることを前提としています。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>顧客データを eコマース プラットフォームから取り込む

1. **eコマース** という名前の Power Query データ ソースを作成し、**テキスト/CSV** コネクタを選択します。

1. eコマースの連絡先の URL https://aka.ms/ciadclasscontacts を入力します。

1. データの編集中に、**変換** を選択して、その後 **1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **DateOfBirth**: 日付
   - **CreatedOn**: 日付/時刻/タイムゾーン

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="生年月日を日付に変換します。":::

1. 右側のペインにある **名前** フィールドで、データ ソースの名前を **eCommerceContacts** に変更します

1. データ ソースを **保存** します。

### <a name="ingest-online-purchase-data"></a>オンライン購入データを取り込む

1. 同じ **eコマース** データ ソースに別のデータ セットを追加します。 **テキスト/CSV** コネクタをもう一度選択します。

1. **オンライン購入** データ の URL https://aka.ms/ciadclassonline を入力します。

1. データの編集中に、**変換** を選択して、その後 **1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **PurchasedOn**: 日付/時刻
   - **TotalPrice**: 通貨

1. サイド ペインの **名前** フィールドで、データ ソースの名前を **eCommercePurchases** に変更します。

1. データ ソースを **保存** します。

### <a name="ingest-customer-data-from-loyalty-schema"></a>ロイヤルティ スキームから顧客データを取り込む

1. **LoyaltyScheme** という名前のデータ ソースを作成し、**テキスト/CSV** コネクタを選択します。

1. ロイヤリティ顧客の URL https://aka.ms/ciadclasscustomerloyalty を入力します。

1. データの編集中に、**変換** を選択して、その後 **1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **DateOfBirth**: 日付
   - **RewardsPoints**: 整数
   - **CreatedOn**: 日付/時刻

1. 右側のペインにある **名前** フィールドで、データ ソースの名前を クエリ から **loyCustomers** に変更します。

1. データ ソースを **保存** します。

### <a name="ingest-customer-data-from-website-reviews"></a>Web サイトのレビューから顧客データを取り込む

1. **Website** という名前のデータ ソースを作成し、**テキスト/CSV** コネクタを選択します。

1. Web レビュー https://aka.ms/CI-ILT/WebReviews の URL を入力します。

1. データの編集中に、**変換** を選択して、その後 **1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **ReviewRating**: 10 進数
   - **ReviewDate**: 日付

1. 右側のペインの **名前** フィールドで、データ ソースの名前をデータ ソースから **レビュー** に変更します。

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

1. その他の活動エンティティを追加し、そのフィールド名を対応するフィールドにマップします:
   - **活動エンティティ**: Reviews:Website
   - **主キー**: ReviewId
   - **タイムスタンプ**: ReviewDate
   - **イベント活動**: ActivityTypeDisplay
   - **追加の詳細**: ReviewRating
   - **活動の種類**: レビュー

1. この活動を実行します。

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>タスク 4 - 顧客の生涯価値予測の構成

統合顧客プロファイルが配置され活動が作成されたことで、顧客の生涯価値 (CLV) 予測を実行できるようになりました。 詳細な手順については、[顧客の生涯価値予測](predict-customer-lifetime-value.md)を参照してください。

1. **インテリジェンス** > **予測** に移動します。

1. **作成** タブで **顧客生涯価値** タイルの **モデルを使用** を選択します。

1. **開始する** を選択します。

1. モデルに **OOB eコマース CLV 予測**、出力エンティティに **OOBeCommerceCLVPrediction** という名前を付けます。

1. モデルの基本設定を定義します:
   - **予測期間**: CLV をどの程度先まで予測するかを定義するために **12 ヶ月または 1 年**。
   - **アクティブな顧客**: 顧客をアクティブと見なすには、少なくとも 1 件のトランザクションが必要である概算時間を設定する、**購入間隔をモデルに計算させる**。
   - **価値の高い顧客**: 価値の高い顧客を **上位 30% のアクティブな支払顧客** として手動で定義します。

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV モデルのガイド付きエクスペリエンスの基本設定ステップ。":::

1. **次へ** を選択します。

1. **必須データ** ステップで、**データの追加** を選択し、トランザクション履歴データを指定します。

    :::image type="content" source="media/clv-model-required.png" alt-text="CLV モデルのガイド付きエクスペリエンスの必要なデータステップを追加します。":::

1. **SalesOrderLine** と eCommercePurchases エンティティを選択して、**次へ** を選択します。 必要なデータはアクティビティから自動的に入力されます。 **保存**、**次へ** の順に選択します。

1. **追加データ (オプション)** ステップでは、顧客活動データをさらに追加して、より多くの顧客対話の分析情報を取得できます。 この例では、**データを追加** を選択して、Web レビュー活動を追加します。

1. **次へ** を選択します。

1. **データ更新** 手順で、モデル スケジュールに対して **月次** を選択します。

1. **次へ** を選択します。

1. すべての詳細を確認した後、**保存と実行** を選択します。

## <a name="task-5---review-model-results-and-explanations"></a>タスク 5 - モデルの結果と説明を確認する

モデルにデータのトレーニングとスコアリングを完了させます。 [CLV モデルの結果と説明](predict-customer-lifetime-value.md#view-prediction-results) をレビューします。

## <a name="task-6---create-a-segment-of-high-value-customers"></a>タスク 6 - 価値の高い顧客のセグメントの作成

モデルを実行すると、新しいエンティティが作成され、**データ** > **エンティティ** に一覧表示されます。 モデルによって作成されたエンティティに基づいて、新しい顧客セグメントを作成できます。

1. 結果ページで **セグメントの作成** を選択します。

1. **OOBeCommerceCLVPrediction** エンティティを使ってルールを作成して、セグメントを定義します。
   - **フィールド**: CLVScore
   - **演算子**: より大きい
   - **値**: 1500

1. **保存** を選択し、セグメントを **実行** します。

これで、今後 12 か月間で $1500 を超える売上を生み出すと予測される顧客を識別するセグメントができました。 より多くのデータが取り込まれると、このセグメントは動的に更新されます。 詳細については、[セグメントの作成と管理](segments.md) をご覧ください。

> [!TIP]
> **新規** を選択して、**作成元** > **インテリジェンス** を選ぶことで、**セグメント** ページから予測モデルに対してセグメントも作成できます。 詳細については、[クイック セグメントで新規セグメントを作成する](segment-quick.md) を参照してください。

[!INCLUDE [footer-include](includes/footer-banner.md)]
