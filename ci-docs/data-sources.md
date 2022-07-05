---
title: データ ソースの概要
description: さまざまなソースからデータをインポートまたは取り込む方法について説明します。
ms.date: 05/18/2022
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
ms.openlocfilehash: fbe44f655bdbc20ef7f0956022395e2dcb570adf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051459"
---
# <a name="data-sources-overview"></a>データ ソースの概要

Dynamics 365 Customer Insights は、幅広いソースからデータを持ち込むための接続を提供します。 データ ソースへの接続は、多くの場合、*データ取り込み* のプロセスと呼ばれます。 データを取り込んだ後、パーソナライズされた体験を構築するために、データを[統一](data-unification.md)し、分析情報を生成し、活性化することができます。

## <a name="add-data-sources"></a>データ ソースの追加

Customer Insights にデータソースを添付したり、インポートしたりすることができます。 以下のリンクは、データソースを追加する手順を提供します。

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

**データ** > **データ ソース** に移動すると、取り込まれた各データソースの名前、ステータス、およびそのデータソースの前回のリフレッシュが表示されます。 データ ソースの一覧を列ごとに並べ替えることができます。

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="データ ソースが追加されました。":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

データの読み込みには時間がかかる場合があります。 正常に最新の情報に更新したら、**エンティティ** ページから取り込んだデータをレビューできます。 詳細については、[エンティティ](entities.md) を参照してください。

## <a name="refresh-data-sources"></a>データ ソースの更新

データ ソースは、自動スケジュールで更新することも、オンデマンドで手動で更新することもできます。 [オンプレミスのデータソース](connect-power-query.md#add-data-from-on-premises-data-sources)データの取り込み中に設定された独自のスケジュールで更新します。 接続されたデータソースの場合、データの取り込みは、そのデータ ソースから利用可能な最新のデータを消費します。

**管理者** > **システム** > [**スケジュール**](system.md#schedule-tab)にアクセスし、取り込んだデータソースのシステムスケジュールによる更新を構成します。

オンデマンドでデータ ソースを更新するには、次の手順を実行します:

1. **データ** > **データ ソース** にアクセスします。

1. 更新するデータ ソースの横にある垂直の省略記号 (&vellip;) を選択し、ドロップダウン リストから **更新** を選択します。 これで、データ ソースが手動で更新されるようになりました。 データ ソースを更新すると、データ ソースで指定されたすべてのエンティティのエンティティ スキーマとデータの両方が更新されます。

1. 既存の更新をキャンセルし、データ ソースを最後の更新状態に戻す場合は、**更新の停止** を選択します。

## <a name="delete-a-data-source"></a>データ ソースの削除

データ ソースは、データが統合、分析情報、アクティブ化、エクスポートなどの処理で使用されていない場合にのみ削除できます。

1. **データ** > **データ ソース** にアクセスします。

2. 削除するデータ ソースの横にある垂直の省略記号 (&vellip;) を選択し、ドロップダウン メニューから **削除** を選択します。

3. 削除を確認します。


[!INCLUDE [footer-include](includes/footer-banner.md)]
