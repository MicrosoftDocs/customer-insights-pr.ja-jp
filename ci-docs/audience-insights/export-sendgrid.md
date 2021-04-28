---
title: Customer Insights のデータを SendGrid にエクスポートする
description: SendGrid への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759771"
---
# <a name="export-segments-to-sendgrid-preview"></a>セグメントを SendGrid にエクスポート (プレビュー)

統合された顧客プロファイルのセグメントを SendGrid 取引先担当者リストにエクスポートし、SendGrid でのキャンペーンと E メール マーケティングに使用します。 

## <a name="prerequisites-for-a-connection"></a>接続の前提条件

-   [SendGrid アカウント](https://sendgrid.com/) と対応する管理者資格情報があります。
-   SendGrid に既存取引先担当者リストと対応する ID があります。 詳細については、[SendGrid - 取引先担当者を管理する](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)を参照してください。
-   対象者に関するインサイトで [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの統合顧客プロファイルには、電子メール アドレスを表示するフィールドが含まれています。

## <a name="known-limitations"></a>既知の制限

- SendGrid に合計で最大 10 万件のプロファイル。
- SendGrid へのエクスポートはセグメントに制限されています。
- 最大 10 万件のプロファイルを SendGrid にエクスポートすると、完了するまでに最大で数時間かかる場合があります。 
- SendGrid にエクスポートできるプロファイルの数は、SendGrid との契約に依存し、制限されています。

## <a name="set-up-connection-to-sendgrid"></a>SendGrid への接続を設定する

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**SendGrid** を選択して、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **SendGrid API キー** [SendGrid APIキー](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)を入力します。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **接続** を選択して、SendGrid への接続を初期化します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、SendGrid セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. **[SendGrid リスト ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** を入力します。

1. **データの照合** セクションの **電子メール** フィールドで、顧客の電子メール アドレスを表す統合顧客プロファイルのフィールドを選択します。 **名**、**姓**、**国/リージョン**、**州**、**市町村**、および **郵便番号** などの、他のオプション フィールドについても同じ手順を繰り返します。

1. エクスポートするセグメントを選択します。 SendGrid に対しては **合計で 10 万件を超える顧客プロファイルは、エクスポートしないことをお勧めします**。 

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による SendGrid へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、SendGrid がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]