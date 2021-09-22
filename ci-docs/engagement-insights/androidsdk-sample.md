---
title: Android SDK サンプル
description: Android SDK について学ぶためのサンプル プロジェクト
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035832"
---
# <a name="run-the-android-sdk-sample"></a>Android SDK サンプルの実行

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

このサンプル Android プロジェクトは、SDK がアプリでどのように機能するかを理解するのに役立ちます。 コードを記述する必要はありません。 取り込みキーを追加するだけで、ワークスペースでイベントをすぐに確認できます。

## <a name="prerequisites"></a>前提条件

- [Android Studio](https://developer.android.com/studio)
- [インジェスト キー](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Android SDK サンプルのダウンロード

1. [エンゲージメント分析情報の Android SDK サンプルをダウンロードする](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip)。
1. 圧縮ファイル `ei-android-sample.zip` を解凍します。
1. 解凍したフォルダーを Android Studio で開きます。
1. `AndroidManifest.xml` ファイルにある `"Your-Ingestion-Key"` 文字列を、**管理者** > **ワークスペース** > **インストール ガイド** のエンゲージメント分析情報にある、ワークスペース インジェスト キーに置き換えます。 

   > [!NOTE]
   > `${applicationId}` セクションを置き換える必要はありません。 自動的に入力されます。

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. **実行** を選択して、サンプル プロジェクトを開始します。
1. ワークスペースでイベントを表示します。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
