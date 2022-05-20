---
title: トランザクション解約予測サンプル ガイド
description: このサンプル ガイドを使用して、既成のトランザクション解約予測モデルを試してください。
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741325"
---
# <a name="transactional-churn-prediction-sample-guide"></a>トランザクション解約予測サンプル ガイド

このガイドでは、以下のデータを使用して、Customer Insights でのトランザクション解約予測のエンドツーエンドの例について説明します。 このガイドで使用されているすべてのデータは、実際の顧客データではなく、Customer Insights サブスクリプション内の *デモ* 環境にある Contoso データセットの一部です。

## <a name="scenario"></a>シナリオ

Contoso は、高品質のコーヒーとコーヒー メーカーを製造し、Contoso Coffee の Web サイトで販売している会社です。 彼らの目標は、製品を通常定期的に購入している顧客のうち、どの顧客が今後 60 日以内にアクティブな顧客でなくなるかを把握することです。 どの顧客が **解約する可能性がある** かを把握することは、顧客をつなぎ止めることに集中することで、マーケティング活動を軽減するのに役立ちます。

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="生年月日を日付に変換。":::

1. 右側のペインにある **名前** フィールドで、データ ソースの名前を **クエリ** から **eCommerceContacts** に変更します

1. データ ソースを保存します。

### <a name="ingest-online-purchase-data"></a>オンライン購入データを取り込む

1. 同じ **eコマース** データ ソースに別のデータ セットを追加します。 **テキスト/CSV** コネクタをもう一度選択します。

1. **オンライン購入** データ の URL https://aka.ms/ciadclassonline を入力します。

1. データの編集中に、**変換**、**1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:

   - **PurchasedOn**: 日付/時刻
   - **TotalPrice**: 通貨
   
1. 右側のペインにある **名前** フィールドで、データ ソースの名前を **クエリ** から **eCommercePurchases** に変更します。

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

## <a name="task-2---data-unification"></a>タスク 2 - データの統合

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>タスク 3 - トランザクション解約予測を構成する

統合された顧客プロファイルが整ったので、トランザクション離反予測を実行できます。 詳細な手順については、[トランザクション離反予測](predict-transactional-churn.md) 記事を参照してください。 

1. **インテリジェンス** > **検出** に移動し、**顧客離反モデル** の使用を選択します。

1. **トランザクション** オプションを選択し、**開始する** を選択します。

1. モデルに **OOB eコマース トランザクション解約予測**、出力エンティティに **OOBeCommerceChurnPrediction** という名前を付けます。

1. 離反モデルの 2 つの条件を定義します:

   * **予測ウィンドウ**: **少なくとも 60** 日。 この設定では、顧客離れをどの程度先まで予測するかを定義します。

   * **解約定義**: **少なくとも 60** 日。 顧客が解約されたと見なされるまでの購入なしの期間。

     :::image type="content" source="media/model-levers.PNG" alt-text="モデル レバーの予測ウィンドウと解約定義を選択します。":::

1. **購入履歴 (必須)** を選択し、購入履歴に対して **データの追加** を選択します。

1. **eCommercePurchases : eCommerce** エンティティを追加し、eコマースのフィールドをモデルに必要な対応するフィールドにマップします。

1. **eCommercePurchases : eCommerce** エンティティを **eCommerceContacts : eCommerce** と結合します。

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="eコマース エンティティを結合します。":::

1. **次へ** を選択し、モデル スケジュールを設定します。

   新しいデータが取り込まれた場合、モデルは新しいパターンを学習するために定期的にトレーニングする必要があります。 この例では、**月** を選択します。

1. すべての詳細を確認した後、**保存と実行** を選択します。

## <a name="task-4---review-model-results-and-explanations"></a>タスク 4 - モデルの結果と説明を確認する

モデルにデータのトレーニングとスコアリングを完了させます。 これで、離反モデルの説明を確認できます。 詳細については、[予測の状態と結果の確認](predict-transactional-churn.md#review-a-prediction-status-and-results) を参照してください。

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>タスク5 - 解約リスクの高い顧客のセグメントを作成する

運用モデルを実行すると、**データ** > **エンティティ** に表示される新しいエンティティが作成されます。   

モデルによって作成されたエンティティに基づいて、新しいセグメントを作成できます。

1.  **セグメント** に移動します。 **新規** を選択し、**作成元** > **インテリジェンス** と選択します。 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="モデル出力を使用してセグメントを作成しています。":::

1. **OOBeCommerceChurnPrediction** エンドポイントを選択し、セグメントを定義します。 
   - フィールド: ChurnScore
   - 演算子: より大きい
   - 値: 0.6

これで、離反リスクの高い顧客を識別する動的に更新されるセグメントができました。

詳細については、[セグメントの作成と管理](segments.md) をご覧ください。


[!INCLUDE [footer-include](includes/footer-banner.md)]
