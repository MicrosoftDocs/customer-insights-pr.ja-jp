---
title: Customer Insights データを Azure Blob Storage にエクスポートする
description: Azure Blob Storage への接続を構成する方法について説明します。
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269198"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Azure Blob Storage 用コネクタ (プレビュー)

Customer Insights データを Azure Blob Storage に保存するか、それを使用してユーザー データを他のアプリケーションに転送します。

## <a name="configure-the-connector-for-azure-blob-storage"></a>Azure Blob Storage のコネクタを構成する

1. 対象者に関するインサイトで、**管理** > **エクスポート先** に移動します。

1. **Azure Blob Storage** で **設定** を選択します。

1. Azure Blob Storage アカウント用の **アカウント名**、**アカウント キー**、**コンテナー** を入力します。
    - Azure Blob ストレージアカウント名とアカウントキーを見つける方法の詳細については、[Azure ポータルでストレージ アカウント設定を管理する](https://docs.microsoft.com/azure/storage/common/storage-account-manage)を参照してください。
    - コンテナの作成方法については、[コンテナを作成する](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)を参照してください。

1. 出力先となる **表示名称** フィールドにはわかりやすい名前を付けます。

1. **次へ** を選択します。

1. エクスポートの出力先とする各エンティティの横にあるボックスを選択します。

1. **保存** を選択します。

エクスポートされたデータは、構成した Azure Blob Storage コンテナーに保存されます。 以下のフォルダー パスが自動的にコンテナーに作成されます。

- システムによって生成されたソース エンティティとエンティティの場合: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - 例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- エクスポートされたエンティティの model.json は、%ExportDestinationName% レベルに存在します
  - 例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>データをエクスポートする

[オンデマンドでデータをエクスポート](export-destinations.md#export-data-on-demand) できます。 エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]