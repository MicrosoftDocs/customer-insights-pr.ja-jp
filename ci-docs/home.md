---
title: Customer Insights を探索する
description: ホーム ページでアプリの詳細を確認します。
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 13b4bfa2f0b0cd69454c025e2f59de3dd6bb75a3
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053303"
---
# <a name="explore-customer-insights"></a>Customer Insights を探索する

[Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) には次の URL からアクセスできます。[https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/)

この **ホーム** ページでは、主要な機能の構成プロセスを示し、セグメント、メジャー、エンリッチメント データの概要を提供します。

:::image type="content" source="media/home-page.png" alt-text="サンプルの分析情報を示すホーム画面のスクリーンショット。":::

## <a name="left-side-pane"></a>左側のペイン

左側のペインを使用して、Customer Insights のさまざまな領域間を移動します。

ビジネス アカウントと個人消費者を相手にする場合は、プライマリ対象ユーザーを選択して、それに応じてフォーカスを設定できます。

## <a name="application-header"></a>アプリケーションのヘッダー

**環境** ピッカーは、作業している環境を表示し、管理者として環境の作成や管理を実行できます。

スマイル アイコンは **フィードバック** コントロールです。 それを選択して、Customer Insights のご意見をお聞かせください。 私たちはお客様のフィードバックを積極的に聞き、何が好きで、どうすれば改善できるかを知らせてくださることに、前もって感謝いたします。

歯車のアイコンで表される **設定** コントロールを使用すると、Customer Insights のセッションの詳細を収集し、Microsoft 365 プロフィールのグローバル設定を構成できます。

疑問符アイコンで表される **ヘルプ** オプションは、コンテキストに応じたヘルプ リンクやその他の役立つリソースを提供します。

プロファイル画像で Microsoft 365 プロファイルの **アカウント マネージャー** が開きます。 **マイ アカウント** を選択し個人設定を管理します。

## <a name="getting-started-with-customer-insights-section"></a>Customer Insights セクションの基本情報

このセクションには、Customer Insights 環境を設定するプロセスを説明するカードが含まれています。

1. **データを追加する** カードはデータ インポートをサポートします。 Customer Insights は[顧客に関するデータを取り込むためのいくつかのオプション](data-sources.md)をサポートします。 **データ ソースを追加する** を選択して開始します。
1. 最初のデータ インポートが正常に完了すると、**データの統合** カードを使用してデータを調和させ、異なるソースから[統合された顧客プロファイルを作成](data-unification.md)できます。 
1. 統合された顧客プロファイルが作成されたら、次は **データの分析** オプションを確認し追加のインサイトを取得します。 KPI を追跡するための[ビジネス メジャー](measures.md)、特定の対象者と繋がるための[セグメントの定義](segments.md)、または AI の助けを借りて[予測の構成](predictions-overview.md)を作成してみてください。
1. 顧客データがインポートされ、統合され、きちんと構造化されたので、[さまざまなエクスポート先](export-destinations.md)を使用して、データに対してアクションを実行します。 **接続の追加** を選択し、お気に入りのサービスに接続します。 たとえば、データを Dynamics 365 Marketing にエクスポートして、アウトバウンド マーケティング キャンペーンを作成したり、顧客体験を構築したりします。 

## <a name="your-customer-insights-section"></a>顧客分析情報セクション

- **セグメント** では、定義した人口統計、行動、またはトランザクション属性に基づいて顧客のグループを表示します。 [セグメントの作成](segments.md)は、顧客ベースをグループ化し、ビジネス活動をより的確にターゲティングするのに役立ちます。

- **ビジネス対策** では、定義した[主要業績評価指標 (KPIs)](measures.md) でタイルを表示します。 たとえば、顧客が解約する平均的な可能性や、顧客ごとの平均オンライン支出などです。

- **エンリッチメント** では、最近完了したエンリッチメント実行の結果を一覧表示します。 [エンリッチメント](enrichment-hub.md)は、顧客ベースに基づく情報を追加します。 これらは、例えば親しんでいる興味の対象をブランドを理解することで得られます。


[!INCLUDE [footer-include](includes/footer-banner.md)]
