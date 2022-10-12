---
title: データ ソースの概要
description: さまざまなソースからデータをインポートまたは取り込む方法について説明します。
ms.date: 09/29/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610058"
---
# <a name="data-sources-overview"></a>データ ソースの概要

Dynamics 365 Customer Insights は、幅広いソースからデータを持ち込むための接続を提供します。 データ ソースへの接続は、多くの場合、*データ取り込み* のプロセスと呼ばれます。 データを取り込んだ後、パーソナライズされた体験を構築するために、データを[統一](data-unification.md)し、分析情報を生成し、活性化することができます。

## <a name="add-or-edit-data-sources"></a>データ ソースの追加または編集

Customer Insights にデータソースを添付したり、インポートしたりすることができます。 以下のリンクは、データソースを追加および編集する手順を提供します。

**データ ソースを添付する**

Microsoft の Azureデータ サービスのいずれかにデータが準備されている場合、Customer Insights はデータを再テストすることなく、簡単にデータソースに接続することができます。 次のいずれかのオプションを選択してください。
- [Azure Data Lake Storage (Common Data Model 内の csv ファイルまたは Parquet ファイル)](connect-common-data-model.md)
- [Azure Synapse Analytics (Lake データベース)](connect-synapse.md)
- [Microsoft Dataverse データ レイク](connect-dataverse-managed-lake.md)

**インポートと変換**

オンプレミスのデータソース、Microsoft、またはサードパーティのデータを使用する場合は、Power Query コネクタを使用してデータをインポートおよび変換します。
- [Power Query コネクタ](connect-power-query.md)

## <a name="review-data-sources"></a>データ リソースのレビュー

ご利用の環境が Customer Insights ストレージを使用するように構成され、オンプレミスのデータソースを使用している場合、Power Platform データフローを使用します。 Power Platform データフローでは、共有データソースと他のユーザーが管理するデータソースを表示できます。 **データソース** ページには、データソースが 3 つのセクションにリストされています。
- **共有済み**: すべての Customer Insights 管理者が管理できるデータソース。 Power Platform データフロー、独自のストレージ アカウント、Dataverse マネージド データ レイクは、共有データ ソースの一例です。
- **自分の管理対象**: 自分がだけが作成して管理できる Power Platform データフローです。 他の Customer Insights 管理者は、これらのデータフローを表示することはできますが、編集、更新、または削除することはできません。
- **他のユーザーの管理対象**: 他の管理者によって作成された Power Platform データフロー。 自分は表示のみ可能です。 支援が必要な場合に連絡するデータフローの所有者のリストが表示されます。
> [!NOTE]
> すべてのエンティティは、他のユーザーが表示および使用できます。 データソースはそれらを作成したユーザーが所有しますが、データの取り込みから得られたエンティティは、Customer Insights のすべてのユーザーが使用できます。

Power Platform データフローを使用しない環境の場合、**データソース** ページには、すべてのデータソースのリストのみが表示されます。 セクションは表示されません。

## <a name="manage-existing-data-sources"></a>既存のデータ ソースの管理

**データ** > **データ ソース** に移動すると、取り込まれた各データソースの名前、ステータス、およびそのデータソースの前回のリフレッシュが表示されます。 データ ソースのリストを任意の列で並べ替えたり、検索ボックスを使用して管理するデータ ソースを検索したりできます。

データ ソースを選択して、使用可能なアクションを表示できます。

:::image type="content" source="media/data_sources_showmore.png" alt-text="データ ソースが追加されました。":::

- プロパティを変更するデータ ソースを [**編集**](#add-or-edit-data-sources) します。
- 最新のデータを含めるデータ ソースを最新の情報に [**更新**](#refresh-data-sources)します。
- 統合前にデータ ソースを [**エンリッチ**](data-sources-enrichment.md)します。
- データ ソースを **削除** します。 データ ソースは、データが統合、分析情報、アクティブ化、エクスポートなどの処理で使用されていない場合にのみ削除できます。

## <a name="refresh-data-sources"></a>データ ソースの更新

データ ソースは、自動スケジュールで更新することも、オンデマンドで手動で更新することもできます。 [オンプレミスのデータソース](connect-power-query.md#add-data-from-on-premises-data-sources)データの取り込み中に設定された独自のスケジュールで更新します。 トラブルシューティングのヒントについては、[PPDF Power Query ベースのデータ ソースの更新に関する問題のトラブルシューティング](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues) を参照してください。

接続されたデータソースの場合、データの取り込みは、そのデータ ソースから利用可能な最新のデータを消費します。

**管理者** > **システム** > [**スケジュール**](schedule-refresh.md)にアクセスし、取り込んだデータソースのシステムスケジュールによる更新を構成します。

データ ソースをオンデマンドで更新するには:

1. **データ** > **データ ソース** にアクセスします。

1. 更新するデータ ソースを選択し、**更新** を選択します。 これで、データ ソースが手動で更新されるようになりました。 データ ソースを更新すると、データ ソースで指定されたすべてのエンティティのエンティティ スキーマとデータの両方が更新されます。

1. 状態を選択して **プロセス詳細** ペインを開き、進行状況を表示します。 ジョブをキャンセルするには、ペインの下部の **ジョブをキャンセルする** を選択します

## <a name="corrupt-data-sources"></a>破損したデータ ソース

取り込まれるデータに破損したレコードが含まれている可能性があり、データ取り込みプロセスがエラーまたは警告で完了する可能性があります。

> [!NOTE]
> データの取り込みがエラーで完了した場合、このデータ ソースを利用する後続の処理 (統合や活動の作成など) はスキップされます。 取り込みが警告付きで完了した場合、後続の処理は続行されますが、一部のレコードが含まれない場合があります。

これらのエラーは、タスクの詳細で確認できます。

:::image type="content" source="media/corrupt-task-error.png" alt-text="破損したデータ エラーを示すタスクの詳細。":::

破損したレコードは、システムで作成されたエンティティに表示されます。

### <a name="fix-corrupt-data"></a>破損したデータの修正

1. 破損したデータを表示するには、**データ** > **エンティティ** に移動し、**システム** セクションで破損したエンティティを探します。 破損したエンティティのネーミング スキーマ: 'DataSourceName_EntityName_corrupt'。

1. 破損したエンティティ、 次に **データ** タブを選択します。

1. レコード内の破損したフィールドとその理由を特定します。

   :::image type="content" source="media/corruption-reason.png" alt-text="破損の理由。" lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **データ** > **エンティティ** では、破損したレコードの一部のみが表示されます。 破損したすべてのレコードを表示するには、[Customer Insights のエクスポート プロセス](export-destinations.md) を使用して、ストレージ アカウントのコンテナーにファイルをエクスポートします。 独自のストレージ アカウントを使用した場合は、ストレージ アカウントの Customer Insights フォルダーも確認できます。

1. 破損したデータを修正します。 たとえば、Azure Data Lake データ ソースの場合、[Data Lake Storage 内のデータを修正、またはmanifest/model.json ファイル内のデータ型を更新](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data) します。 Power Query データ ソースの場合は、ソース ファイル内のデータを修正し、**Power Query - クエリを編集** ページで [変換ステップでデータ型を修正](connect-power-query.md#data-type-does-not-match-data) します。

次のデータソースの更新後、修正されたレコードは Customer Insights に取り込まれ、下流のプロセスに渡されます。

たとえば、「birthday」 列のデータ型は 「date」 に設定されています。 顧客レコードには、誕生日が 「01/01/19777」 と入力されています。 システムは、このレコードに破損のフラグを立てます。 ソース システムの誕生日を '1977' に変更します。 データ ソースの自動更新後、フィールドは有効なフォーマットとなり、破損したエンティティからレコードが削除されます。

[!INCLUDE [footer-include](includes/footer-banner.md)]
