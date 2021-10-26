---
title: エンゲージメント インサイトの機能を使用する
description: すばやく開始するためのヘルプ リソースについての概要。
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3505c15c4319c8cc8823bcd89d3b8adc944a87dd
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623683"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Dynamics 365 Customer Insights エンゲージメント インサイトの機能を使用する

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

エンゲージメント インサイト機能により、web サイト上の顧客の行動を収集、測定できます。 対象ユーザーのインサイト機能と統合されているため、顧客プロファイルレポートと共に豊富なリアルタイムの行動分析を確認できます。 この記事のリンクは、環境の構成、設定を簡単に実行する場合に役立ちます。

## <a name="step-1-review-prerequisites"></a>ステップ 1: 前提条件のレビュー

まず、アクティブな Microsoft Azure Active Directory (AAD) ユーザー アカウントが必要です。 次に、エンゲージメント インサイトのワークスペースを設定する前に、次の記事をお読みください。

- マイクロソフトの [サービス使用条件](terms-of-service.md) を確認し、同意します。  
- [Cookie とユーザーの同意を管理する](user-consent-storage.md) の記事を読む。 その後、ユーザー同意の通知を更新する必要があるかどうかを評価します。 以前に 「必須ではない」 クッキーを設定していなかった場合は、サイトポリシーを更新する必要があります。
- 重要な用語と概念については、[用語集](glossary.md)を確認してください。

## <a name="step-2-explore-engagement-insights"></a>ステップ 2: エンゲージメントの分析情報を探る

エンゲージメント インサイトへの初回アクセス時には、設定の構成、ポリシーの確認、機能の確認ができます。

1. マイクロソフトの AAD ユーザー (学校または職場) アカウントを使用して、[エンゲージメント インサイト機能ポータル](https://home.ci.ai.dynamics.com/app/engagement-insights)にログインします。

1. 地域を選択し、電子メールの更新とオファーの受信をオプトインする場合は、チェックボックスをオンにします。

1. エンゲージメント インサイト (プレビュー) **利用規約** と **プライバシーに関する声明** を確認し、**デモを確認する** を選択してこれらの設定を受け入れます。

1. サンプル データのセットを使用して製品を探索します。

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>ステップ3: ワークスペースを設定してレポートを作成する

ワークスペースは、ユーザー アクティビティをリアルタイムで表示し、レポートの保存や管理ができる場所です。 Web サイトにコードを追加して *イベント* (ユーザーから送られる活動データ) の収集を開始ます。

1. [ワークスペースを作成](create-workspace.md)し、メンバーを追加します。

1. [Web サイトにコードを追加する](instrument-website.md)か、または [モバイル アプリ](developer-resources.md#capture-events-from-mobile-apps) にコードを追加して、ワークスペースに送られるユーザーのアクティビティを確認します。

1. [リアルタイム レポート](view-reports.md)を表示することで、ブラウザ、デバイス、オペレーティング システム、場所、言語ごとのアクティブユーザーを確認できます。 [カスタム レポート](custom-reports.md)を作成して、独自の視覚化を作成することもできます。

1. [ディメンション](dimensions.md)を作成して、新規ユーザーとリピーターで訪問者を並べ替え、[メトリック](metrics.md)を作成して、ユーザーの行動をよりよく理解し、[セグメント](segments.md)を作成して、特性または Web サイトのインタラクションに基づいて訪問者のサブセットを識別します。
    
## <a name="step-4-export-data-to-other-channels"></a>ステップ 4: 他のチャネルにデータをエクスポートする

Web解析データの *改良されたイベント* (仮想ビュー) を作成できます。 次に、データをフィルター処理して Azure Data Lake Storage にエクスポートします。 エクスポートされたデータをデータ ソースとして取り込むことができます。

1. エクスポートする [改良されたイベントを作成](refined-events.md)します。

1. [データを Azure Data Lake Storage にエクスポートします](export-events.md)。

1. [対象ユーザー インサイトとエンゲージメント インサイトの間にリンクを作成](integrate-audience-insights-engagement-insights.md)し、2 つの機能間でデータを共有します。

1. **不明点を明らかにする** 機能を使って、[以前に認証されたユーザーからの Web イベントを認識します](unknown-to-known.md)。

1. [個人情報を含むイベントデータの削除およびエクスポート](delete-export-personal-data.md)をする方法について説明します。

## <a name="step-5-create-and-manage-funnel-reports"></a>ステップ5: じょうごレポートを作成および管理する

じょうごレポートは、ウェブサイトまたはモバイル アプリを介して顧客体験中に発生するステップに関する情報を収集します。 すぐに使用できるプロファイル レポートとカスタム レポートを作成するだけでなく、じょうごレポートを作成して、顧客が購入する前にたどる経路を特定できます。 

1. [じょうごレポートを作成](funnel-reports.md)して、意思決定のために情報を提供し、最適化とプロセス改善の領域を特定します。

1. エンゲージメント インサイト [Android SDK](get-started-android.md)または [iOS SDK](get-started-ios.md) をモバイル アプリに組み込んだら、クロスチャネルじょうごレポートを作成します。

1. [じょうごインサイト](funnel-reports.md#funnel-insights)を使用して、じょうごレポートのステップに関する顧客の行動に対するより深い分析情報を得ることができます。
 
## <a name="step-6-stay-connected"></a>ステップ 6: 接続を維持する

皆様の積極的なご参加に感謝するとともに、関連するすべてのフィードバックを今後のリリースに反映させていきます。 次のいずれかのチャネルでフィードバックを共有し、問題を報告してください。
- [コミュニティ](https://go.microsoft.com/fwlink/?linkid=2141648)
- [フィードバックを提供する](https://go.microsoft.com/fwlink/?linkid=2143222)
- [サポートの要請](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
