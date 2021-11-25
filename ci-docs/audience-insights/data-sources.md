---
title: データ ソースを使用してデータを取り込む
description: さまざまなソースからデータをインポートする方法について説明します。
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 27cbd0346b1219c7812f4b90327dd27b645c2b8e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732148"
---
# <a name="data-sources-overview"></a>データ ソースの概要

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Customer Insights の対象者に関するインサイト機能は、幅広いソースからのデータに接続します。 データ ソースへの接続は、多くの場合、*データ取り込み* のプロセスと呼ばれます。 データを取り込んだ後、[統合](data-unification.md) およびアクションを実行できます。

## <a name="add-a-data-source"></a>データ ソースの追加

選択したオプションに応じて、データ ソースを追加する方法に関する詳細な記事を参照してください。

データ ソースは、主に次の 3 つの方法で追加できます:

- [多数の Power Query コネクタを使用して](connect-power-query.md)
- [Common Data Model フォルダーから](connect-common-data-model.md)
- [自分の Microsoft Dataverse レイク から](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>オンプレミスのデータ ソースからデータを追加する

オンプレミスのデータ ソースから、対象ユーザー分析情報へのデータの取り込みは、Microsoft Power Platform データフローに基づいてサポートされています。 データフローは、環境を設定するときに [Microsoft Dataverse 環境 URL を指定](create-environment.md) することで、Customer Insights で有効にできます。

Dataverse 環境を Customer Insights に関連付け後に作成されるデータ ソースは、既定で [Power Platform データフロー](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) を使用します。 データフローは、データ ゲートウェイを使用したオンプレミス接続をサポートします。 Dataverse 環境が関連付けられる前に存在したデータ ソースを削除して再作成し、[オンプレミス データ ゲートウェイを使用](/data-integration/gateway/service-gateway-app) します。

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
