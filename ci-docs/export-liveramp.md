---
title: セグメントを LiveRamp にエクスポート (プレビュー)
description: LiveRamp への接続とエクスポートを構成する方法を説明します。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 3e30a16dcb276fa6c951ad0b42ed0a4792f87ce3
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050769"
---
# <a name="export-segments-to-liverampreg-preview"></a>セグメントを LiveRamp&reg; にエクスポート (プレビュー)

LiveRamp でデータを有効にし、デジタル、ソーシャル、およびテレビなど 500 以上のプラットフォームに接続します。 LiveRamp でデータを操作して、広告キャンペーンをターゲット設定、非表示、パーソナライズします。

## <a name="prerequisites-for-a-connection"></a>接続の前提条件

- このコネクタを使用するには、LiveRamp サブスクリプションが必要です。
- サブスクリプションを取得するには、直接 [LiveRamp に連絡](https://liveramp.com/contact/) します。 [LiveRamp オンボードについて](https://liveramp.com/our-platform/data-onboarding/)。

## <a name="set-up-connection-to-liveramp"></a>LiveRamp への接続を設定する

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**LiveRamp** を選択して、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. LiveRamp Secure FTP (SFTP) アカウント の **ユーザー名** と **パスワード** を入力します。
これらの資格情報は、LiveRamp オンボードの資格情報とは異なる場合があります。

1. **検証** を選択して、LiveRamp への接続をテストします。

1. 検証に成功したら、**同意する** チェックボックスを選択して、**データのプライバシーとコンプライアンス** に同意します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、LiveRamp セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. **キー識別子の選択** フィールドで、**メール**、**名前と住所**、または **電話** を選択して、ID 解決のために LiveRamp に送信します。
   > [!div class="mx-imgBorder"]
   > ![属性マッピング付きの LiveRamp コネクタ。](media/export-liveramp-segments.png "属性マッピング付きの LiveRamp コネクタ")

1. 選択したキー識別子の *Customer* エンティティから対応する属性をマッピングします。

1. **属性の追加** を選択し、送信する属性をさらに LiveRamp にマップします。

   > [!TIP]
   > より多くのキー識別子属性を LiveRamp に送信すると、一致率が高くなる可能性があります。

1. LiveRamp にエクスポートするセグメントを選択します。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Liveramp へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、LiveRamp がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。

[!INCLUDE [footer-include](includes/footer-banner.md)]
