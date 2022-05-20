---
title: Customer Insights で環境を作成する
description: Dynamics 365 Customer Insights のライセンス サブスクリプションを使用して環境を作成するステップ。
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: c64ac94a7e0e743d3c13e32e394cc5d409420622
ms.sourcegitcommit: c00441bc60b978e25f930b06c9d97b46fe462538
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712908"
---
# <a name="create-an-environment-in-customer-insights"></a>Customer Insights で環境を作成する

この記事では、組織が Dynamics 365 Customer Insights サブスクリプションを購入後に、新しい環境を作成する方法について説明します。 

組織は、Customer Insights ライセンスごとに複数の環境を作成できます。 組織が複数のライセンスを購入する場合、[サポート チームに問い合わせて](https://go.microsoft.com/fwlink/?linkid=2079641)、利用可能な環境の数を増やします。 容量とアドオン容量の詳細については、[Dynamics 365 ライセンスガイド](https://go.microsoft.com/fwlink/?LinkId=866544) をレビューしてください。

> [!NOTE]
> このサービスをお試しになりたい場合は、[トライアル環境をセットアップする](trial-signup.md)をご覧ください。

## <a name="create-a-new-environment"></a>新しい環境を作成する

Customer Insights のサブスクリプション ライセンスを購入すると、Microsoft 365 テナントのグローバル管理者が、環境の作成に招待するメールを受け取ります。 [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) にアクセスし、使用を開始します。 

ガイド付きエクスペリエンスでは、新しい環境に必要なすべての情報を収集するステップを実行するのに役立ちます。 環境を作成または管理するには、Customer Insights で [管理者権限](permissions.md) が必要です。

1. 環境ピッカーを開き、**+ 新規** を選択します。
  
   :::image type="content" source="media/environment-picker.png" alt-text="環境ピッカーを選択します。":::

1. 次のセクションで概説されているガイド付きのエクスペリエンスに従ってください。

### <a name="step-1-provide-environment-information"></a>ステップ 1: 環境情報を提供する

**基本情報** ステップで、環境を最初から作成するか、それとも[別の環境からデータをコピーする](manage-environments.md#copy-the-environment-configuration)かを選択します。

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="新しい Customer Insights 環境を作成するダイアログ。":::

次の詳細を入力します:
   - **名前**: この環境の名前。 既存の環境からコピーする場合は、このフィールドには既にに入力されていますが、変更することもできます。
   - **ビジネスを選択する**: 新しい環境のプライマリ対象ユーザーを選択します。 個々の消費者 (B-to-C) または[ビジネス アカウント](work-with-business-accounts.md) (B-to-B)。
   - **タイプ**: 実稼働環境、またはサンドボックス環境のどちらを作成するかを選択します。 サンドボックス環境では、スケジュールされたデータの更新は許可されておらず、事前の実装とテストを目的としています。 サンドボックス環境は、現在選択されている本番環境と同じプライマリ対象ユーザーを使用します。
   - **リージョン** : サービスが展開、ホストされるリージョンを示します。

### <a name="step-2-configure-data-storage"></a>ステップ 2: データ ストレージを構成する

**データ ストレージ** ステップで、Customer Insights からデータを保存する場所を選択します。

**Customer Insights ストレージ** (Customer Insights チームによって管理される Azure Data Lake) および **Azure Data Lake Storage** (独自の Azure Data Lake Storage) の 2 つのオプションがあります。 既定では、Customer Insights のストレージが選択されています。

:::image type="content" source="media/data-storage-environment.png" alt-text="Azure Data Lake Storage を選択してデータを保存します。":::

データを Azure Data Lake Storage に保存することによって、データがその Azure ストレージ アカウントの適切な地理的場所に転送されて保存されることに同意するものとします。 この場所は、Dynamics 365 Customer Insights でデータが保存されている場所とは異なる場合があります。 詳細については、[Microsoft Trust Center](https://www.microsoft.com/trust-center) を参照してください。

> [!NOTE]
> Customer Insights では現在、以下をサポートしています。  
> - 環境作成時に選択したのと同じ Azure リージョンの Azure Data Lake Storage アカウント。
> - Gen2 であり *階層型名前空間* を有効している Azure Data Lake Storage アカウント。 Azure Data Lake Gen1 ストレージ アカウントはサポートしていません。

Azure Data Lake Storage オプションでは、認証用にリソース ベース オプションとサブスクリプション ベース オプションのどちらかを選択できます。 詳細については、[Azure サービス プリンシパルを使用した Azure Data Lake Storage アカウントに接続](connect-service-principal.md) を参照してください。 `customerinsights` と名前の付いたコンテナ ストレージは、ストレージ アカウントに存在する必要があります。

データの取り込みなどのシステム プロセスが完了すると、システムは指定したストレージ アカウントに対応するフォルダーを作成します。 データ ファイルと *model.json* ファイルが作成され、プロセス名に基づいたフォルダーに追加されます。

Customer Insights の複数の環境を作成し、それらの環境からの出力エンティティをストレージ アカウントに保存することを選択した場合、Customer Insights はコンテナーの `ci_environmentID` で環境ごとに個別のフォルダーを作成します。

### <a name="step-3-connect-to-microsoft-dataverse"></a>ステップ 3: Microsoft Dataverse に接続する
   
**Microsoft Dataverse** ステップを使用すると、Customer Insights を Dataverse 環境に接続できます。

自分の Microsoft Dataverse 環境を提供し、Dynamics 365 Marketing や Power Apps のモデル駆動型アプリケーションなどの Dataverse ベースのビジネス アプリケーションを使用してデータ (プロファイルと分析情報) を共有します。 自分の Dataverse 環境がない場合はこのフィールドを空にしてください。環境がプロビジョニングされます。

自分の Dataverse 環境を接続すると、[Power Platform データフローとゲートウェイを使用してオンプレミス データ ソースからデータを取り込む](data-sources.md#add-data-from-on-premises-data-sources)こともできます。

> [!IMPORTANT]
> 1. データ共有を有効にするには、Customer Insights と Dataverse が同じリージョンにある必要があります。
> 1. Dataverse 環境のグローバル管理者ロールが必要です。 特定のセキュリティ グループにこの [Dataverse 環境が関連付けられいる](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment)か確認して、それらのセキュリティ グループに自分が追加されていることを確認してください。
> 1. 既存の Customer Insights 環境はまだ Dataverse 環境に関連付けられていません。 [Dataverse 環境への既存の接続を削除する](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment)方法について説明します。

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Microsoft Dataverse とのデータ共有を新しいインスタンスで自動的に有効にする":::

独自の Azure Data Lake Storage から Microsoft Dataverse とのデータ共有を有効にする方法の詳細については、[Microsoft Dataverse への接続](manage-environments.md#connect-to-microsoft-dataverse)を参照してください。

Customer Insights では、次のデータ共有シナリオがサポートされていません。
- Dataverse とのデータ共有を有効にした場合、[エンティティに予測値または欠落値を作成する](predictions.md) ことができなくなります。

### <a name="step-4-finalize-the-settings"></a>ステップ 4: 設定の終了処理

**レビュー** ステップで、指定されたすべての設定を実行します。 すべてが完了したように見えたら、**作成** を選択して、環境を設定します。 

ほとんどの設定は後で変更することもできます。 詳細については、[環境を管理する](manage-environments.md) を参照してください。

## <a name="work-with-your-new-environment"></a>新しい環境で作業する

Customer Insights の構成を開始するのに役立つ次の記事を確認してください。 

- [ユーザーを追加し、権限を割り当てる](permissions.md)。
- [データソースを取り込み](data-sources.md)、[データ統合プロセス](data-unification.md)を通してそれらを実行し、[統一された顧客プロファイル](customer-profiles.md)を取得する。
- [統一された顧客プロファイルを充実させる](enrichment-hub.md)または [予測モデルを実行する](predictions-overview.md)。
- [セグメントを作成](segments.md) して顧客をグループ化し、[メジャー](measures.md)を作成して KPI をレビューします。
- [接続](connections.md)と[エクスポート](export-destinations.md)を設定し、他のアプリケーションでデータのサブセットを処理します。
