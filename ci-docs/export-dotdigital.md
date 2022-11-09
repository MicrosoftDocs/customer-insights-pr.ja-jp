---
title: セグメントを DotDigital にエクスポート (プレビュー)
description: DotDigital への接続とエクスポートを構成する方法を説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724992"
---
# <a name="export-segments-to-dotdigital-preview"></a>セグメントを DotDigital にエクスポート (プレビュー)

統合顧客プロファイルのセグメントを DotDigital のアドレス帳にエクスポートし、キャンペーン、電子メール マーケティング、および DotDigital で顧客セグメントを構築するために使用します。

## <a name="prerequisites"></a>前提条件

- [DotDigital アカウント](https://dotdigital.com/) と、[API ユーザー](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user)。
- DotDigital の[新規](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) または既存のアドレス帳からの DotDigital ID。 アドレス帳を選択して開くと、URL に ID が表示されます。
- Customer Insights で [構成されたセグメント](segments.md)。
- エクスポートされたセグメントの Unified customer profile には、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Bring your own storage (BYOS) と組み合わせたプライベート リンクはサポートされていません。
- プロバイダー側の制限により、DotDigital へのエクスポートあたり最大 100 万の顧客プロファイル。完了には最大 3 時間かかる場合があります。 DotDigital にエクスポートできる顧客プロファイルの数は、DotDigital との契約によって異なります。
- セグメントのみ。

## <a name="set-up-connection-to-dotdigital"></a>DotDigital への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**DotDigital** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **DotDigital API のユーザー名とパスワード** を入力します。

1. **DotDigital アドレス帳 ID** を入力します。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **接続** を選択して、接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、DotDigital セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。

1. オプションで、**名**、**姓**、**氏名**、**性別**、**郵便番号** をエクスポートします。

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

DotDigital では、セグメントを [DotDigital アドレス帳](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) で検索します。

[!INCLUDE [footer-include](includes/footer-banner.md)]
