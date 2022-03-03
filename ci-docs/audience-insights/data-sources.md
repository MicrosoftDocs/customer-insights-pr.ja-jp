---
title: データ ソースを使用してデータを取り込む
description: さまざまなソースからデータをインポートする方法について説明します。
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: e7bcf82c4fe3625ef791ec2b0a7651be0356a006
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354055"
---
# <a name="data-sources-overview"></a>データ ソースの概要



Dynamics 365 Customer Insights の対象者に関するインサイト機能は、幅広いソースからのデータに接続します。 データ ソースへの接続は、多くの場合、*データ取り込み* のプロセスと呼ばれます。 データを取り込んだ後、[統合](data-unification.md) およびアクションを実行できます。

## <a name="add-a-data-source"></a>データ ソースの追加

選択したオプションに応じて、データ ソースを追加する方法については、詳細な記事を参照してください。

データ ソースとして次のデータを追加できます:

- [多数の Power Query コネクタから](connect-power-query.md)
- [Common Data Model フォルダーから](connect-common-data-model.md)
- [自分の Microsoft Dataverse レイク から](connect-dataverse-managed-lake.md)
- [Azure Synapse Analytics データベースから](connect-synapse.md)

> [!NOTE]
> 試用版を使用している場合、インポート方法のセクションには **Customer Insights データ ライブラリ** オプションが含まれます。 このオプションを選択して、さまざまな業界で利用可能なサンプル データセットを選択します。 詳細については、[Dynamics 365 Customer Insights 試用版](../trial-signup.md)をご覧ください。

## <a name="add-data-from-on-premises-data-sources"></a>オンプレミスのデータ ソースからデータを追加する

オンプレミスのデータ ソースから、対象ユーザー分析情報へのデータの取り込みは、Microsoft Power Platform データフローに基づいてサポートされています。 Customer Insights でデータフローを有効にするには、環境を設定するときに[Microsoft Dataverse 環境 URL の提供](create-environment.md)を参照してください。

Dataverse 環境を Customer Insights に関連付けた後に作成されるデータ ソースは、既定で[Power Platform データフロー](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)を使用します。 データフローは、データ ゲートウェイを使用したオンプレミス接続をサポートします。 [オンプレミスのデータ ゲートウェイを使用して](/data-integration/gateway/service-gateway-app)、Dataverse 環境が関連付けられる前に存在するデータソースを削除して再作成できます。

既存の Power BI または Power Apps 環境からのデータ ゲートウェイが表示され、Customer Insights で再利用できます。 データ ソース ページには、Microsoft Power Platform 環境に移動するためのリンクが表示され、オンプレミスのデータ ゲートウェイを表示および構成することができます。

## <a name="review-ingested-data"></a>取り込んだデータのレビュー

取り込んだ各データ ソースの名前、状態、ソースのデータが最後に更新された時刻が表示されます。 データ ソースの一覧を列ごとに並べ替えることができます。

> [!div class="mx-imgBorder"]
> ![データ ソースが追加されました。](media/configure-data-datasource-added.png "追加されたデータ ソース")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

データの読み込みには時間がかかる場合があります。 正常に最新の情報に更新したら、**エンティティ** ページから取り込んだデータをレビューできます。 詳細については、[エンティティ](entities.md) を参照してください。

## <a name="refresh-a-data-source"></a>データ ソースの更新

データ ソースは、自動スケジュールで更新することも、オンデマンドで手動で更新することもできます。 

**管理** > **システム** > [**スケジュール**](system.md#schedule-tab) に移動し、取り込まれたデータ ソースすべてのスケジュール済みの更新を構成します。

オンデマンドでデータ ソースを更新するには、次の手順を実行します:

1. 対象者に関するインサイトで、**データ** > **データ ソース** に移動します。

2. 更新するデータ ソースの横にある縦の省略記号を選択し、ドロップダウン リストから **更新** を選択します。

3. これで、データ ソースが手動で更新されるようになりました。 データ ソースを更新すると、データ ソースで指定されたすべてのエンティティのエンティティ スキーマとデータの両方が更新されます。

4. 既存の更新をキャンセルし、データ ソースを最後の更新状態に戻す場合は、**更新の停止** を選択します。

## <a name="delete-a-data-source"></a>データ ソースの削除

1. 対象者に関するインサイトで、**データ** > **データ ソース** に移動します。

2. 削除するデータ ソースの横にある縦の省略記号を選択し、ドロップダウン メニューから **削除** を選択します。

3. 削除を確認します。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
