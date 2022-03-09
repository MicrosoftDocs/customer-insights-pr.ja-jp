---
title: Cookie とユーザーの同意を管理して、ユーザー データを Dynamics 365 Customer Insights に保存します
description: Web サイトの訪問者を識別するために Cookie とユーザーの同意がどのように使用されるかを説明します。
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228991"
---
# <a name="manage-cookies-and-user-consent"></a>Cookie とユーザーの同意の管理

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights エンゲージメント インサイト機能は Web サイトの訪問者を識別に Cookie や (`localStorage`) キーを使用しています。

Cookie は、ユーザーと Web サイトのやり取りに関する情報を格納する小さなファイルです。 それらは Web ブラウザーに保存されます。 ユーザー が Cookie を保存した Web サイトにアクセスすると、ブラウザーはその情報をサーバーに送信し、サーバーはユーザーに固有の情報を返します。 これは、たとえば、ユーザーが Web サイトから離れた場合でも、オンライン ショッピング カートで選択したアイテムを保持することを可能にする技術です。

## <a name="user-consent"></a>ユーザーの同意

[一般データ保護規則 (GDPR)](/dynamics365/get-started/gdpr/) は、欧州連合 (EU) の規則で、組織がユーザーのプライバシーとセキュリティをどのように取り扱うべきかを規定しています。 Cookie には、GDPR の対象となるオンライン識別子などの「個人データ」を保存または収集することがよくあります。 ユーザーのビジネスが EU のデータ主体を雇用および/または販売している場合、GDPR はユーザーに影響を与えます。 [Microsoft が GDPR の遵守を支援する方法については詳細をご覧ください](https://www.microsoft.com/trust-center/privacy/gdpr-faqs)。

エンゲージメント インサイト SDK が Cookie またはその他の機密情報を保存できるようにするには、ユーザーが同意したかどうかを指定する必要があります。 これは、SDK の初期化時に、構成の `userConsent` フィールドを設定することで発生します。

ユーザーの同意がないことを示すと、SDK はデータを保存せず、ユーザーの行動を追跡するために使用できるイベントを送信しません。 以前に保存されたデータはブラウザーから削除されます。

ユーザー同意値が指定されていない場合、SDK はユーザーが同意したと見なします。 つまり、(お客様として) SDK でユーザー同意の値を指定しない場合、データが収集されます。 ただし、ユーザーの同意の値を "true" にする必要があると指定した場合、ユーザーが明示的な同意を辞退したり、提供できなかった場合、データは収集されません。

以下は、ユーザーの同意を得て Web SDK を初期化するためのコード スニペットです。
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>エンゲージメント インサイト機能における訪問者データ ストレージ

### <a name="cookies"></a>クッキー

- _msei
    - 匿名のユーザー ID を格納します。 この Cookie は顧客ドメインに設定され、有効期限は 365 日です。

### <a name="local-storage"></a>ローカル ストレージ

また、エンゲージメント インサイト機能では、(`localStorage`) キーを使用して、機密性の低いデータを追跡できます。 このデータはブラウザー自体に完全に保存され、サーバーとの間でトラフィックが送受信されることはありません。

- *EISession.Id*
    - セッション ID、開始日時、有効期限など、実行中のユーザー セッションに関する情報を格納します。
- *EISession.Previous*
    - 現在のセッションで既にアクセスしたページの URL を格納します。

ローカル ストレージのキーは自動的に期限切れにはならず、次の SDK セッションでリセットされます。

## <a name="deleting-cookies"></a>Cookie の削除

顧客は、ブラウザー設定を使用していつでも手動で Cookie とローカル ストレージ キーを削除できます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
