---
title: Customer Insights のデータを SFTP ホストにエクスポートする
description: SFTP ホストへの接続の構成方法を説明します。
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268004"
---
# <a name="connector-for-sftp-preview"></a>SFTP のコネクタ (プレビュー)

顧客データをセキュリティで保護されたファイル転送プロトコル (SFTP) ホストにエクスポートして、サード パーティ アプリケーションで使用します。

## <a name="prerequisites"></a>前提条件

- SFTP ホストと対応する資格情報が必要です。

## <a name="connect-to-sftp"></a>SFTP に接続する

1. **管理** > **エクスポート先** へと移動します。

1. **SFTP** 配下で **設定** を選択します。

1. 出力先となる **表示名称** フィールドにはわかりやすい名前を付けます。

1. SFTP アカウントの **ユーザー名**、**パスワード**、**ホスト名**、および **エクスポート フォルダー** を入力します。

1. **検証する** を選択して接続をテストします。

1. 検証が成功したら、データ **Gzip 圧縮** または **解凍** をエクスポートするかどうか選択し、エクスポートされたファイルに対して **フィールド区切り文字** を選択します。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **次へ** を選択して、エクスポートの構成を開始します。

## <a name="configure-the-export"></a>エクスポートを構成する

1. エクスポートするエンティティ (セグメントなど) を選択します。

   > [!NOTE]
   > 選択した各エンティティは、エクスポート時に最大 5 つの出力ファイルになります。 

1. **保存** を選択します。

## <a name="export-the-data"></a>データをエクスポートする

[オンデマンドでデータをエクスポート](export-destinations.md) できます。 エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。

## <a name="known-limitations"></a>既知の制限

- エクスポートの実行時間は、システムのパフォーマンスによって異なります。 サーバーの最小構成としては、2 つの CPU コアと 1Gb のメモリをお勧めします。 
- 2 つの CPU コアと 1Gb のメモリの推奨される最小構成を使用する場合、最大 1 億件の顧客プロファイルを持つエンティティのエクスポートには 90 分かかる場合があります。 

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による SFTP 経由のデータ転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、エクスポート先がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]