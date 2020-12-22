---
title: Customer Insights のデータを Google 広告にエクスポートする
description: Google 広告への接続を構成する方法を説明します。
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568460"
---
# <a name="connector-for-google-ads-preview"></a>Google 広告用コネクタ (プレビュー)

統合顧客プロファイルのセグメントを Google 広告のオーディエンス リストにエクスポートし、それらを使用して Google 検索、Gmail、YouTube、Google ディスプレイ ネットワークに広告を掲載します。 

## <a name="prerequisites"></a>前提条件

-   [Google 広告アカウント](https://ads.google.com/) と対応する管理者資格情報があります。
-   Google 広告には既存のオーディエンスと対応する ID があります。 詳細については、[Google 広告のオーディエンス](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) を参照してください。
-   [セグメントを構成](segments.md) しました
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレス、名、姓を表示するフィールドが含まれています

## <a name="connect-to-google-ads"></a>Google Ads に接続する

1. **管理** > **エクスポート先** へと移動します。

1. **Google 広告** で **設定** を選択します。

1. **表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。

1. **[Google 広告の顧客 ID](https://support.google.com/google-ads/answer/1704344)** を入力します。

1. **[Google 広告で承認された開発者トークン](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** を入力します。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **[Google 広告オーディエンス ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** を入力して、**接続** を選択し、Google 広告への接続を初期化します。

1. **Google 広告による認証** を選択し、Google 広告の認証情報を入力します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Google 広告 接続のスクリーンショットをエクスポートする":::

1. **次へ** を選択してエクスポートを構成します。

## <a name="configure-the-connector"></a>コネクタの構成

1. **データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。 **名** フィールドと **姓** フィールドに同じ手順を繰り返します。

1. エクスポートするセグメントを選択します。 合計で最大 100 万の顧客プロファイルを Google 広告にエクスポートできます。

1. **保存** を選択します。

## <a name="export-the-data"></a>データをエクスポートする

[オンデマンドでデータをエクスポート](export-destinations.md) できます。 エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。 Google 広告では、セグメントが [Google 広告のオーディエンス](https://support.google.com/google-ads/answer/7558048?hl=en/) の下に表示されるようになりました。

## <a name="known-limitations"></a>既知の制限

- Google 広告 へのエクスポートごとに 100 万プロファイルまで。
- Google 広告へのエクスポートはセグメントに制限されています。
- プロバイダー側の制限により、合計 100 万のプロファイルを持つセグメントのエクスポートには、最大 5 分かかる場合があります。 
- Google 広告でのマッチングには、最大 48 時間かかる場合があります。

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Google 広告へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Google 広告がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。
