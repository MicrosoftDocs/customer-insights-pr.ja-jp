---
title: セグメントを ActiveCampaign にエクスポートする
description: 接続を構成して、ActiveCampaign にエクスポートする方法を学びます。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725406"
---
# <a name="export-segments-to-activecampaign-preview"></a>セグメントを ActiveCampaign にエクスポートする (プレビュー)

統合された顧客プロファイルのセグメントを ActiveCampaign にエクスポートし、マーケティング活動に使用します。

## <a name="prerequisites"></a>前提条件

- [ActiveCampaign アカウント](https://www.activecampaign.com/) および対応する管理者資格情報。
- [ActiveCampaign リスト ID](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign)。
- [ActiveCampaign API キー](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key)および REST エンドポイント ホスト名。
- Customer Insights で [構成されたセグメント](segments.md)。
- エクスポートされたセグメントの Unified customer profile には、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Bring your own storage (BYOS) と組み合わせたプライベート リンクはサポートされていません。
- ActiveCampaign へのエクスポートあたり最大 100 万の顧客プロファイル。完了するまでに最大 90 分かかる場合があります。 ActiveCampaign にエクスポートできる顧客プロファイルの数は、ActiveCampaign との契約によって異なります。
- セグメントのみ。

## <a name="set-up-connection-to-activecampaign"></a>ActiveCampaign への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**ActiveCampaign** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. ActiveCampaign API キーおよび REST エンドポイント ホスト名 を入力してください。 REST エンドポイントのホスト名はホスト名のみで、https:// は含まれません。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **接続** を選択して、接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポート用の接続** フィールドで、ActiveCampaign セクションから、接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. **ActiveCampaign リスト ID** を入力します。

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。

1. オプションで、**姓**、**名**、および **電話番号** をエクスポートして、よりパーソナライズされた電子メールを作成します。 **属性の追加** を選択し、これらのフィールドをマップします。

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
