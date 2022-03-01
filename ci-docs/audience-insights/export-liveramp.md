---
title: LiveRamp コネクタ
description: データを LiveRamp にエクスポートする方法について説明します。
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667190"
---
# <a name="liverampreg-connector-preview"></a>LiveRamp&reg; コネクタ (プレビュー)

LiveRampでデータをアクティブ化して、デジタル、ソーシャル、テレビのエコシステム全体で 500 を超えるプラットフォームに接続します。 LiveRamp でデータを操作して、広告キャンペーンをターゲット設定、非表示、パーソナライズします。

## <a name="prerequisites"></a>前提条件

- このコネクタを使用するには、LiveRamp サブスクリプションが必要です。
- サブスクリプションを取得するには、直接 [LiveRamp に連絡](https://liveramp.com/contact/) します。 [LiveRamp オンボードについて](https://liveramp.com/our-platform/data-onboarding/)。

## <a name="connect-to-liveramp"></a>LiveRamp への接続

1. 対象者に関するインサイトで、**管理** > **エクスポート先** に移動します。

1. **LiveRamp** タイルで、**設定** を選択します。

1. 出力先となる **表示名称** フィールドにはわかりやすい名前を付けます。

1. LiveRamp Secure FTP (SFTP) アカウント の **ユーザー名** と **パスワード** を入力します。
これらの資格情報は、LiveRamp オンボードの資格情報とは異なる場合があります。

1. **検証** を選択して、LiveRamp への接続をテストします。

1. 検証に成功したら、**同意する** チェックボックスを選択して、**データのプライバシーとコンプライアンス** に同意します。

1. **次へ** を選択して、LiveRamp コネクタを設定します。

## <a name="configure-the-connector"></a>コネクタの構成

1. **キー識別子の選択** フィールドで、**メール**、**名前と住所**、または **電話** を選択して、ID 解決のために LiveRamp に送信します。

1. 選択したキー識別子に対応する統合顧客エンティティの対応する属性をマッピングします。

1. **属性を追加** を選択して、LiveRamp に送信する追加の属性をマップします。

   > [!TIP]
   > より多くのキー識別子属性を LiveRamp に送信すると、一致率が高くなる可能性があります。

1. LiveRamp にエクスポートするセグメントを選択します。

1. **保存** を選択します。

> [!div class="mx-imgBorder"]
> ![属性マッピング付きの LiveRamp コネクタ](media/export-liveramp-segments.png "属性マッピング付きの LiveRamp コネクタ")

## <a name="export-the-data"></a>データをエクスポートする

エクスポートのすべての前提条件が完了すると、まもなくエクスポートが開始されます。 エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。
エクスポートが正常に完了したら、LiveRamp オンボードにサインインして、データをアクティブ化して配布できます。

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Liveramp へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、LiveRamp がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。