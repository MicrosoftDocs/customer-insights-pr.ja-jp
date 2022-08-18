---
title: データを Azure Synapse Analytics にエクスポートする (プレビュー)
description: Azure Synapse Analytics への接続を構成する方法について説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259850"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>データを Azure Synapse Analytics にエクスポートする (プレビュー)

Azure Synapse は、データ ウェアハウスやビッグ データ システムにおいて分析時間を短縮する分析サービスです。 [Azure Synapse](/azure/synapse-analytics/overview-what-is) では、Customer Insights のデータを取り込んで使用できます。

## <a name="prerequisites"></a>前提条件

> [!NOTE]
> すべての **ロールの割り当て** を説明どおりに設定してください。

- Customer Insights で、Azure Active Directory (AD) ユーザー アカウントに[管理者の役割](permissions.md#add-users) が必要です。

Azure の場合:

- 有効な Azure サブスクリプション。

- 新しい Azure Data Lake Storage Gen2 アカウントを使用する場合、[Customer Insights のサービス プリンシパル](connect-service-principal.md)に **ストレージ Blob データ投稿者** アクセス許可が必要です。 Data Lake Storage Gen2 では、[階層型名前空間](/azure/storage/blobs/data-lake-storage-namespace) を有効にすることが **必要** です。

- Azure Synapse workspace が配置されているリソース グループでは、*サービス プリンシパル* と、*Customer Insights の管理者アクセス許可を持つ Azure AD ユーザー* に、**閲覧者**[アクセス許可](/azure/role-based-access-control/role-assignments-portal) が必要です。

- *Customer Insights の管理者アクセス許可を持つ Azure AD ユーザー* には、Azure Synapse workspace にデータが配置されてリンクされている、Azure Data Lake Storage Gen2 アカウントに **ストレージ Blob データ投稿者** アクセス許可が必要です。 詳細については、[Azure ポータルを使用した BLOB およびキュー データへのアクセスのための Azure ロールの割り当て](/azure/storage/common/storage-auth-aad-rbac-portal) と [ストレージ BLOB データ共同作成者のアクセス許可](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) を参照してください。

- *[Azure Synapse workspace マネージド ID](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* には、データが配置され、Azure Synapse ワークスペースにリンクされている Azure Data Lake Storage Gen2 アカウントの **ストレージ BLOB データ共同作成者** アクセス許可が必要です。 詳細は、[Azure ポータルを使用した BLOB およびキュー データへのアクセスのための Azure ロールの割り当て](/azure/storage/common/storage-auth-aad-rbac-portal) と [ストレージ BLOB データ共同作成者のアクセス許可](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) を参照してください。

- Azure Synapse workspace では、*Customer Insights のサービス プリンシパル* に **Synapse 管理者**[ロールを割り当てられる](/azure/synapse-analytics/security/how-to-set-up-access-control) 必要があります。

- Customer Insights 環境がデータを [自分の Azure Data Lake Storage](own-data-lake-storage.md) に保存する場合、Azure Synapse Analytics への接続を設定するユーザーには、少なくとも Data Lake Storage アカウントの組み込み **閲覧者** ロールが必要です。 詳細については、[Azure ポータルを使用した Azure ロールの割り当て](/azure/role-based-access-control/role-assignments-portal) を参照してください。

## <a name="set-up-connection-to-azure-synapse"></a>Azure Synapse への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**Azure Synapse Analytics** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. Customer Insights のデータを使用するサブスクリプションを選択または検索します。 サブスクリプションが選択されると、**ワークスペース**、**ストレージ アカウント**、**コンテナー** も選択できます。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)] 共有接続でエクスポートを構成するには、Customer Insights で **共同作成者** の権限が最低限必要です。

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、Azure Synapse Analytics セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの識別可能な **表示名** と **データベース名** を指定します。 エクスポートにより、新しい [Azure Synapse レイク データベース](/azure/synapse-analytics/database-designer/concepts-lake-database) が接続で定義されたワークスペース内に作成されます。

1. Azure Synapse Analytics にエクスポートするエンティティを選択します。
   > [!NOTE]
   > [Common DataModel フォルダー](connect-common-data-model.md) に基づくデータソースはサポートされていません。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Synapse Analytics にエクスポートされたデータをクエリするには、エクスポートのワークスペースにあるデスティネーション ストレージへの **ストレージ BLOB データ閲覧者** アクセスが必要です。

## <a name="update-an-export"></a>エクスポートの更新

1. **データ** > **エクスポート** に移動します。

1. 更新するエクスポートで **編集** を選択します。

   - 選択からエンティティを **追加** または **削除** します。 エンティティを選択から削除しても、Synapse Analytics データベースからは削除されません。 ただし、今後データを更新しても、そのデータベース内の削除されたエンティティは更新されません。

   - **データベース名を変更** すると、新しい Synapse Analytics データベースを作成します。 以前に構成された名前のデータベースは、今後の更新では更新が行われません。

[!INCLUDE [footer-include](includes/footer-banner.md)]
