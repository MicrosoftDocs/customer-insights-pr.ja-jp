---
title: Power BI コネクタ
description: Power BI で Dynamics 365 Customer Insights コネクタの使用方法を学びます。
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406154"
---
# <a name="connector-for-power-bi-preview"></a>Power BI のコネクタ (プレビュー)

Power BI Desktop を使用してデータをビジュアル化します。 統合された顧客データを使用して、追加のインサイトを生成し、レポートをビルドします。

## <a name="prerequisites"></a>前提条件

- 統合顧客プロファイルがあります。
- [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/)の最新バージョンがコンピュータにインストールされている。 [Power BI Desktop の詳細](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)

## <a name="configure-the-connector-for-power-bi"></a>Power BI のコネクタの構成

1. Power BI Desktop で、**ファイル** > **データの取得** を選択します。

1. **詳細を表示** を選択して、**Dynamics 365 Customer Insights** を検索します

1. 結果を選択して、**接続** を選択します。

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
