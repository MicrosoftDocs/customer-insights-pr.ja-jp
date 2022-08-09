---
title: セグメントを MicrosoftAdvertising にエクスポート (プレビュー)
description: Microsoft Advertising への接続とエクスポートを構成する方法を説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196538"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>セグメントを MicrosoftAdvertising にエクスポート (プレビュー)

Customer Insights セグメントを Microsoft Advertising にエクスポートして、カスタマー マッチの対象者を作成します。 これらの対象者を広告キャンペーンに使用します。

## <a name="prerequisites"></a>前提条件

- [Microsoft Advertising アカウント](https://ads.microsoft.com/) と対応する管理者資格情報。
- Microsoft Advertising の顧客 ID とアカウントID。 顧客 ID (`cid`) とアカウントID (`aid`) は、Microsoft Advertising にサインインしているときに URL のパラメーターで確認します。
- Customer Match の使用条件に同意している。
- Customer Insights で [構成されたセグメント](segments.md)。
- エクスポートされたセグメントの Unified customer profile には、電子メール アドレスを表示するフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- Microsoft Advertising へのエクスポートあたり最大 500'000 の顧客プロファイル。最大 10 分かかる場合があります。
- セグメントのみ。

## <a name="set-up-connection-to-microsoft-advertising"></a>Microsoft Advertising への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**Microsoft Advertising** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定は管理者です。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **Microsoft Advertising 顧客 ID** を入力します。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **接続** を選択して、接続を初期化します。

1. **Microsoft Advertising による認証** を選択して、Microsoft Advertising の管理者資格情報を入力します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、Microsoft Advertising セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. エクスポートするセグメントを選択します。 Microsoft Advertising のカスタマー マッチの対象者は、エクスポート用に選択されたセグメントの名前で自動的に作成されます。 各セグメントは、個別のカスタマー マッチの対象者になります。

1. **Microsoft Advertising の顧客 ID とアカウントID** を入力します。

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスのフィールドを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
