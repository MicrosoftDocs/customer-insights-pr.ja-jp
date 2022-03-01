---
title: Customer Insights のデータを Autopilot にエクスポートする
description: Autopilot への接続を構成する方法を説明します。
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269244"
---
# <a name="connector-for-autopilot-preview"></a>Autopilot 用コネクタ (プレビュー)

統合された顧客プロファイルのセグメントを Autopilot にエクスポートし、Autopilot での E メール マーケティングに使用します。 

## <a name="prerequisites"></a>前提条件

-   [Autopilot 広告アカウント](https://www.autopilothq.com/) と対応する管理者資格情報があります。
-   対象者に関するインサイトで [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。

## <a name="connect-to-autopilot"></a>Autopilot に接続する

1. **管理** > **エクスポート先** へと移動します。

1. **Autopilot** で **設定** を選択します。

1. **表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Autopilot 接続の構成ペイン。":::

1. **Autopilot API キー** [自動操縦 API キー](https://autopilot.docs.apiary.io/#)を入力します。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **接続** を選択して、Autopilot への接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **次へ** を選択してエクスポートを構成します。

## <a name="configure-the-connector"></a>コネクタの構成

1. **データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。 **名**、**姓** など、他の任意フィールドに同じ手順を繰り返します。

1. エクスポートするセグメントを選択します。 Autopilot に対しては **合計で 10 万件を超える顧客プロファイルは、エクスポートしないことをお勧めします**。 

1. **保存** を選択します。

## <a name="export-the-data"></a>データをエクスポートする

[オンデマンドでデータをエクスポート](export-destinations.md) できます。 エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。

## <a name="known-limitations"></a>既知の制限

- 合計で最大 10 万の顧客プロファイルを Autopilot にエクスポートできます。
- Autopilot へのエクスポートはセグメントに制限されています。
- 最大 10 万件のプロファイルを Autopilot にエクスポートすると、完了するまでに最大で数時間かかる場合があります。 
- Autopilot にエクスポートできるプロファイルの数は、Autopilot との契約に依存し、制限されています。

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Autopilot へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Autopilot がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]