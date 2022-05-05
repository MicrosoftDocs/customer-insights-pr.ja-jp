---
title: Customer Insights データを Constant Contact にエクスポート
description: Constant Contact への接続とエクスポートを構成する方法を説明します。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 310de0355f71829346f0e35508487e5962d6e912
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647315"
---
# <a name="export-segments-to-constant-contact-preview"></a>セグメントを Constant Contact にエクスポート (プレビュー)

統合顧客プロファイルのセグメントを Constant Contact にエクスポートし、マーケティング活動に使用します。 

## <a name="prerequisites-for-a-connection"></a>接続の前提条件

-   [Constant Contact アカウント](https://www.constantcontact.com/account-home) と対応する管理者資格情報がある。
-   Customer Insights で [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Constant Contact へのエクスポートごとに最大 100 万の顧客プロファイルをエクスポートできます。
- Constant Contact へのエクスポートはセグメントに限定されています。
- 最大 100 万の顧客プロファイルを Constant Contact にエクスポートすると、完了するまでに最大 1 時間かかる場合があります。 
- Constant Contact にエクスポートできる顧客プロファイルの数は、Constant Contact との契約によって異なり、限定されます。

## <a name="set-up-connection-to-constant-contact"></a>Constant Contact への接続を設定する

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**Constant Contact** を選択して接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **接続** を選択して、Constant Contact への接続を初期化します。

1. **コンスタントコンタクトで認証する** を選択し、コンスタント コンタクトの管理者認証情報を入力します。 

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、Constant Contact セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. [**Constant Contact リスト ID**](https://app.constantcontact.com/pages/contacts/ui#lists) を入力します。 Constant Contact でリストを開き、URL でリスト ID を検索します。

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。 セグメントを Constant Contact にエクスポートする必要があります。

1. オプションで、名 と 姓 を追加フィールドとしてエクスポートし、よりパーソナライズされた電子メールを作成できます。 **属性の追加** を選択し、これらのフィールドをマップします。

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Constant Contact へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンスの境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可することになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Constant Contact がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。

Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。
