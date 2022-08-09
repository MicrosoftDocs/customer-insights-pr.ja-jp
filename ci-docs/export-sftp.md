---
title: データを SFTP ホストにエクスポートする (ビデオを含む)
description: SFTP ロケーションへの接続とエクスポートを構成する方法を説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207235"
---
# <a name="export-data-to-sftp-hosts-preview"></a>データを SFTP ホストにエクスポートする (プレビュー)

顧客データをセキュリティで保護されたファイル転送プロトコル (SFTP) ロケーションにエクスポートし、サード パーティ アプリケーションで使用します。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>前提条件

- SFTP ホストと対応する資格情報が必要です。

## <a name="known-limitations"></a>既知の制限

- ファイアウォールの SFTP デスティネーションは現在サポートされていません。
- エクスポートの実行時間は、システムのパフォーマンスによって異なります。 サーバーの最小構成としては、2 つの CPU コアと 1Gb のメモリをお勧めします。
- 2 つの CPU コアと 1Gb のメモリの推奨される最小構成を使用する場合、最大 1 億件の顧客プロファイル。90 分かかる場合があります。
- 認証に SSH キーを使用する場合は、必ず PEM または SSH.COM 形式として[秘密キーを作成](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) してください。 Putty を使用している場合は、Open SSH としてエクスポートして秘密キーを変換します。 以下の秘密キーがサポートされています。
  - OpenSSL PEM および ssh.com 形式の RSA
  - OpenSSL PEM および ssh.com 形式の DSA
  - OpenSSL PEM 形式の ECDSA 256/384/521
  - OpenSSH キー形式の ED25519 および RSA

## <a name="set-up-connection-to-sftp"></a>SFTP への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**SFTP** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. SSH を介して認証するか、接続のユーザー名/パスワードを使用するかを選択し、必要な詳細を入力します。 認証に SSH キーを使用する場合は、必ず PEM または SSH.COM 形式として[秘密キーを作成](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) してください。 Putty を使用している場合は、Open SSH としてエクスポートして秘密キーを変換します。 以下の秘密キーがサポートされています。
   - OpenSSL PEM および ssh.com 形式の RSA
   - OpenSSL PEM および ssh.com 形式の DSA
   - OpenSSL PEM 形式の ECDSA 256/384/521
   - OpenSSH キー形式の ED25519 および RSA

1. **検証する** を選択して接続をテストします。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、SFTP セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. データを **Gzip 形式** または **解凍済み** のどちらでエクスポートするか、およびエクスポートされたファイルの **フィールド区切り記号** を選択します。

1. エクスポートするエンティティ (セグメントなど) を選択します。

   > [!NOTE]
   > 選択した各エンティティは、エクスポート時に最大 5 つの出力ファイルに分割されます。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> 大量のデータを含むエンティティのエクスポートでは、エクスポートごとに同じフォルダーに複数の CSV ファイルが作成される場合があります。 エクスポートの分割は、エクスポートの完了にかかる時間を最小限にするためのパフォーマンス上の理由で実施されます。

[!INCLUDE [footer-include](includes/footer-banner.md)]
