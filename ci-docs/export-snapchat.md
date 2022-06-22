---
title: Customer Insights データを Snapchat にエクスポート
description: Snapchat への接続とエクスポートを構成する方法を説明します。
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d64b482c322af8632e29ec41d6e34c390c5e646c
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947282"
---
# <a name="export-segments-to-snapchat-preview"></a>セグメントを Snapchat にエクスポート (プレビュー)

統合顧客プロファイルのセグメントを Snapchat にエクスポートし、広告に使用します。 

## <a name="prerequisites-for-a-connection"></a>接続の前提条件

-   [Snapchat ビジネス アカウント](https://business.snapchat.com/)、[Snapchat Ads アカウント](https://ads.snapchat.com/)、および対応する管理者資格情報がある。 組織アカウントのメンバーであり、特定の Ad アカウントのデータ管理者であることが必要です。 
-   Snapchat Audience Manager に SAM (Snap Audience Match) タイプの対象ユーザーが 1 人以上いること。 
-   Customer Insights で [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの Unified customer profile には、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Snapchat へのエクスポートはセグメントに限定されています。
- 最大 100 万の顧客プロファイルを Snapchat にエクスポートすると、完了するまでに最大 15 分かかる場合があります。 

## <a name="set-up-connection-to-snapchat"></a>Snapchat への接続を設定する

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**Snapchat** を選択して、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **接続** を選択して、Snapchat への接続を初期化します。

1. **Snapchat による認証** を選択して、Snapchat の管理者資格情報を入力します。 

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、Snapchat セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. [**Snapchat セグメント/対象者 ID**](https://businesshelp.snapchat.com/s/article/custom-audiences)を入力します。 対象ユーザー ID は、Snapchat Audience Manager でオーディエンスを選択した後の URL で確認することができます。 

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。 セグメントを Snapchat にエクスポートする必要があります。

1. エクスポートするセグメントを選択します。 

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Snapchat へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンスの境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可することになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Snapchat がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。

Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。
