---
title: Dynamics 365 Customer Insights の使用の開始
description: Customer Insights の概要は、リソースをすばやく開始するのに役立ちます。
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1a19d83930d667bdca5301dcc5a3ffa5db6a7bdc
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741139"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights の使用の開始

Customer Insights は、顧客の理解を深めるのに役立ちます。 さまざまなトランザクション、行動、および観測ソースからのデータを接続して、360 度の顧客ビューを作成します。 これらのインサイトを使用して、顧客中心のエクスペリエンスとプロセスを推進します。 顧客データを統合して理解し、インテリジェントなインサイトおよびアクションに活用します。

## <a name="step-1-create-an-environment"></a>ステップ 1: 環境の作成

まず、作業する環境を作成する必要があります。 組織がすでにライセンスを購入している場合は、[環境を作成する](create-environment.md)を参照してください。 Customer Insights の試用を開始するには、[試用環境を設定する](trial-signup.md) を参照してください。

## <a name="step-2-explore-customer-insights"></a>ステップ 2: Customer Insights を探索する

Customer Insights に初めてログインするときに、設定を構成して製品を調べることができます。

1. Microsoft Azure Active Directory (AAD) ユーザー アカウントを使用して、[Customer Insights にログインします](https://home.ci.ai.dynamics.com)。

1. [環境を変えて](manage-environments.md#switch-environments)、デモ データを見て、[Customer Insights を探索する](home.md)。

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>ステップ 3: データの取り込み、統合、関連付けを設定します

統合プロファイルは、データを洞察し、アクションを実行するための基盤となります。 様々なソースからデータを取り込み、データの統一プロセスを実行して、統一されたプロファイルを組み合わせます。 取り込んだエンティティ間で関連付けを指定し、エンリッチメント機能を使用してプロファイルに情報を追加します。

1. 複数のオプションからデータ ソースを作成してデータを取り込みます。 [Power Query コネクタ](connect-power-query.md)、[Common Data Model フォルダー](connect-common-data-model.md)、[Microsoft Dataverse](connect-dataverse-managed-lake.md) の中から選択します。 

1. [ソース フィールド](map-entities.md)を識別し、[重複](remove-duplicates.md)を削除し、[条件を一致](match-entities.md)させ、[フィールドを統合](merge-entities.md)することにより、[データ統合プロセス](data-unification.md)を実行します。

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

1. 統合オプションをレビューします。たとえば、その他の Dynamics 365 アプリと [顧客カード アドイン](customer-card-add-in.md) などです。  


[!INCLUDE [footer-include](includes/footer-banner.md)]
