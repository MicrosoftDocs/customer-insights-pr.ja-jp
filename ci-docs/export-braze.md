---
title: セグメントを Braze にエクスポートする (プレビュー)
description: Braze への接続とエクスポートを構成する方法を説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 84dc7f13f30e0334d431fe5b5866c7f87e82ab27
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195113"
---
# <a name="export-segments-to-braze-preview"></a>セグメントを Braze にエクスポートする (プレビュー)

統合顧客プロファイルのセグメントを Braze にエクスポートして、マーケティング活動に使用します。

## <a name="prerequisites"></a>前提条件

- [Braze アカウント](https://www.braze.com/)と対応する管理者資格情報。
- [Braze API キー](https://www.braze.com/docs/api/basics/)
- Customer Insights で [構成されたセグメント](segments.md)。
- エクスポートされたセグメントの統合顧客プロファイルには、メール アドレスと Braze 顧客 ID を表すフィールドが含まれています。

## <a name="known-limitations"></a>既知の制限

- Braze に対して最大 100 万の顧客プロファイル。完了するまでに最大 40 分かかる場合があります。 Braze にエクスポートできる顧客プロファイルの数は、Braze との契約によって異なります。
- セグメントのみ。

## <a name="set-up-connection-to-braze"></a>Braze への接続を設定します

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**Braze** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. Braze API キーを入力してサインインを続行します。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **接続** を選択して、接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、Braze セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。 **顧客 ID** フィールドで、顧客の Braze ID を表すフィールドを選択します。 Braze のセグメントは、Dynamics 365 Customer Insights のセグメントと同じ名前で作成されます。 データを照合するためのオプション フィールドをさらに選択できます。

1. エクスポートするエンティティまたはセグメントを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
