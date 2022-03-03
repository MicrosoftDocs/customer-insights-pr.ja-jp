---
title: サブスクリプション解約予測サンプル ガイド
description: このサンプル ガイドを使用して、既成のサブスクリプション解約予測モデルを試してください。
ms.date: 11/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5de57155b47b74efa4c5ef2fe63a3c87505644be
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355619"
---
# <a name="subscription-churn-prediction-sample-guide"></a>サブスクリプション解約予測サンプル ガイド

以下に示すサンプル データを使用して、サブスクリプション解約予測のエンドツーエンドの例について説明します。 

## <a name="scenario"></a>シナリオ

Contoso は、高品質のコーヒーとコーヒー メーカーを製造し、Contoso Coffee の Web サイトで販売している会社です。 彼らは最近、定期的にコーヒーを飲む顧客のためにサブスクリプション ビジネスを始めた。 彼らの目標は、どの加入した顧客が今後数か月以内にサブスクリプションをキャンセルする可能性があるかを把握することです。 どの顧客が **解約する可能性がある** かを把握することは、顧客をつなぎ止めることに集中することで、マーケティング活動を軽減するのに役立ちます。

## <a name="prerequisites"></a>前提条件

- 少なくとも Customer Insights の[共同作成者権限](permissions.md) があること。
- [新しい環境で](manage-environments.md) 次の手順を実行することをお勧めします。

## <a name="task-1---ingest-data"></a>タスク 1 - データの取り込み

[データ インジェスト](data-sources.md)と [Power Query コネクタを使用したデータ ソースのインポート](connect-power-query.md)に関する記事を特にご確認ください。 以下の情報は、一般的なデータの取り込みに精通していることを前提としています。 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>顧客データを eコマース プラットフォームから取り込む

1. **eコマース** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。

1. eコマースの連絡先の URL https://aka.ms/ciadclasscontacts を入力します。

1. データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:

   - **DateOfBirth**: 日付
   - **CreatedOn**: 日付/時刻/タイムゾーン

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="生年月日を日付に変換します。":::

1. 右側のペインにある **名前** フィールドで、データ ソースの名前を **クエリ** から **eCommerceContacts** に変更します

1. データ ソースを保存します。

### <a name="ingest-customer-data-from-loyalty-schema"></a>ロイヤルティ スキームから顧客データを取り込む

1. **LoyaltyScheme** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。

1. eコマースの連絡先の URL https://aka.ms/ciadclasscustomerloyalty を入力します。

1. データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:

   - **DateOfBirth**: 日付
   - **RewardsPoints**: 整数
   - **CreatedOn**: 日付/時刻

1. 右側のペインにある **名前** フィールドで、データ ソースの名前を **クエリ** から **loyCustomers** に変更します。

1. データ ソースを保存します。

### <a name="ingest-subscription-information"></a>サブスクリプション情報の取り込み

1. **SubscriptionHistory** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。

1. eコマースの連絡先の URL https://aka.ms/ciadchurnsubscriptionhistory を入力します。

1. データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:

   - **SubscriptioID**: 整数
   - **SubscriptionAmount**: 通貨
   - **SubscriptionEndDate**: 日付/時刻
   - **SubscriptionStartDate**: 日付/時刻
   - **TransactionDate**: 日付/時刻
   - **IsRecurring**: True/False
   - **Is_auto_renew**: True/False
   - **RecurringFrequencyInMonths**: 整数

1. 右側のペインにある **名前** フィールドで、データ ソースの名前を **クエリ** から **SubscriptionHistory** に変更します。

1. データ ソースを保存します。

### <a name="ingest-customer-data-from-website-reviews"></a>Web サイトのレビューから顧客データを取り込む

1. **Web サイト** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。

1. eコマースの連絡先の URL https://aka.ms/ciadclasswebsite を入力します。

1. データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:

   - **ReviewRating**: 整数
   - **ReviewDate**: 日付

1. 右側のペインにある '名前' フィールドで、データ ソースの名前を **クエリ** から **webReviews** に変更します。

## <a name="task-2---data-unification"></a>タスク 2 - データの統合

データを取り込んだ後、**マップ、照合、マージ** のプロセスを開始して、統一顧客プロファイルを作成します。 詳細については、[データの統合](data-unification.md) を参照してください。

### <a name="map"></a>マップ

1. データを取り込んだ後、連絡先を eコマースおよびロイヤルティ データから共通のデータ型にマップします。 **データ** > **統合** > **マップ** に移動します。

1. 顧客プロファイルを表すエンティティ - **eCommerceContacts** および **loyCustomers** を選択します。 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="eコマースとロイヤルティ データソースを統合します。":::

1. **eCommerceContacts** の主キーとして **ContactId**、**loyCustomers** の主キーとして **LoyaltyID** を選択します。

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="LoyaltyId を主キーとして統合します。":::

### <a name="match"></a>照合

1. **照合** タブに移動して、**順序の設定** を選択します。

1. **プライマリ** ドロップダウン リストで、**eCommerceContacts : eCommerce** をプライマリ ソースとして選択してから、すべてのレコードを含めます。

1. **エンティティ 2** ドロップダウン リストで、**loyCustomers : LoyaltyScheme** を選択してから、すべてのレコードを含めます。

   :::image type="content" source="media/unify-match-order.PNG" alt-text="eコマースとロイヤルティの一致を統合します。":::

1. **新しいルールの作成** を選択します

1. FullName を使用して最初の条件を追加します。

   * eCommerceContacts では、ドロップダウンで **FullName** を選択します。
   * loyCustomers では、ドロップダウンで **FullName** を選択します。
   * **正規化** ドロップダウンを選択して、**種類 (電話、名前、住所、...)** を選択します。
   * **精度レベル** の設定: **基本** と **値**: **高い**。

1. 新しいルールに **FullName, Email** という名前を入力します。

   * **条件の追加** を選択し、メール アドレスの 2 番目の条件を追加します
   * エンティティ eCommerceContacts では、ドロップダウンで **メール** を選択します。
   * エンティティ loyCustomers では、ドロップダウンで **メール** を選択します。 
   * 正規化を空白のままにします。 
   * **精度レベル** の設定: **基本** と **値**: **高い**。

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="名前とメールの照合ルールを統一します。":::

7. **保存** と **実行** を選択します。

### <a name="merge"></a>マージ

1. **マージ** タブに移動します。

1. **loyCustomers** エンティティの **ContactId** で、表示名を **ContactIdLOYALTY** に変更して、取り込まれた別の ID とは区別されるようにします。

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="ロイヤルティ ID から contactid に名前を変更します。":::

1. **保存** と **実行** を選択し、マージ プロセスを開始します。


## <a name="task-3---configure-the-subscription-churn-prediction"></a>タスク 3 - サブスクリプション解約予測を構成する

統合顧客プロファイルが整ったら、サブスクリプション解約予測を実行できます。 詳細な手順については、[サブスクリプション離反予測](predict-subscription-churn.md)記事を参照してください。 

1. **インテリジェンス** > **検出** に移動し、**顧客離反モデル** の使用を選択します。

1. **サブスクリプション** オプションを選択し、**開始する** を選択します。

1. モデルに **OOB サブスクリプション解約予測**、出力エンティティに **OOBSubscriptionChurnPrediction** という名前を付けます。

1. 離反モデルの 2 つの条件を定義します:

   * **サブスクリプションが終了してからの日数**: **少なくとも 60** 日。 サブスクリプション終了後、顧客がこの期間に更新しなかった場合は、解約されたとみなされます。 

   * **解約定義**: **少なくとも 93** 日。 モデルが解約する可能性のある顧客を予測する期間。 先のことを考えれば考えるほど、結果の精度は低くなります。

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="モデル レバーの予測ウィンドウと解約定義を選択します。":::

1. **必要なデータの追加** を選択し、サブスクリプション履歴の **データの追加** を選択します。

1. **Subscription : SubscriptionHistory** エンティティを追加し、eコマースのフィールドをモデルに必要な対応するフィールドにマップします。

1. **Subscription : SubscriptionHistory** エンティテと **eCommerceContacts : eCommerce** を結合し、関連付けに **eCommerceSubscription** という名前を付けます。

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="eコマース エンティティを結合します。":::

1. 顧客アクティビティで、**webReviews : Website** エンティティを追加し、webReviews のフィールドをモデルに必要な対応するフィールドにマップします。 
   - 主キー: ReviewId
   - タイムスタンプ: ReviewDate
   - イベント: ReviewRating

1. Web サイトレ ビューのアクティビティを構成します。 アクティビティ **レビュー** を選択し、**webReviews : Website** エンティティを **eCommerceContacts : eCommerce** と結合します。

1. **次へ** を選択し、モデル スケジュールを設定します。

   新しいデータが取り込まれた場合、モデルは新しいパターンを学習するために定期的にトレーニングする必要があります。 この例では、**月** を選択します。

1. すべての詳細を確認した後、**保存と実行** を選択します。

## <a name="task-4---review-model-results-and-explanations"></a>タスク 4 - モデルの結果と説明を確認する

モデルにデータのトレーニングとスコアリングを完了させます。 これで、サブスクリプション解約モデルの説明を確認できるようになりました。 詳細については、[予測の状態と結果の確認](predict-subscription-churn.md#review-a-prediction-status-and-results) を参照してください。

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>タスク5 - 解約リスクの高い顧客のセグメントを作成する

運用モデルを実行すると、**データ** > **エンティティ** に表示される新しいエンティティが作成されます。   

モデルによって作成されたエンティティに基づいて、新しいセグメントを作成できます。

1.  **セグメント** に移動します。 **新規** を選択し、**作成元** > **インテリジェンス** と選択します。 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="モデル出力を使用してセグメントを作成しています。":::

1. **OOBSubscriptionChurnPrediction** エンドポイントを選択して、セグメントを定義します: 
   - フィールド: ChurnScore
   - 演算子: より大きい
   - 値: 0.6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="サブスクリプション解約セグメントを設定します。":::

これで、このサブスクリプション ビジネスの解約リスクの高い顧客を識別するセグメントが動的に更新されます。

詳細については、[セグメントの作成と管理](segments.md) をご覧ください。


[!INCLUDE[footer-include](../includes/footer-banner.md)]