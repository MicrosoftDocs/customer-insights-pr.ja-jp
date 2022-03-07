---
title: ユーザー データを保存するための Cookie とユーザーの同意の管理
description: Web サイトの訪問者を識別するために Cookie とユーザーの同意がどのように使用されるかを説明します。
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036744"
---
# <a name="manage-cookies-and-user-consent"></a>Cookie とユーザーの同意の管理

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights エンゲージメント インサイト機能は Cookie と ローカル ストレージ (`localStorage`) を使用して、Web サイトの訪問者を識別します。

Cookie は、ユーザーと Web サイトのやり取りに関する情報を格納する小さなファイルです。 それらは Web ブラウザーに保存されます。 ユーザー が Cookie を保存した Web サイトにアクセスすると、ブラウザーはその情報をサーバーに送信し、サーバーはユーザーに固有の情報を返します。 これは、たとえば、ユーザーが Web サイトから離れた場合でも、オンライン ショッピング カートで選択したアイテムを保持することを可能にする技術です。

## <a name="user-consent"></a>ユーザーの同意

[一般データ保護規則 (GDPR)](/dynamics365/get-started/gdpr/) は、欧州連合 (EU) の規則で、組織がユーザーのプライバシーとセキュリティをどのように取り扱うべきかを規定しています。 Cookie には、GDPR の対象となるオンライン識別子などの「個人データ」を保存または収集することがよくあります。 ユーザーのビジネスが EU のデータ主体を雇用および/または販売している場合、GDPR はユーザーに影響を与えます。 [Microsoft が GDPR の遵守を支援する方法については詳細をご覧ください](https://www.microsoft.com/trust-center/privacy/gdpr-faqs)。

エンゲージメント インサイト SDK が Cookie またはその他の機密情報を保存できるようにするには、ユーザーが同意したかどうかを指定する必要があります。 これは、SDK の初期化時に行われます。

ユーザーの同意がないことを示すと、SDK はデータを保存せず、ユーザーの行動を追跡するために使用できるイベントを送信しません。 以前に保存されたデータはブラウザーから削除されます。

ユーザー同意値が指定されていない場合、SDK はユーザーが同意したと見なします。 つまり、(お客様として) SDK でユーザー同意の値を指定しない場合、データが収集されます。 ただし、ユーザーの同意の値を "true" にする必要があると指定した場合、ユーザーが明示的な同意を辞退したり、提供できなかった場合、データは収集されません。

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>エンゲージメント インサイト機能における訪問者データ ストレージ

### <a name="cookies"></a>クッキー

- _msei
    - 匿名のユーザー ID を格納します。 この Cookie は顧客ドメインに設定され、有効期限は 365 日です。

### <a name="local-storage"></a>ローカル ストレージ

エンゲージメント インサイト機能では、ローカル ストレージ (`localStorage`) を使用して機密性の低いデータも追跡します。 このデータはブラウザー自体に完全に保存され、サーバーとの間でトラフィックが送受信されることはありません。

- *EISession.Id* 
    - セッション ID、開始日時、有効期限など、実行中のユーザー セッションに関する情報を格納します。
- *EISession.Previous*
    - 現在のセッションで既にアクセスしたページの URL を格納します。
    
ローカル ストレージのキーは自動的には失効しません。 これらは、SDK によって次のセッション中にリセットされます。

## <a name="deleting-cookies"></a>Cookie の削除

顧客は、ブラウザー設定を使用していつでも手動で Cookie とローカル ストレージ キーを削除できます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]