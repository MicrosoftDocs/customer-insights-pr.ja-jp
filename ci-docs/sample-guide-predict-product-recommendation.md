---
title: 製品のレコメンデーション予測サンプル ガイド
description: このサンプル ガイドを使用して、既成の製品レコメンデーション予測モデルを試してください。
ms.date: 05/16/2022
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
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762692"
---
# <a name="product-recommendation-prediction-sample-guide"></a>製品のレコメンデーション予測サンプル ガイド

以下に示すサンプル データを使用して、製品レコメンデーション予測のエンドツーエンドの例について説明します。

## <a name="scenario"></a>シナリオ

Contoso は、高品質のコーヒーとコーヒー メーカーを製造し、Contoso Coffee の Web サイトで販売している会社です。 その目標は、定期的な顧客にどの製品を推奨すべきかを理解することです。 顧客が **購入する可能性が高い** ことを把握することで、特定のアイテムに焦点を当ててマーケティングの労力を軽減できます。

## <a name="prerequisites"></a>前提条件

- 少なくとも Customer Insights の[共同作成者権限](permissions.md) があること。
- [新しい環境で](manage-environments.md) 次の手順を実行することをお勧めします。

## <a name="task-1---ingest-data"></a>タスク 1 - データの取り込み

[データ インジェスト](data-sources.md)と [Power Query コネクタを使用したデータ ソースのインポート](connect-power-query.md)に関する記事を特にご確認ください。 以下の情報は、一般的なデータの取り込みに精通していることを前提としています。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>顧客データを eコマース プラットフォームから取り込む

1. **eコマース** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。

1. e コマースの連絡先の URL を入力します: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts)。

1. データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **DateOfBirth**: 日付
   - **CreatedOn**: 日付/時刻/タイムゾーン

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="生年月日を日付に変換します。":::

1. 右側のペインにある '名前' フィールドで、データ ソースの名前を **クエリ** から **eCommerceContacts** に変更します

1. データ ソースを **保存** します。

### <a name="ingest-online-purchase-data"></a>オンライン購入データを取り込む

1. 同じ **eコマース** データ ソースに別のデータ セットを追加します。 **テキスト/CSV** コネクタをもう一度選択します。

1. **オンライン購入** データ [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline) の URL を入力します。

1. データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **PurchasedOn**: 日付/時刻
   - **TotalPrice**: 通貨

1. サイド ペインの **名前** フィールドで、データ ソースの名前を **クエリ** から **eCommercePurchases** に変更します。

1. データ ソースを **保存** します。

### <a name="ingest-customer-data-from-loyalty-schema"></a>ロイヤルティ スキームから顧客データを取り込む

1. **LoyaltyScheme** という名前のデータ ソースを作成し、インポート オプションを選択して、**テキスト/CSV** コネクタを選択します。

1. e コマースの連絡先 [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty) の URL を入力します。

1. データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:
   - **DateOfBirth**: 日付
   - **RewardsPoints**: 整数
   - **CreatedOn**: 日付/時刻

1. 右側のペインにある **名前** フィールドで、データ ソースの名前を **クエリ** から **loyCustomers** に変更します。

1. データ ソースを **保存** します。

## <a name="task-2---data-unification"></a>タスク 2 - データの統合

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>タスク 3 - 製品レコメンデーション予測を構成する

統合された顧客プロファイルが整ったので、製品レコメンデーション予測を実行できます。

1. **インテリジェンス** > **予測** に移動して、**製品レコメンデーション** を選択します。

1. **開始する** を選択します。

1. モデルに **OOB 製品レコメンデーション モデル予測**、出力エンティティには **OOBProductRecommendationModelPrediction** という名前を付けます。

1. モデルの 3 つの条件を定義します。

   - **製品数**: この値を **5** に設定します。 この設定は、顧客に推奨する製品の数を定義します。

   - **期待される再購入**: **はい** を選択して、顧客が以前に購入したことのある製品をおすすめ候補に含めることを指定します。

   - **ウィンドウを見返す:** 少なくとも **365 日** を選択してください。 この設定で、レコメンデーションへの入力として顧客のアクティビティをさかのぼって振り返る期間が定義されます。

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="製品レコメンデーション モデルモデル マッピングです。":::

1. **必須データの追加** 手順で、**データを追加する** を選択します。

1. **データの追加** ウィンドウで、購入履歴エンティティとして **SalesOrderLine** を選択します。 この時点では、まだ構成されていない可能性があります。 ウィンドウでリンクを開き、次の手順で活動を作成します。
   1. **活動名** を入力し、**活動エンティティ** として *eCommercePurchases:eCommerce* を選択します。 **主キー** は *PurchaseId* です。
   1. *eCommerceContacts:eCommerce entity* との関係を定義して名前を付け、外部キーとして **ContactId** を選択します。
   1. 活動を統合するには、**イベント活動** を *TotalPrice* 設定し、タイムスタンプを *PurchasedOn* に設定します。 [顧客活動](activities.md) で概説されているように、より多くのフィールドを指定できます。
   1. **活動の種類** の場合は、*SalesOrderLine* を選択します。 次の活動フィールドをマップします:
      - 受注明細行 ID: PurchaseId
      - 受注 ID: PurchaseId
      - 受注データ: PurchasedOn
      - 製品 ID: ProductId
      - 金額: TotalPrice
   1. モデル構成に戻る前に、活動を確認して終了してください。

1. **活動を選択** 手順に戻り、**活動** セクションで新しく作成された活動を選択します。 **次** を選択すると、属性マッピングはすでに入力されています。**保存** を選択します。

1. このサンプル ガイドでは、製品情報データがないため、**製品情報の追加** および **製品フィルター** の設定をスキップします。

1. **データ更新** 手順で、モデル スケジュールを設定します。

   新しいデータが取り込まれた場合、モデルは新しいパターンを学習するために定期的にトレーニングする必要があります。 この例では、**月** を選択します。

1. すべての詳細を確認した後、**保存と実行** を選択します。 モデルを初めて実行するには、数分かかります。

## <a name="task-4---review-model-results-and-explanations"></a>タスク 4 - モデルの結果と説明を確認する

モデルにデータのトレーニングとスコアリングを完了させます。 これで、製品レコメンデーション モデルの説明を確認できるようになりました。 詳細については、[予測の状態と結果の確認](predict-transactional-churn.md#review-a-prediction-status-and-results) を参照してください。

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>タスク 5 - 購入数の多い製品のセグメントを作成する

運用モデルを実行すると、**データ** > **エンティティ** に表示される新しいエンティティが作成されます。

モデルによって作成されたエンティティに基づいて、新しいセグメントを作成できます。

1. **セグメント** に移動します。 **新規** を選択し、**インテリジェンスから作成** を選択します。

   ![モデル出力を使用してセグメントを作成しています。](media/segment-intelligence.png)

1. **OOBProductRecommendationModelPrediction** エンドポイントを選択して、セグメントを定義します。

   - フィールド: ProductID
   - 値: 上位 3 つの製品 ID を選択する

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="モデルの結果からセグメントを作成します。":::

これで、動的に更新されるセグメントができました。これは、最も推奨される 3 つの製品の購入に関心がある可能性のある顧客を識別します。

詳細については、[セグメントの作成と管理](segments.md) をご覧ください。

[!INCLUDE [footer-include](includes/footer-banner.md)]
