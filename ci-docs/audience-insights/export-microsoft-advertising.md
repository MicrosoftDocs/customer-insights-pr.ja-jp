---
title: Customer Insights データを Microsoft Advertising にエクスポートする
description: Microsoft Advertising への接続とエクスポートを構成する方法を説明します。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 12fd221acb7c0eed443c9b860aca42dcb2b3788c
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618067"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>セグメントを MicrosoftAdvertising にエクスポート (プレビュー)

Customer Insights セグメントを Microsoft Advertising にエクスポートして、カスタマー マッチの対象者を作成します。 これらの対象者を広告キャンペーンに使用します。

## <a name="prerequisites"></a>前提条件

-   [Microsoft Advertising アカウント](https://ads.microsoft.com/) と対応する管理者資格情報。
-   カスタマー マッチの使用条件に同意しました。 
-   対象者に関するインサイトの [構成済みセグメント](segments.md)。
-   エクスポートされたセグメントの統合された顧客プロファイルには、メール アドレスのあるフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Microsoft Advertising へのエクスポートごとに最大 500'000 の顧客プロファイルをエクスポートできます。
- Microsoft Advertising へのエクスポートはセグメントに限定されています。
- 最大 500'000 の顧客プロファイルを Microsoft Advertising にエクスポートすると、完了するまでに最大 10 分かかる場合があります。 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Microsoft Advertising への接続を設定する

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**Microsoft Advertising** を選択して、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定は管理者です。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **接続** を選択して、Microsoft Advertising への接続を初期化します。

1. **Microsoft Advertising による認証** を選択して、Microsoft Advertising の管理者資格情報を入力します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、Microsoft Advertising セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. エクスポートするセグメントを選択します。 Microsoft Advertising のカスタマー マッチの対象者は、エクスポート用に選択されたセグメントの名前で自動的に作成されます。 各セグメントは、個別のカスタマー マッチの対象者になります。 

1. **Microsoft Advertising の顧客 ID とアカウントID** を入力します。 顧客 ID (`cid`) とアカウントID (`aid`) は、Microsoft Advertising にサインインしているときに URL のパラメーターで確認できます。

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスのフィールドを選択します。 セグメントを Microsoft Advertising にエクスポートする必要があります。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Microsoft Advertising へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンスの境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可することになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Microsoft Advertising がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。

Dynamics 365 Customer Insights の管理者は、このエクスポート先を、この機能の使用を停止するために、いつでも削除できます。
