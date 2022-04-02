---
title: Customer Insights データを Iterable にエクスポートする
description: Iterable への接続とエクスポートを構成する方法を説明します。
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4de499fcc4a5a0dcc2dfd3bae02913c81a59647b
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524151"
---
# <a name="export-segment-lists-to-iterable-preview"></a>セグメント リストを Iterable にエクスポートする (プレビュー)

統合顧客プロファイルのセグメントを Iterable にエクスポートして、マーケティング活動に使用します。

## <a name="prerequisites"></a>前提条件

-   [Iterable アカウント](https://iterable.com/)と対応する管理者資格情報を保有しています。
-   対象者に関するインサイトで [セグメントを構成](segments.md) したこと。
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Iterable へのエクスポートはセグメントに制限されています。
- 最大 100 万の顧客プロファイルを Iterable にエクスポートすると、完了するまでに最大 30 分かかる場合があります。 
- Iterable にエクスポートできる顧客プロファイルの数は、Iterable との契約によって異なり、限定されます。

## <a name="set-up-connection-to-iterable"></a>Iterable への接続を設定します

1. **管理** > **接続** に移動します。

1. **接続の追加** を選択して **Iterable** を選択し、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. [Iterable API キー](https://support.iterable.com/hc/en-us/articles/360043464871)を入力してサインインを続行します。 

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **接続** を選択して Iterable への接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、Iterable セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

3. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。 セグメントを Iterable にエクスポートする必要があります。Iterable で作成されたリストには、Dynamics 365 Customer Insights のセグメント名とまったく同じ名前が付けられます。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Iterable へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft はそのようなデータをお客様の指示に従って転送しますが、Iterable がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。

Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。
