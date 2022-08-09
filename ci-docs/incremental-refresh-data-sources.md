---
title: Power Query と Azure Data Lake のデータソースの増分更新
description: Power Query または Azure Data Lake のデータソースに基づく大規模データソースの新規、および更新データを更新します。
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207143"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Power Query と Azure Data Lake のデータソースの増分更新

Power Query または Azure Data Lake に基づくデータソースを増分更新することには、以下の利点があります。

- **更新速度の増強** - 変更のあったデータのみが更新されます。 例えば、履歴データセットの過去 5 日間だけを更新することができます。
- **安定性の増加** - 更新の規模を縮小化することで、揮発性のソース システムへの接続を長期間維持する必要がなくなり、接続の問題が発生するリスクが軽減されます。
- **リソース消費の軽減** - データ全体の一部のみを更新することで、コンピューター上のリソース使用効率が向上し、環境への負荷が軽減します。

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Power Query に基づくデータソースの増分更新を構成する

Customer Insights により、増分取り込みをサポートする Power Query を使用してインポートされるデータ ソースの増分更新ができます。 たとえば、データ レコードが最後に更新された日付と時刻のフィールドを持つ Azure SQL データベースなどです。

1. [Power Query ベースの新しいデータ ソースを作成します](connect-power-query.md)。

1. [Azure SQL データベース](/power-query/connectors/azuresqldatabase)などの、増分更新に対応するデータ ソースを選択します。

1. 取り込むエンティティまたはテーブルを選択します。

1. この変換の手順を完了し、**保存** を選択します。

1. **増分更新を設定する** ダイアログ ボックスで、**設定** を選択して、**増分更新の設定** を開きます。 **スキップ** を選択すると、データソースがデータセット全体を更新します。
   > [!TIP]
   > 既存のデータ ソースを編集することで、増分更新を後から適用することも可能です。

1. **増分更新の設定** にて、データ ソースの作成時に選択したすべてのエンティティーの増分更新を構成します。

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="増分更新の設定を更新する。":::

1. エンティティを選択し、次の詳細を指定します：

   - **主キーの設定**：エンティティまたはテーブルの主キーを選択します。
   - **最終更新フィールドの設定**：このフィールドには、日付または時刻タイプの属性のみが表示されます。 レコードが最後に更新された日時を示す属性を選択します。 これは、増分更新概算時間枠内にあるレコードを識別するために使用されます。
   - **すべての更新を確認する**：増分更新の時間枠の長さを指定します。

1. **保存** を選択して、データ ソースの作成を完了します。 最初のデータ更新は全体の更新になります。 その後の更新からは、上記手順で設定したように増分の更新が行われます。

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Azure Data Lake データソースの増分更新の構成

Customer Insightsは、Azure Data Lake Storage に接続されたデータソースの増分更新を可能にします。 エンティティに対して増分インジェストと更新を使用するには、Azure Data Lake データソースの追加時、またはそれ以降のデータソースの編集時にそのエンティティを構成します。 エンティティ データ フォルダには、次のフォルダが含まれている必要があります:

- **FullData**: フォルダには、初期レコードを含むデータ ファイルが必要です
- **IncrementalData**: 増分更新を含む **yyyy/mm/dd/hh** 形式の日付/時刻階層フォルダです。 **hh** は更新の UTC 時間を表し、**Upserts** と **Deletes** フォルダが含まれています。 **Upserts** は、既存レコードの更新や新規レコードを含むデータファイルです。 **削除** には、削除するレコードのあるデータ ファイルが含まれています。

1. データソースを追加または編集する場合、そのエンティティの **属性** ペインに移動します。

1. 属性を確認します。 作成日や最終更新日の属性が、*dateTime* **Data format** と *Calendar.Date* **セマンティックタイプ** で設定されていることを確認します。 必要に応じて属性を編集し、**完了** を選択します。

1. **エンティティを選択** ペインで、エンティティを編集します。 **増分インジェスト** チェックボックスが選択されています。

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="データソースのエンティティの増分更新を設定する。":::

   1. フルデータ、増分データのアップサート、増分データの削除のための .csv または .parquet ファイルを含むルートフォルダを参照してください。
   1. フルデータと増分ファイルの両方の拡張子を入力します (\.csv または \.parquet)。
   1. .csv ファイルの場合は列区切り文字を選択し、ファイルの最初の行を列ヘッダーとして使用するかどうかを選択します。
   1. **保存** を選択します。

1. **最終更新日** で、日付のタイムスタンプ属性を選択します。

1. **主キー** が選択されていない場合は、主キーを選択します。 主キーは、エンティティに固有の属性です。 属性を有効な主キーにするには、重複する値、欠落している値、または null 値を含めないようにする必要があります。 文字列、整数、および GUID データ型属性が主キーとしてサポートされています。

1. **閉じる** を選択し、ペインを保存して閉じます。

1. データ ソースの追加または編集を続行します。

[!INCLUDE [footer-include](includes/footer-banner.md)]
