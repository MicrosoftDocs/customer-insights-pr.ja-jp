---
title: Web サイト にコードを追加する
description: コードスニペットを追加して、Web サイトのイベント取得する方法。
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035100"
---
# <a name="install-the-code-snippet-on-a-website"></a>Web サイトのコード スニペットをインストールする

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

この記事では、管理者がコードスニペットを Web サイトにインストールする方法を説明します。 このスクリプトを Web サイトに追加すると、直ちにワークスペースにイベントが表示されるようになります。 詳細については、[ワークスペースと環境の管理](manage-environments-workspaces.md) を参照してください。 モバイル アプリでイベントをキャプチャするには、[開発者リソースの概要](developer-resources.md)を参照してください。


### <a name="prerequisites"></a>前提条件

* データを保存するには、ワークスペースの管理者権限が必要です。
* アクティビティ データを送信するには、Webサイトやプロジェクトをオンラインでホストする必要があります。 ローカル ファイルから送信されたデータは、サーバーが受け入れません。


## <a name="add-code-to-your-website"></a>Web サイト にコードを追加する
1.  **管理者** > **ワークスペース** に移動し、**インストール ガイド** を選択します。
1. **コードのコピー** を選択し、コードスニペットをコピーします。 既定では、ワークスペースの取り込みキーはコード スニペットに埋め込まれています。
:::image type="content" source="media/copy-code.png" alt-text="コード スニペット ページのスクリーンショット。":::
3. コピーしたコードスニペットを web サイトの <head> タグの近く、他のスクリプトや CSS  タグの前に追加してください。
4.  更新した Web サイトを公開して、数分後には流入してくる Web トラフィックを捉えることができます。
5.  データを表示するには、ナビゲーション ペインのワークスペース スイッチャーから自分のワークスペースを選択します。 **検出** セクションでレポートの 1 つを選択します。

## <a name="configuration-options"></a>構成オプション

コードスニペットでは、以下の設定オプションを変更できます:

- **ingestionKey**: ワークスペースにイベントを送信する際に使用される取り込みキーです。 取り込みキーを変更して、イベントを別のワークスペースに送信できます。 取り込みキーは、各ワークスペースに固有となります。 
- **autoCapture** : ページビューと Web サイトとのインタラクションをキャプチャするかどうかを指定します。 以下の 2 つのオプションがあります:
    - **表示**: *true* に設定するとページビューをキャプチャします。 ページ ビューは、[ベース イベント](glossary.md#base-event)の一種である *ビュー* [イベント](glossary.md#event)として取得されます。
    - **クリック**: *true* にに設定すると Web サイトの訪問者のインタラクションをキャプチャします。 対話は、[ベース イベント](glossary.md#base-event)の一種である *アクション* [イベント](glossary.md#event)として取得されます。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
