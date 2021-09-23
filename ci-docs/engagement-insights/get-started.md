---
title: エンゲージメント インサイトの機能を使用する
description: すばやく開始するためのヘルプ リソースについての概要。
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494600"
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

1. **エンゲージメント インサイト (プレビュー) 利用規約** と **プライバシーに関する声明** を確認し、**デモを確認する** を選択してこれらの設定を受け入れます。

1. サンプル データのセットを使用して製品を探索します。

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>ステップ 3: ワークスペースを設定し、Web サイトにコードを追加します

ワークスペースは、ユーザー アクティビティをリアルタイムで表示し、レポートの保存や管理ができる場所です。 Web サイトにコードを追加して *イベント* (ユーザーから送られる活動データ) の収集を開始ます。

1. [ワークスペースを作成](create-workspace.md)し、メンバーを追加します。

1. [ウェブサイトにコードを追加する](instrument-website.md) か、または [モバイル アプリ](developer-resources.md#capture-events-from-mobile-apps) にコードを追加して、ワークスペースに送られるユーザーのアクティビティを確認します。

1. [リアルタイム レポート](view-reports.md)を表示することで、ブラウザ、デバイス、オペレーティング システム、場所、言語ごとのアクティブユーザーを確認できます。 [カスタム レポート](custom-reports.md)を作成して、独自の視覚化を作成することもできます。
    
## <a name="step-4-export-data-to-other-channels"></a>ステップ 4: 他のチャネルにデータをエクスポートする

Web解析データの *改良されたイベント* (仮想ビュー) を作成できます。 次に、データをフィルター処理して Azure Data Lake Storage にエクスポートします。 エクスポートされたデータをデータ ソースとして取り込むことができます。 詳細情報については、[対象ユーザー インサイトとエンゲージメント インサイトの間にリンクを作成する](integrate-audience-insights-engagement-insights.md)を参照してください。

1. エクスポートする [改良されたイベントを作成](refined-events.md)します。

1. Data Lake Storage に[データをエクスポート](export-events.md)します。

1. [対象ユーザー インサイトとエンゲージメント インサイトの間にリンクを作成](integrate-audience-insights-engagement-insights.md)し、2 つの機能間でデータを共有します。

1. [個人情報を含むイベントデータの削除およびエクスポート](delete-export-personal-data.md)をする方法について説明します。
 
## <a name="step-5-stay-connected"></a>ステップ 5: 接続を維持する

皆様の積極的なご参加に感謝するとともに、関連するすべてのフィードバックを今後のリリースに反映させていきます。 次のいずれかのチャネルでフィードバックを共有し、問題を報告してください。
- [コミュニティ](https://go.microsoft.com/fwlink/?linkid=2141648)
- [フィードバックを提供する](https://go.microsoft.com/fwlink/?linkid=2143222)
- [サポートの要請](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
