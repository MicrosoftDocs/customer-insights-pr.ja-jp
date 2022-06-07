---
title: 独自の Azure Data Lake Storage Gen2 アカウントを使用する
author: mukeshpo
description: Customer Insights データの保存に独自の Azure Data Lake Storage アカウントを使用する際の要件を説明します。
ms.author: mukeshpo
ms.date: 05/30/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 9fcd7645e34bf310ac3a1b98a0dd9a60598b19dc
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833925"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>独自の Azure Data Lake Storage Gen2 アカウントを使用する

Dynamics 365 Customer Insights は、すべてのデータを [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction) に保存するオプションを提供します。

データを Data Lake Storage に保存することで、その Azure ストレージ アカウントの適切な地理的場所にデータを転送し、保存することに、同意したと見なします。 詳細については [Microsoft セキュリティ センター](https://www.microsoft.com/trust-center) を参照してください。

Customer Insights の管理者は、このプロセスで [環境を作成し](create-environment.md)、[データ ストレージ オプションを指定](create-environment.md#step-2-configure-data-storage) できます。

## <a name="prerequisites-to-use-your-storage-account"></a>ストレージ アカウントを使用する前提条件

- Azure Data Lake Storage アカウントは、Customer Insights 環境の作成時の選択と同じ Azure 地域に存在する必要があります。 **管理者** > **システム** > **詳細情報** から、Customer Insights 環境の地域を確認できます。
- Data Lake Storage は Gen2 であり、さらに [階層型名前空間を有効化する](/azure/storage/blobs/create-data-lake-storage-account) 必要があります。 Gen1 のストレージ アカウントには未対応です。
- `customerinsights` と名前の付いたコンテナ ストレージは、ストレージ アカウントに存在する必要があります。 Customer Insights で独自の Data Lake Storage を使用する前に、その作成が必要です Customer Insights 環境を設定する管理者には、ストレージア カウントまたは `customerinsights` コンテナーで、ストレージ BLOB データ共同作成者またはストレージ BLOB データ所有者のロールが必要です。 ストレージ アカウントでアクセス許可を割り当てる際の詳細は、[ストレージ アカウントの作成](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) を参照してください。

## <a name="connect-customer-insights-with-your-storage-account"></a>Customer Insights を独自のストレージ アカウントに接続する

新しい環境を作成する際は、Data Lake Storage アカウントが存在し、前提条件をすべて満たすことを確認してください。

1. 環境作成時の **データ ストレージ** ステップで、**出力データの保存** を **Azure Data Lake Storage Gen2** に設定します。
1. **ストレージに接続する** 方法を選択します。 リソースに基づくオプションとサブスクリプションに基づくオプションのどちらかを、認証に選択できます。 詳細については、[Azure サービス プリンシパルを使用して Azure Data Lake Storage アカウントに接続する](connect-service-principal.md) を参照してください。
   - **Azure サブスクリプション** に対して、`customerinsights` コンテナを含む **サブスクリプション**、**リソース グループ**、**ストレージ アカウント** を選択します。
   - **アカウント キー** に対して、Data Lake Storage アカウントの **アカウント名** と **アカウント キー** を提供します。 この認証方法を使用すると、組織がキーをローテーションしたかどうかが通知されます。 ローテーションした場合は、新しいキーで [環境の構成を更新する](manage-environments.md#edit-an-existing-environment) 必要があります。

データの取り込みなど、システム プロセスが完了すると、システムがストレージ アカウントに対応するフォルダーを作成します。 データ ファイルと *model.json* ファイルが作成され、プロセス名に基づいたフォルダーに追加されます。

Customer Insights の複数の環境を作成し、それらの環境からの出力エンティティをストレージ アカウントに保存することを選択した場合、Customer Insights はコンテナーの `ci_environmentID` で環境ごとに個別のフォルダーを作成します。
