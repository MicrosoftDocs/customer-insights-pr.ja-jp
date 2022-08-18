---
title: SFTP カスタム インポートで顧客プロファイルをエンリッチする (プレビュー)
description: SFTP カスタム インポート エンリッチメントに関する一般情報。
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 831d1d3d3045379bbc5bcdcd4b05b8a147221f31
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237772"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>SFTP カスタム インポートで顧客プロファイルをエンリッチする (プレビュー)

セキュリティで保護されたファイル転送プロトコル (SFTP) カスタム インポートを使用すると、データ統合のプロセスを行う必要のないデータをインポートできます。 これは、データを取り込むための柔軟で安全かつ簡単な方法です。 SFTP カスタム インポートは、エンリッチメントに必要な顧客プロファイル データをエクスポートできる [SFTP エクスポート](export-sftp.md) と組み合わせて使用できます。 次に、データを処理して強化し、SFTP カスタム インポートを使用して、エンリッチメントされたデータを Dynamics 365 Customer Insights に戻すことができます。

## <a name="prerequisites"></a>前提条件

- SFTP ホスト上でインポートするファイルのファイル名と場所 (パス) がわかっていること。

- インポートするデータの Common Data Model スキーマを指定する *model.json* ファイルが用意されています。 このファイルは、インポートするファイルと同じディレクトリにある必要があります。

- SFTP [接続](connections.md) が [構成済み](#configure-the-connection-for-sftp-custom-import) であること。

## <a name="file-schema-example"></a>ファイルスキーマの例

SFTP サーバーにインポートするファイルを含むディレクトリには、*model.json* ファイルも含まれている必要があります。 このファイルは、データのインポートに使用するスキーマを定義します。 スキーマは、フィールド マッピングを指定するため、[共通データ モデル](/common-data-model/) を使用します。 model.json ファイルの簡単な例は次のようになります:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="configure-the-connection-for-sftp-custom-import"></a>SFTP カスタム インポートの接続を構成する

Customer Insights の [管理者](permissions.md#admin) であり、データをインポートする SFTP ロケーションのユーザー資格情報、URL、ポート番号を知っている必要があります。

1. エンリッチメントの構成時に **つながりの追加** を選択するか、または **管理** > **接続** に移動し、カスタム インポート タイルで **設定** を選択します。

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="接続の構成ページ インポートのカスタマイズ":::

1. 接続の名前を入力します。

1. インポートするデータが存在する SFTP サーバーの有効なユーザー名、パスワード、およびホスト URL を入力します。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **確認** を選択して設定を確認し、**保存** を選択します。

## <a name="configure-the-import"></a>インポートの構成

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。

1. **SFTP カスタム インポート** タイルで **データのエンリッチ** を選択します。

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP カスタム インポート タイル。":::

1. 概要を確認し、**次へ** を選択します。

1. 接続を選択します。 接続できない場合は、管理者に連絡してください。

1. **顧客データセット** を選択し、エンリッチするプロファイルまたはセグメントを選択します。 *顧客* エンティティは、すべての顧客プロファイルをエンリッチするのに対し、セグメントは、そのセグメントに含まれる顧客プロファイルのみをエンリッチします。

1. **次へ** を選択します。

1. インポートするデータファイルの **パス** と **ファイル名** を入力します。

1. **次へ** を選択します。

1. エンリッチメントと **出力エンティティ名** の **名前** を指定します。

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。

1. **実行** を選択してエンリッチメント処理を開始するか、閉じるを選択して **エンリッチメント** ページに戻ります。

## <a name="view-enrichment-results"></a>エンリッチメントの結果の表示

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>次の手順

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
