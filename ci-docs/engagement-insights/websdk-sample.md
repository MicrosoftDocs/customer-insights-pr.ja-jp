---
title: Web SDK サンプルの実行
description: Web SDK サンプルを個人設定して実行する方法を説明します。
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036609"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Dynamics 365 Customer Insights エンゲージメント インサイト機能の Web SDK サンプルを実行する

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

エンゲージメント インサイト機能のWeb SDK ライブラリは、Web サイトで使用できるサンプル コードを含む JavaScript ライブラリです。

## <a name="prerequisites"></a>前提条件

- [Visual Studio Code](https://code.visualstudio.com/) をインストールします。
- Visual Studio Code で [Live Server 拡張機能をインストール](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) し、Live Server の実行方法を確認します。
- [取り込みキー](instrument-website.md) が必要です。

## <a name="run-sample"></a>サンプルの実行

1. [Web SDK サンプルをダウンロードします](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip)。

1. 圧縮ファイル `ei_websdk_sample.zip` を解凍します。

1. 解凍したフォルダーを Visual Studio Code で開きます。

1. `ei_websdk_sample.html` ファイルで、文字列 "INGESTION_KEY" をエンゲージメント インサイト機能ポータルからの取り込みキーに、文字列 "NAME" を SDK をインスタンス化するためのグローバル名に置き換えます。 すべての出現箇所を必ず置き換えてください。

1. Visual Studio Code で Live Server を使用して `ei_websdk_sample.html` ファイルを開くには、ステータス バーから **ライブに移行** を選択します。

1. ページを開くと、ビュー イベントが自動的に送信されます。 ページ上のボタンのいずれかをクリックすると、アクション イベントが送信されます。 **イベントの追跡** ボタンはカスタム イベントも送信します。 **Bing へ移動** ボタンを選択すると、Bing の Web サイトに移動する前に、アクション イベントを送信します。

1. ワークスペースに移動したときのイベントの流れを確認します。 このワークスペースは、手順 4 で入力した取り込みキーに関連付けられます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]