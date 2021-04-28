---
title: SFTP カスタム インポートによるエンリッチメント
description: SFTP カスタム インポート エンリッチメントに関する一般情報。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896287"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>カスタム データで顧客プロファイルを強化する (プレビュー)

セキュリティで保護されたファイル転送プロトコル (SFTP) カスタムインポートでは、データ統合のプロセスを必要としないデータをインポートできます。 これは、データを取り込むための柔軟で安全かつ簡単な方法です。 SFTP カスタム インポートは、エンリッチメントに必要な顧客プロファイル データをエクスポートできる [SFTP エクスポート](export-sftp.md) と組み合わせて使用できます。 次に、データを処理して強化し、SFTP カスタム インポートを使用して、エンリッチしたデータを Dynamics 365 Customer Insights の対象者に関するインサイト機能に戻すことができます。

## <a name="prerequisites"></a>前提条件

SFTP カスタム インポートを構成するには、次の前提条件が満たされている必要があります:

- SFTP ホスト上に、インポートするファイルのファイル名とロケーション (パス) がある。
- インポートするデータの [Common Data Model スキーマ](/common-data-model/) を指定する *model.json* ファイルがある。 このファイルは、インポートするファイルと同じディレクトリにある必要があります。
- SFTP 接続は既に管理者によって構成されている、*または* [管理者](permissions.md#administrator) アクセス許可を所有していること。 データのインポート元となる SFTP ロケーションに対して、ユーザー資格情報、URL、およびポート番号が必要です。


## <a name="configure-the-import"></a>インポートの構成

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。

1. **SFTP カスタム インポート タイル** で **データのエンリッチ** を選択し、**開始する** を選択します。

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP カスタム インポート タイル。":::

1. ドロップダウンから [接続](connections.md) を選択します。 接続できない場合は、管理者に連絡してください。 管理者の場合は、**つながりの追加** を選択し、ドロップダウンから **SFTP カスタム インポート** を選択することで、接続を作成できます。

1. **カスタム インポートに接続する** を選択し、選択した接続を確認します。

1.  **次へ** 選択し、インポートするデータファイルの **ファイル名** と **パス** を入力します。

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="データの場所を入力する際のスクリーンショット。":::

1. **次へ** を選択し、エンリッチメントの名前と出力エンティティの名前を指定します。 

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。

## <a name="configure-the-connection-for-sftp-custom-import"></a>SFTP カスタム インポートの接続を構成する 

接続を構成するには、管理者である必要があります。 エンリッチメントの構成時に **つながりの追加** を選択するか、*または* **管理** > **接続** に移動し、カスタム インポート タイルで **設定** を選択します。

1. **表示名** ボックスに接続の名前を入力します。

1. インポートするデータが存在する STFP サーバーの有効なユーザー名、パスワード、およびホスト URL を入力します。

1. 内容を確認し、**同意する** チェックボックスを選択して、**データのプライバシーとコンプライアンス** に同意してください。

1. **検証** を選択して、構成を検証します。

1. 検証が完了したら、**保存** をクリックして接続を保存できます。

> [!div class="mx-imgBorder"]
   > ![Experian 接続構成ページ](media/enrichment-SFTP-connection.png "Experian 接続構成ページ")


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
