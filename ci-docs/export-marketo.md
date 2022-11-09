---
title: セグメントを Marketo にエクスポート (プレビュー)
description: Marketo への接続とエクスポートを構成する方法を説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724946"
---
# <a name="export-segments-to-marketo-preview"></a>セグメントを Marketo にエクスポート (プレビュー)

統合顧客プロファイルのセグメントをエクスポートして、キャンペーンを生成し、電子メール マーケティングを提供して Marketo で特定の顧客グループを使用します。

## <a name="prerequisites"></a>前提条件

- [Marketo アカウント](https://login.marketo.com/) と対応する管理者資格情報。
- [Marketo クライアント ID、クライアント シークレット、REST エンドポイントのホスト名](https://developers.marketo.com/rest-api/authentication/)。
- [Marketo の既存のリスト](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) と対応する ID。
- [構成されたセグメント](segments.md)。
- エクスポートされたセグメントの Unified customer profile には、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Bring your own storage (BYOS) と組み合わせたプライベート リンクはサポートされていません。
- Marketo へのエクスポートあたり最大 100 万の顧客プロファイル。最大 3 時間かかる場合があります。 Marketo にエクスポートできる顧客プロファイルの数は、Marketo との契約によって異なります。
- セグメントのみ。

## <a name="set-up-connection-to-marketo"></a>Marketo への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**Marketo** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **Marketo クライアント ID、クライアント シークレット、REST エンドポイントのホスト名** を入力します。 REST エンドポイントのホスト名はホスト名のみで、https:// は含まれません。 例: xyz-abc-123.mktorest.com。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **接続** を選択して、接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、Marketo セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. **Marketo リスト ID** を入力します。 リスト ID は純粋な数値です。 たとえば、Marketo リスト ID が ST12345A7 の場合、数字の前後の文字を削除して、*12345* を入力します。

1. **データマッチング** セクションで、顧客のメール アドレスまたは顧客の Marketo ID を表すフィールドを少なくとも 1 つ選択します。

1. オプションで、**名**、**姓**、**市**、**都道府県**、**国/地域** をエクスポートし、パーソナライズされたメールを作成します。 **属性の追加** を選択し、これらのフィールドをマップします。

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Marketo では、セグメントが [Marketo リスト](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) の下に表示されます。

[!INCLUDE [footer-include](includes/footer-banner.md)]
