---
title: セグメントを MoEngage にエクスポートする
description: MoEngage への接続とエクスポートを構成する方法を説明します。
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199115"
---
# <a name="export-segments-to-moengage-preview"></a>セグメントを MoEngage にエクスポート (プレビュー)

統合された顧客プロファイルのセグメントを MoEngage にエクスポートし、MoEngage での E メール マーケティングに使用します。

## <a name="prerequisites-for-a-connection"></a>接続の前提条件

- [MoEngage アカウント](https://www.moengage.com/)と対応する管理者資格情報。
- MoEngage の [設定] > [API] からの MoEngage API キー。
- Customer Insights で [構成されたセグメント](segments.md)。

## <a name="known-limitations"></a>既知の制限

- MoEngage へのエクスポートあたり最大 100,000 の顧客プロファイル。最大 15 分かかる場合があります。 MoEngage にエクスポートできる顧客プロファイルの数は、MoEngage との契約によって異なります。
- セグメントのみ。

## <a name="set-up-connection-to-moengage"></a>MoEngage への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **接続の追加** を選択して **MoEngage** を選択し、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. [MoEngage データ API ID および API キー](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY) を入力します。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **接続** を選択して、MoEngage への接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、MoEngage セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。 他のオプション フィールドについても同じ手順を繰り返します。

1. エクスポートするセグメントを選択します。 MoEngage の **セグメント** > **カスタム セグメント** で選択したセグメントと同じ名前のセグメントを1つ以上作成します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
