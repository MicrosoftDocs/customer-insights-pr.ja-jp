---
title: Web SDK サンプルの実行
description: Web SDK サンプルを個人設定して実行する方法を説明します。
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225337"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Dynamics 365 Customer Insights エンゲージメント インサイト機能の Web SDK サンプルを実行する

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

エンゲージメント インサイト機能のWeb SDK ライブラリは、Web サイトで使用できるサンプル コードを含む JavaScript ライブラリです。

## <a name="prerequisites"></a>前提条件

- [Visual Studio Code](https://code.visualstudio.com/) をインストールします。
- Visual Studio Code で [Live Server 拡張機能をインストール](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) し、Live Server の実行方法を確認します。
- [エンゲージメント分析情報ワークスペース](create-workspace.md)が必要です。

## <a name="run-sample"></a>サンプルの実行

1. [Web SDK サンプルをダウンロードします](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip)。

1. 圧縮ファイル `ei_websdk_sample.zip` を解凍します。

1. 解凍したフォルダーを Visual Studio Code で開きます。

1. ワークスペースのエンゲージメント分析情報ポータルに移動します。 **管理者** > **ワークスペース**、次に **インストール ガイド** を選択します。 最初のオプションに従い、**コードをコピーする** を選択して、JavaScript コード スニペットをコピーします。

1. `ei_websdk_sample.html` ファイルで、コピーしたコード スニペットを次の行に貼り付けます:

   - <-- この行の下にあるエンゲージメント分析情報ポータルから JavaScript コード スニペットを貼り付けます -->

1. Visual Studio Code で Live Server を使用して `ei_websdk_sample.html` ファイルを開くには、ステータス バーから **ライブに移行** を選択します。

1. ページを開くと、ビュー イベントが自動的に送信されます。 ページ上のボタンのいずれかをクリックすると、アクション イベントが送信されます。 **イベントの追跡** ボタンはカスタム イベントも送信します。 **Bing へ移動** ボタンを選択すると、Bing の Web サイトに移動する前に、アクション イベントを送信します。

1. ワークスペースに移動したときのイベントの流れを確認します。 このワークスペースは、手順 4 で入力した取り込みキーに関連付けられます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
