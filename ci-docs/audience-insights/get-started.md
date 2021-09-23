---
title: Dynamics 365 Customer Insights で対象ユーザー インサイト機能を使用する
description: 対象ユーザー インサイトの概要は、リソースをすばやく開始するのに役立ちます。
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: aaaf1848df175469d8af07754ac153b777781ffb
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466583"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights の対象ユーザー インサイト機能を使用する

対象ユーザー インサイトを使用することで、顧客についての理解を深めることができます。 さまざまなトランザクション、行動、および観測ソースからのデータを接続して、360 度の顧客ビューを作成します。 これらのインサイトを使用して、顧客中心のエクスペリエンスとプロセスを推進します。 顧客データを統合して理解し、インテリジェントなインサイトおよびアクションに活用します。

## <a name="step-1-create-an-environment"></a>ステップ 1: 環境の作成

まず、作業する環境を作成する必要があります。 組織がすでにライセンスを購入している場合は、[有料サブスクリプションを開始する](get-started-paid.md)を参照してください。 対象者インサイトの試用版を開始するには、[試用版環境のセットアップ](get-started-trial.md)を参照してください。 

## <a name="step-2-explore-audience-insights"></a>ステップ 2: 対象ユーザーの分析情報を探る

対象ユーザー インサイトへの初めてのサインイン時は、構成設定を行い、製品をの詳細を確認することができます。

1. Microsoft Azure Active Directory (AAD) ユーザー アカウントを使用して、[対象ユーザー インサイトにログイン](https://home.ci.ai.dynamics.com)します。

1. [環境の変更をして](manage-environments.md#switch-environments)デモデータを表示し、[ 対象ユーザーの分析情報の詳細確認をします](home.md)。

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>ステップ 3: データの取り込み、統合、関連付けを設定します

統合プロファイルは、データを洞察し、アクションを実行するための基盤となります。 様々なソースからデータを取り込み、データの統一プロセスを実行して、統一されたプロファイルを組み合わせます。 取り込んだエンティティ間で関連付けを指定し、エンリッチメント機能を使用してプロファイルに情報を追加します。 

1. 複数のオプションからデータ ソースを作成してデータを取り込みます。 [Power Query コネクタ](connect-power-query.md)、[ Common Data Model フォルダ](connect-common-data-model.md)、または [Microsoft Dataverse](connect-common-data-service-lake.md) から選択します。 

1. [マッピング](map-entities.md)、[一致](match-entities.md)、と[マージ](merge-entities.md)のフェーズを介して、[データ統合プロセス](data-unification.md)を実行します。

1. [システムが作成するエンティティ](entities.md)にを身につけ、[取り込んだエンティティ間の関連付け](relationships.md)を作成します。
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>ステップ 4: 予測、アクティビティ、および測定値を使用して統合プロファイルを強化する

統一されたプロファイルを設定することで、データを強化し、提供する情報をさらに増やすことができます。

1. 拡張されたエンリッチメント プロバイダーのライブラリから [顧客データのエンリッチ](enrichment-hub.md) を選択します。

1. [既成のモデル](predictions-overview.md)を使用して、解約の可能性や予想収益を予測します。

1. 取り込んだデータに基づいて[アクティビティを構成](activities.md)し、顧客とのやり取りを時系列で可視化します。 

1. [対策を構築し](measures.md)、ビジネス目標と KPI を評価します。
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>ステップ 5: セグメントを作成し、さまざまなエクスポート オプションを使用してデータをアクティブ化します

顧客に関するさまざまな情報を含めたデータが完成したら、次はそのデータを活用したアクションを考えてみましょう。 

1. 顧客層のサブセットである[セグメントを作成し](segments.md)、ターゲットとなる顧客に適切なアクションを起こします。

1. 顧客データを利用可能な[エクスポート オプション](export-destinations.md)の拡張されたカタログを参照します。 たとえば、データを使用してプロモーションを管理し、デジタル マーケティングと連絡を取ることができます。

1. [エンゲージメント インサイトへの直接接続](../engagement-insights/integrate-audience-insights-engagement-insights.md)や、[Customer Card アドイン](customer-card-add-in.md)によるその他 Dynamics 365 アプリへの接続など、統合オプションを検討します。  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
