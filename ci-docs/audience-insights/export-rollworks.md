---
title: Customer Insights データを RollWorks にエクスポート
description: RollWorks への接続とエクスポートを構成する方法を説明します。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 392084105628ba4e6008a1386a5ac80c809a004e
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225571"
---
# <a name="export-segments-to-rollworks-preview"></a>セグメントを RollWorks にエクスポート (プレビュー)

統合顧客プロファイルのセグメントを RollWorks にエクスポートし、広告に使用します。 

## <a name="prerequisites-for-a-connection"></a>接続の前提条件

-   [RollWorks アカウント](https://www.rollworks.com/) と対応する管理者資格情報がある。
-   対象者に関するインサイトで [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- RollWorks へのエクスポートごとに最大 250'000 の顧客プロファイルをエクスポートできます。
- 顧客プロファイルが 100 未満のセグメントを RollWorks にエクスポートすることはできません。 
- RollWorks へのエクスポートはセグメントに限定されています。
- 最大 250,000 の顧客プロファイルを RollWorks にエクスポートすると、完了するまでに最大 10 分かかる場合があります。 
- RollWorks にエクスポートできる顧客プロファイルの数は、RollWorks との契約によって異なり、限定されます。

## <a name="set-up-connection-to-rollworks"></a>RollWorks への接続を設定する

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**RollWorks** を選択して、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **接続** を選択して、RollWorks への接続を初期化します。

1. **RollWorks による認証** を選択して、RollWorks の管理者資格情報を入力します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、RollWorks セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. **RollWorks 広告者 ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles) を入力します。

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。 セグメントを RollWorks にエクスポートする必要があります。

1. エクスポートするセグメントを選択します。 メンバー数が 100 以上のセグメントを選択します。 小さいセグメントをエクスポートすることはできません。 さらに、エクスポートするセグメントの最大サイズは、エクスポートごとに 250'000 メンバーです。 

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による RollWorks へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンスの境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可することになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、RollWorks がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。

Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。
