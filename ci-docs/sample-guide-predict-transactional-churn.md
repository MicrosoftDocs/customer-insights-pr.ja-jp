---
title: トランザクション解約予測サンプル ガイド
description: このサンプル ガイドを使用して、既成のトランザクション解約予測モデルを試してください。
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609690"
---
# <a name="transactional-churn-prediction-sample-guide"></a>トランザクション解約予測サンプル ガイド

このガイドは、サンプル データを使用して、トランザクション チャーン予測のエンドツーエンドの例について説明します。 [新しい環境で](manage-environments.md) この予測を実行することをお勧めします。

## <a name="scenario"></a>シナリオ

Contoso は、高品質のコーヒーとコーヒー マシンを製造する会社です。 Contoso Coffee の Web サイトで製品を販売しています。 彼らの目標は、製品を通常定期的に購入している顧客のうち、どの顧客が今後 60 日以内にアクティブな顧客でなくなるかを把握することです。 どの顧客が **解約する可能性がある** かを把握することは、顧客をつなぎ止めることに集中することで、マーケティング活動を軽減するのに役立ちます。

## <a name="prerequisites"></a>前提条件

- 少なくとも [共同作成者のアクセス許可](permissions.md)。

## <a name="task-1---ingest-data"></a>タスク 1 - データの取り込み

[データ インジェスト](data-sources.md) と [Power Query データ ソースへの接続](connect-power-query.md) に関する記事をご確認ください。 以下の情報は、一般的なデータの取り込みに精通していることを前提としています。

### <a name="ingest-customer-data-from-ecommerce-platform"></a>顧客データを eコマース プラットフォームから取り込む

1. **eCommerce** という名前のデータ ソースを作成し、**テキスト/CSV** コネクタを選択します。

1. eコマースの連絡先の URL https://aka.ms/ciadclasscontacts を入力します。

1. データの編集中に、**変換** を選択して、その後 **1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:

   - **DateOfBirth**: 日付
   - **CreatedOn**: 日付/時刻/タイムゾーン

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="生年月日を日付に変換。":::

1. 右側のペインにある **名前** フィールドで、データ ソースの名前を **eCommerceContacts** に変更します

1. データ ソースを保存します。

### <a name="ingest-online-purchase-data"></a>オンライン購入データを取り込む

1. 同じ **eコマース** データ ソースに別のデータ セットを追加します。 **テキスト/CSV** コネクタをもう一度選択します。

1. オンライン購入データ https://aka.ms/ciadclassonline の URL を入力します。

1. データの編集中に、**変換** を選択して、その後 **1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:

   - **PurchasedOn**: 日付/時刻
   - **TotalPrice**: 通貨

1. 右側のペインにある **名前** フィールドで、データ ソースの名前を クエリ から **eCommercePurchases** に変更します。

1. データ ソースを保存します。

### <a name="ingest-customer-data-from-loyalty-schema"></a>ロイヤルティ スキームから顧客データを取り込む

1. **LoyaltyScheme** という名前のデータ ソースを作成し、**テキスト/CSV** コネクタを選択します。

1. eコマースの連絡先の URL https://aka.ms/ciadclasscustomerloyalty を入力します。

1. データの編集中に、**変換** を選択して、その後 **1 行目をヘッダーとして使用** の順に選択します。

1. 以下にリストされている列のデータ型を更新します:

   - **DateOfBirth**: 日付
   - **RewardsPoints**: 整数
   - **CreatedOn**: 日付/時刻

1. 右側のペインにある **名前** フィールドで、データ ソースの名前を クエリ から **loyCustomers** に変更します。

1. データ ソースを保存します。

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

## <a name="task-4---configure-transaction-churn-prediction"></a>タスク 4 - トランザクション解約予測を構成する

統合された顧客プロファイルと活動が整ったので、トランザクション離反予測を実行できます。

1. **インテリジェンス** > **予測** に移動します。

1. **作成** タブで **顧客離反モデル** の **モデルを使用** を選択します。

1. 離反のタイプに **トランザクション** を選択し、**開始する** を選択します。

1. モデルに **OOB eコマース トランザクション解約予測**、出力エンティティに **OOBeCommerceChurnPrediction** という名前を付けます。

1. **次へ** を選択します。

1. モデルの基本設定を定義します:

   - **予測ウィンドウ**: 顧客チャーンをどの程度先まで予測するかを定義するには、**60** 日。

   - **チャーン定義**: 顧客が解約されたと見なされるまでの購入なしの期間を示す **60** 日。

     :::image type="content" source="media/model-levers.PNG" alt-text="モデル基本設定の予測ウィンドウと解約定義を選択します。":::

1. **次へ** を選択します。

1. **購入履歴 (必須)** を選択し、購入履歴に対して **データの追加** を選択します。

1. **SalesOrderLine** と eCommercePurchases エンティティを選択して、**次へ** を選択します。 必要なデータはアクティビティから自動的に入力されます。 **保存**、**次へ** の順に選択します。

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="eコマース エンティティを結合します。":::

1. **追加データ (オプション)** ステップをスキップします。

1. **データ更新** 手順で、モデル スケジュールに対して **月次** を選択します。

1. すべての詳細を確認した後、**保存と実行** を選択します。

## <a name="task-5---review-model-results-and-explanations"></a>タスク 5 - モデルの結果と説明を確認する

モデルにデータのトレーニングとスコアリングを完了させます。 チャーン モデルの説明をレビューします。 詳細については、[予測と結果の表示](predict-transactional-churn.md#view-prediction-results) を参照してください。

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>タスク 6 - 解約リスクの高い顧客のセグメントを作成する

製造モデルを実行すると、新しいエンティティが作成され、**データ** > **エンティティ** に一覧表示されます。 モデルによって作成されたエンティティに基づいて、新しいセグメントを作成できます。

1. 結果ページで **セグメントの作成** を選択します。

1. **OOBeCommerceChurnPrediction** エンティティを使ってルールを作成して、セグメントを定義します。
   - **フィールド**: ChurnScore
   - **演算子**: より大きい
   - **値**: 0.6

1. **保存** を選択し、セグメントを **実行** します。

これで、離反リスクの高い顧客を識別する動的に更新されるセグメントができました。 詳細については、[セグメントの作成と管理](segments.md) をご覧ください。

> [!TIP]
> **新規** を選択して、**作成元** > **インテリジェンス** を選ぶことで、**セグメント** ページから予測モデルに対してセグメントも作成できます。 詳細については、[クイック セグメントで新規セグメントを作成する](segment-quick.md) を参照してください。

[!INCLUDE [footer-include](includes/footer-banner.md)]
