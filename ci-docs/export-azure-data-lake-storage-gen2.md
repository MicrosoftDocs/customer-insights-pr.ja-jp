---
title: Azure Data Lake Storage Gen2 にデータをエクスポートする (プレビュー)
description: Azure Data Lake Storage Gen2 への接続を構成する方法を説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196446"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Azure Data Lake Storage Gen2 にデータをエクスポートする (プレビュー)

Customer Insights データを Data Lake Storage Gen2 アカウントに保存するか、それを使用してデータを他のアプリケーションに転送します。

## <a name="prerequisites"></a>前提条件

- [Azure Data Lake Gen 2 で使用するストレージ アカウント](/azure/storage/blobs/create-data-lake-storage-account)。 ストレージ アカウント名とキーを見つけるには、[Azure portal で Azure ストレージ アカウントを管理する](/azure/storage/common/storage-account-manage) を参照してください。
- [Azure Blob Storage コンテナー](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

## <a name="known-limitations"></a>既知の制限

- Azure Data Lake Storage Gen2 の場合、[標準パフォーマンスとプレミアム パフォーマンス レベル](/azure/storage/blobs/create-data-lake-storage-account) のいずれかを選択します。 プレミアム パフォーマンス レベルを選択する場合は、[アカウント タイプとしてプレミアム ブロック BLOB を選択します](/azure/storage/common/storage-account-overview#types-of-storage-accounts)。

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Azure Data Lake Storage Gen2 への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **接続を追加** を選択し、**Azure Data Lake Gen 2** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. Azure Data Lake Storage Gen2 の **アカウント名**、**アカウント キー**、および **コンテナ** を入力します。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、Azure Data Lake セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. Azure Data Lake Storage Gen2 ストレージのフォルダー名を入力します。

1. エクスポートの出力先とする各エンティティの横にあるボックスを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

エクスポート データは、構成した Azure Data Lake Gen 2 のストレージ コンテナーに保存されます。

> [!TIP]
> 大量のデータを含むエンティティのエクスポートでは、エクスポートごとに同じフォルダーに複数の CSV ファイルが作成される場合があります。 エクスポートの分割は、エクスポートの完了にかかる時間を最小限にするためのパフォーマンス上の理由で実施されます。

[!INCLUDE [footer-include](includes/footer-banner.md)]
