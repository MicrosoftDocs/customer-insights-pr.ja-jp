---
title: 顧客の生涯価値予測サンプル ガイド
description: このサンプル ガイドを使用して、顧客の生涯価値予測モデルを試してください。
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129951"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>顧客の生涯価値 (CLV) 予測サンプル ガイド

このガイドでは、サンプル データを使用した Customer Insights での顧客の生涯価値 (CLV) 予測の例を順を追って説明します。

## <a name="scenario"></a>シナリオ

Contoso は高品質のコーヒーとコーヒー メーカーを製造する会社です。 Contoso Coffee の Web サイトで製品を販売しています。 同社は、顧客が今後 12 か月で生み出す価値 (売上) を把握したいと考えています。 今後 12 か月の顧客の期待値を知ることで、価値の高い顧客にマーケティング活動を行うことができます。

## <a name="prerequisites"></a>前提条件

- 少なくとも、対象者に関するインサイトで [共同作成者のアクセス許可](permissions.md)。
- [新しい環境で](manage-environments.md) 次の手順を実行することをお勧めします。

## <a name="task-1---ingest-data"></a>タスク 1 - データの取り込み

[データ インジェストについて](data-sources.md) と [Power Query コネクタを使用したデータ ソースのインポート](connect-power-query.md) の記事を確認します。 以下の情報は、一般的なデータの取り込みに精通していることを前提としています。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>顧客データを eコマース プラットフォームから取り込む

1. **eコマース** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。

1. eコマースの連絡先 URL [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts) を入力します。

1. データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **DateOfBirth**: 日付
   - **CreatedOn**: 日付/時刻/タイムゾーン

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="生年月日を日付に変換します。":::

1. 右側のペインにある '名前' フィールドで、データ ソースの名前を **クエリ** から **eCommerceContacts** に変更します

1. データ ソースを **保存** します。

### <a name="ingest-online-purchase-data"></a>オンライン購入データを取り込む

1. 同じ **eコマース** データ ソースに別のデータ セットを追加します。 **テキスト/CSV** コネクタをもう一度選択します。

1. **オンライン購入** データ の URL https://aka.ms/ciadclassonline を入力します。

1. データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **PurchasedOn**: 日付/時刻
   - **TotalPrice**: 通貨

1. サイド ペインの **名前** フィールドで、データ ソースの名前を **クエリ** から **eCommercePurchases** に変更します。

1. データ ソースを **保存** します。

### <a name="ingest-customer-data-from-loyalty-schema"></a>ロイヤルティ スキームから顧客データを取り込む

1. **LoyaltyScheme** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。

1. eコマースの連絡先の URL https://aka.ms/ciadclasscustomerloyalty を入力します。

1. データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **DateOfBirth**: 日付
   - **RewardsPoints**: 整数
   - **CreatedOn**: 日付/時刻

1. 右側のペインにある **名前** フィールドで、データ ソースの名前を **クエリ** から **loyCustomers** に変更します。

1. データ ソースを **保存** します。

### <a name="ingest-customer-data-from-website-reviews"></a>Web サイトのレビューから顧客データを取り込む

1. **Web サイト** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。

1. eコマースの連絡先の URL https://aka.ms/CI-ILT/WebReviews を入力します。

1. データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:

   - **ReviewRating**: 10 進数
   - **ReviewDate**: 日付

1. 右側のペインの '名前' フィールドで、データ ソースの名前を **Query** から **Reviews** に変更します。

1. データ ソースを **保存** します。

## <a name="task-2---data-unification"></a>タスク 2 - データの統合

データを取り込んだ後、データ統合プロセスを開始して、統合された顧客プロファイルを作成します。 詳細については、[データの統合](data-unification.md) を参照してください。

### <a name="map"></a>マップ

1. データを取り込んだ後、連絡先を eコマースおよびロイヤルティ データから共通のデータ型にマップします。 **データ** > **統合** > **マップ** に移動します。

1. 顧客プロファイルを表すエンティティ - **eCommerceContacts** および **loyCustomers** を選択します。 次に、**適用** を選択します。

   ![eコマースとロイヤルティ データソースを統合します。](media/unify-ecommerce-loyalty.png)

1. **eCommerceContacts** の主キーとして **ContactId**、**loyCustomers** の主キーとして **LoyaltyID** を選択します。

   ![LoyaltyId を主キーとして統合します。](media/unify-loyaltyid.png)

1. **保存** を選択します。

### <a name="match"></a>照合

1. **照合** タブに移動して、**順序の設定** を選択します。

1. **プライマリ** ドロップダウン リストで、**eCommerceContacts : eCommerce** をプライマリ ソースとして選択し、すべてのレコードを含めます。

1. **エンティティ 2** ドロップダウン リストで、**loyCustomers : LoyaltyScheme** を選択し、すべてのレコードを含めます。

   ![eコマースとロイヤルティの一致を統合します。](media/unify-match-order.png)

1. **ルールの追加** を選択します

1. FullName を使用して最初の条件を追加します。

   - eCommerceContacts の場合は、ドロップダウンで **FullName** を選択します。
   - loyCustomers の場合は、ドロップダウンで **FullName** を選択します。
   - **正規化** ドロップダウンを選択して、**種類 (電話、名前、住所、...)** を選択します。
   - **精度レベル** の設定: **基本** と **値**: **高い**。

1. 新しいルールに **FullName, Email** という名前を入力します。

   - **条件の追加** を選択し、メール アドレスの 2 番目の条件を追加します
   - エンティティ eCommerceContacts の場合、ドロップダウンで **電子メール** を選択します。
   - エンティティ loyCustomers の場合、ドロップダウンで **電子メール** を選択します。
   - 正規化を空白のままにします。
   - **精度レベル** の設定: **基本** と **値**: **高い**。

   ![名前とメールの照合ルールを統一します。](media/unify-match-rule.png)

1. **完了** を選択します。

1. **保存** と **実行** を選択します。

### <a name="merge"></a>マージ

1. **マージ** タブに移動します。

1. **loyCustomers** エンティティの **ContactId** で、表示名を **ContactIdLOYALTY** に変更して、取り込まれた別の ID とは区別されるようにします。

   ![ロイヤルティ ID から contactid に名前を変更します。](media/unify-merge-contactid.png)

1. **保存** と **マージおよびダウンストリーム プロセスを実行する** を選択します。

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>タスク 3 - 顧客の生涯価値予測の構成

統合された顧客プロファイルが用意できたので、顧客の生涯価値予測を実行できるようになりました。 詳細な手順については、[顧客の生涯価値予測 (プレビュー)](predict-customer-lifetime-value.md) を参照してください。

1. **インテリジェンス**  > **予測** に移動し、**顧客の生涯価値モデル** を選択します。

1. サイド ペインの情報に目を通し、**開始する** を選択します。

1. モデルに **OOB eコマース CLV 予測**、出力エンティティに **OOBeCommerceCLVPrediction** という名前を付けます。

1. CLV モデルのモデルの基本設定を定義します:
   - **予測期間**: **12 か月間または 1 年**。 この設定では、顧客の生涯価値をどのくらい先まで予測するかを定義します。
   - **アクティブな顧客**: アクティブな顧客がビジネスにどのような意味を持つかを指定します。 顧客がアクティブであると見なされるには、少なくとも 1 件のトランザクションを持つ必要がある履歴期間を設定します。 このモデルは、アクティブな顧客の CLV のみを予測します。 モデルでトランザクションの履歴データに基づいて期間を計算するか、特定の期間を指定するかのいずれかを選択します。 このサンプル ガイドでは、既定のオプションである **モデルで購入間隔を計算** します。
   - **価値の高い顧客**: 価値の高い顧客を上位支払顧客のパーセンタイルとして定義します。 モデルはこの入力を使用して、価値の高い顧客のビジネス定義に適合する結果を提供します。 モデルに価値の高い顧客を定義させることもできます。 パーセンタイルを算出する発見的規則を使用します。 価値の高い顧客を今後の上位支払顧客のパーセンタイルとして定義することもできます。 このサンプル ガイドでは、価値の高い顧客を **アクティブな支払顧客の上位 30%** として手動で定義し、**次へ** を選択します。

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV モデルのガイド付きエクスペリエンスの基本設定ステップ。":::

1. **必須データ** ステップで、**データの追加** を選択し、トランザクション履歴データを指定します。

1. **eCommercePurchases : eCommerce** エンティティを追加し、モデルに必要な属性をマップします:
   - トランザクション ID: eCommerce.eCommercePurchases.PurchaseId
   - トランザクションの日付: eCommerce.eCommercePurchases.PurchasedOn
   - トランザクション金額: eCommerce.eCommercePurchases.TotalPrice
   - 製品 ID: eCommerce.eCommercePurchases.ProductId

1. **次へ** を選択します。

1. **eCommercePurchases : eCommerce** エンティティと **eCommerceContacts : eCommerce** の関係を設定します。

1. **追加データ (オプション)** ステップでは、顧客活動データをさらに追加できます。 このデータは、顧客のビジネスとのやり取りについてより多くのインサイトを得るのに役立ち、CLV に貢献する可能性があります。 Web ログ、顧客サービス ログ、特典プログラム履歴などの、顧客との重要なやり取りを追加すると、予測の精度を向上させることができます。 **データの追加** を選択し、より多くの顧客活動データを追加します。

1. 顧客活動エンティティを追加し、そのフィールド名をモデルに必要な対応するフィールドにマップします:
   - 顧客活動エンティティ: Reviews:Website
   - 主キー: Website.Reviews.ReviewId
   - タイムスタンプ: Website.Reviews.ReviewDate
   - イベント (活動名): Website.Reviews.ActivityTypeDisplay
   - 詳細 (金額または値): Website.Reviews.ReviewRating

1. **次へ** を選択し、活動およびトランザクション データと顧客データの関係を構成します。  
   - 活動の種類: 既存を選択
   - 活動ラベル: Review
   - 対応するラベル: Website.Reviews.UserId
   - 顧客エンティティ: eCommerceContacts:eCommerce
   - 関連付け: WebsiteReviews

1. **次へ** を選択し、モデル スケジュールを設定します。

   新しいデータが取り込まれたときに、モデルは新しいパターンを学習するために、定期的にトレーニングする必要があります。 この例では、**月単位** を選択します。

1. すべての詳細を確認した後、**保存と実行** を選択します。

## <a name="task-4---review-model-results-and-explanations"></a>タスク 4 - モデルの結果と説明を確認する

モデルにデータのトレーニングとスコアリングを完了させます。 次に、CLV モデルの結果と説明を確認できます。 詳細については、[予測の状態と結果の確認](predict-customer-lifetime-value.md#review-prediction-status-and-results) を参照してください。

## <a name="task-5---create-a-segment-of-high-value-customers"></a>タスク 5 - 価値の高い顧客のセグメントの作成

モデルを実行すると、新しいエンティティが作成され、**データ** > **エンティティ** に一覧表示されます。 モデルによって作成されたエンティティに基づいて、新しい顧客セグメントを作成できます。

1. **セグメント** に移動します。 

1. **新規** を選択し、**作成元** > **インテリジェンス** と選択します。

   ![モデル出力を使用してセグメントを作成しています。](media/segment-intelligence.png)

1. **OOBeCommerceCLVPrediction** エンティティを選択し、セグメントを定義します:
  - フィールド: CLVScore
  - 演算子: より大きい
  - 値: 1500

1. **レビュー** を選択し、セグメントを **保存** します。

これで、今後 12 か月間で $1500 を超える売上を生み出すと予測される顧客を識別するセグメントができました。 より多くのデータが取り込まれると、このセグメントは動的に更新されます。

詳細については、[セグメントの作成と管理](segments.md) をご覧ください。
