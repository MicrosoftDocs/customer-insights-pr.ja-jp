---
title: Customer Insights のデータを DotDigital にエクスポートする
description: DotDigital への接続とエクスポートを構成する方法を説明します。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e3a79603f9f5746ee176d3d4299a30510c7459e
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618389"
---
# <a name="export-segments-to-dotdigital-preview"></a>セグメントを DotDigital にエクスポート (プレビュー)

統合顧客プロファイルのセグメントを DotDigital のアドレス帳にエクスポートし、キャンペーン、電子メール マーケティング、および DotDigital で顧客セグメントを構築するために使用します。 

## <a name="prerequisites-for-a-connection"></a>接続の前提条件

-   [DotDigital アカウント](https://dotdigital.com/)があり、[API ユーザー](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user)を作成している。 接続を作成するには、API ユーザーの資格情報を使用する必要がある
-   DotDigital には既存のアドレス帳と対応する ID があります。 アドレス帳を選択して開くと、URL に ID が表示されます。 詳細については、[DotDigital アドレス帳](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) を参照してください。
-   対象者に関するインサイトで [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- DotDigital へのエクスポートごとに最大 100 万の顧客プロファイル。
- DotDigital へのエクスポートはセグメントに制限されています。
- プロバイダー側の制限により、合計 100 万の顧客プロファイルを持つセグメントのエクスポートには最大 3 時間かかる場合があります。 
- DotDigital にエクスポートできる顧客プロファイルの数は、 DotDigital との契約によって異なり、限定されます。

## <a name="set-up-connection-to-dotdigital"></a>DotDigital への接続を設定する

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**DotDigital** を選択して接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **DotDigital API のユーザー名とパスワード** を入力します。 

1. **[DotDigital アドレス帳 ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** を入力します。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **接続** を選択して、DotDigital への接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。 

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、DotDigital セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。


1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。 **名**、**姓**、**氏名**、**性別**、**郵便番号** などの、他のオプション フィールドについても同じ手順を繰り返します。

1. エクスポートするセグメントを選択します。 合計で最大 100 万の顧客プロファイルを DotDigital にエクスポートできます。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 
 
DotDigital では、セグメントを [DotDigital アドレス帳](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) で検索できるようになりました。


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による DotDigital へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、DotDigital がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
