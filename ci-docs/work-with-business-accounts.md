---
title: ビジネス アカウントに関する作業
description: Dynamics 365 Customer Insights で主なターゲット対象ユーザーとしてのビジネス アカウントについて確認します。
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: 9bf91671b744198b2f37391edc7abf58eca3c820
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053119"
---
# <a name="work-with-business-accounts"></a>ビジネス アカウントに関する作業

Dynamics 365 Customer Insights では、個人の消費者 (B-to-B) とビジネス アカウント (B-to-B) など、さまざまな主要ターゲット対象ユーザー向けに環境を構成できます。 B-to-C シナリオでは、データは個人を中心にしています。 B-to-B の場合、主なターゲット対象ユーザーは取引先企業 - 組織または企業 - および取引先担当者です。 この記事は、ビジネス アカウントの環境を開始するのに役立ちます。 環境の焦点に応じて、Customer Insights の機能領域の違いが一覧表示されます。 違いの詳細については、機能領域のドキュメントを確認してください。 

## <a name="create-an-environment-for-business-accounts"></a>ビジネス アカウントの環境を作成する

管理者は[既存の組織に環境を作成](create-environment.md)できます。 新しい環境を作成するプロセスのステップでは、管理者に環境のプライマリ ターゲット対象ユーザーを要求します。 ライセンス購入後の対象者分析情報の初期設定の場合、ガイド付きのエクスペリエンスが最初の環境の作成に役立ちます。

その後、サポートされているすべてのソースからデータ ソースとしてビジネス アカウントおよび関連取引先担当者の[データを取り込む](data-sources.md)ことができます。

データを統合した後、関係構成の一部として[アカウント階層を指定](relationships.md#set-up-account-hierarchies)します。 また、[セマンティック マッピングを構成](semantic-mappings.md)して、取引先担当者と取引先企業エンティティを接続することもできます。 

## <a name="switch-between-primary-target-audience"></a>プライマリ ターゲット対象ユーザーを切り替える

組織が個人の顧客とビジネス アカウントの環境を維持している場合、左側のペインのスイッチャーを使用して、プライマリ ターゲット対象ユーザーを選択できます。

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="個人の顧客とビジネス アカウントの間でプライマリ ターゲット対象ユーザーを変更するスイッチャー。":::

## <a name="supported-feature-areas"></a>サポートされている機能領域

- [活動](activities.md): 活動を作成してタイムラインに表示するための取引先企業および関連する取引先担当者をサポートします。
- [リレーションシップ](relationships.md): 活動ウィザードは、エンティティ間にリレーションシップを作成するのに役立ち、取引先企業ビューに取引先担当者からのすべての活動を表示できます。 取引先担当者はドリルアップして取引先担当者ビューを表示でき、階層はアカウント活動の集計に使用できます。
- [メジャー](measures.md): 1 回の計算でメジャー ビルダーから作成されたメジャーをサポートします。 オプションの設定により、メジャーを作成するときにサブアカウントをロールアップできます。
- [セグメント](segments.md): セグメント ビルダーを使用して最初から作成されたセグメントをサポートします。 新しい演算子を使用する際、セグメント作成時にアカウント階層を組み込むことができます。
- [データ インジェスト](data-sources.md): この領域のすべての機能は、ビジネス アカウントと個人の顧客で同じです。
- [データの統合](data-unification.md): この領域のすべての機能は、ビジネス アカウントと個人の顧客で同じです。
- [エンリッチメント](enrichment-hub.md): 一部のエンリッチメント タイプは個々の顧客シナリオでのみ使用できますが、その他のエンリッチメント タイプはビジネス アカウントでのみ使用できます。
- [予測とすぐに使えるモデル](predictions-overview.md): トランザクション離反予測には、ビジネス アカウントの追加手順が含まれています。 その他の予測は、個々の顧客のみが利用できます。
- [アクティブ化とエクスポート](export-destinations.md): エクスポートは、ビジネス アカウントと個人の顧客の両者が利用できます。 一部のエクスポートでは、ビジネス アカウントで有効にするために、基になるセグメントに投影される追加の構成および取引先担当者情報が必要となります。
- [システム設定](system.md)および[ユーザー管理](permissions.md): この領域のすべての機能は、ビジネス アカウントと個人の顧客で同じです。

