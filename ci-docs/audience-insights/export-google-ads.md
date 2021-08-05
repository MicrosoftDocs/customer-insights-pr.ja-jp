---
title: Customer Insights のデータを Google 広告にエクスポートする
description: Google Ads への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c16967bf8ea1fd02b3f991d7b7d3715a71fa8681
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604283"
---
# <a name="export-segments-to-google-ads-preview"></a>セグメントを Google Ads にエクスポート (プレビュー)

統一された顧客プロファイルのセグメントを Google Ads 対象ユーザー リストにエクスポートし、それらを使用して Google 検索、Gmail、YouTube、および Google ディスプレイ ネットワークで宣伝できます。 

## <a name="prerequisites-for-connection"></a>接続の前提条件

-   [Google 広告アカウント](https://ads.google.com/) と対応する管理者資格情報があります。
-   [承認済みの Google Ads 開発者トークン](https://developers.google.com/google-ads/api/docs/first-call/dev-token) を所有していること。 
-   [カスタマー マッチのポリシー](https://support.google.com/adspolicy/answer/6299717) の要件を満たしていること。
-   [リマーケティング リスト サイズ](https://support.google.com/google-ads/answer/7558048) の要件を満たしていること。
-   Google 広告には既存のオーディエンスと対応する ID があります。 詳細については、[Google 広告のオーディエンス](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) を参照してください。
-   [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの統合された顧客プロファイルには、電子メール アドレス、姓、名を表示するフィールドが含まれています。

## <a name="known-limitations"></a>既知の制限

- Google 広告 へのエクスポートごとに 100 万プロファイルまで。
- Google 広告へのエクスポートはセグメントに制限されています。
- プロバイダー側の制限により、合計 100 万のプロファイルを持つセグメントのエクスポートには、最大 5 分かかる場合があります。 
- Google 広告でのマッチングには、最大 48 時間かかる場合があります。

## <a name="set-up-connection-to-google-ads"></a>Google Ads への接続を設定する

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**Google Ads** を選択して、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **[Google 広告の顧客 ID](https://support.google.com/google-ads/answer/1704344)** を入力します。

1. **[Google 広告で承認された開発者トークン](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** を入力します。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **Google 広告による認証** を選択し、Google 広告の認証情報を入力します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。 

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、Google Ads セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は利用できません。

1. **[Google 広告オーディエンス ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** を入力して、**接続** を選択し、Google 広告への接続を初期化します。

1. **データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。

1. エクスポートするセグメントを選択します。 合計で最大 100 万の顧客プロファイルを Google 広告にエクスポートできます。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 

[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Google 広告へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Google 広告がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエクスポート先はいつでも削除できます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
