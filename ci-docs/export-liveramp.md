---
title: セグメントを LiveRamp にエクスポート (プレビュー)
description: LiveRamp への接続とエクスポートを構成する方法を説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196722"
---
# <a name="export-segments-to-liverampreg-preview"></a>セグメントを LiveRamp&reg; にエクスポート (プレビュー)

LiveRamp でデータを有効にし、デジタル、ソーシャル、およびテレビなど 500 以上のプラットフォームに接続します。 LiveRamp でデータを操作して、広告キャンペーンをターゲット設定、非表示、パーソナライズします。

## <a name="prerequisites"></a>前提条件

- このコネクタを使用するための LiveRamp サブスクリプション。 サブスクリプションを取得するには、直接 [LiveRamp に連絡](https://liveramp.com/contact/) します。 [LiveRamp オンボードについて](https://liveramp.com/our-platform/data-onboarding/)。

## <a name="known-limitations"></a>既知の制限

- LiveRamp エクスポートは SFTP エクスポートを使用しています。 ファイアウォールの SFTP デスティネーションは現在サポートされていません。
- 認証に SSH キーを使用する場合は、必ず PEM または SSH.COM 形式として[秘密キーを作成](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) してください。 Putty を使用している場合は、Open SSH としてエクスポートして秘密キーを変換します。 以下の秘密キーがサポートされています。
  - OpenSSL PEM および ssh.com 形式の RSA
  - OpenSSL PEM および ssh.com 形式の DSA
  - OpenSSL PEM 形式の ECDSA 256/384/521
  - OpenSSH キー形式の ED25519 および RSA
- エクスポートの実行時間は、システムのパフォーマンスによって異なります。 サーバーの最小構成としては、2 つの CPU コアと 1Gb のメモリをお勧めします。
- 2 つの CPU コアと 1Gb のメモリの推奨される最小構成を使用する場合、最大 1 億件の顧客プロファイルを持つエンティティのエクスポートには 90 分かかる場合があります。
- LiveRamp にエクスポートできるプロファイル (またはデータ) の実際の数は、LiveRamp とのサブスクリプションによって異なります。

## <a name="set-up-connection-to-liveramp"></a>LiveRamp への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**LiveRamp** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. SSH を介して認証するか、接続のユーザー名/パスワードを使用するかを選択し、必要な詳細を入力します。

1. **検証** を選択して、LiveRamp への接続をテストします。

1. 検証に成功したら、[データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、LiveRamp セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. **データの接続** フィールドで、**メール**、**名前と住所**、または **電話** を選択して、ID 解決のために LiveRamp に送信します。

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="属性マッピング付きの LiveRamp コネクタ。":::

1. 選択したキー識別子の *Customer* エンティティから対応する属性をマッピングします。

1. **属性の追加** を選択し、送信する属性をさらに LiveRamp にマップします。

   > [!TIP]
   > より多くのキー識別子属性を LiveRamp に送信すると、一致率が高くなる可能性があります。

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
