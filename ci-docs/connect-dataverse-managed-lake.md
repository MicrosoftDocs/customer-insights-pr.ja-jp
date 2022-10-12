---
title: Microsoft Dataverse の管理された Data Lake に接続する
description: Microsoft Dataverse が管理する  Data Lake からデータをインポートする。
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609801"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Microsoft Dataverse の管理された Data Lake に接続する

Microsoft Dataverse ユーザーは、Microsoft Dataverse マネージド レイクにある分析エンティティに素早く接続することができます。 環境のデータ ソース は 1 つだけで、同じ Dataverse が管理するレイクを同時に使用できます。

> [!NOTE]
> 進んで、管理レイクで使用できるエンティティのリストを表示するには、Dataverse 組織の管理者である必要があります。

## <a name="prerequisites"></a>前提条件

- Azure Data Lake Storage などのオンライン サービスに保存されるデータは、Dynamics 365 Customer Insights で処理や保存される場所とは異なる場所に保存される場合があります。  オンライン サービスに保存されているデータをインポート、あるいは接続することで、 Dynamics 365 Customer Insights にデータの転送と保存がされることに同意するものとします。詳細については、 [Microsoft Trust Center](https://www.microsoft.com/trust-center) をご覧ください。

- [変更の追跡](/power-platform/admin/enable-change-tracking-control-data-synchronization)が有効な Dataverse エンティティのみ表示されます。 これらのエンティティは、Dataverse マネージド データ レイクにエクスポートして、Customer Insights で使用できます。 すぐに使える Dataverse テーブルは、デフォルトで変更の追跡が有効になっています。 カスタム テーブルの変更の追跡を有効にする必要があります。 Dataverse テーブルで変更の追跡が有効になっているか確認するには、[Power Apps](https://make.powerapps.com) > **データ** > **テーブル** に移動します。 目的のテーブルを見つけて選択します。 **設定** > **詳細オプション** に移動して **変更の追跡** の設定を確認します。

## <a name="connect-to-a-dataverse-managed-lake"></a>Dataverse マネージド レイクに接続する

1. **データ** > **データ ソース** にアクセスします。

1. **データソースの追加** を選択します。

1. **Microsoft Dataverse** を選択します。

1. データソースの **名前** とオプションの **説明** を入力します。

1. Dataverse の組織で使用する **サーバーアドレス** を入力し、**サインイン** を選択します。

1. 使用可能なリストから、エンティティとして Customer Insights に取り込むテーブルを選択します。

   > [!NOTE]
   > 既に選択されているテーブルは、他の Dynamics 365 アプリケーション (例: Dynamics 365 Sales Insights や Customer Service Insights) で使用されている可能性があります。 この選択を変更することはできません。 これらのテーブルは、データソースが作成されると、エンティティとして利用できるようになります。

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dataverse 環境内のエンティティのリストを表示するダイアログ ボックス。":::

1. 選択した内容を保存すると、Dataverse から選択したテーブルの同期が始まります。 新しく追加された接続は、**データソース** ページで確認することができます。 選択されたすべてのテーブルが同期されるまで、更新のキューに入り、エンティティ数が 0 と表示されます。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

データの読み込みには時間がかかる場合があります。 正常に最新の情報に更新したら、[**エンティティ**](entities.md) ページから取り込んだデータをレビューできます。

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataverse マネージド レイク データ ソースを編集する

データ ソースを作成した後に、エンティティの選択を編集します。 例えば、Dataverse に追加のエンティティが追加されており、これらもインポートしたいとします。
別の Dataverse Data Lakeに接続するには、[新しいデータ ソースを作成します](#connect-to-a-dataverse-managed-lake)。

1. **データ** > **データ ソース** にアクセスします。

1. 更新するデータ ソースの横にある、**編集** を選択します。

1. 使用可能なエンティティのリストから追加するエンティティを選択します。

1. **保存** をクリックして変更を適用し、**データ ソース** ページに戻ります。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>取り込みエラー、またはデータの破損の一般的な理由

取り込まれたデータに対して以下のようなチェックを行い、破損したレコードを発見します:

- フィールドの値がその列のデータ型と一致しません。
- フィールドに文字が含まれてるため、列が期待されるスキーマと一致しません。 例: 不適切な書式の引用符、エスケープされていない引用符、改行文字など。
- datetime/date/datetimeoffset 列がある場合、標準の ISO 形式に準拠していない場合は、それらの形式をモデルで指定する必要があります。

### <a name="schema-or-data-type-mismatch"></a>スキーマまたはデータ型の不一致

データがスキーマに準拠していない場合、レコードは破損していると分類されます。 ソース データまたはスキーマのいずれかを修正し、データを再取り込みしてください。

### <a name="datetime-fields-in-the-wrong-format"></a>Datetime フィールドの形式が正しくない

エンティティの日時フィールドが、ISO または en-US 形式ではない。 Customer Insights の既定の日付時間形式は en-US 形式です。 エンティティ内のすべての日時フィールドは同じ形式である必要があります。 Customer Insights は、モデルまたは manifest.json のソースまたはエンティティ レベルで注釈または特性が作成される場合、他の形式もサポートします。 例:

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  manifest.json では、エンティティ レベルまたは属性レベルで日時形式を指定できます。 エンティティ レベルでは、*.manifest.cdm.json のエンティティで "exhibitsTraits" を使用して、datatime 形式を定義します。 属性レベルでは、entityname.cdm.json の属性に "appliedTraits" を使用します。

**エンティティ レベルの Manifest.json**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**属性レベルの Entity.json**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
