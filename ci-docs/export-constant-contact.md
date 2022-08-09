---
title: セグメントを Constant Contact にエクスポート (プレビュー)
description: Constant Contact への接続とエクスポートを構成する方法を説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4d2ec29c194dc481ee40048b8ecbed813291b4d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196492"
---
# <a name="export-segments-to-constant-contact-preview"></a>セグメントを Constant Contact にエクスポート (プレビュー)

統合顧客プロファイルのセグメントを Constant Contact にエクスポートし、マーケティング活動に使用します。

## <a name="prerequisites"></a>前提条件

- [Constant Contact アカウント](https://www.constantcontact.com/account-home) と対応する管理者資格情報。
- [固定連絡先リスト ID](https://app.constantcontact.com/pages/contacts/ui#lists)。 Constant Contact でリストを開き、URL でリスト ID を検索します。
- Customer Insights で [構成されたセグメント](segments.md)。
- エクスポートされたセグメントの Unified customer profile には、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Constant Contact へのエクスポートあたり最大 100 万の顧客プロファイル。完了するまでに最大 1 時間かかる場合があります。 Constant Contact にエクスポートできる顧客プロファイルの数は、Constant Contact との契約によって異なります。
- セグメントのみ。

## <a name="set-up-connection-to-constant-contact"></a>Constant Contact への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**Constant Contact** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **接続** を選択して、接続を初期化します。

1. **コンスタントコンタクトで認証する** を選択し、コンスタント コンタクトの管理者認証情報を入力します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、Constant Contact セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. **Constant Contact リスト ID** を入力します。

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。

1. オプションで、**名** と **姓** を追加フィールドとしてエクスポートし、よりパーソナライズされた電子メールを作成します。 **属性の追加** を選択し、これらのフィールドをマップします。

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
