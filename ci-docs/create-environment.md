---
title: 新しい環境を作成する方法
description: Dynamics 365 Customer Insights で環境を作成するステップです。
ms.date: 05/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 62969527ceed906ff06fb9be90b972496323ce0a
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052751"
---
# <a name="how-to-create-a-new-environment"></a>新しい環境を作成する方法

[Dynamics 365 Customer Insights のサブスクリプション ライセンスを購入](paid-license.md) した後で、Microsoft 365 テナントのグローバル管理者は、環境の作成に招待するメールを受け取ります。 [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) にアクセスし、使用を開始します。 このシナリオでは、[ステップ 1: 基本情報の提供](#step-1-provide-basic-information) に直接移動できます。

最初の環境を作成した後、Microsoft 365 テナントのグローバル管理者は [組織のユーザーを管理者として追加](permissions.md) できます。 それ以降、これらの管理者はユーザーと環境を管理できます。 Customer Insights のライセンスを組織が複数購入する場合、[サポート チームに問い合わせて](https://go.microsoft.com/fwlink/?linkid=2079641)、利用可能な環境の数を増やします。 容量とアドオン容量の詳細については、[Dynamics 365 ライセンスガイド](https://go.microsoft.com/fwlink/?LinkId=866544) をレビューしてください。

> [!TIP]
> このサービスをお試しになりたい場合は、[トライアル環境をセットアップする](trial-signup.md)をご覧ください。

## <a name="prerequisites"></a>前提条件

環境を作成または管理するには、Customer Insights で [管理者権限](permissions.md) が必要です。

## <a name="start-the-environment-creation-process"></a>環境の作成プロセスを開始する

1. 環境ピッカーを開き、**+ 新規** を選択します。
  
   :::image type="content" source="media/environment-picker.png" alt-text="環境ピッカーを選択します。":::

1. 次のセクションに記載されたガイド付きエクスペリエンスに従って、必要なすべての情報を新しい環境に提供してください。 以前に環境を構成した場合は、その [構成をコピーする](#copy-the-environment-configuration) こともできます。

## <a name="step-1-provide-basic-information"></a>ステップ 1: 基本情報を提供する

**基本情報** ステップで、環境を最初から作成するか、それとも[別の環境からデータをコピーする](#copy-the-environment-configuration)かを選択します。

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="新しい Customer Insights 環境を作成するダイアログ。":::

次の詳細を入力します:

- **名前**: この環境の名前。 既存の環境からコピーする場合は、このフィールドには既にに入力されていますが、変更することもできます。
- **ビジネスを選択する**: 新しい環境のプライマリ対象ユーザーを選択します。 個々の消費者 (B-to-C) または[ビジネス アカウント](work-with-business-accounts.md) (B-to-B)。 小売業者やコーヒー店など、主に個人と取引する組織の場合は、個人の消費者を選択します。 自動車メーカーや製紙会社など、主な取引先が他の企業である場合、ビジネス アカウントを選択します。
- **タイプ**: 実稼働環境、またはサンドボックス環境のどちらを作成するかを選択します。 サンドボックス環境では、スケジュールされたデータの更新は許可されておらず、事前の実装とテストを目的としています。 サンドボックス環境は、現在選択されている本番環境と同じプライマリ対象ユーザーを使用します。
- **リージョン** : サービスが展開、ホストされるリージョンを示します。 [独自の Azure Data Lake Storage アカウントを使用する](own-data-lake-storage.md) か、[既存の Microsoft Dataverse 組織に接続する](customer-insights-dataverse.md) には、Customer Insights 環境が同じリージョンに存在する必要があります。

## <a name="step-2-configure-data-storage"></a>ステップ 2: データ ストレージを構成する

**データ ストレージ** ステップで、Customer Insights からデータを保存する場所を選択します。

選択できるオプションは 2 つ存在します。

- **Customer Insights ストレージ**: データ ストレージは Customer Insights チームが管理します。 これは既定のオプションであり、独自のストレージ アカウントにデータを保存するための特別な要件がない限り、このオプションの使用を推奨します。
- **Azure Data Lake Storage**: データの保存場所を完全に制御するために、独自の Azure Data Lake Storage アカウントを指定してデータを保存します。 詳細については [独自の Azure Data Lake Storage アカウントを使用する](own-data-lake-storage.md) を参照してください。

:::image type="content" source="media/data-storage-environment.png" alt-text="データの保存に適したオプションを選択します。":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>ステップ 3: Microsoft Dataverse に接続する

**Microsoft Dataverse** ステップを使用すると、Customer Insights を Dataverse 環境に接続できます。 データを Dataverse と共有し、Dynamics 365 Marketing や Power Apps のモデル駆動型アプリケーションなど、Dataverse に基づくビジネス アプリケーションでデータを使用します。


独自の Dataverse 環境がない場合は、このフィールドを空白のままにすると、環境が作成されます。

詳細については [Microsoft Dataverse で Customer Insights データを操作する](customer-insights-dataverse.md) を参照してください。

:::image type="content" source="media/dataverse-provisioning.png" alt-text="正味の新しい環境に対して自動で有効化された、Microsoft Dataverse とのデータ共有。":::

### <a name="step-4-finalize-the-settings"></a>ステップ 4: 設定の終了処理

**レビュー** ステップで、指定した設定をすべて実行します。 すべてが完了したように見えたら、**作成** を選択して、環境を設定します。

一部の設定は後で変更できます。 詳細については、[環境を管理する](manage-environments.md) を参照してください。

## <a name="work-with-your-new-environment"></a>新しい環境で作業する

Customer Insights の構成を開始するのに役立つ次の記事を確認してください。

- [ユーザーを追加し、権限を割り当てる](permissions.md)。
- [データソースを取り込み](data-sources.md)、[データ統合プロセス](data-unification.md)を通してそれらを実行し、[統一された顧客プロファイル](customer-profiles.md)を取得する。
- [統一された顧客プロファイルを充実させる](enrichment-hub.md)または [予測モデルを実行する](predictions-overview.md)。
- [セグメントを作成](segments.md) して顧客をグループ化し、[メジャー](measures.md)を作成して KPI をレビューします。
- [接続](connections.md)と[エクスポート](export-destinations.md)を設定し、他のアプリケーションでデータのサブセットを処理します。

## <a name="copy-the-environment-configuration"></a>環境の構成をコピーする

管理者は、新しい環境を作成するときに、既存の環境から構成をコピーする選択ができます。

:::image type="content" source="media/environment-settings-dialog.png" alt-text="環境設定の設定オプションのスクリーンショット。":::

データのコピー元となる組織の、利用可能なすべての環境のリストが表示されます。

以下の構成設定がコピーされます：

- Power Query 経由でインポートしたデータソース
- データ統合構成
- Segments
- メジャー
- 顧客間関係
- アクティビティ
- 検索/フィルター インデックス
- エクスポート
- スケジュールを更新する
- エンリッチメント
- 予測モデル
- ロールの割り当て

## <a name="set-up-a-copied-environment"></a>コピーした環境の設定

環境の構成をコピーする場合は、いくつかの追加の手順を実行して資格情報を確認する必要があります:

- 顧客のプロファイル。 最初に、データ ソースを認証して取り込み、データの統合を実行して顧客プロファイルを再作成します。
- データ ソースの資格情報。 データ ソースの認証と更新を手動で行う場合は、それぞれのデータ ソースに資格情報を提供する必要があります。
- Common Data Model フォルダーと Dataverse によるデータソース。 ソース環境と同じ名前で、これらのデータ ソースを手動で作成する必要があります。
- エクスポートとエンリッチメントに使用される接続シークレット。 接続を再認証してから、エンリッチメントとエクスポートを再アクティブ化する必要があります。

コピーした環境の作成が完了すると、確認メッセージが表示されます。 **データソースに移動する** を選択してデータ ソースのリストを表示します。

すべてのデータソースの状態が **資格情報が必須** となっています。 データソースを編集し、資格情報を入力して更新します。

:::image type="content" source="media/data-sources-copied.png" alt-text="コピーされた、認証が必要なデータソースのリスト。":::

データソースの更新後、**データ** > **統一** に移動します。 ここには、ソース環境に由来する設定があります。 必要に応じて編集するか、**実行** を選択してデータ統合プロセスを開始し、統合された顧客エンティティを作成します。

データ統合の完了後は、**計測** と **セグメント** に移動し、それらを更新します。

エクスポートとエンリッチメントを再度アクティブ化する前に、**管理者** > **接続** に移動して、新しい環境での接続を再認証します。

[!INCLUDE [footer-include](includes/footer-banner.md)]
