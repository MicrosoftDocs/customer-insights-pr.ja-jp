---
title: Customer Insights データを LinkedIn Ads にエクスポート
description: LinkedIn Ads への接続とエクスポートを構成する方法を説明します。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7a6bb466652b8703a4784329a5e675965f557e82
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231109"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>セグメントを LinkedIn Ads にエクスポート (プレビュー)

統合された顧客プロファイルのセグメントを LinkedIn Ads にエクスポートして、Matched Audiences を作成します。 Matched Audiences を会社のターゲット設定と連絡先のターゲット設定に使用します。

## <a name="prerequisites"></a>前提条件

-   [LinkedIn Campaign Manager アカウント](https://business.linkedin.com/marketing-solutions/ads) と対応する管理者資格情報があります。
-   対象者に関するインサイトで [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの顧客プロファイルには、メール アドレスのあるフィールドが含まれています。

## <a name="known-limitations"></a>既知の制限

- Customer Insights のセグメントには、一意のプロファイルを少なくとも 300 件含める必要があります。 
- LinkedIn Ads へのエクスポートごとに最大 10 万の顧客プロファイルをエクスポートできます。
- LinkedIn Ads へのエクスポートはセグメントに限定されています。
- 最大 10 万の顧客プロファイルを LinkedIn Ads にエクスポートすると、完了するまでに最大 10 分かかる場合があります。 

## <a name="set-up-the-connection-to-linkedin-ads"></a>LinkedIn Ads への接続を設定する

1. 対象者に関するインサイトで、**管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**LinkedIn Ads** を選択して、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者です。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. [LinkedIn Campaign Manager アカウント ID](https://www.linkedin.com/help/lms/answer/a424270) を入力します。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **接続** を選択して、Campaign Monitor への接続を初期化します。

1. **LinkedIn による認証** を選択して、LinkedIn Campaign Manager の管理者資格情報を入力します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、エクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、LinkedIn Ads セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. データをエクスポートして、LinkedInで [連絡先のターゲット設定](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) または [会社のターゲット設定](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) を行うかを選択します。 

1. **データ マッチング** セクションの取引先担当者ターゲティングでは、顧客のメール アドレス、Apple Ad ID、Google Ad ID、Google ユーザー ID、または最初と姓を表すフィールドを少なくとも 1 つ選択します。 会社のターゲティングを選択する場合は、会社名、メール ドメイン、LinkedIn ページの URL、銘柄記号、または Web サイトを表すフィールドを少なくとも 1 つ選択します。 追加のフィールドを選択して、エクスポートをさらに定義できます。 

1. エクスポートするセグメントを選択します。 LinkedIn Campaign Manager の Matched Audiences は、エクスポートするために選択したセグメントの名前で自動的に作成されます。 各セグメントは、個別の Matched Audience になります。 

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による LinkedIn Ads へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンスの境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可することになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、LinkedIn Ads がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。

Dynamics 365 Customer Insights の管理者は、このエクスポート先を、この機能の使用を停止するために、いつでも削除できます。
