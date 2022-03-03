---
title: 事前に認証された不明な訪問者から既知の訪問者の範囲でウェブイベントを認識する
description: 不明から既知の機能では、ウェブサイト上のイベントを、以前に認証した訪問者と関連付けることができます。
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: 75ce776fd5be1c426508ae6f5c239c86bdd3ec39
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230686"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>以前に認証した訪問者のウェブイベントを認識する

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

**不明から既知** エンゲージメント インサイトの機能により、Web サイト上のイベントを以前に認証した訪問者に関連付けることができます。 この機能を無効にすると、以前の訪問時に認証して去った訪問者は、再訪問時に再度認証しないと識別されません。 

たとえば、ある人が先週 Web サイトにアクセスし、そのサイトのユーザーアカウントにログインして、製品カタログを閲覧したとします。 その人は翌週、自分のアカウントにサインインすることなく、さらに多くの製品を閲覧します。 **不明から既知** 機能を使っているサイトのオーナーは、同じ人が戻ってきたことと、その人がサイトで何をしたかを知ることができます。 これにより、Web サイトアクティビティのさらに正確なレポートと分析が可能になります。

## <a name="enable-unknown-to-known"></a>不明から既知を有効化する

この機能を有効にするには、 [ワークスペース管理者](user-roles.md) である必要があります。 

1. エンゲージメント インサイトで、**管理者** > **ワークスペース** にアクセスします。 
2. **設定** タブを選択します。
3. **不明から既知** セクションで、トグルを **有効** に設定します。

![不明から既知を有効化する](media/U2Ktoggle.png "不明から既知を有効化する")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>サイトのトラッキングに JavaScript コードを追加するスニペット

Web サイトでは、[エンゲージメント インサイト ウェブ SDK](advanced-SDK-implementation.md)を使って、以下 のJavaScriptサンプルで **ユーザーの authId** を取得することができます。 **不明から既知** 機能を動作させるには、authId を取得し、*さらに* userMapping を True に設定する必要があります (以下のサンプルの JavaScript スニペット参照)。

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
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
