---
title: iOS SDK サンプルの実行
description: iOS SDK について学ぶためのサンプル プロジェクト
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232848"
---
# <a name="run-the-ios-sdk-sample"></a>iOS SDK サンプルの実行

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

このサンプル iOS プロジェクトは、SDK がアプリでどのように機能するかを理解するのに役立ちます。 コードを記述する必要はありません。 取り込みキーを追加するだけで、ワークスペースでイベントをすぐに確認できます。

## <a name="prerequisites"></a>前提条件

- [Xcode バージョン 9+](https://developer.apple.com/xcode/downloads/)
- [取り込みキー](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>iOS SDK サンプルのダウンロード

1. [エンゲージメント インサイトの iOS SDK サンプルをダウンロードする](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip)。
1. 圧縮ファイル `ei-ios-sample.zip` を解凍します。
1. サンプル アプリ プロジェクトを Xcode で開きます。
1. `EIConfig.plist` ファイルで `ingestionKey` フィールドにある文字列 `“YOUR-INGESTION-KEY”` を、**管理者** > **ワークスペース** > **インストール ガイド** にあるエンゲージメント・インサイトのワークスペース取り込みキーに置き換えてください。
1. **実行** を選択して、サンプル プロジェクトを開始します。
1. ワークスペースでイベントを表示します。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
