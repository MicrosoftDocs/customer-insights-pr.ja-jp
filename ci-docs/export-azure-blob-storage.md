---
title: Azure Blob Storage にデータをエクスポートする (プレビュー)
description: Blob Storage への接続とエクスポートを構成する方法を説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195710"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Azure Blob Storage にデータをエクスポートする (プレビュー)

Customer Insights データを Blob Storage に保存するか、それを使用してユーザーのデータを他のアプリケーションに転送します。

## <a name="prerequisites"></a>前提条件

- [Azure Blob Storage アカウント](/azure/storage/blobs/create-data-lake-storage-account) 名とアカウント キー。 名前とキーを見つけるには、[Azure portal で Azure ストレージ アカウントを管理する](/azure/storage/common/storage-account-manage) を参照してください。
- [Azure Blob Storage コンテナー](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

## <a name="known-limitations"></a>既知の制限

- Azure Blob Storage の場合、[標準パフォーマンスとプレミアム パフォーマンス レベル](/azure/storage/blobs/storage-blob-performance-tiers)のいずれかを選択します。 プレミアム パフォーマンス レベルを選択する場合は、[アカウント タイプとしてプレミアム ブロック BLOB を選択します](/azure/storage/common/storage-account-overview#types-of-storage-accounts)。

## <a name="set-up-connection-to-blob-storage"></a>Blob Storage への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **接続を追加** を選択し、**Azure Blob Storage** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. Blob Storage アカウントに **アカウント名**、**アカウント キー**、**コンテナー** を入力します。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

このエクスポートを構成するには、この接続タイプの[アクセス許可](export-destinations.md#set-up-a-new-export) が必要です。

> [!IMPORTANT]
> Azure Blob Storage アカウントの[ソフト削除設定](/azure/storage/blobs/soft-delete-blob-enable) をオンにした場合、エクスポートは失敗します。 データを BLOB にエクスポートするには、ソフト削除をオフにします。

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、Azure Blob Storage セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. Blob Storage のフォルダー名を入力します。

1. エクスポートの出力先とする各エンティティの横にあるボックスを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

エクスポート データは、構成した Blob Storage コンテナーに保存されます。 以下のフォルダー パスが自動的にコンテナーに作成されます。

- システムによって生成されたソース エンティティとエンティティの場合:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  例: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > 大量のデータを含むエンティティのエクスポートでは、エクスポートごとに同じフォルダーに複数の CSV ファイルが作成される場合があります。 エクスポートの分割は、エクスポートの完了にかかる時間を最小限にするためのパフォーマンス上の理由で実施されます。

- エクスポートされたエンティティの model.json は、*%ExportDestinationName%* レベルにあります。  
  
  例: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
