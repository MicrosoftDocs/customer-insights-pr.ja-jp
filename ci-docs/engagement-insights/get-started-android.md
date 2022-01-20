---
title: Android SDK の利用を開始する
description: Android SDK をパーソナライズして実行する方法を学ぶ
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 71ec4841303bd17d3f605547be8d6032c58a7b21
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977581"
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

## <a name="integrate-the-sdk-into-your-application"></a>SDK をアプリケーションに統合する
プロセスを開始するには、作業するワークスペースを選択し、Android モバイル プラットフォームを選択して、Android SDK をダウンロードします。

- 左側のナビゲーション ペインのワークスペース スイッチャーを使用して、ワークスペースを選択します。

- 既存のワークスペースがない場合は、**新しいワークスペース** を選択し、手順に従って [新しいワークスペース](create-workspace.md) を作成します。

- ワークスペースを作成したら、**管理者** > **ワークスペース** に移動し、**インストール ガイド** を選択します。

## <a name="configure-the-sdk"></a>SDK を構成する

SDK をダウンロードしたら、Android Studio で SDK を操作して、イベントを有効にして定義できます。 これには 2 つの方法があります:
### <a name="option-1-use-jitpack-recommended"></a>オプション 1: JitPack を使用する (推奨)
1. JitPack リポジトリをルートに追加します: `build.gradle`
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. 依存関係を追加します:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>オプション 2: ダウンロード リンクを使用する
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

## <a name="enable-auto-instrumentation"></a>自動インストルメンテーションを有効にする

1. `manifests` フォルダ配下にある `AndroidManifest.xml` ファイルに、ネットワークとインターネットの許可を追加します。
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. `AndroidManifest.xml` ファイルでエンゲージメント インサイト SDK の設定を行います。

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

   >[!NOTE]
   >`Action` イベントは手動で追加する必要があります。

1. (オプション) その他の構成には、エンドポイント コレクター URL の設定が含まれます。 それらは、`AndroidManifest.xml` のインジェスト キー メタデータの下に追加できます。

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>カスタム イベントの実装

SDK を初期化した後、`MainActivity`  環境でイベントとそのプロパティを操作できます。


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

## <a name="set-user-details-for-your-event-optional"></a>イベントのユーザー詳細を設定する (オプション)

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
