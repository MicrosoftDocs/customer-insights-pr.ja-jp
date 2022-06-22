---
title: Common Data Model データを Azure Data Lake アカウントに接続する
description: Azure Data Lake Storage を使用して、Common Data Model データを操作します。
ms.date: 05/30/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2ab7ec77252be33f1203959c2a596ddec20425f2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011569"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Azure Data Lake Storage のデータへの接続

Azure Data Lake Storage Gen2 アカウントを使用して  Dynamics 365 Customer Insights にデータを取り込みます。 データ インジェストは、完全または増分にすることができます。

## <a name="prerequisites"></a>前提条件

- データ インジェストは Azure Data Lake Storage *Gen2* アカウントのみに対応しています。 Data Lake Storage Gen1 ストレージ アカウントを使用してデータを取り込むことはできません。

- Azure Data Lake Storage アカウントは、[階層型名前空間](/azure/storage/blobs/data-lake-storage-namespace)が有効となっている必要があります。 データは、ルートフォルダを定義し、エンティティごとにサブフォルダを持つ階層的なフォルダ形式で保存する必要があります。 サブ フォルダには、完全なデータ フォルダまたは増分データフォルダを含めることができます。

- Azure サービス プリンシパルで認証するには、テナントで構成されていることを確認してください。 詳細については、[Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。

- 接続してデータを取り込む Azure Data Lake Storage は、Dynamics 365 Customer Insights 環境と同じ Azure リージョンにある必要があります。 別の Azure リージョンにあるデータ レイクから Common Data Model フォルダーへの接続はサポートされていません。 環境の Azure リージョンを知るには、Customer Insights で **管理者** > **システム** > **関連** に移動します。

- オンライン サービスに保存されたデータは、Dynamics 365 Customer Insights でデータが処理または保存される場所とは別の場所に保存される場合があります。  オンライン サービスに保存されているデータをインポート、あるいは接続することで、 Dynamics 365 Customer Insights にデータの転送と保存がされることに同意するものとします。詳細については、 [Microsoft Trust Center](https://www.microsoft.com/trust-center) をご覧ください。

- ストレージ アカウントにアクセスするには、Customer Insights プリンシパルが次のいずれかの役割を果たしている必要があります。 詳細については、[ストレージ アカウントにアクセスするためのアクセス許可をサービス プリンシパルに付与する](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account)を参照してください。
  - ストレージ Blob データ閲覧者
  - ストレージ Blob データ所有者
  - ストレージ Blob データ共同作成者

- データレイク ストレージ内のデータは、データのストレージに関する共通データモデル標準に準拠し、データファイル (*.csv または*.parquet) のスキーマを表す共通データモデル マニフェストを備えている必要があります。 マニフェストには、エンティティの列やデータ型、データ ファイルの場所やファイル タイプなど、エンティティの詳細を記載する必要があります。 詳細については、[Common Data Model のマニフェスト](/common-data-model/sdk/manifest)を参照してください。 マニフェストが存在しない場合、Storage Blob Data Owner または Storage Blob Data Contributor のアクセス権を持つ Admin ユーザーは、データの取り込み時にスキーマを定義することができます。

## <a name="connect-to-azure-data-lake-storage"></a>Azure Data Lake Storage への接続

1. **データ** > **データ ソース** にアクセスします。

1. **データソースの追加** を選択します。

1. **Azure data lake storage** を選択します。

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Azure Data Lake の接続の詳細を入力するダイアログボックス。" lightbox="media/data_sources_ADLS.png":::

1. データソースの **名前** とオプションの **説明** を入力します。 この名前はデータ ソースを一意に識別し、ダウンストリーム プロセスで参照されるため、変更できません。

1. **ストレージの接続方法** について、次のいずれかを選択します。 詳細については、[Azure サービス プリンシパルで Customer Insights を Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。

   - **Azure リソース**: **リソース ID** を入力します。オプションとして、Azure プライベート リンクを介してストレージ アカウントからデータを取り込む場合は、**プライベートリンクを有効にする**.を選択します。 詳しくは、[Private Link](security-overview.md#private-links-tab)を確認してください
   - **Azure サブスクリプション**：**サブスクリプション** を選択し、**リソース グループ** と **ストレージ アカウント** を選択します。 オプションとして、Azure Private Link を介してストレージ アカウントからデータを取り込む場合は、**プライベート リンクを有効にする** を選択します。 詳しくは、[Private Link](security-overview.md#private-links-tab)を確認してください
  
   > [!NOTE]
   > データ ソースを作成する際は、コンテナーまたはストレージ アカウントに対して、次のいずれかのロールが必要です:
   >
   >  - ストレージ BLOB データ閲覧者は、ストレージ アカウントから読み取りを行い、Customer Insights にデータを取り込む上で十分です。 
   >  - ストレージ BLOB データの共同作成者や所有者は、Customer Insights でマニフェスト ファイルを直接編集する場合に必要です。  
  
1. データをインポートするデータとスキーマを含む **コンテナ** (model.json または manifest.json ファイル) の名前を選択し、**次へ** を選択します。
   > [!NOTE]
   > 環境内にある別のデータ ソースに関連付けられている model.json または manifest.json ファイルは一覧に表示されません。 ただし、同じ model.json または manifest.json ファイルを複数の環境のデータ ソースに使用できます。

1. 新しいスキーマを作成するには、[新しいスキーマファイルを作成する](#create-a-new-schema-file)に移動します。

1. 既存のスキーマを使用するには、model.json または manifest.cdm.json ファイルを含むフォルダーに移動します。 ディレクトリ内を検索してファイルを見つけることができます。

1. json ファイルを選択し、**次へ** を選択します。 使用可能なエンティティの一覧が表示されます。

   :::image type="content" source="media/review-entities.png" alt-text="選択するエンティティのリストのダイアログ ボックス":::

1. 含めるエンティティを選択します。

   :::image type="content" source="media/ADLS_required.png" alt-text="主キーが必要であることを示すダイアログ ボックス":::

   > [!TIP]
   > JSON 編集インターフェースでエンティティを編集するには、**その他** > **スキーマ ファイルの編集** を選択します。 変更を行い、**保存** を選択します。

1. 増分インジェストが必要なエンティティを選択した場合、**増分更新** の下に **必須** と表示されます。 これらの各エンティティについては、[ Azure Data Lake データソースの増分更新を構成する](incremental-refresh-data-sources.md)を参照してください。

1. 主キーが定義されていない選択されたエンティティの場合、**主キー** の下に **必須** が表示されます。 各エンティティーについて:
   1. **必須** を選択します。 **エンティティの編集** パネルが表示されます。
   1. **主キー** を選択します。 主キーは、エンティティに固有の属性です。 属性を有効な主キーにするには、重複する値、欠落している値、または null 値を含めないようにする必要があります。 文字列、整数、および GUID データ型属性が主キーとしてサポートされています。
   1. 必要に応じて、パーティション パターンを変更します。
   1. **閉じる** を選択し、パネルを保存して閉じます。

1. 含まれる各エンティティの **属性** の数を選択します。 **属性の管理** ページが表示されます。

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="データ プロファイリングを選択するためのダイアログ ボックス。":::

   1. 新しい属性の作成、既存の属性の編集、削除を行います。 名前、データ形式を変更したり、セマンティック タイプを追加したりできます。
   1. 解析やその他の機能を有効にするには、エンティティ全体または特定の属性の **データ プロファイリング** を選択します。 既定では、データ プロファイルが有効になっているエンティティはありません。
   1. **完了** を選択します。

1. **保存** を選択します。 **データソース** ページが開き、新しいデータソースが **更新** された状態で表示されます。

### <a name="create-a-new-schema-file"></a>新しいスキーマ ファイルの作成

1. **新しいスキーマ ファイル** を選択します。

1. ファイル名を入力し、**保存** を選択します。

1. **新しいエンティティ** を選択します。 **新規エンティティ** パネルが表示されます。

1. エンティティ名を入力し、**データファイルの場所** を選択します。
   - **複数の .csv または .parquet ファイル**: ルートフォルダーを参照し、パターンの種類を選択し、式を入力します。
   - **単一の .csv または .parquet ファイル**: .csv または .parquet ファイルを参照し、選択します。

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="データファイルの場所がハイライトされている、新しいエンティティを作成するダイアログ ボックス。":::

1. **保存** を選択します。

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="属性を定義または自動生成するためのダイアログボックス。":::

1. 手動で属性を追加する場合は **属性を定義する** を選択し、自動生成する場合は **自動生成** を選択します。 属性を定義するには、名前を入力し、データ形式とオプションのセマンティック タイプを選択します。 自動生成された属性の場合:

   1. 属性が自動生成されたら、**属性を確認する** を選択します。 **属性の管理** ページが表示されます。

   1. 各属性のデータ形式が正しいことを確認してください。

   1. 解析やその他の機能を有効にするには、エンティティ全体または特定の属性の **データ プロファイリング** を選択します。 既定では、データ プロファイルが有効になっているエンティティはありません。

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="データ プロファイリングを選択するためのダイアログ ボックス。":::

   1. **完了** を選択します。 **エンティティの選択** ページが表示されます。

1. 該当する場合は、引き続きエンティティと属性を追加します。

1. すべてのエンティティを追加したら、**含める** を選択してデータ ソースの取り込みにエンティティを含めます。

   :::image type="content" source="media/ADLS_required.png" alt-text="主キーが必要であることを示すダイアログ ボックス":::

1. 増分インジェストが必要なエンティティを選択した場合、**増分更新** の下に **必須** と表示されます。 これらの各エンティティについては、[ Azure Data Lake データソースの増分更新を構成する](incremental-refresh-data-sources.md)を参照してください。

1. 主キーが定義されていない選択されたエンティティの場合、**主キー** の下に **必須** が表示されます。 各エンティティーについて:
   1. **必須** を選択します。 **エンティティの編集** パネルが表示されます。
   1. **主キー** を選択します。 主キーは、エンティティに固有の属性です。 属性を有効な主キーにするには、重複する値、欠落している値、または null 値を含めないようにする必要があります。 文字列、整数、および GUID データ型属性が主キーとしてサポートされています。
   1. 必要に応じて、パーティション パターンを変更します。
   1. **閉じる** を選択し、パネルを保存して閉じます。

1. **保存** を選択します。 **データソース** ページが開き、新しいデータソースが **更新** された状態で表示されます。


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Azure Data Lake Storage データ ソースを編集する

オプションで *ストレージアカウントへの接続* を更新することができます。 詳細については、[Azure サービス プリンシパルで Customer Insights を Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。 ご利用のストレージ アカウントとは異なるコンテナーに接続をする場合や、アカウント名を変更する場合は、[新しいデータ ソースの接続を作成してください](#connect-to-azure-data-lake-storage)。

1. **データ** > **データ ソース** にアクセスします。

1. 更新するデータ ソースの横にある、**編集** を選択します。

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Azure Data Lake データ ソースを編集するダイアログボックス。":::

1. 次の情報のいずれかを変更します:

   - **説明設定**
   - **次使用してストレージを接続する** および接続情報。 接続の更新時に、**コンテナー** 情報を変更することはできません。
      > [!NOTE]
      > 次のいずれかの役割をストレージ アカウントまたはコンテナに割り当てる必要があります:
        > - ストレージ Blob データ閲覧者
        > - ストレージ Blob データ所有者
        > - ストレージ Blob データ共同作成者

   - Azure Private Link を介してストレージアカウントからデータを取り込む場合は、**Private Link を有効** にします。 詳しくは、[Private Link](security-overview.md#private-links-tab)を確認してください

1. **次へ** を選択します。
1. 次のいずれかを変更します:
   - コンテナとは異なるエンティティのセットを持つ別の model.json または manifest.json ファイルに移動します。
   - 取り込むエンティティを追加するには、**新しいエンティティ** を選択します。
   - 依存関係がない場合、すでに選択されているエンティティを削除するには、エンティティを選択し、**削除** を選択します。 
      > [!IMPORTANT]
      > 既存の model.json または manifest.json ファイルとエンティティのセットに依存関係がある場合、エラー メッセージが表示され、別の model.json または manifest.json ファイルを選択できません。 model.json または manifest.json ファイルを変更する前にこれらの依存関係を削除するか、依存関係の削除を回避するために使用する model.json または manifest.json ファイルを使用して新しいデータ ソースを作成します。
   - データ ファイルの場所または主キーを変更するには、**編集** を選択します。
   - 増分取り込みデータを変更するには、次をを参照してください: [Azure Data Lake データソースの増分更新を構成する](incremental-refresh-data-sources.md)

1. 属性の追加や変更、データ プロファイリングを有効にするには、**属性** を選択します。 そして **完了** を選択します。

1. **保存** をクリックして変更を適用し、**データ ソース** ページに戻ります。
