---
title: Customer Insights のデータを Marketo にエクスポートする
description: Marketo への接続を構成する方法を説明します。
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570409"
---
# <a name="connector-for-marketo-preview"></a>Marketo 用コネクタ (プレビュー)

統合顧客プロファイルのセグメントをエクスポートして、キャンペーンを生成し、電子メール マーケティングを提供して Marketo で特定の顧客グループを使用します。

## <a name="prerequisites"></a>前提条件

-   [Marketo アカウント](https://login.marketo.com/) と対応する管理者資格情報があります。
-   Marketo に既存のリストと対応する ID があります。 詳細については、[Marketo リスト](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) を参照してください。
-   [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。

## <a name="connect-to-marketo"></a>Marketo への接続

1. **管理** > **エクスポート先** へと移動します。

1. **Marketo** で **設定** を選択します。

1. **表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。

1. **[Marketo クライアント ID、クライアント シークレット、REST エンドポイントのホスト名](https://developers.marketo.com/rest-api/authentication/)** を入力します。

1. **[Marketo リスト ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** を入力します 

1. **同意する** を選択して、**データのプライバシーとコンプライアンス** を確認し、**接続** を選択して、Marketo への接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Marketo 接続のスクリーンショットをエクスポートする":::

1. **次へ** を選択してエクスポートを構成します。

## <a name="configure-the-connector"></a>コネクタの構成

1. **データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。 

1. オプションで、**名**、**姓**、**市**、**都道府県**、**国/地域** を追加フィールドとしてエクスポートし、よりパーソナライズされた電子メールを作成できます。 **属性の追加** を選択し、これらのフィールドをマップします。

1. エクスポートするセグメントを選択します。 合計で最大 100 万の顧客プロファイルを Marketo にエクスポートできます。

   :::image type="content" source="media/export-segment-marketo.png" alt-text="フィールドとセグメントを選択して、Marketo にエクスポートする":::

1. **保存** を選択します。

## <a name="export-the-data"></a>データをエクスポートする

[オンデマンドでデータをエクスポート](export-destinations.md) できます。 エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。 Marketo では、セグメントが [Marketo リスト](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) の下に表示されるようになりました。

## <a name="known-limitations"></a>既知の制限

- Marketo へのエクスポートごとに 100 万プロファイルまで。
- Marketo へのエクスポートはセグメントに制限されています。
- 合計 100 万のプロファイルを持つセグメントのエクスポートには、最大 3 時間かかる場合があります。 
- Marketo にエクスポートできるプロファイルの数は、Marketo との契約に依存し、制限されています。

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Marketo へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Marketo がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。
