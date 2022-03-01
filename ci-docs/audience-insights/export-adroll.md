---
title: Customer Insights のデータを AdRollにエクスポート
description: AdRoll への接続を構成する方法について説明します。
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697080"
---
# <a name="connector-for-adroll-preview"></a>AdRoll 用コネクタ (プレビュー)

統合顧客プロファイルのセグメントを AdRoll にエクスポートし、広告に使用します。 

## <a name="prerequisites"></a>前提条件

-   [AdRoll アカウント](https://www.adroll.com/) と対応する管理者資格情報があります。
-   対象者に関するインサイトで [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。

## <a name="connect-to-adroll"></a>AdRoll に接続する

1. **管理** > **エクスポート先** へと移動します。

1. **AdRoll** で **設定** を選択します。

1. **表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll 接続の構成ペイン。":::

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **接続** を選択して、AdRoll への接続を初期化します。

1. **AdRoll による認証** を選択し、AdRoll の管理者資格情報を入力します。 

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **AdRoll 広告者 ID** [AdRoll 広告](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles) を入力します。

1. **次へ** を選択してエクスポートを構成します。

## <a name="configure-the-connector"></a>コネクタの構成

1. **データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。 セグメントを AdRoll にエクスポートする必要があります。

1. エクスポートするセグメントを選択します。 メンバー数が 100 以上のセグメントを選択します。 小さいセグメントをエクスポートすることはできません。 さらに、エクスポートするセグメントの最大サイズは、エクスポートごとに 250'000 メンバーです。 

1. **保存** を選択します。

## <a name="export-the-data"></a>データをエクスポートする

[オンデマンドでデータをエクスポート](export-destinations.md) できます。 エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。

## <a name="known-limitations"></a>既知の制限

- 1 回のエクスポートで 250'000 プロファイルを AdRoll にエクスポートできます。
- プロファイルが 100 未満のセグメントを AdRoll にエクスポートできません。 
- AdRoll へのエクスポートはセグメントに制限されています。
- 最大 250'000 のプロファイルを AdRoll にエクスポートすると、完了するまでに最大 10 分かかる場合があります。 
- AdRoll にエクスポートできるプロファイルの数は、AdRoll との契約に依存し、制限されています。

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による AdRoll へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、AdRoll がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。

Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。
