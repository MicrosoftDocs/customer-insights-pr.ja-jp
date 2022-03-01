---
title: Customer Insights データを Klaviyo にエクスポートする
description: 接続を構成して、Klaviyo にエクスポートする方法を説明します。
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7c1297fd5381c00c07d6501186c51fe4798773d1
ms.sourcegitcommit: 205f931ec671a0ab1850f2c1c94df3307ffb62c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "7385794"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>セグメント リストを Klaviyo にエクスポートする (プレビュー)

統合された顧客プロファイルのセグメントを Klaviyo にエクスポートし、マーケティング活動に使用します。

## <a name="prerequisites"></a>前提条件

-   [Klaviyo アカウント](https://www.klaviyo.com/) および対応する管理者資格情報を所有していること。
-   対象者に関するインサイトで [セグメントを構成](segments.md) したこと。
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Klaviyo へのエクスポートごとに最大100,000 件のプロファイルをエクスポートできます。
- Klaviyo へのエクスポートはセグメントに制限されています。
- 最大 100 万件のプロファイルを Klaviyo にエクスポートすると、完了するまでに最大 20 分かかる場合があります。 
- Klaviyo にエクスポートできるプロファイルの数は、Klaviyo との契約内容に制限されます。

## <a name="set-up-connection-to-klaviyo"></a>Klaviyo への接続を設定する

1. **管理** > **接続** に移動します。

1. **接続の追加** を選択し、**Klaviyo** を選択し、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. ご利用の [Klaviyo API キー](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) を入力してログインを続行します。 

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. Klaviyo への接続を開始するには、**接続** を選択します。

1. **Klaviyo で認証する** を選択し、Klaviyo の管理者認証情報を入力します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポート用の接続** フィールドで、Klaviyo セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. [**Klaviyo リスト ID**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID) を入力します。     

3. **データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。 セグメントを Klaviyo にエクスポートする必要があります。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights から Klaviyo へのデータ送信を可能にすると、Dynamics 365 Customer Insights のコンプライアンスの範囲を越えて、個人情報などの機密性の高い情報が潜在的に含まれるデータの転送を許可することになります。 マイクロソフトは、お客様の指示により当該データを転送しますが、お客様は、Klaviyo がお客様の持つプライバシーまたはセキュリティに関する義務を確実に果たす責任を負います。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。

Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。
