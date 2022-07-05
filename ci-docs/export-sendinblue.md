---
title: セグメントを Sendinblue にエクスポートする (プレビュー)
description: 接続を構成して、Sendinblue にエクスポートする方法を学びます。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f6550b5c57866702631b4c294bb059279461bd6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081682"
---
# <a name="export-segments-to-sendinblue-preview"></a>セグメントを Sendinblue にエクスポートする (プレビュー)

統合された顧客プロファイルのセグメントをエクスポートして、キャンペーンを生成したり、電子メール マーケティングを行ったり、Sendinblue で特定の顧客グループを使用したりすることができます。

## <a name="prerequisites-for-connection"></a>接続の前提条件

-   [Sendinblue アカウント](https://www.sendinblue.com/) および対応する管理者資格情報を所有していること。
-   Sendinblue には既存のリストと対応する ID があること。
-   [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Sendinblue へのエクスポートごとに最大 100 万の顧客プロファイル。
- Sendinblue へのエクスポートはセグメントに制限されています。
- 合計 100 万の顧客プロファイルを持つセグメントをエクスポートすると、最大 90 分かかる場合があります。 
- Sendinblue にエクスポートできる顧客プロファイルの数は、Sendinblue との契約によって異なり、限定されます。

## <a name="set-up-connection-to-sendinblue"></a>Sendinblue への接続を設定する

1. **管理** > **接続** に移動します。

1. **接続の追加** を選択し、**Sendinblue** を選んで、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **[Sendinblue API キー](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)** を入力します。

1. **同意する** を選択して、**データのプライバシーとコンプライアンス** を確認し、**接続** を選択して、Sendinblue への接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポート用の接続** フィールドで、Sendinblue セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. **Sendinblue リスト ID** を入力します 

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。 

1. オプションで、**姓**、**名**、および **電話番号** をエクスポートして、よりパーソナライズされた電子メールを作成できます。 **属性の追加** を選択し、これらのフィールドをマップします。

1. エクスポートするセグメントを選択します。 

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights から Sendinblue へのデータ送信を可能にすると、Dynamics 365 Customer Insights のコンプライアンスの範囲を越えて、個人情報などの機密性の高い情報が潜在的に含まれるデータの転送を許可することになります。 Microsoft はお客様の指示でそのようなデータを送信することがありますが、Sendinblue が関係するプライバシーまたはセキュリティのすべての義務を満たすよう見届ける責任はお客様にあります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエクスポート先はいつでも削除できます。


[!INCLUDE [footer-include](includes/footer-banner.md)]
