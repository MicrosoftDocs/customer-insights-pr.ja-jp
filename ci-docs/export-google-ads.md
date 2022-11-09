---
title: セグメントを Google Ads にエクスポート (プレビュー)
description: Google Ads への接続とエクスポートを構成する方法を説明します。
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725084"
---
# <a name="export-segments-to-google-ads-preview"></a>セグメントを Google Ads にエクスポート (プレビュー)

統一された顧客プロファイルのセグメントを Google Ads 対象ユーザー リストにエクスポートし、それらを使用して Google 検索、Gmail、YouTube、および Google ディスプレイ ネットワークで宣伝できます。

## <a name="prerequisites"></a>前提条件

- [Google Ads アカウント](https://ads.google.com/) と対応する管理者資格情報。
- [Google Ads 顧客 ID](https://support.google.com/google-ads/answer/1704344)。
- [Customer Match のポリシー](https://support.google.com/adspolicy/answer/6299717) の要件を満たしている。
- [リマーケティング リスト サイズ](https://support.google.com/google-ads/answer/7558048) の要件を満たしている。
- [構成されたセグメント](segments.md)。
- エクスポートされたセグメントの統合顧客プロファイルには、メール アドレス、電話、モバイル広告主 ID、サードパーティ ユーザー ID、または住所を表すフィールドが含まれています。

## <a name="known-limitations"></a>既知の制限

- Bring your own storage (BYOS) と組み合わせたプライベート リンクはサポートされていません。
- プロバイダー側の制限により、Google Ads へのエクスポートあたり最大 100 万の顧客プロファイルをエクスポートします。完了には最大 30 分かかる場合があります。
- セグメントのみ。
- Google Ads でのマッチングには、最大 48 時間かかる場合があります。

## <a name="set-up-connection-to-google-ads"></a>Google Ads への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**Google Ads** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. Google Ads の顧客 ID を入力します。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **Google 広告による認証** を選択し、Google 広告の認証情報を入力します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、Google Ads セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. 既存の環境を使用するするか、新しい環境を作成するかを選択します。
   - 既存の Google Ads オーディエンスを更新するには、[Google Ads オーディエンス ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns)を入力します。
   - 新しいオーディエンスを作成するには、Google オーディエンス ID フィールドを空白のままにします。 Customer Insights により、Google Ads アカウントに新しいオーディエンスが自動的に作成され、エクスポートされたセグメントの名前が使用されます。

1. **データ マッチング** セクションで、エクスポートする 1 つ以上のデータ フィールドを選択し、Customer Insights の対応するデータ フィールドを表すフィールドを選択します。

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
