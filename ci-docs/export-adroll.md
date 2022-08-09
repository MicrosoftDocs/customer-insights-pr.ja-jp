---
title: セグメントを AdRoll にエクスポート (プレビュー)
description: AdRoll への接続とエクスポートを構成する方法を説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8110eab199920ab8fc2ea15678139faf264a242a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195756"
---
# <a name="export-segments-to-adroll-preview"></a>セグメントを AdRoll にエクスポート (プレビュー)

統合顧客プロファイルのセグメントを AdRoll にエクスポートし、広告に使用します。

## <a name="prerequisites"></a>前提条件

- [AdRoll アカウント](https://www.adroll.com/) と対応する管理者資格情報。
- [AdRoll 広告者 ID](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles)。
- Customer Insights で [構成されたセグメント](segments.md)。
- エクスポートされたセグメントの Unified customer profile には、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- AdRoll へのエクスポートあたり最大 25 万の顧客プロファイル。完了するまでに最大 10 分かかる場合があります。 AdRoll にエクスポートできる顧客プロファイルの数は、AdRoll との契約によって異なります。
- セグメントのみ。 セグメントには、少なくとも 100 の顧客プロファイルが含まれている必要があります。

## <a name="set-up-connection-to-adroll"></a>AdRoll への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**AdRoll** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **接続** を選択して、接続を初期化します。

1. **AdRoll による認証** を選択し、AdRoll の管理者資格情報を入力します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、AdRoll セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. **AdRoll 広告主 ID** を入力してください。

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
