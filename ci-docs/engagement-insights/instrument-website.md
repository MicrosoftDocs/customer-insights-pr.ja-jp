---
title: Web サイト にコードを追加する
description: コードスニペットを追加して、Web サイトの Dynamics 365 Customer Insights イベント取得する方法。
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558863"
---
# <a name="install-the-web-sdk-on-a-website"></a>Web サイトに Web SDK をインストールする

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

この記事では、管理者が Web サイトに Web ソフトウェア開発ツールキット (SDK) をインストールする方法について説明します。 Web サイトをインストルメント化するとすぐに、ワークスペースでイベントが表示されるようになります。 詳細については、[ワークスペースと環境の管理](manage-environments-workspaces.md) を参照してください。 モバイル アプリでイベントをキャプチャするには、[開発者リソースの概要](developer-resources.md)を参照してください。


### <a name="prerequisites"></a>前提条件

* データを保存するには、ワークスペースの管理者権限が必要です。
* アクティビティ データを送信するには、Webサイトやプロジェクトをオンラインでホストする必要があります。 ローカル ファイルから送信されたデータは、サーバーが受け入れません。


## <a name="add-web-sdk-to-your-website"></a>Web サイトに Web SDK を追加する

**管理者** > **ワークスペース** に移動し、**インストール ガイド** を選択します。 Web SDK をインストールする 2 つのオプションがあります。 1 つはダウンロード リンクを使用する方法で、2 つ目は Node Package Manager (NPM) パッケージをインストールする方法です。

### <a name="option-1-using-the-download-link"></a>オプション 1: ダウンロード リンクを使用する

1. **コードのコピー** を選択し、コードスニペットをコピーします。 既定では、ワークスペースの取り込みキーはコード スニペットに埋め込まれています。
  :::image type="content" source="media/copy-code.png" alt-text="コード スニペット ページのスクリーンショット。":::

1. コピーしたコードを Web サイト、 <head> タグの近く、他のスクリプトや CSS  タグの前に追加してください。
1. 更新した Web サイトを公開して、数分後には流入してくる Web トラフィックを捉えることができます。
1. データを表示するには、ナビゲーション ペインのワークスペース スイッチャーから自分のワークスペースを選択します。 **検出** セクションでレポートの 1 つを選択します。

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>オプション 2: NPM パッケージを使用する (JavaScript ベースの Web アプリの場合に推奨)

1. [NPM Web ページ](https://www.npmjs.com/package/engagementinsights-web)に移動し、指示に従って Web SDK NPM パッケージをインストールして設定します。
1. 更新した Web サイトを公開して、数分後には流入してくる Web トラフィックを捉えることができます。
1. データを表示するには、ナビゲーション ペインのワークスペース スイッチャーから自分のワークスペースを選択します。 **検出** セクションでレポートの 1 つを選択します。

## <a name="configuration-options"></a>構成オプション

コードスニペットでは、以下の設定オプションを変更できます:

- **ingestionKey**: ワークスペースにイベントを送信する際に使用される取り込みキーです。 取り込みキーを変更して、イベントを別のワークスペースに送信できます。 取り込みキーは、各ワークスペースに固有となります。
- **autoCapture** : ページビューと Web サイトとのインタラクションをキャプチャするかどうかを指定します。 以下の 2 つのオプションがあります:
    - **表示**: *true* に設定するとページビューをキャプチャします。 ページ ビューは、[ベース イベント](glossary.md#base-event)の一種である *ビュー* [イベント](glossary.md#event)として取得されます。
    - **クリック**: *true* にに設定すると Web サイトの訪問者のインタラクションをキャプチャします。 対話は、[ベース イベント](glossary.md#base-event)の一種である *アクション* [イベント](glossary.md#event)として取得されます。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
