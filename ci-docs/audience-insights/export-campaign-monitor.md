---
title: Customer Insights データを Campaign Monitor にエクスポート
description: Campaign Monitor への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d2cc3ec944faa1d77ffb44e8abb422d753c5625d0ccef75cbb7efb14cb7c3741
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031893"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>セグメントを Campaign Monitor にエクスポート (プレビュー)

統合顧客プロファイルのセグメントを Campaign Monitor にエクスポートし、マーケティング活動に使用します。

## <a name="prerequisites"></a>前提条件

-   [Campaign Monitor アカウント](https://www.campaignmonitor.com/) と対応する管理者資格情報がある。
-   対象者に関するインサイトで [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。

## <a name="known-limitations"></a>既知の制限

- Campaign Monitor には、1 回のエクスポートにつき 100 万プロファイルまでエクスポートできます。
- Campaign Monitor へのエクスポートはセグメントに限定されます。
- 最大 100 万のプロファイルを Campaign Monitor にエクスポートすると、完了するまでに最大 20 分かかります。 
- Campaign Monitor にエクスポートできるプロファイルの数は、Campaign Monitor との契約によって異なり、制限されます。

## <a name="set-up-connection-to-campaign-monitor"></a>Campaign Monitor への接続を設定する

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**Campaign Monitor** を選択して接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **接続** を選択して、Campaign Monitor への接続を初期化します。

1. **Campaign Monitor による認証** を選択して、Campaign Monitor の管理者資格情報を入力します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、Campaign Monitor セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. [**Campaign Monitor リスト ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id) を入力します。    
   Campaign Monitor の **アカウント設定** から最初に [API キーを生成](https://www.campaignmonitor.com/api/getting-started/) し、API リスト ID を表示します。  

3. **データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。 セグメントを Campaign Monitor にエクスポートする必要があります。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Campaign Monitor へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンスの境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可することになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Campaign Monitor がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。

Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。
