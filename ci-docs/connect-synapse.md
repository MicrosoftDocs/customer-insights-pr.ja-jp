---
title: Azure Synapse データ ソースに接続する (プレビュー)
description: Azure Synapse のデータベースを Dynamics 365 Customer Insights のデータ ソースとして使用します。
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7bc0c3614e6dd39fbd65ae098ed679d95d09de9d
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259804"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Azure Synapse Analytics データ ソースに接続する (プレビュー)

Azure Synapse Analytics は、データ ウェアハウスとビッグ データ システム全体の分析情報までの時間を短縮するエンタープライズ分析サービスです。 Azure Synapse Analytics は、エンタープライズ データ ウェアハウジングで使用される最高の SQL テクノロジー、ビッグ データで使用される Spark テクノロジー、ログおよび時系列分析用の Data Explorer、データ統合と ETL/ELT 用のパイプラインを統合し、Power BI、Cosmos DB、AzureML などの他の Azure サービスとの緊密な統合を実現します。

詳細については、[Azure Synapse の概要](/azure/synapse-analytics/overview-what-is)を参照してください。

## <a name="prerequisites"></a>前提条件

> [!NOTE]
> [ファイアウォールを有効化した](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) Synapse ワークスペースには現在対応していません。
> [!IMPORTANT]
> すべての **ロールの割り当て** を説明どおりに設定してください。  

**Customer Insights**:

* Customer Insights の **管理者** ロールを持っていること。 [Customer Insights のユーザー権限](permissions.md#add-users) の詳細を参照してください。

**Azure**:

- 有効な Azure サブスクリプション。

- 新しい Azure Data Lake Storage Gen2 アカウントを使用する場合、"Customer Insights 向け Dynamics 365 AI" である *Customer Insights のサービス プリンシパル* に **ストレージ Blob データ投稿者** アクセス許可が必要です。 [Customer Insights のサービス プリンシパルを使用した Azure Data Lake Storage への接続](connect-service-principal.md)についてご覧ください。 Data Lake Storage Gen2 では、[階層型名前空間](/azure/storage/blobs/data-lake-storage-namespace) を有効にすることが **必要** です。

- Azure Synapse workspace が配置されているリソース グループでは、"Customer Insights 向け Dynamics 365 AI" である *サービス プリンシパル* と、*Customer Insights のユーザー* は、少なくとも **閲覧者** 許可が必要です。 詳細については、[Azure ポータルを使用した Azure ロールの割り当て](/azure/role-based-access-control/role-assignments-portal) を参照してください。

- *ユーザー* には、データが配置され、Azure Synapse ワークスペースにリンクされている Azure Data Lake Storage Gen2 アカウントの **ストレージ BLOB データ共同作成者** アクセス許可が必要です。 詳細については、[Azure ポータルを使用した BLOB およびキュー データへのアクセスのための Azure ロールの割り当て](/azure/storage/common/storage-auth-aad-rbac-portal) と [ストレージ BLOB データ共同作成者のアクセス許可](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) を参照してください。

- *[Azure Synapse ワークスペース マネージド ID](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* には、データが配置され、Azure Synapse ワークスペースにリンクされている Azure Data Lake Storage Gen2 アカウントの **ストレージ BLOB データ共同作成者** アクセス許可が必要です。 詳細は、[Azure ポータルを使用した BLOB およびキュー データへのアクセスのための Azure ロールの割り当て](/azure/storage/common/storage-auth-aad-rbac-portal) と [ストレージ BLOB データ共同作成者のアクセス許可](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) を参照してください。

- Azure Synapse workspace では、"Customer Insights 向け Dynamics 365 AI" である *Customer Insights のサービス プリンシパル* に **Synapse 管理者** ロールを割り当てられる必要があります。 詳細については、[Synapse ワークスペースのアクセス制御を設定する方法](/azure/synapse-analytics/security/how-to-set-up-access-control) を参照してください。

- Customer Insights 環境がデータを [自分の Azure Data Lake Storage](own-data-lake-storage.md) に保存する場合、Azure Synapse Analytics への接続を設定するユーザーには、少なくとも Data Lake Storage アカウントの組み込み **閲覧者** ロールが必要です。 詳細については、[Azure ポータルを使用した Azure ロールの割り当て](/azure/role-based-access-control/role-assignments-portal) を参照してください。

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Azure Synapse Analytics のデータ レイク データベースに接続する

1. **データ** > **データ ソース** にアクセスします。

1. **データソースの追加** を選択します。

1. **Azure Synapse Analytics (プレビュー)** の方法を選択します。

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Synapse Analytics データに接続するためのダイアログ ボックス":::
  
1. データソースの **名前** とオプションの **説明** を入力します。

1. Azure Synapse Analytics への [使用可能な接続](connections.md) を選択するか、[新しい接続を作成します](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse)。

1. 選択した Azure Synapse Analytics 接続で接続されているワークスペースから **データベース** を選択し、**次へ** を選択します。 現在、*レイク データベース* データベース タイプのみサポートしています。

1. 接続されているデータベースから取り込むエンティティを選択し、**次へ** を選択します。

1. オプションで、データ プロファイルを許可するデータ エンティティを選択します。

1. **保存** を選択して選択を適用し、Azure Synapse Analytics のレイク データベース テーブルにリンクされている新しく作成されたデータ ソースからのデータの取り込みを開始します。 **データソース** ページが開き、新しいデータソースが **更新** された状態で表示されます。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

データの読み込みには時間がかかる場合があります。 正常に最新の情報に更新したら、[**エンティティ**](entities.md) ページから取り込んだデータをレビューできます。

[!INCLUDE [footer-include](includes/footer-banner.md)]
