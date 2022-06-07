---
title: Customer Insights データを Criteo にエクスポートする
description: Criteo への接続とエクスポートを構成する方法を説明します。
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 854f5f0c53f053fc5d742d69a045db1926fec00c
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808771"
---
# <a name="export-segments-to-criteo-preview"></a>セグメントを Criteo にエクスポートする (プレビュー)

Unified customer profile のセグメントをエクスポートして、キャンペーンを生成してメール マーケティングを提供し、Criteo の特定の顧客グループを使用します。

## <a name="prerequisites-for-connection"></a>接続の前提条件

-   [Criteo と Dynamics のリターゲティング アカウント](https://www.criteo.com/login/)と、対応する管理者資格情報を保有しています。
-   [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの Unified customer profile には、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Criteo へのエクスポートごとに最大 100 万の顧客プロファイル。
- Criteo へのエクスポートはセグメントに制限されています。
- 合計 100 万の顧客プロファイルを持つセグメントをエクスポートすると、最大 30 分かかる場合があります。 
- Criteo にエクスポートできる顧客プロファイルの数は、Criteo との契約によって異なり、限定されます。

## <a name="set-up-connection-to-criteo"></a>Criteo への接続を設定します

1. **管理** > **接続** に移動します。

1. **接続の追加** を選択して **Criteo** を選択し、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認し、**接続** を選択して Criteo への接続を初期化します。

1. **Criteo で認証する** を選択し、Criteo の管理者ユーザー名と資格情報を提供します。 

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、Criteo セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。 

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。 

1. オプションで、**広告主 ID** と **名前** をエクスポートできます

1. エクスポートするセグメントを選択します。 

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Criteo へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft はそのようなデータをお客様の指示に従って転送しますが、Criteo がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。


[!INCLUDE[footer-include](includes/footer-banner.md)]
