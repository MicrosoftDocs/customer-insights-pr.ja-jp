---
title: 製品のレコメンデーション予測サンプル ガイド
description: このサンプル ガイドを使用して、既成の製品レコメンデーション予測モデルを試してください。
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b219935dfbd9f7acc1104d83e2ca281801a1a4251ae4c19fc03d4b1ce46f4613
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035191"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>製品のレコメンデーション予測 (プレビュー) サンプル ガイド

以下に示すサンプル データを使用して、製品レコメンデーション予測のエンドツーエンドの例について説明します。

## <a name="scenario"></a>シナリオ

Contoso は、高品質のコーヒーとコーヒー メーカーを製造している会社で、Contoso Coffee の Web サイトで販売しています。 その目標は、定期的な顧客にどの製品を推奨すべきかを理解することです。 顧客が **購入する可能性が高い** ことを把握することで、特定のアイテムに焦点を当ててマーケティングの労力を軽減できます。

## <a name="prerequisites"></a>前提条件

- 少なくとも Customer Insights の[共同作成者権限](permissions.md) があること。
- [新しい環境で](manage-environments.md) 次の手順を実行することをお勧めします。

## <a name="task-1---ingest-data"></a>タスク 1 - データの取り込み

特に [データの取り込み](data-sources.md) と [Power Query コネクタを使用したデータ ソースのインポート](connect-power-query.md) についての記事を確認します。 以下の情報は、一般的なデータの取り込みに精通していることを前提としています。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>顧客データを eコマース プラットフォームから取り込む

1. **eコマース** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。

1. eコマースの連絡先の URL https://aka.ms/ciadclasscontacts を入力します。

1. データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **DateOfBirth**: 日付
   - **CreatedOn**: 日付/時刻/タイムゾーン

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="生年月日を日付に変換します。":::

5. 右側のペインにある '名前' フィールドで、データ ソースの名前を **クエリ** から **eCommerceContacts** に変更します

6. データ ソースを **保存** します。

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

## <a name="task-2---data-unification"></a>タスク 2 - データの統合

データを取り込んだ後、データ統合プロセスを開始して、統合された顧客プロファイルを作成します。 詳細については、[データの統合](data-unification.md) を参照してください。

### <a name="map"></a>マップ

1. データを取り込んだ後、連絡先を eコマースおよびロイヤルティ データから共通のデータ型にマップします。 **データ** > **統合** > **マップ** に移動します。

2. 顧客プロファイルを表すエンティティ - **eCommerceContacts** および **loyCustomers** を選択します。

   ![eコマースとロイヤルティ データソースを統合します。](media/unify-ecommerce-loyalty.png)

3. **eCommerceContacts** の主キーとして **ContactId**、**loyCustomers** の主キーとして **LoyaltyID** を選択します。

   ![LoyaltyId を主キーとして統合します。](media/unify-loyaltyid.png)

### <a name="match"></a>照合

1. **照合** タブに移動して、**順序の設定** を選択します。

2. **プライマリ** ドロップダウン リストで、**eCommerceContacts : eCommerce** をプライマリ ソースとして選択してから、すべてのレコードを含めます。

3. **エンティティ 2** ドロップダウン リストで、**loyCustomers : LoyaltyScheme** を選択してから、すべてのレコードを含めます。

   ![eコマースとロイヤルティの一致を統合します。](media/unify-match-order.png)

4. **新しいルールの作成** を選択します

5. FullName を使用して最初の条件を追加します。

   - eCommerceContacts では、ドロップダウンで **FullName** を選択します。
   - loyCustomers では、ドロップダウンで **FullName** を選択します。
   - **正規化** ドロップダウンを選択して、**種類 (電話、名前、住所、...)** を選択します。
   - **精度レベル** の設定: **基本** と **値**: **高い**。

6. 新しいルールに **FullName, Email** という名前を入力します。

   - **条件の追加** を選択し、メール アドレスの 2 番目の条件を追加します
   - エンティティ eCommerceContacts では、ドロップダウンで **メール** を選択します。
   - エンティティ loyCustomers では、ドロップダウンで **メール** を選択します。
   - 正規化を空白のままにします。
   - **精度レベル** の設定: **基本** と **値**: **高い**。

   ![名前とメールの照合ルールを統一します。](media/unify-match-rule.png)

7. **保存** と **実行** を選択します。

### <a name="merge"></a>マージ

1. **マージ** タブに移動します。

1. **loyCustomers** エンティティの **ContactId** で、表示名を **ContactIdLOYALTY** に変更して、取り込まれた別の ID とは区別されるようにします。

   ![ロイヤルティ ID から contactid に名前を変更します。](media/unify-merge-contactid.png)

1. **保存** と **実行** を選択し、マージ プロセスを開始します。

## <a name="task-3---configure-product-recommendation-prediction"></a>タスク 3 - 製品レコメンデーション予測を構成する

統合顧客プロファイルが整ったら、サブスクリプション解約予測を実行できます。

1. **インテリジェンス** > **予測** に移動して、**製品レコメンデーション** を選択します。

1. **開始する** を選択します。

1. モデルに **OOB 製品レコメンデーション モデル予測**、出力エンティティには **OOBProductRecommendationModelPrediction** という名前を付けます。

1. モデルの 3 つの条件を定義します。

   - **製品数**: この値を **5** に設定します。 この設定は、顧客に推奨する製品の数を定義します。

   - **期待される再購入**: **はい** を選択して、顧客が以前に購入したことのある製品をおすすめ候補に含めることを指定します。

   - **ウィンドウを見返す:** 少なくとも **365 日** を選択してください。 この設定で、レコメンデーションへの入力として顧客のアクティビティをさかのぼって振り返る期間が定義されます。
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="製品レコメンデーション モデルモデル マッピングです。":::

1. **必要なデータ** を選択し、購入履歴に対して **データの追加** を選択します。

1. **eCommercePurchases : eCommerce** エンティティを追加し、eコマースのフィールドをモデルに必要な対応するフィールドにマップします。

1. **eCommercePurchases : eCommerce** エンティティを **eCommerceContacts : eCommerce** と結合します。

   ![eコマース エンティティを結合します。](media/model-purchase-join.png)

1. **次へ** を選択し、モデル スケジュールを設定します。

   新しいデータが取り込まれた場合、モデルは新しいパターンを学習するために定期的にトレーニングする必要があります。 この例では、**月** を選択します。

1. すべての詳細を確認した後、**保存と実行** を選択します。


## <a name="task-4---review-model-results-and-explanations"></a>タスク 4 - モデルの結果と説明を確認する

モデルにデータのトレーニングとスコアリングを完了させます。 これで、製品レコメンデーション モデルの説明を確認できるようになりました。 詳細については、[予測の状態と結果の確認](predict-subscription-churn.md#review-a-prediction-status-and-results) を参照してください。

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>タスク 5 - 購入数の多い製品のセグメントを作成する

運用モデルを実行すると、**データ** > **エンティティ** に表示される新しいエンティティが作成されます。

モデルによって作成されたエンティティに基づいて、新しいセグメントを作成できます。

1. **セグメント** に移動します。 **新規** を選択し、**作成元** > **インテリジェンス** と選択します。

   ![モデル出力を使用してセグメントを作成しています。](media/segment-intelligence.png)

1. **OOBProductRecommendationModelPrediction** エンドポイントを選択して、セグメントを定義します。

   - フィールド: ProductID
   - 演算子: 値
   - 値: 上位 3 つの製品 ID を選択する

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="モデルの結果からセグメントを作成します。":::

これで、最も推奨される 3 つの製品を購入する意欲のある顧客を識別する、動的に更新されるセグメントができました 

詳細については、[セグメントの作成と管理](segments.md) をご覧ください。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
