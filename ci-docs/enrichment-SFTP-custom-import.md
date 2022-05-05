---
title: SFTP カスタム インポートによるエンリッチメント
description: SFTP カスタム インポート エンリッチメントに関する一般情報。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f52d24cbe793bee7948ad2af31059cd3edf40f94
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646541"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>カスタム データで顧客プロファイルを強化する (プレビュー)

セキュリティで保護されたファイル転送プロトコル (SFTP) カスタム インポートを使用すると、データ統合のプロセスを行う必要のないデータをインポートできます。 これは、データを取り込むための柔軟で安全かつ簡単な方法です。 SFTP カスタム インポートは、エンリッチメントに必要な顧客プロファイル データをエクスポートできる [SFTP エクスポート](export-sftp.md) と組み合わせて使用できます。 次に、データを処理して強化し、SFTP カスタム インポートを使用して、エンリッチメントされたデータを Dynamics 365 Customer Insights に戻すことができます。

## <a name="prerequisites"></a>前提条件

SFTP カスタム インポートを構成するには、次の前提条件が満たされている必要があります:

- SFTP ホストにインポートするファイルのファイル名と場所 (パス) があること。
- インポートするデータの [Common Data Model スキーマ](/common-data-model/) を指定する *model.json* ファイルがある。 このファイルは、インポートするファイルと同じディレクトリにある必要があります。
- SFTP 接続は既に管理者によって構成されている、*または* [管理者](permissions.md#admin) アクセス許可を所有していること。 データのインポート元となる SFTP ロケーションに対して、ユーザー資格情報、URL、およびポート番号が必要です。


## <a name="configure-the-import"></a>インポートの構成

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。

1. **SFTP カスタム インポート タイル** で **データのエンリッチ** を選択し、**開始する** を選択します。

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP カスタム インポート タイル。":::

1. ドロップダウン リストから [接続](connections.md) を選択してください。 接続できない場合は、管理者に連絡してください。 管理者の場合は、**接続の追加** を選択して、ドロップダウン リストから **SFTP カスタム インポート** を選択することで、接続を作成できます。

1. **カスタム インポートに接続する** を選択し、選択した接続を確認します。

1.  **次へ** を選択して、インポートするデータファイルの **パス** および **ファイル名** を入力します。

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="データの場所を入力する際のスクリーンショット。":::

1. **次へ** を選択して、顧客データ セットを選択します。 これは、すべての顧客プロファイルまたはセグメントのいずれかです。

1. **次へ** を選択し、エンリッチメントの名前と出力エンティティの名前を指定します。 

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。

## <a name="configure-the-connection-for-sftp-custom-import"></a>SFTP カスタム インポートの接続を構成する 

接続を構成するには、管理者である必要があります。 エンリッチメントの構成時に **つながりの追加** を選択するか、*または* **管理** > **接続** に移動し、カスタム インポート タイルで **設定** を選択します。

1. **表示名** ボックスに接続の名前を入力します。

1. インポートするデータが存在する SFTP サーバーの有効なユーザー名、パスワード、およびホスト URL を入力します。

1. 内容を確認し、**同意する** チェックボックスを選択して、**データのプライバシーとコンプライアンス** に同意してください。

1. **検証** を選択して、構成を検証します。

1. 確認が完了したら、**保存** を選択して接続を保存できます。

   > [!div class="mx-imgBorder"]
   > ![Experian 接続の構成ページ。](media/enrichment-SFTP-connection.png "Experian 接続の構成ページ")


## <a name="defining-field-mappings"></a>フィールド マッピングの定義 

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

## <a name="next-steps"></a>次のステップ

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
