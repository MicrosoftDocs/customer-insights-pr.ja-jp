---
title: SFTP カスタム インポートによるエンリッチメント
description: SFTP カスタム インポート エンリッチメントに関する一般情報。
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595861"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>カスタム データで顧客プロファイルを強化する (プレビュー)

セキュリティで保護されたファイル転送プロトコル (SFTP) カスタム インポートを使用すると、データ統合のプロセスを行う必要のないデータをインポートできます。 これは、データを取り込むための柔軟で安全かつ簡単な方法です。 SFTP カスタム インポートは、エンリッチメントに必要な顧客プロファイル データをエクスポートできる [SFTP エクスポート](export-sftp.md) と組み合わせて使用できます。 次に、データを処理して強化し、SFTP カスタム インポートを使用して、エンリッチしたデータを Dynamics 365 Customer Insights の対象者に関するインサイト機能に戻すことができます。

## <a name="prerequisites"></a>前提条件

SFTP カスタム インポートを構成するには、次の前提条件が満たされている必要があります:

- データのインポート元となる SFTP の場所に、ユーザー資格情報 (ユーザー名とパスワード) があります。
- STFP ホストに URL とポート番号 (通常は22) があります。
- SFTP ホストにインポートするファイルのファイル名と場所があります。
- インポートするデータのスキーマを指定する *model.json* ファイルがあります。 このファイルは、インポートするファイルと同じディレクトリにある必要があります。
- [管理者](permissions.md#administrator) のアクセス許可があります。

## <a name="configuration"></a>構成

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。

1. **SFTP カスタム インポート タイル** で **データの強化** を選択します。

   > [!div class="mx-imgBorder"]
   > ![SFTP カスタム インポート タイル](media/SFTP_Custom_Import_tile.png "SFTP カスタム インポート タイル")

1. **開始する** を選択し、SFTP サーバーの資格情報とアドレスを指定します。 たとえば、sftp://mysftpserver.com:22 です。

1. データを含むファイルの名前と、ルート フォルダーにない場合は、SFTP サーバー上のファイルへのパスを入力します。

1. **カスタム インポート への接続** を選択して、すべての入力を確認します。

   > [!div class="mx-imgBorder"]
   > ![SFTP カスタム インポート構成ポップアップ](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP カスタム インポート構成ポップアップ")

## <a name="defining-field-mappings"></a>フィールド マッピングの定義 

SFTP サーバーにインポートするファイルを含むディレクトリには、*model.json* ファイルも含まれている必要があります。 このファイルは、データのインポートに使用するスキーマを定義します。 スキーマは、[Common Data Model](/common-data-model/) を使用して、フィールド マッピングを指定する必要があります。 model.json ファイルの簡単な例は次のようになります:

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
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
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

## <a name="enrichment-results"></a>強化の結果

エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。 [スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。 処理時間は、インポートするデータのサイズと SFTP サーバーへの接続によって異なります。

エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくインポートしたカスタム エンリッチメント データを確認できます。 さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。

**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。

## <a name="next-steps"></a>次の手順

エンリッチされた顧客データの上に構築します。 [セグメント](segments.md)、[メジャー](measures.md)、[データのエクスポート](export-destinations.md) を作成し、パーソナライズされたエクスペリエンスを顧客に提供します。




[!INCLUDE[footer-include](../includes/footer-banner.md)]