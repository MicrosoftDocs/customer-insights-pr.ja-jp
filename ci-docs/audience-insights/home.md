---
title: 対象者に関するインサイトのホーム ページ
description: ホーム ページでアプリの詳細を確認します。
ms.date: 01/07/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7cc767f5d80b213a4c1bb5b2e8062bd44c15279b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477047"
---
# <a name="create-a-new-environment"></a>新しい環境の作成

## <a name="create-a-trial-environment"></a>試用版環境の作成

[試用版サインアップ ページ](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights) で試用版にサインアップできます。 

> [!NOTE]
> 試用期間は 30 日後に終了します。

1. **無料試用版へのサインアップ** オプションを選択し、**今すぐサインアップ** を選択します。

1. 職場または学校のメール アドレスを入力し、ご自身の詳細を入力して、**次へ** を選択します。

   :::image type="content" source="media/trial-signup-dialog.png" alt-text=" 無料の試用版にサインアップするためのダイアログ":::

1. 新しい環境の **名前** を入力します。 

1. 試用版の種類を選択します。

1. 環境に応じた **リージョン** を選択します。

1. オプションで、Dynamics 365 組織の管理者の場合: **詳細設定** を選択し、顧客離反などの予測機能を使用する組織の URL を指定します。

1. **作成** を選びます。 

環境が作成されると、架空のデータを使用してアプリを確認できる **デモ** 環境が表示されます。 業種に合わせてサンプル データを変更できます。 ヘッダーで、**設定** アイコンを選択し、**デモの設定** を選択します。 さらに、視覚的なテーマを変更できます。 

サインアップ プロセス中に作成した [環境に切り替え](#switch-environments) て、独自のデータを使用します。

## <a name="create-a-new-production-or-sandbox-environment"></a>新しい運用環境またはサンドボックス環境の作成

ご使用の環境で、アプリヘッダーの **環境** ピッカーを選択し、**新規** を選択します。

[試用版環境を作成](#create-a-trial-environment) する場合と同様に、手順を実行します。 既定では、データは Customer Insights の管理された Data Lake に保存されます。 **詳細設定** を選択して独自の Azure Data Lake にデータを保存すると、追加オプションが表示されます。 アカウント名とアカウント キーを入力して、Azure Data Lake への接続を確立します。 

> [!IMPORTANT]
> Azure Data Lake Storage にデータを保存することで、データがその Azure Storage アカウントの適切な地理的位置に転送され保存されることに同意することになりますが、Dynamics 365 Customer Insights でデータが保存される場所とは異なる場合があります。 [Microsoft Trust Center を詳しく知る。](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>ホーム ページの詳細を確認します。

[Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/)からの対象者インサイトへは、次の URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/) からアクセスできます。
**ホーム** ページには、[マップ](map-entities.md)、[一致](match-entities.md)、および[マージ](merge-entities.md) フェーズ完了後のセグメント、メジャー、およびエンリッチメント データ (構成されている場合) の概要が表示されます。

> [!div class="mx-imgBorder"] 
> ![ホーム ページでのインサイト](media/home-page-insights.png "ホーム ページでのインサイト")

**最近のセグメント** 配下で、定義した人口統計、行動、またはトランザクションの属性に基づいた顧客のグループが表示されます。 [セグメントの作成](segments.md)は、顧客ベースをグループ化し、ビジネス活動をより的確にターゲティングするのに役立ちます。

**最近のメジャー** には、定義した[主要業績評価指標 (KPI)](measures.md) がタイル表示されます。 たとえば、顧客が解約する平均的な可能性や、顧客ごとの平均オンライン支出などです。

**最近のエンリッチメント** セクションには、最近完了したエンリッチメントの実行結果が一覧表示されます。 [エンリッチメント](enrichment-hub.md)は、顧客ベースに基づく情報を追加します。 これらは、例えば親しんでいる興味の対象をブランドを理解することで得られます。

## <a name="switch-environments"></a>環境の切り替え

ページ右上隅にある **環境** コントロールを選択肢て、環境を変更します。

> [!div class="mx-imgBorder"] 
> ![環境の切り替え](media/home-page-environment-switcher.png "環境の切り替え")

管理者は[複数の環境](manage-environments.md)を作成、管理できます。 たとえば、組織が国際的に事業を展開していて、データや分析情報をさまざまな方法で分離する必要がある場合には、複数の環境を維持することが有効かもしれません。

## <a name="next-step"></a>次のステップ

ホームページで自分の分析情報を見るには、まずデータに対して[データソースの追加](data-sources.md)と[統合](data-unification.md)を行い、顧客プロファイルを構築する必要があります。


[!INCLUDE[footer-include](../includes/footer-banner.md)]