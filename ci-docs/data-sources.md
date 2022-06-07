---
title: データ ソースを使用してデータを取り込む
description: さまざまなソースからデータをインポートする方法について説明します。
ms.date: 03/18/2022
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
ms.openlocfilehash: 355d52eabde90e0764817cf479821264ebb2e5eb
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800472"
---
# <a name="data-sources-overview"></a>データ ソースの概要



Dynamics 365 Customer Insights は、さまざまなソースからのデータに接続します。 データ ソースへの接続は、多くの場合、*データ取り込み* のプロセスと呼ばれます。 データを取り込んだ後、[統合](data-unification.md) およびアクションを実行できます。

## <a name="add-a-data-source"></a>データ ソースの追加

選択したオプションに応じて、データ ソースを追加する方法については、詳細な記事を参照してください。

データ ソースとして次のデータを追加できます:

- [多数の Power Query コネクタから](connect-power-query.md)
- [Common Data Model フォルダーから](connect-common-data-model.md)
- [自分の Microsoft Dataverse レイク から](connect-dataverse-managed-lake.md)
- [Azure Synapse Analytics データベースから](connect-synapse.md)

## <a name="add-data-from-on-premises-data-sources"></a>オンプレミスのデータ ソースからデータを追加する

オンプレミスのデータ ソースからのデータの取り込みは、Microsoft Power Platform データフローに基づいてサポートされています。 Customer Insights でデータフローを有効にするには、環境を設定するときに[Microsoft Dataverse 環境 URL の提供](create-environment.md)を参照してください。

Dataverse 環境を Customer Insights に関連付けた後に作成されるデータ ソースは、既定で[Power Platform データフロー](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)を使用します。 データフローは、データ ゲートウェイを使用したオンプレミス接続をサポートします。 [オンプレミスのデータ ゲートウェイを使用して](/data-integration/gateway/service-gateway-app)、Dataverse 環境が関連付けられる前に存在するデータソースを削除して再作成できます。

既存の Power BI または Power Apps 環境からのデータ ゲートウェイが表示され、Customer Insights で再利用できます。 データ ソース ページには、Microsoft Power Platform 環境に移動するためのリンクが表示され、オンプレミスのデータ ゲートウェイを表示および構成することができます。

> [!IMPORTANT]
> ゲートウェイが最新バージョンに更新されていることを確認してください。 更新プログラムをインストールして、ゲートウェイ画面に表示されるプロンプトから直接ゲートウェイを再構成するか、[最新バージョンをダウンロードする](https://powerapps.microsoft.com/downloads/)ことができます。 最新のゲートウェイ バージョンを使用しない場合、データフローの更新は失敗し、**キーワードはサポートされていません: 構成プロパティ。パラメータ名: キーワード** のようなエラーメッセージが表示されます。。

## <a name="review-ingested-data"></a>取り込んだデータのレビュー
環境に Power Platform データフローが含まれる場合、**データ ソース** ページには以下の 3 つのセクションがリストされます。 
- **共有済み**: すべての Customer Insights 管理者が管理できるデータソース。 Power BI データフロー、独自のストレージ アカウント、および Dataverse マネージド データ レイクは、共有データ ソースの一例です。
- **自分の管理対象**: 自分がだけが作成して管理できる Power Platform データフロー。 他の Customer Insights 管理者は、これらのデータフローを表示することはできますが、編集、更新、または削除することはできません。
- **他のユーザーの管理対象**: 他の管理者によって作成された Power Platform データフロー。 自分は表示のみ可能です。 支援が必要な場合に連絡するデータフローの所有者のリストが表示されます。
> [!NOTE]
> すべてのエンティティは、他のユーザーが表示および使用できます。 ユーザーのコンテキスト性はデータ ソースにのみ適用され、これらのデータフローから生じるエンティティには適用されません。

Power Platform データフローが使用されない場合、グループやセクションは表示されません。 **データ ソース** ページには、すべてのデータ ソースのリストのみが含まれています。

取り込んだ各データ ソースの名前、状態、ソースのデータが最後に更新された時刻が表示されます。 データ ソースの一覧を列ごとに並べ替えることができます。

> [!div class="mx-imgBorder"]
> ![データ ソースが追加されました。](media/configure-data-datasource-added.png "追加されたデータ ソース")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

データの読み込みには時間がかかる場合があります。 正常に最新の情報に更新したら、**エンティティ** ページから取り込んだデータをレビューできます。 詳細については、[エンティティ](entities.md) を参照してください。

## <a name="refresh-a-data-source"></a>データ ソースの更新

データ ソースは、自動スケジュールで更新することも、オンデマンドで手動で更新することもできます。 

**管理** > **システム** > [**スケジュール**](system.md#schedule-tab) に移動し、取り込まれたデータ ソースすべてのスケジュール済みの更新を構成します。

オンデマンドでデータ ソースを更新するには、次の手順を実行します:

1. **データ** > **データ ソース** にアクセスします。

2. 更新するデータ ソースの横にある垂直の省略記号 (&vellip;) を選択し、ドロップダウン リストから **更新** を選択します。

3. これで、データ ソースが手動で更新されるようになりました。 データ ソースを更新すると、データ ソースで指定されたすべてのエンティティのエンティティ スキーマとデータの両方が更新されます。

4. 既存の更新をキャンセルし、データ ソースを最後の更新状態に戻す場合は、**更新の停止** を選択します。

## <a name="delete-a-data-source"></a>データ ソースの削除

1. **データ** > **データ ソース** にアクセスします。

2. 削除するデータ ソースの横にある垂直の省略記号 (&vellip;) を選択し、ドロップダウン メニューから **削除** を選択します。

3. 削除を確認します。


[!INCLUDE [footer-include](includes/footer-banner.md)]
