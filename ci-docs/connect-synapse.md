---
title: Azure Synapse Analytics のデータを取り込む
description: Azure Synapse のデータベースを Dynamics 365 Customer Insights のデータ ソースとして使用します。
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646865"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Azure Synapse データ ソースに接続する (プレビュー)

Azure Synapse Analytics は、データ ウェアハウスとビッグ データ システム全体の分析情報までの時間を短縮するエンタープライズ分析サービスです。 Azure Synapse Analytics は、エンタープライズ データ ウェアハウジングで使用される最高の SQL テクノロジー、ビッグ データで使用される Spark テクノロジー、ログおよび時系列分析用の Data Explorer、データ統合と ETL/ELT 用のパイプラインを統合し、Power BI、Cosmos DB、AzureML などの他の Azure サービスとの緊密な統合を実現します。

詳細については、[Azure Synapse の概要](/azure/synapse-analytics/overview-what-is)を参照してください。

## <a name="prerequisites"></a>前提条件

Dynamics 365 Customer Insights から Azure Synapse への接続を構成するには、次の前提条件が満たされている必要があります。

> [!IMPORTANT]
> すべての **ロールの割り当て** を説明どおりに設定してください。  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights の前提条件

* Customer Insights の **管理者** ロールを持っていること。 [Customer Insights のユーザー権限](permissions.md#assign-roles-and-permissions) の詳細を参照してください。

Azure の場合: 

- 有効な Azure サブスクリプション。

- 新しい Azure Data Lake Storage Gen2 アカウントを使用する場合、*Customer Insights のサービス プリンシパル* に **ストレージ Blob データ投稿者** アクセス許可が必要です。 [Customer Insights のサービス プリンシパルを使用した Azure Data Lake Storage への接続](connect-service-principal.md)についてご覧ください。 Data Lake Storage Gen2 では、[階層型名前空間](/azure/storage/blobs/data-lake-storage-namespace) を有効にすることが **必要** です。

- Azure Synapse workspace が配置されているリソース グループでは、*サービス プリンシパル* と、*Customer Insights のユーザー* は、少なくとも **閲覧者** 許可が必要です。 詳細については、[Azure ポータルを使用した Azure ロールの割り当て](/azure/role-based-access-control/role-assignments-portal) を参照してください。

- *ユーザー* には、データが配置され、Azure Synapse ワークスペースにリンクされている Azure Data Lake Storage Gen2 アカウントの **ストレージ BLOB データ共同作成者** アクセス許可が必要です。 詳細については、[Azure ポータルを使用した BLOB およびキュー データへのアクセスのための Azure ロールの割り当て](/azure/storage/common/storage-auth-aad-rbac-portal) と [ストレージ BLOB データ共同作成者のアクセス許可](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) を参照してください。

- *[Azure Synapse ワークスペース マネージド ID](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* には、データが配置され、Azure Synapse ワークスペースにリンクされている Azure Data Lake Storage Gen2 アカウントの **ストレージ BLOB データ共同作成者** アクセス許可が必要です。 詳細は、[Azure ポータルを使用した BLOB およびキュー データへのアクセスのための Azure ロールの割り当て](/azure/storage/common/storage-auth-aad-rbac-portal) と [ストレージ BLOB データ共同作成者のアクセス許可](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) を参照してください。

- Azure Synapse workspace では、*Customer Insights のサービス プリンシパル* に **Synapse 管理者** ロールを割り当てられる必要があります。 詳細については、[Synapse ワークスペースのアクセス制御を設定する方法](/azure/synapse-analytics/security/how-to-set-up-access-control) を参照してください。

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Azure Synapse Analytics のデータ レイク データベースに接続する

1. **データ** > **データ ソース** にアクセスします。

1. **データソースの追加** を選択します。

1. **Azure Synapse Analytics (プレビュー)** の方法を選択します。

1. データ ソースの **名前** を入力し、**次へ** を選択してデータ ソースを作成します。 

1. Azure Synapse Analytics への[使用可能な接続](connections.md)を選択するか、新しい接続を作成します。

1. を選択してください湖データベース選択した Azure Synapse Analytics 接続に接続されているワークスペースから **レイク データベース** を選択して **次へ** を選択してください。

1. 接続されたデータベースから取り込むエンティティを選択します。 

1. オプションで、データ プロファイルを許可するデータ エンティティを選択します。 

1. **保存** を選択して選択を適用し、Azure Synapse Analytics のレイク データベース テーブルにリンクされている新しく作成されたデータ ソースからのデータの取り込みを開始します。
