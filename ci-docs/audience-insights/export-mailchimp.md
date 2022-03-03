---
title: Customer Insights のデータを Mailchimp にエクスポートする
description: Mailchimp への接続とエクスポートを構成する方法を説明します。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f7a33f2eddb6b625ddb8663b97103de75beab44c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226852"
---
# <a name="export-segments-to-mailchimp-preview"></a>セグメントを Mailchimp にエクスポート (プレビュー)

統合顧客プロファイルのセグメントを Mailchimp にエクスポートして、ニュースレターと電子メール キャンペーンを作成します。

## <a name="prerequisites-for-connection"></a>接続の前提条件

-   [Mailchimp アカウント](https://mailchimp.com/) と対応する管理者資格情報があります。
-   Mailchimp に既存のオーディエンスと対応する ID があります。 詳細については、[Mailchimp オーディエンス](https://mailchimp.com/help/create-audience/) を参照してください。
-   [セグメントを構成](segments.md) しました
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Mailchimp へのエクスポートごとに最大 100 万の顧客プロファイル。
- Mailchimp へのエクスポートはセグメントに制限されています。
- 100 万の顧客プロファイルを持つセグメントをエクスポートすると、最大 3 時間かかる場合があります。 
- Mailchimp にエクスポートできる顧客プロファイルの数は、Mailchimp との契約によって異なり、限定されます。

## <a name="set-up-connection-to-mailchimp"></a>Mailchimp への接続を設定する

1. **管理** > **接続** に移動します。

1. **接続の追加** を選択し、**Mailchimp** を選んで、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **接続** を選択して、Mailchimp への接続を初期化します。

1. **Mailchimp による認証** を選択し、Mailchimp の認証情報を入力します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。 

## <a name="configure-the-connector"></a>コネクタの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ**> **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、Mailchimp セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. **[Mailchimp 対象者 ID](https://mailchimp.com/help/find-audience-id/)** を入力します

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。 

1. オプションで、**名** と **姓** をエクスポートし、パーソナライズされたメールを作成できます。 **属性の追加** を選択し、これらのフィールドをマップします。

1. エクスポートするセグメントを選択します。 合計で最大 100 万の顧客プロファイルを Mailchimp にエクスポートできます。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Mailchimp へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Mailchimp がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
