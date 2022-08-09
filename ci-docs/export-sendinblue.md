---
title: セグメントを Sendinblue にエクスポートする (プレビュー)
description: 接続を構成して、Sendinblue にエクスポートする方法を学びます。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 816a3b242fadaa5a75db878adf0a76baf638e41c
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196952"
---
# <a name="export-segments-to-sendinblue-preview"></a>セグメントを Sendinblue にエクスポートする (プレビュー)

統合された顧客プロファイルのセグメントをエクスポートして、キャンペーンを生成したり、電子メール マーケティングを行ったり、Sendinblue で特定の顧客グループを使用したりすることができます。

## <a name="prerequisites"></a>前提条件

- [Sendinblue アカウント](https://www.sendinblue.com/) および対応する管理者資格情報。
- [SendinBlue API キー](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)。
- Sendinblue には既存のリストと対応する ID。
- [構成されたセグメント](segments.md)。
- エクスポートされたセグメントの Unified customer profile には、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Sendinblue へのエクスポートあたり最大 100 万の顧客プロファイル。完了するまでに最大 90 分かかる場合があります。 Sendinblue にエクスポートできる顧客プロファイルの数は、Sendinblue との契約によって異なります。
- セグメントのみ。

## <a name="set-up-connection-to-sendinblue"></a>Sendinblue への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**Sendinblue** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **SendinBlue API キー** を入力します。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **接続** を選択して、接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポート用の接続** フィールドで、Sendinblue セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. **Sendinblue リスト ID** を入力します。

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。

1. オプションで、**姓**、**名**、および **電話番号** をエクスポートして、よりパーソナライズされた電子メールを作成します。 **属性の追加** を選択し、これらのフィールドをマップします。

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
