---
title: Power BI コネクタ
description: Power BI で Dynamics 365 Customer Insights コネクタの使用方法を学びます。
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e901114703a43b4b4e751e0a93eb4876d7636c00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647155"
---
# <a name="connector-for-power-bi-preview"></a>Power BI のコネクタ (プレビュー)

Power BI Desktop を使用してデータをビジュアル化します。 統合された顧客データを使用して、追加のインサイトを生成し、レポートをビルドします。

## <a name="prerequisites"></a>前提条件

- 統合顧客プロファイルがあります。
- 最新バージョンの [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) がコンピュータにインストールされます。 [Power BI Desktop の詳細](/power-bi/desktop-what-is-desktop)

## <a name="configure-the-connector-for-power-bi"></a>Power BI のコネクタの構成

1. Power BI Desktop で、**ファイル** > **データの取得** を選択します。

1. **詳細を表示** を選択して、**Dynamics 365 Customer Insights** を検索します

1. **接続** を選択します。

1. Customer Insightsに使用するのと同じ組織アカウントを使用して **サインイン** して、**接続** を選択します。
   > [!NOTE]
   > この手順で指定するアカウントは、Customer Insights からデータをフェッチするために使用され、Power BI にサインインしているものと同じである必要はありません。 データの取得に使用されるアカウントをリセットするには、Power BI を開き、**ファイル** > **オプション** > **設定** > **データ ソース設定** に移動します。 データ ソースの一覧で、**Dynamics 365 Customer Insights へのログイン** を選択し、**アクセス許可のクリア** を選択します。  

1. **検索** ダイアログ ボックス。 アクセス可能なすべての環境を一覧表示します。 環境を展開し、任意のフォルダー (エンティティ、メジャー、セグメント、エンリッチメント) を開きます。 たとえば、**エンティティ** フォルダを開き、インポートできるすべてのエンティティを表示します。

   ![Power BIコネクタ ナビゲータ。](media/power-bi-navigator.png "Power BI コネクタ ナビゲーター")

1. 含めるエンティティの横にあるチェックボックスを選択して、**読み込みます**。 複数の環境から複数のエンティティを選択できます。

1. エンティティがロードされている間、ダイアログボックスが表示されます。 選択したエンティティをすべて読み込むと、Power BI の機能を使用して、データを視覚化できます。

## <a name="large-data-sets"></a>大規模なデータセット

Power BI の Customer Insights コネクタは、最大 100 万の顧客プロファイルを含むデータセットで機能するように設計されています。 大きなデータセットのインポートは出来る可能性がありますが、時間がかかります。 さらに、Power BI 制限によりプロセスがタイムアウトになる可能性があります。 詳細については、[Power BI : 大きなデータセットの推奨事項](/power-bi/admin/service-premium-what-is#large-datasets)を参照してください。 

### <a name="work-with-a-subset-of-data"></a>データのサブセットを使用する

データのサブセットを使用することを検討してください。 たとえば、すべての顧客レコードを Power BI にエクスポートする代わりに、[セグメント](segments.md) を作成できます。

## <a name="troubleshooting"></a>トラブルシューティング​​

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Power BI に Customer Insights 環境はに表示されません

Customer Insights で 2 つの同一のエンティティ間で定義された複数の [リレーションシップ](relationships.md) をもつ環境は、Power BI コネクタでは使用できません。

重複したリレーションシップは特定して削除できます。

1. Power BI で欠損している環境上で **データ** > **リレーションシップ** に移動します。
2. 重複したリレーションシップを特定します。
   - 同じ 2 つのエンティティ間に複数のリレーションシップが定義されているかどうかを確認してください。
   - 統合プロセスに含まれる 2 つのエンティティ間に作成されたリレーションシップがあるかどうかを確認します。 統合プロセスに含まれるすべてのエンティティ間に定義された暗黙のリレーションシップがあります。
3. 識別された重複するリレーションシップをすべて削除します。

重複したリレーションシップを削除した後、Power BI コネクタに再接続してみます。 これで環境が利用可能になりました。

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Power BI Desktop にエンティティを読み込む際の日付フィールドのエラー

MM / DD / YYYY のような日付形式のフィールドを含むエンティティを読み込むと、ロケール形式の不一致が原因でエラーが発生する可能性があります。 この不一致は、Customer Insights の日付フィールドは米国形式で保存されるため、Power BI Desktop ファイルは英語 (米国) 以外のロケールに設定されます。

Power BI Desktop ファイルには単一のロケール設定があり、データを取得するときに適用されます。 これらの日付フィールドを正しく解釈するには、.BPI ファイルのロケールを英語 (米国) に設定します。 [Power BI Desktop のロケールを変更する方法について説明します](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
