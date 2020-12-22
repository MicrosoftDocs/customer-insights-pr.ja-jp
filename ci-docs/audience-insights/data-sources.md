---
title: データ ソースを使用してデータを取り込む
description: さまざまなソースからデータをインポートする方法について説明します。
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643959"
---
# <a name="overview-about-data-sources"></a>データ ソースの概要

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Customer Insights の対象者に関するインサイト機能は、幅広いソースからのデータに接続します。 データ ソースへの接続は、多くの場合、*データ取り込み* のプロセスと呼ばれます。 データを取り込んだ後、[統合](data-unification.md) およびアクションを実行できます。

## <a name="add-a-data-source"></a>データ ソースの追加

選択したオプションに応じて、データ ソースを追加する方法に関する詳細な記事を参照してください。

データ ソースは、主に次の 3 つの方法で追加できます:

- [多数の Power Query コネクタを使用して](connect-power-query.md)
- [Common Data Model フォルダーから](connect-common-data-model.md)
- [自分の Common Data Service レイク から](connect-common-data-service-lake.md)

> [!NOTE]
> オンプレミスのデータ ソースからのデータはまだ追加できません。

## <a name="review-ingested-data"></a>取り込んだデータのレビュー

取り込んだ各データ ソースの名前、状態、ソースのデータが最後に更新された時刻が表示されます。 データ ソースの一覧を列ごとに並べ替えることができます。

> [!div class="mx-imgBorder"]
> ![追加されたデータ ソース](media/configure-data-datasource-added.png "追加されたデータ ソース")

|ステータス  |内容  |
|---------|---------|
|成功   |**最終更新** 列に時間が記載されている場合、データ ソースは正常に取り込まれました。
|開始前   |データ ソースには、まだデータが取り込まれていないか、ドラフト モードのままです。         |
|更新中    |データ取り込みが進行中です。 この操作をキャンセルするには、**アクション** 列で **更新を中止** を選択します。 データ ソースの更新を停止すると、最後の更新状態に戻ります。       |
|失敗     |データの取り込みでエラーが発生しました。         |

**更新の状態** を選択し、エラーの詳細や下流プロセスの更新など、更新状態の詳細を確認します。

データの読み込みには時間がかかる場合があります。 正常に最新の情報に更新したら、**エンティティ** ページから取り込んだデータをレビューできます。 詳細については、[エンティティ](entities.md) を参照してください。

## <a name="refresh-a-data-source"></a>データ ソースの更新

データ ソースは、自動スケジュールで更新することも、オンデマンドで手動で更新することもできます。 

**管理** > **システム** > [**スケジュール**](system.md#schedule-tab) に移動し、取り込まれたデータ ソースすべてのスケジュール済みの更新を構成します。

オンデマンドでデータ ソースを更新するには、次の手順を実行します:

1. 対象者に関するインサイトで、**データ** > **データ ソース** に移動します

2. 更新するデータ ソースの横にある縦の省略記号を選択して、ドロップダウンリストから **更新** を選択します。

3. これで、データ ソースが手動で更新されるようになりました。 データ ソースを更新すると、エンティティ スキーマと、データ ソースで指定されているすべてのエンティティのデータの両方が更新されます。

4. 既存の更新をキャンセルし、データ ソースを最後の更新状態に戻す場合は、**更新の停止** を選択します。

## <a name="delete-a-data-source"></a>データ ソースの削除

1. 対象者に関するインサイトで、**データ** > **データ ソース** に移動します。

2. 削除するデータ ソースの横にある縦の省略記号を選択し、ドロップダウンメニューから **削除** を選択します。

3. 削除を確認します。
