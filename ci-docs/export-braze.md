---
title: セグメントを Braze にエクスポートする (プレビュー)
description: Braze への接続とエクスポートを構成する方法を説明します。
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081495"
---
# <a name="export-segments-to-braze-preview"></a>セグメントを Braze にエクスポートする (プレビュー)

統合顧客プロファイルのセグメントを Braze にエクスポートして、マーケティング活動に使用します。

## <a name="prerequisites"></a>前提条件

- [Braze アカウント](https://www.braze.com/)と対応する管理者資格情報。
- 既存の [Braze のセグメント](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/)。
- Customer Insights で [構成されたセグメント](segments.md)。
- エクスポートされたセグメントの統合顧客プロファイルには、メール アドレスと Braze 顧客 ID を表すフィールドが含まれています。

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

1. **エクスポートの接続** フィールドで、Braze セクションから接続を選択します。 このセクションが表示されない場合は、この種類の接続を利用できません。  

1. エクスポートの **表示名** を追加する

1. エクスポート先の Braze セグメントの API 識別子を **Braze セグメント API 識別子** フィールドに追加します。 識別子は、Braze プラットフォームのセグメントの詳細にあります。

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。 **顧客 ID** フィールドで、顧客の Braze ID を表すフィールドを選択します。 セグメントを Braze にエクスポートする必要があります。 オプションで、さらにフィールドを選択できます。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Braze へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft はそのようなデータをお客様の指示に従って転送しますが、Braze がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。

Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。
