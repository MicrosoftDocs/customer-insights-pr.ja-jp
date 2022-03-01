---
title: Customer Insights のデータを DotDigital にエクスポートする
description: DotDigital への接続を構成する方法を説明します。
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644454"
---
# <a name="connector-for-dotdigital-preview"></a>DotDigital 用コネクタ (プレビュー)

統合顧客プロファイルのセグメントを DotDigital のアドレス帳にエクスポートし、キャンペーン、電子メール マーケティング、および DotDigital で顧客セグメントを構築するために使用します。 

## <a name="prerequisites"></a>前提条件

-   [DotDigital アカウント](https://dotdigital.com/) と対応する管理者資格情報があります。
-   DotDigital には既存のアドレス帳と対応する ID があります。 アドレス帳を選択して開くと、URL に ID が表示されます。 詳細については、[DotDigital アドレス帳](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) を参照してください。
-   対象者に関するインサイトで [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。

## <a name="connect-to-dotdigital"></a>DotDigital への接続

1. **管理** > **エクスポート先** へと移動します。

1. **DotDigital** で **設定** を選択します。

1. **表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="DotDigital エクスポート の構成ペイン。":::

1. **DotDigital のユーザー名とパスワード** を入力します。

1. **[DotDigital アドレス帳 ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** を入力します。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **接続** を選択して、DotDigital への接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **次へ** を選択してエクスポートを構成します。

## <a name="configure-the-connector"></a>コネクタの構成

1. **データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。 **名**、**姓**、**氏名**、**性別**、**郵便番号** などの、他のオプション フィールドについても同じ手順を繰り返します。

1. エクスポートするセグメントを選択します。 合計で最大 100 万の顧客プロファイルを DotDigital にエクスポートできます。

1. **保存** を選択します。

## <a name="export-the-data"></a>データをエクスポートする

[オンデマンドでデータをエクスポート](export-destinations.md) できます。 エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。 DotDigital では、セグメントを [DotDigital アドレス帳](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) で検索できるようになりました。

## <a name="known-limitations"></a>既知の制限

- DotDigital へのエクスポートごとに 100 万プロファイルまで。
- DotDigital へのエクスポートはセグメントに制限されています。
- プロバイダー側の制限により、合計 100 万のプロファイルを持つセグメントのエクスポートには最大 3 時間かかる場合があります。 
- DotDigital にエクスポートできるプロファイルの数は、DotDigital との契約に依存し、制限されています。

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による DotDigital へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、DotDigital がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。
