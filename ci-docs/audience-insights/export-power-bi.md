---
title: Power BI コネクタ
description: Power BI で Dynamics 365 Customer Insights コネクタの使用方法を学びます。
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477094"
---
# <a name="connector-for-power-bi-preview"></a>Power BI のコネクタ (プレビュー)

Power BI Desktop を使用してデータをビジュアル化します。 統合された顧客データを使用して、追加のインサイトを生成し、レポートをビルドします。

## <a name="prerequisites"></a>前提条件

- 統合顧客プロファイルがあります。
- [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/)の最新バージョンがコンピュータにインストールされている。 [Power BI Desktop の詳細](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)

## <a name="configure-the-connector-for-power-bi"></a>Power BI のコネクタの構成

1. Power BI Desktop で、**ファイル** > **データの取得** を選択します。

1. **詳細を表示** を選択して、**Dynamics 365 Customer Insights** を検索します

1. **接続** を選択します。

1. Customer Insightsに使用するのと同じ組織アカウントを使用して **サインイン** して、**接続** を選択します。
   > [!NOTE]
   > この手順で指定するアカウントは、Customer Insights からデータをフェッチするために使用され、Power BI にサインインしているものと同じである必要はありません。 データの取得に使用されるアカウントをリセットするには、Power BI を開き、**ファイル** > **オプション** > **設定** > **データ ソース設定** に移動します。 データ ソースの一覧で、**Dynamics 365 Customer Insights へのログイン** を選択し、**アクセス許可のクリア** を選択します。  

1. **検索** ダイアログ ボックス。 アクセス可能なすべての環境を一覧表示します。 環境を展開し、任意のフォルダー (エンティティ、メジャー、セグメント、エンリッチメント) を開きます。 たとえば、**エンティティ** フォルダを開き、インポートできるすべてのエンティティを表示します。

   ![Power BIコネクタ ナビゲータ](media/power-bi-navigator.png "Power BI コネクタ ナビゲーター")

1. 含めるエンティティの横にあるチェックボックスを選択して、**読み込みます**。 複数の環境から複数のエンティティを選択できます。

1. エンティティがロードされている間、ダイアログボックスが表示されます。 選択したエンティティをすべて読み込むと、Power BI の機能を使用して、データを視覚化できます。

## <a name="large-data-sets"></a>大規模なデータセット

Power BI の Customer Insights コネクタは、最大 100 万の顧客プロファイルを含むデータセットで機能するように設計されています。 大きなデータセットのインポートは出来る可能性がありますが、時間がかかります。 さらに、Power BI 制限によりプロセスがタイムアウトになる可能性があります。 詳細については、[Power BI : 大きなデータセットの推奨事項](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets)を参照してください。 

### <a name="work-with-a-subset-of-data"></a>データのサブセットを使用する

データのサブセットを使用することを検討してください。 たとえば、すべての顧客レコードを Power BI にエクスポートする代わりに、[セグメント](segments.md) を作成できます。

## <a name="troubleshooting"></a>トラブルシューティング​​

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Power BI に Customer Insights 環境はに表示されません

対象者に関するインサイトの 2 つの同一エンティティ間で定義された[リレーションシップ](relationships.md)が複数ある環境は、Power BI コネクタでは使用できません。

重複したリレーションシップは特定して削除できます。

1. Power BI にない環境の対象者インサイトで、**データ** > **リレーションシップ** に進みます。
2. 重複したリレーションシップを特定します。
   - 同じ 2 つのエンティティ間に複数のリレーションシップが定義されているかどうかを確認してください。
   - 統合プロセスに含まれる 2 つのエンティティ間に作成されたリレーションシップがあるかどうかを確認します。 統合プロセスに含まれるすべてのエンティティ間に定義された暗黙のリレーションシップがあります。
3. 識別された重複するリレーションシップをすべて削除します。

重複したリレーションシップを削除した後、Power BI コネクタに再接続してみます。 これで環境が利用可能になりました。

[!INCLUDE[footer-include](../includes/footer-banner.md)]

