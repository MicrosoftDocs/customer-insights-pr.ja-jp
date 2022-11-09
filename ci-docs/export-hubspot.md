---
title: Customer Insights のデータを HubSpot にエクスポートする
description: 接続を構成して、HubSpot にエクスポートする方法を説明します。
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725360"
---
# <a name="export-segments-to-hubspot-preview"></a>セグメントを HubSpot にエクスポート (プレビュー)

統合顧客プロファイルのセグメントを HubSpot にエクスポートして、メール マーケティングに使用します。

## <a name="prerequisites-for-a-connection"></a>接続の前提条件

- [HubSpot アカウント](https://www.hubspot.com/) と対応する管理者資格情報。
- HubSpot からの [API キー](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key)。
- Customer Insights で [構成されたセグメント](segments.md)。

## <a name="known-limitations"></a>既知の制限

- Bring your own storage (BYOS) と組み合わせたプライベート リンクはサポートされていません。
- HubSpot へのエクスポートごとに最大 100,000 の顧客プロファイル。完了するまでに最大 15 分かかる場合があります。 HubSpot にエクスポートできる顧客プロファイルの数は、HubSpot との契約によって異なり、限定されます。
- セグメントのみ。

## <a name="set-up-connection-to-hubspot"></a>HubSpot への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**HubSpot** を選択して、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. プロンプトが表示されたら、HubSpot の資格情報を入力します。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **接続** を選択して、HubSpot への接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、HubSpot セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。 他のオプション フィールドについても同じ手順を繰り返します。

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
