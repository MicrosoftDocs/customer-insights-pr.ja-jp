---
title: Android SDK の利用を開始する
description: Android SDK をパーソナライズして実行する方法を学ぶ
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036924"
---
# <a name="get-started-with-the-android-sdk"></a>Android SDK の利用を開始する

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

このチュートリアルでは、Dynamics 365 Customer Insights のエンゲージメント分析情報 SDK を使用して、Android アプリケーションをインストルメント化するプロセスについて説明します。 5 分以内にポータルにイベントが表示されるようになります。

## <a name="configuration-options"></a>構成オプション
以下の構成オプションを、SDK に送ることができます。

- **ingestionKey**: ワークスペースにイベントを送信するために使用されるインジェスト キー。

## <a name="prerequisites"></a>前提条件

- Android Studio

- 最小 Android API レベル: 16 (Jelly Bean)

- インジェスト キー (取得するには、以下の手順を参照してください)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>ステップ 1: SDK をアプリケーションに統合する
プロセスを開始するには、作業するワークスペースを選択し、Android モバイル プラットフォームを選択して、Android SDK をダウンロードします。

- 左側のナビゲーション ペインのワークスペース スイッチャーを使用して、ワークスペースを選択します。

- 既存のワークスペースがない場合は、**新しいワークスペース** を選択し、手順に従って [新しいワークスペース](create-workspace.md) を作成します。

## <a name="step-2-configure-the-sdk"></a>ステップ 2: SDK を構成する

1. ワークスペースを作成したら、**管理者** > **ワークスペース** に移動し、**インストール ガイド** を選択します。 

1. [エンゲージメント分析情報の Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) をダウンロードし、`libs` フォルダに `eiandroidsdk-debug.aar` ファイルを配置します。

1. プロジェクト レベルの `build.gradle` ファイルを開き、次のスニペットを追加します:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. `manifests` フォルダの下にある、`AndroidManifest.xml` ファイルを用いて、エンゲージメント分析情報の SDK 構成を設定します。 
1. **インストール ガイド** から、XML スニペットをコピーします。 `Your-Ingestion-Key` は自動的に入力されます。

   > [!NOTE]
   > `${applicationId}` セクションを置き換える必要はありません。 自動的に入力されます。
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. 上部の `autoCapture` フィールドを `true` または `false` に設定し、`View` イベントの自動取り込みを有効または無効にします。

1. (オプション) その他の構成には、エンドポイント コレクター URL の設定が含まれます。 それらは、`AndroidManifest.xml` のインジェスト キー メタデータの下に追加できます。
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>ステップ 3: MainActivity から SDK を初期化する 

SDK を初期化した後、MainActivity 環境でイベントとそのプロパティを操作できます。

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>すべてのイベントのプロパティを設定します (オプション)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

コンテキスト イベント プロパティでは、次の種類がサポートされています。
- String
- Date
- Double
- Long
- Boolean
- UUID

### <a name="track-an-event"></a>イベントを追跡

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>イベントのユーザー詳細を設定する (オプション)

SDK を使用すると、すべてのイベントで送信できるユーザー情報を定義できます。 `Analytics` レベルの `setUser(user: User)` API を呼び出すことにより、ユーザー情報を指定できます。

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

`User` データ クラスには、次の文字列プロパティが含まれています。

- **localId** : ユーザーのローカル ID です。
- **authId**: 認証されたユーザー ID です。
- **authType**: 認証されたユーザー ID を取得するために使用される認証の種類。
- **name**: ユーザー名です。
- **email**: ユーザーのメール アドレスです。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
