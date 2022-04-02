---
title: Customer Insights データを Braze にエクスポートする
description: Braze への接続とエクスポートを構成する方法を説明します。
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8d7cf95c1f157c771b2d655346464e5af03d73b9
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524154"
---
# <a name="export-segment-lists-to-braze-preview"></a>セグメント リストを Braze にエクスポートする (プレビュー)

統合顧客プロファイルのセグメントを Braze にエクスポートして、マーケティング活動に使用します。

## <a name="prerequisites"></a>前提条件

-   [Braze アカウント](https://www.braze.com/)と対応する管理者資格情報を保有しています。
-   対象者に関するインサイトで [セグメントを構成](segments.md) したこと。
-   エクスポートされたセグメントの統合顧客プロファイルには、メール アドレスと Braze 顧客 ID を表すフィールドが含まれています。 

## <a name="known-limitations"></a>既知の制限

- Braze へのエクスポートはセグメントに制限されています。
- 最大 100 万の顧客プロファイルを Braze にエクスポートすると、完了するまでに最大 40 分かかる場合があります。 
- Braze にエクスポートできる顧客プロファイルの数は、Braze との契約によって異なり、限定されます。

## <a name="set-up-connection-to-braze"></a>Braze への接続を設定します

1. **管理** > **接続** に移動します。

1. **接続の追加** を選択して **Braze** を選択し、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. [Braze API キー](https://www.braze.com/docs/api/basics/)を入力してサインインを続行します。 

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **接続** を選択して Braze への接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、Braze セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。  

3. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択し、[顧客 ID] フィールドで、顧客の Braze ID を表すフィールドを選択します。 セグメントを Braze にエクスポートする必要があります。 Braze のセグメントは、Dynamics 365 Customer Insights のセグメントと同じ名前で作成されます。 データを照合するための追加のオプション フィールドを選択できます。 

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Braze へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft はそのようなデータをお客様の指示に従って転送しますが、Braze がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。

Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。
