---
title: 高度な web SDK シナリオ
description: SDK でウェブサイトをインストルメント化する際に考慮すべき高度なシナリオ。
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036334"
---
# <a name="advanced-web-sdk-instrumentation"></a>高度な Web SDK のインストルメント化

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

この記事では、Dynamics 365 Customer Insights エンゲージメント・インサイト・ケイパビリティSDKを使って [ウェブサイトをインストルメント化](instrument-website.md) する際に考慮すべき高度なシナリオについて説明します。

## <a name="setting-user-details-for-your-event"></a>イベントのユーザー詳細情報を設定する

SDK を使用すると、すべてのイベントで送信できるユーザー情報を定義できます。 コードスニペット構成の `src`、`name`、`cfg` と同様に、`user` というプロパティでユーザーの詳細を指定することができます (このプロパティの期待されるデータは `IUser` オブジェクトです)。

`IUser` オブジェクトは以下の文字列プロパティを含みます:

- **localId** : ユーザーのローカル ID です。
- **authId**: 認証されたユーザー ID です。
- **authType**: 認証されたユーザー ID の取得に使用される認証タイプです。
- **name**: ユーザー名です。
- **email**: ユーザーのメール アドレスです。
    
次の例では、ユーザー情報を送信するコード スニペットを示しています。 関数が * で示されている場合は、それらの値を呼び出す実装に置き換えてください。  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

また、SDK上の `setUser(user: IUser)` API を呼び出してユーザー情報を指定することもできます。 `setUser API` を呼び出した後に送信されるテレメトリには、ユーザー情報が含まれています。

## <a name="adding-custom-properties-for-each-event"></a>イベントごとのカスタムプロパティを追加する

SDK では、イベントごとに送信できるカスタム プロパティを指定することができます。 カスタム プロパティは、キーと値のペアを含むオブジェクトとして指定できます (値は `string | number | boolean` のタイプにすることができます)。 オブジェクトは、コード スニペットの構成にある `src`、`name`、`cfg` と同様に、`props` というプロパティで追加できます。 

次の例では、カスタム プロパティを送信するコード スニペットを示しています:

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

また、SDK上の `setProperty(name: string, value: string | number | boolean)`  API を呼び出すことで、カスタム プロパティを個別に指定することもできます。

## <a name="sending-custom-events"></a>カスタム イベントの送信

SDK を使用してカスタム イベントを送信できます。 イベントの名前と、イベントとともに送信されるプロパティを指定する必要があります。

次の例では、カスタム イベントを追跡するコード スニペットを示しています。 「NAME」は、スニペット構成の `name` キーにある値です。 また、SDK が読み込まれるウィンドウ オブジェクトの変数名でもあります。

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]