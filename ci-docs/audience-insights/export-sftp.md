---
title: Customer Insights のデータを SFTP ホストにエクスポートする
description: SFTP ホストへの接続の構成方法を説明します。
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643509"
---
# <a name="connector-for-sftp-preview"></a>SFTP のコネクタ (プレビュー)

顧客データをセキュリティで保護されたファイル転送プロトコル (SFTP) ホストにエクスポートして、サード パーティ アプリケーションで使用します。

## <a name="prerequisites"></a>前提条件

- SFTP ホストと対応する資格情報の可用性。

## <a name="connect-to-sftp"></a>SFTP に接続

1. **管理** > **エクスポート先** へと移動します。

1. **SFTP** 配下で **設定** を選択します。

1. 出力先となる **表示名称** フィールドにはわかりやすい名前を付けます。

1. SFTP アカウントの **ユーザー名**、**パスワード**、**ホスト名** を入力します。 例: SFTP サーバーのルート フォルダーが /root/folder であり、データを /root/folder/ci_export_destination_folder にエクスポートする場合、ホストを sftp://<server_address>/ci_export_destination_folder" にする必要があります。

1. **検証する** を選択して接続をテストします。

1. 検証が正常に終了したら、データのエクスポート形式 (**圧縮** または **非圧縮**) を選択し、**フィールド区切り文字** を選択します。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **次へ** を選択して、エクスポートの構成を開始します。

## <a name="configure-the-connection"></a>接続を構成する

1. エクスポートをする **顧客の属性** を選択します。 1つまたは複数の属性をエクスポートできます。

1. **次へ** を選択します。

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

## <a name="export-the-data"></a>データをエクスポートする

[オンデマンドでデータをエクスポート](export-destinations.md) できます。 エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による SFTP 経由のデータ転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、エクスポート先がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。
