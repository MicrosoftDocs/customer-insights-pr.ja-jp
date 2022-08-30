---
title: 新しい環境を作成する
description: Dynamics 365 Customer Insights で環境を作成するステップです。
ms.date: 08/15/2022
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
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304250"
---
# <a name="create-a-new-environment"></a>新しい環境を作成する

[Dynamics 365 Customer Insights のサブスクリプション ライセンスを購入](paid-license.md) した後で、Microsoft 365 テナントのグローバル管理者は、環境の作成に招待するメールを受け取ります。 [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) にアクセスし、使用を開始します。 このシナリオでは、[ステップ 1: 基本情報の提供](#step-1-provide-basic-information) で始めます。

最初の環境を作成した後、Microsoft 365 テナントのグローバル管理者は [組織のユーザーを管理者として追加](permissions.md) できます。 これらの管理者はユーザーと環境を管理できます。 Customer Insights のライセンスを組織が複数購入する場合、[サポート チームに問い合わせて](https://go.microsoft.com/fwlink/?linkid=2079641)、利用可能な環境の数を増やします。 容量とアドオン容量の詳細については、[Dynamics 365 ライセンスガイド](https://go.microsoft.com/fwlink/?LinkId=866544) をレビューしてください。 追加の環境を作成できるようになったら、[環境の作成プロセスを開始する](#start-the-environment-creation-process) に移動します。

> [!TIP]
> このサービスをお試しになりたい場合は、[トライアル環境をセットアップする](trial-signup.md)をご覧ください。

## <a name="prerequisites"></a>前提条件

Customer Insights の [管理者権限](permissions.md)

## <a name="start-the-environment-creation-process"></a>環境の作成プロセスを開始する

1. 環境ピッカーを開き、**+ 新規** を選択します。
  
   :::image type="content" source="media/environment-picker.png" alt-text="環境ピッカーを選択します。":::

1. 次のセクションに記載されたガイド付きエクスペリエンスに従って、必要なすべての情報を新しい環境に提供してください。

## <a name="step-1-provide-basic-information"></a>ステップ 1: 基本情報を提供する

1. 環境を最初から作成するか、それとも別の環境からデータをコピーするかを選択します。 [別の環境からのデータのコピー](#copy-the-environment-configuration) には追加の手順が必要です。

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="新しい Customer Insights 環境を作成するダイアログ。":::

1. 次の詳細を入力します:

   - **名前**: この環境の名前。 既存の環境からコピーする場合は、このフィールドには既にに入力されていますが、変更することもできます。
   - **ビジネスを選択する**: 新しい環境の主な対象者: 個人の消費者 (B-to-C) または[ビジネス アカウント](work-with-business-accounts.md) (B-to-B)。 小売業者やコーヒー店など、主に個人と取引する組織の場合は、個人の消費者を選択します。 自動車メーカーや製紙会社など、主な取引先が他の企業である場合、ビジネス アカウントを選択します。
   - **種類**: 環境の種類: 運用環境またはサンドボックス環境。 サンドボックス環境では、スケジュールされたデータの更新は許可されておらず、事前の実装とテストを目的としています。 サンドボックス環境は、現在選択されている本番環境と同じプライマリ対象ユーザーを使用します。
   - **リージョン**: サービスが展開、ホストされるリージョン。 [独自の Azure Data Lake Storage アカウントを使用する](own-data-lake-storage.md) か、[既存の Microsoft Dataverse 組織に接続する](customer-insights-dataverse.md) には、Customer Insights 環境が同じリージョンに存在する必要があります。

1. **次へ** を選択します。

## <a name="step-2-configure-data-storage"></a>ステップ 2: データ ストレージを構成する

1. Customer Insights のデータを保存する場所を選択します。

   - **Customer Insights ストレージ**: データ ストレージは自動的に管理されます。 これは既定のオプションであり、独自のストレージ アカウントにデータを保存するための特別な要件がない限り、このオプションの使用を推奨します。
   - **Azure Data Lake Storage**: データの保存場所を完全に制御するために、独自の Azure Data Lake Storage アカウントにデータを保存します。 [独自の Azure Data Lake Storage アカウントを使用する](own-data-lake-storage.md) の手順に従います。

   :::image type="content" source="media/data-storage-environment.png" alt-text="データの保存に適したオプションを選択します。":::

1. **次へ** を選択します。

## <a name="step-3-connect-to-microsoft-dataverse"></a>ステップ 3: Microsoft Dataverse に接続する

Dataverse 環境がある場合、Customer Insights に接続します。 データを Dataverse と共有し、Dynamics 365 Marketing や Power Apps のモデル駆動型アプリケーションなど、Dataverse に基づくビジネス アプリケーションでデータを使用します。

1. [Microsoft Dataverse で Customer Insights データを操作する](customer-insights-dataverse.md) の手順に従います。

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="正味の新しい環境に対して自動で有効化された、Microsoft Dataverse とのデータ共有。":::

1. **次へ** を選択します。

## <a name="step-4-finalize-the-settings"></a>ステップ 4: 設定の終了処理

指定した設定を確認します。 すべてが完了したように見えたら、**作成** を選択して、環境を設定します。

後で一部の設定を変更するには、[環境の管理](manage-environments.md) を参照してください。

## <a name="work-with-your-new-environment"></a>新しい環境で作業する

Customer Insights の構成を開始するのに役立つ次の記事を確認してください。

- [ユーザーを追加し、権限を割り当てる](permissions.md)。
- [データソースを取り込み](data-sources.md)、[データ統合プロセス](data-unification.md)を通してそれらを実行し、[統一された顧客プロファイル](customer-profiles.md)を取得する。
- [統一された顧客プロファイルを充実させる](enrichment-hub.md)または [予測モデルを実行する](predictions-overview.md)。
- [セグメントを作成](segments.md) して顧客をグループ化し、[メジャー](measures.md)を作成して KPI をレビューします。
- [接続](connections.md)と[エクスポート](export-destinations.md)を設定し、他のアプリケーションでデータのサブセットを処理します。

## <a name="copy-the-environment-configuration"></a>環境の構成をコピーする

管理者として、既存の環境から構成をコピーすることを選択した場合は、組織で使用可能なすべての環境のリストから選択します。

:::image type="content" source="media/environment-settings-dialog.png" alt-text="環境設定の設定オプションのスクリーンショット。":::

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

### <a name="set-up-a-copied-environment"></a>コピーした環境の設定

環境の構成をコピーすると、新たな環境のコピーが作成されたことを示す確認メッセージが表示されます。 資格情報を確認するには次の手順を実行します:

1. **データソースに移動する** を選択してデータ ソースのリストを表示します。 すべてのデータソースの状態が **資格情報が必須** と表示されます。

   :::image type="content" source="media/data-sources-copied.png" alt-text="コピーされた、認証が必要なデータソースのリスト。":::

1. データソースを編集し、資格情報を入力して更新します。 Common Data Model フォルダーと Dataverse のデータ ソースはソース環境と同じ名前で手動で作成する必要があります。

1. データソースの更新後、**データ** > **統一** に移動します。 ここには、ソース環境に由来する設定があります。 必要に応じて編集するか、**統合** > **顧客プロファイルと依存関係を統合する** を選択してデータ統合プロセスを開始し、統合された顧客エンティティを作成します。

   > [!TIP]
   > 取引先企業と取引先担当者の場合は、**アカウントを統合する** > **プロファイルと依存関係を統合する** を選択します。

1. データ統合の完了後は、**計測** と **セグメント** に移動し、それらを更新します。

1. **管理者** > **接続** に移動し、新しい環境で接続を再認証します。

1. **データ** > **濃縮** と **データ** > **輸出** に移動し、それらを再アクティブ化します。

[!INCLUDE [footer-include](includes/footer-banner.md)]
