---
title: iOS SDK の利用を開始する
description: iOS SDKをパーソナライズして実行する方法を学ぶ
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e4d0555d2fc377fae62ff5db64c032fcebcb04
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226221"
---
# <a name="get-started-with-the-ios-sdk"></a>iOS SDK の利用を開始する

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

このチュートリアルでは、Dynamics 365 Customer Insights のエンゲージメント分析情報 SDK を使用して iOS アプリケーションをインストルメント化する方法について説明します。 5 分以内にポータルにイベントが表示されるようになります。

## <a name="configuration-options"></a>構成オプション

以下の構成オプションは、提供されている `EIConfig.plist` ファイルを介して SDK に渡すことができます。

- **ingestionKey**: プロジェクトにイベントを送信するために使用されるインジェスト キー。
- **autocollectAction**: アクション イベントの自動インストルメンテーションを有効または無効にするブール値。
- **autocollectAction**: ビュー イベントの自動インストルメンテーションを有効または無効にするブール値。
- **endpointUrl**: イベントが送信されるエンドポイント URL。

## <a name="prerequisites"></a>前提条件

- Xcode バージョン 9 以上
- iOS バージョン 8.2 以上
- インジェスト キー (取得するには、以下の手順を参照してください)

## <a name="integrate-the-sdk-into-your-application"></a>SDK をアプリケーションに統合する

プロセスを開始するには、作業するワークスペースを選択し、iOS モバイル プラットフォームを選択して、SDK をダウンロードします。

- 左側のナビゲーション ペインのワークスペース スイッチャーを使用して、ワークスペースを選択します。

- 既存のワークスペースがない場合は、**新しいワークスペース** を選択し、手順に従って [新しいワークスペース](create-workspace.md) を作成します。

- ワークスペースを作成したら、**管理者** > **ワークスペース** に移動し、**インストール ガイド** を選択します。

## <a name="configure-the-sdk"></a>SDK を構成する

SDK をダウンロードしたら、Xcode で SDK を操作して、イベントを有効にして定義できます。 これには次の 2 つの方法があります

### <a name="option-1-using-cocoapods-recommended"></a>オプション 1: CocoaPods を使用する (推奨)
CocoaPods は、Swift と Objective-C の Cocoa プロジェクトで使用する依存関係管理ツールです。 これを使用すると、iOS 向けエンゲージメント インサイト SDK の統合が容易になります。 CocoaPods は、エンゲージメント インサイト SDK の最新バージョンにアップグレードすることもできます。 ここでは、CocoaPods を使ってエンゲージメント インサイト SDK を Xcode プロジェクトに統合する方法を紹介します。 

1. CocoaPods をインストールします。 

1. プロジェクトのルート ディレクトリ内に Podfile iというファイルを新規に作成し、その中に以下のステートメントを追加します。 YOUR_TARGET_PROJECT_NAME をご利用の Xcode プロジェクトの名前に 置換えます。 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
上記のポッド構成には、SDK のデバッグ バージョンとリリースバージョンの両方が含まれています。 プロジェクトに最適な方を選択してください。

1. 次のコマンドを実行して、ポッドをインストールします:  `pod install --repo-update `

### <a name="option-2-using-download-link"></a>オプション 2: ダウンロード リンクを使用する

1. [エンゲージメント分析情報の iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) をダウンロードし、`Frameworks` フォルダに `EIObjC.xcframework` ファイルを配置します。

1. `Frameworks` フォルダが存在しない場合は、プロジェクト フォルダに作成してください。

## <a name="enable-auto-instrumentation"></a>自動インストルメンテーションを有効にする
 
コーディングせずに自動インストルメンテーションを簡単に有効にすることができます。 プロジェクトが実行されると、プロジェクトは設定されたインジェスト キーを使用して、自動的に `view` および `action` イベントを追跡します。 

1. 次のフィールドのプロジェクト ディレクトリ フォルダに、提供された `EIConfig.plist` ファイルを更新して含めます。
    - インジェスト キー = `"Your-Ingestion-Key"`
    - autocollectView = YES
    - autocollectAction = YES

2. 次に、Xcode でプロジェクトに `EIConfig.plist` ファイルを追加します。 



自動インストルメンテーションを無効にするには、プロジェクト ディレクトリ フォルダに保存された `EIConfig.plist` ファイルの次のフィールドを更新します。 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>カスタム イベントの実装

1. Xcode でプロジェクトを開き、**全般** 設定に移動します。 
1. フレームワーク、ライブラリ、および埋め込みコンテンツ セクションの下のプロジェクトに、`EIObjC.xcframework` を追加します。

1. AppDelegate.m のフレームワーク ヘッダー ファイルを次のスニペットでインポートします:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. didFinishLaunchingWithOptions アプリケーションから エンゲージメント分析情報 SDK を初期化します。
1. **インストール ガイド** から、XML スニペットをコピーします。

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. イベントの追跡:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>イベントのユーザー詳細を設定する

SDK を使用すると、すべてのイベントで送信できるユーザー情報を定義できます。 SDK の `setUser:(nonnull EIUser *)user` API を呼び出すことにより、ユーザー情報を指定できます。

`Analytics` レベルでユーザーの詳細を指定すると、すべてのテレメトリにこの情報が含められます。 ただし、EIEvent オブジェクトの `setUser:(nonnull EIUser *)user` API を呼び出してイベント レベルで指定した場合、情報が含まれるのはその特定のイベントのみです。

`EIUser` データ クラスには、次の NSString プロパティが含まれています。

- **localId** : ユーザーのローカル ID です。
- **authId**: 認証されたユーザー ID です。
- **authType**: 認証されたユーザー ID の取得に使用される認証タイプです。
- **name**: ユーザー名です。
- **email**: ユーザーのメール アドレスです。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
