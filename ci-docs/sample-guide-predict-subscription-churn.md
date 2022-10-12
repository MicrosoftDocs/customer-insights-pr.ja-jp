---
title: サブスクリプション解約予測サンプル ガイド
description: このサンプル ガイドを使用して、既成のサブスクリプション解約予測モデルを試してください。
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610012"
---
# <a name="subscription-churn-prediction-sample-guide"></a>サブスクリプション解約予測サンプル ガイド

このガイドは、サンプル データを使用して、サブスクリプション解約予測のエンドツーエンドの例について説明します。 [新しい環境で](manage-environments.md) この予測を実行することをお勧めします。

## <a name="scenario"></a>シナリオ

Contoso は、高品質のコーヒーとコーヒー マシンを製造する会社です。 Contoso Coffee の Web サイトで製品を販売しています。 彼らは最近、定期的にコーヒーを飲む顧客のためにサブスクリプション ビジネスを始めた。 彼らの目標は、どの加入した顧客が今後数か月以内にサブスクリプションをキャンセルする可能性があるかを把握することです。 どの顧客が **解約する可能性がある** かを把握することは、顧客をつなぎ止めることに集中することで、マーケティング活動を軽減するのに役立ちます。

## <a name="prerequisites"></a>前提条件

- 少なくとも Customer Insights の[共同作成者権限](permissions.md) があること。

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

1. データ ソースを保存します。

### <a name="ingest-customer-data-from-loyalty-schema"></a>ロイヤルティ スキームから顧客データを取り込む

1. **LoyaltyScheme** という名前のデータ ソースを作成し、**テキスト/CSV** コネクタを選択します。

1. ロイヤリティ顧客の URL https://aka.ms/ciadclasscustomerloyalty を入力します。

1. データの編集中に、**変換** を選択して、その後 **1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **DateOfBirth**: 日付
   - **RewardsPoints**: 整数
   - **CreatedOn**: 日付/時刻

1. 右側のペインにある **名前** フィールドで、データ ソースの名前を クエリ から **loyCustomers** に変更します。

1. データ ソースを保存します。

### <a name="ingest-subscription-information"></a>サブスクリプション情報の取り込み

1. **SubscriptionHistory** という名前のデータ ソースを作成し、**テキスト/CSV** コネクタを選択します。

1. サブスクリプションの URL https://aka.ms/ciadchurnsubscriptionhistory を入力します。

1. データの編集中に、**変換** を選択して、その後 **1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **SubscriptioID**: 整数
   - **SubscriptionAmount**: 通貨
   - **SubscriptionEndDate**: 日付/時刻
   - **SubscriptionStartDate**: 日付/時刻
   - **TransactionDate**: 日付/時刻
   - **IsRecurring**: True/False
   - **Is_auto_renew**: True/False
   - **RecurringFrequencyInMonths**: 整数

1. 右側のペインの **名前** フィールドで、データ ソースの名前を **SubscriptionHistory** に変更します。

1. データ ソースを保存します。

### <a name="ingest-customer-data-from-website-reviews"></a>Web サイトのレビューから顧客データを取り込む

1. **Website** という名前のデータ ソースを作成し、**テキスト/CSV** コネクタを選択します。

1. Web レビュー https://aka.ms/ciadclasswebsite の URL を入力します。

1. データの編集中に、**変換** を選択して、その後 **1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **ReviewRating**: 整数
   - **ReviewDate**: 日付

1. 右側のペインの **名前** フィールドで、データ ソースの名前を **webReviews** に変更します。

## <a name="task-2---data-unification"></a>タスク 2 - データの統合

[データ統合に関する](data-unification.md) 記事をレビューします。 以下の情報は、一般的なデータ統合の取り込みに精通していることを前提としています。

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>タスク 3 - トランザクション履歴の活動

[お客様の活動に関する](activities.md) 記事をレビューする。 以下の情報は、一般的な活動作成に精通していることを前提としています。

1. *サブスクリプション* エンティティとその主キー、**CustomerId** とともに **SubscriptionHistory** と呼ばれる活動を作成します。

1. 間の関係を作成します *SubscriptionHistory:Subscription* と *eCommerceContacts:eCommerce* との間と、2 つのエンティティを接続するための外部キーとしての **CustomerID** との関係を作成します。

1. **EventActivity** に対しては **SubscriptionType**、そして **TimeStamp** に対して **SubscriptionEndDate** を選択します。

1. **活動の種類** に対して **サブスクリプション** を選択して活動データを意味的にマッピングします。

1. この活動を実行します。

1. その他の活動エンティティを追加し、そのフィールド名を対応するフィールドにマップします:
   - 顧客活動エンティティ: Reviews:Website
   - 主キー: Website.Reviews.ReviewId
   - タイムスタンプ: Website.Reviews.ReviewDate
   - イベント (活動名): Website.Reviews.ActivityTypeDisplay
   - 詳細 (金額または値): Website.Reviews.ReviewRating

1. この活動を実行します。

## <a name="task-4---configure-the-subscription-churn-prediction"></a>タスク 4 - サブスクリプション解約予測を構成する

統合顧客プロファイルが配置され活動が作成されたら、サブスクリプション解約予測を実行できます。 詳細な手順については、[サブスクリプション離反予測](predict-subscription-churn.md) を参照してください。

1. **インテリジェンス** > **予測** に移動します。

1. **作成** タブで **顧客離反モデル** タイルの **モデルを使用** を選択します。

1. 離反のタイプに **サブスクリプション** を選択し、**開始する** を選択します。

1. モデルに **OOB サブスクリプション解約予測**、出力エンティティに **OOBSubscriptionChurnPrediction** という名前を付けます。

1. モデルの基本設定を定義します:
   - **サブスクリプションが終了してからの日数**: サブスクリプションが終了した後、この期間にサブスクリプションを更新しない場合、顧客が解約されたと見なされることを示す日数は **60** 日。
   - **チャーンを予測するために将来を調査する日数**: 解約する可能性のある顧客をモデルが予測する期間は、**93** 日。 先のことを考えれば考えるほど、結果の精度は低くなります。

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="モデル基本設定とチャーン定義を選択します。":::

1. **次へ** を選択します。

1. **必須データ** ステップで、**データの追加** を選択し、サブスクリプション履歴データを指定します。

1. **サブスクリプション** および SubscriptionHistory エンティティを選択し、**次へ** を選択します。 必要なデータはアクティビティから自動的に入力されます。 **保存** を選択します。

1. 顧客アクティビティで、**データの追加** を選択します。

1. この例では、Web レビュー アクティビティを追加します。

1. **次へ** を選択します。

1. **データ更新** 手順で、モデル スケジュールに対して **月次** を選択します。

1. すべての詳細を確認した後、**保存と実行** を選択します。

## <a name="task-5---review-model-results-and-explanations"></a>タスク 5 - モデルの結果と説明を確認する

モデルにデータのトレーニングとスコアリングを完了させます。 サブスクリプション チャーン モデルの説明をレビューします。 詳細については、[予測と結果の表示](predict-subscription-churn.md#view-prediction-results) を参照してください。

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>タスク 6 - 解約リスクの高い顧客のセグメントを作成する

モデルを実行すると、新しいエンティティが作成され、**データ** > **エンティティ** に一覧表示されます。 モデルによって作成されたエンティティに基づいて、新しいセグメントを作成できます。

1. 結果ページで **セグメントの作成** を選択します。

1. **OOBSubscriptionChurnPrediction** エンティティを使ってルールを作成して、セグメントを定義します。
   - **フィールド**: ChurnScore
   - **演算子**: より大きい
   - **値**: 0.6

1. **保存** を選択し、セグメントを **実行** します。

これで、このサブスクリプション ビジネスの解約リスクの高い顧客を識別するセグメントが動的に更新されます。 詳細については、[セグメントの作成と管理](segments.md) をご覧ください。

> [!TIP]
> **新規** を選択して、**作成元** > **インテリジェンス** を選ぶことで、**セグメント** ページから予測モデルに対してセグメントも作成できます。 詳細については、[クイック セグメントで新規セグメントを作成する](segment-quick.md) を参照してください。

[!INCLUDE [footer-include](includes/footer-banner.md)]
