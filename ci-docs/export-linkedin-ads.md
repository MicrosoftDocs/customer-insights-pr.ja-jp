---
title: セグメントを LinkedIn Ads にエクスポート (プレビュー)
description: LinkedIn Ads への接続とエクスポートを構成する方法を説明します。
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304709"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>セグメントを LinkedIn Ads にエクスポート (プレビュー)

統合された顧客プロファイルのセグメントを LinkedIn Ads にエクスポートして、Matched Audiences を作成します。 Matched Audiences を会社のターゲット設定と連絡先のターゲット設定に使用します。

## <a name="prerequisites"></a>前提条件

- [LinkedIn Campaign Manager アカウント](https://business.linkedin.com/marketing-solutions/ads) と対応する管理者資格情報。
- [LinkedIn Campaign Manager 取引先企業 ID](https://www.linkedin.com/help/lms/answer/a424270)。
- Customer Insights で [構成されたセグメント](segments.md)。
- エクスポートされたセグメントには、[取引先担当者ターゲット設定](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) また　LinkedIn で [企業ターゲット設定](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) を選択するかどうかに応じて、少なくとも 1 つの特定のフィールドが必要です。 [エクスポートの開始を構成する](#configure-an-export) 場合、可能なフィールドは、**データ マッチング** ステップで一覧表示されます。

## <a name="known-limitations"></a>既知の制限

- LinkedIn へのエクスポートあたり最大 10 万の顧客プロファイル。完了するまでに最大 10 分かかる場合があります。
- セグメントのみ。 セグメントには、少なくとも 300 の一意のプロファイルが含まれている必要があります。

## <a name="set-up-connection-to-linkedin-ads"></a>LinkedIn Ads への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**LinkedIn Ads** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. LinkedIn Campaign Manager アカウント ID を入力します。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **接続** を選択して、接続を初期化します。

1. **LinkedIn による認証** を選択して、LinkedIn Campaign Manager の管理者資格情報を入力します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、LinkedIn Ads セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. データをエクスポートして、LinkedInで [連絡先のターゲット設定](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) または [会社のターゲット設定](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) を行うかを選択します。

1. **データ マッチング** セクションの取引先担当者ターゲティングでは、顧客のメール アドレス、Apple Ad ID、Google Ad ID、Google ユーザー ID、または最初と姓を表すフィールドを少なくとも 1 つ選択します。 会社のターゲティングを選択する場合は、会社名、メール ドメイン、LinkedIn ページの URL、銘柄記号、または Web サイトを表すフィールドを少なくとも 1 つ選択します。

1. オプションで、フィールドを追加して、エクスポートをさらに定義できます。 **属性の追加** を選択し、これらのフィールドをマップします。

1. エクスポートするセグメントを選択します。 LinkedIn Campaign Manager の Matched Audiences は、エクスポートするために選択したセグメントの名前で自動的に作成されます。 各セグメントは、個別の Matched Audience になります。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
