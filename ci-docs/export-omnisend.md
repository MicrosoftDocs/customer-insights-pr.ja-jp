---
title: セグメントを Omnisend にエクスポート (プレビュー)
description: Omnisend への接続とエクスポートを構成する方法を説明します。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 15918b2e2550869115d30ea4d84b4549c3c7d1ca
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052287"
---
# <a name="export-segments-to-omnisend-preview"></a>セグメントを Omnisend にエクスポート (プレビュー)

統合された顧客プロファイルのセグメントを Omnisend にエクスポートし、マーケティング活動に使用します。

## <a name="prerequisites"></a>前提条件

-   [Omnisend アカウント](https://www.omnisend.com/) と対応する管理者資格情報があります。
-   Customer Insights で [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Omnisend へのエクスポートごとに最大 100 万の顧客プロファイルをエクスポートでき、完了するまでに最大 4 時間かかる場合があります。
- Omnisend へのエクスポートはセグメントに限定されています。
- Omnisend にエクスポートできる顧客プロファイルの数は、Omnisend との契約によって異なります。

## <a name="set-up-connection-to-omnisend"></a>Omnisend への接続を設定する

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**Omnisend** を選択して、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. [Omnisend API キー](https://support.omnisend.com/en/articles/1061890-generating-api-key) を入力します。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **接続** を選択して、Omnisend への接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、Omnisend セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。 セグメントを Omnisend にエクスポートする必要があります。 必要に応じて、名、姓、住所、国/地域、都道府県、市区町村、郵便番号をエクスポートし、パーソナライズされたメールを作成できます。 **属性の追加** を選択し、これらのフィールドをマップします。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Ommisend へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンスの境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可することになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Omnisend がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。

Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエクスポート先はいつでも削除できます。
