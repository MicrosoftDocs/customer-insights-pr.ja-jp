---
title: セグメントを Marketo にエクスポート (プレビュー)
description: Marketo への接続とエクスポートを構成する方法を説明します。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8cd24cf436bd5fdfd4ec3834d35baa1495e37ca4
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053211"
---
# <a name="export-segments-to-marketo-preview"></a>セグメントを Marketo にエクスポート (プレビュー)

統合顧客プロファイルのセグメントをエクスポートして、キャンペーンを生成し、電子メール マーケティングを提供して Marketo で特定の顧客グループを使用します。

## <a name="prerequisites-for-connection"></a>接続の前提条件

-   [Marketo アカウント](https://login.marketo.com/) と対応する管理者資格情報があります。
-   Marketo に既存のリストと対応する ID があります。 詳細については、[Marketo リスト](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) を参照してください。
-   [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Marketo へのエクスポートごとに最大 100 万の顧客プロファイル。
- Marketo へのエクスポートはセグメントに制限されています。
- 合計 100 万の顧客プロファイルを持つセグメントをエクスポートすると、最大 3 時間かかる場合があります。 
- Marketo にエクスポートできる顧客プロファイルの数は、Marketo との契約によって異なり、限定されます。

## <a name="set-up-connection-to-marketo"></a>Marketo への接続を設定する

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**Marketo** を選択して、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **[Marketo クライアント ID、クライアント シークレット、REST エンドポイントのホスト名](https://developers.marketo.com/rest-api/authentication/)** を入力します。 REST エンドポイントのホスト名はホスト名のみで、`https://` は含まれません。 例: `xyz-abc-123.mktorest.com`。 

1. **同意する** を選択して、**データのプライバシーとコンプライアンス** を確認し、**接続** を選択して、Marketo への接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、Marketo セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. **[Marketo リスト ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** を入力します。 リスト ID は純粋な数値です。 たとえば、Marketo リスト ID が ST12345A7 の場合、数字の前後の文字を削除して、`12345` を入力します。 

1. **データマッチング** セクションで、顧客のメール アドレスまたは顧客の Marketo ID を表すフィールドを少なくとも 1 つ選択します。 

1. オプションで、**名**、**姓**、**市**、**都道府県**、**国/地域** をエクスポートし、パーソナライズされたメールを作成できます。 **属性の追加** を選択し、これらのフィールドをマップします。

1. エクスポートするセグメントを選択します。 合計で最大 100 万の顧客プロファイルを Marketo にエクスポートできます。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 Marketo では、セグメントが [Marketo リスト](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) の下に表示されるようになりました。


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Marketo へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Marketo がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。


[!INCLUDE [footer-include](includes/footer-banner.md)]
