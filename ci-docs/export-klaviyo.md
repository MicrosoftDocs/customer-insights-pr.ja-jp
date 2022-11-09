---
title: Klaviyo にセグメントをエクスポートする (プレビュー)
description: 接続を構成して、Klaviyo にエクスポートする方法を説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 075e6758f2c6992a1185756f9beecf852fdd0a96
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724600"
---
# <a name="export-segments-to-klaviyo-preview"></a>Klaviyo にセグメントをエクスポートする (プレビュー)

統合された顧客プロファイルのセグメントを Klaviyo にエクスポートし、マーケティング活動に使用します。

## <a name="prerequisites"></a>前提条件

- [Klaviyo アカウント](https://www.klaviyo.com/) および対応する管理者資格情報。
- [Klaviyo API キー](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys)。
- [Klaviyo リスト ID](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID)。
- Customer Insights で [構成されたセグメント](segments.md)。
- エクスポートされたセグメントの Unified customer profile には、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Bring your own storage (BYOS) と組み合わせたプライベート リンクはサポートされていません。
- Klaviyo へのエクスポートあたり最大 100 万の顧客プロファイル。完了するまでに最大 20 分かかる場合があります。 Klaviyo にエクスポートできる顧客プロファイルの数は、Klaviyo との契約によって異なります。
- セグメントのみ。

## <a name="set-up-connection-to-klaviyo"></a>Klaviyo への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**Klaviyo** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. ご利用の Klaviyo API キー を入力してログインを続行します。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **接続** を選択して、接続を初期化します。

1. **Klaviyo で認証する** を選択し、Klaviyo の管理者認証情報を入力します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポート用の接続** フィールドで、Klaviyo セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. **Klaviyo リスト ID** を入力します。

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
