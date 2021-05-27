---
title: Customer Insights データを Azure Synapse Analytics にエクスポート
description: Azure Synapse Analytics への接続を構成する方法について説明します。
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977383"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>データを Azure Synapse Analytics にエクスポート (プレビュー)

Azure Synapse は、データ ウェアハウスやビッグ データ システムにおいて分析時間を短縮する分析サービスです。 [Azure Synapse](/azure/synapse-analytics/overview-what-is) では、Customer Insights のデータを取り込んで使用できます。

## <a name="prerequisites"></a>前提条件

Customer Insights から Azure Synapse への接続を構成するには、次の前提条件を満たす必要があります。

> [!NOTE]
> すべての **ロールの割り当て** を説明どおりに設定してください。  

## <a name="prerequisites-in-customer-insights"></a>Customer Insights の前提条件

* 対象者に関するインサイトで **管理者** ロールを持っていること。 詳細については、[対象者に関するインサイトでのユーザー アクセス許可の設定](permissions.md#assign-roles-and-permissions) を参照してください

Azure の場合: 

- 有効な Azure サブスクリプション。

- 新しい Azure Data Lake Storage Gen2 アカウントを使用する場合、*対象者に関するインサイトのサービス プリンシパル* には、**ストレージ Blob データ共同作成者** アクセス許可が必要です。 詳細は、[対象者に関するインサイトの Azure サービス プリンシパルを持つ Azure Data Lake Storage Gen2 アカウントへの接続](connect-service-principal.md) を参照してください。 Data Lake Storage Gen2 では、[階層型名前空間](/azure/storage/blobs/data-lake-storage-namespace) を有効にすることが **必要** です。

- Azure Synapse ワークスペースが配置されているリソース グループでは、*サービス プリンシパル* と *対象者に関するインサイトのユーザー* に、少なくとも **閲覧者** のアクセス許可を割り当てる必要があります。 詳細については、[Azure ポータルを使用した Azure ロールの割り当て](/azure/role-based-access-control/role-assignments-portal) を参照してください。

- *ユーザー* には、データが配置され、Azure Synapse ワークスペースにリンクされている Azure Data Lake Storage Gen2 アカウントの **ストレージ BLOB データ共同作成者** アクセス許可が必要です。 詳細については、[Azure ポータルを使用した BLOB およびキュー データへのアクセスのための Azure ロールの割り当て](/azure/storage/common/storage-auth-aad-rbac-portal) と [ストレージ BLOB データ共同作成者のアクセス許可](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) を参照してください。

- *[Azure Synapse ワークスペース マネージド ID](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* には、データが配置され、Azure Synapse ワークスペースにリンクされている Azure Data Lake Storage Gen2 アカウントの **ストレージ BLOB データ共同作成者** アクセス許可が必要です。 詳細は、[Azure ポータルを使用した BLOB およびキュー データへのアクセスのための Azure ロールの割り当て](/azure/storage/common/storage-auth-aad-rbac-portal) と [ストレージ BLOB データ共同作成者のアクセス許可](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) を参照してください。

- Azure Synapse ワークスペースでは、*対象者に関するインサイトのサービス プリンシパル* に **Synapse 管理者** ロールを割り当てる必要があります。 詳細については、[Synapse ワークスペースのアクセス制御を設定する方法](/azure/synapse-analytics/security/how-to-set-up-access-control) を参照してください。

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Azure Synapse への接続とエクスポートを設定する

### <a name="configure-a-connection"></a>接続の構成

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**Azure Synapse Analytics** を選択するか、**Azure Synapse Analytics** タイルで **設定** を選択して、接続を構成します。

1. 接続にわかりやすい名前を 表示名 フィールドに付けます。 接続名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. Customer Insights のデータを使用するサブスクリプションを選択または検索します。 サブスクリプションが選択されると、**ワークスペース**、**ストレージ アカウント**、**コンテナー** も選択できます。

1. **保存** を選択して、接続を保存します。

### <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、**Azure Synapse Analytics** セクションから接続を選択します。 このセクション名が表示されない場合、この種類の [接続](connections.md) は使用できません。

1. エクスポートの識別可能な **表示名** と **データベース名** を指定します。

1. Azure Synapse Analytics にエクスポートするエンティティを選択します。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。

### <a name="update-an-export"></a>エクスポートの更新

1. **データ** > **エクスポート** に移動します。

1. 更新するエクスポートで **編集** を選択します。

   - 選択からエンティティを **追加** または **削除** します。 エンティティを選択から削除しても、Synapse Analytics データベースからは削除されません。 ただし、今後データを更新しても、そのデータベース内の削除されたエンティティは更新されません。

   - **データベース名を変更** すると、新しい Synapse Analytics データベースを作成します。 以前に構成された名前のデータベースは、今後の更新では更新が行われません。
