---
title: Customer Insights データを InMobi にエクスポートする
description: InMobi への接続とエクスポートを構成する方法を説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195894"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Customer Insights データを InMobi にエクスポートする (プレビュー)

セグメント リストまたはその他のデータを Customer Insights インスタンスから [InMobi](https://www.inmobi.com/) にエクスポートします。

## <a name="prerequisites"></a>前提条件

- [InMobi アカウント](https://www.inmobi.com/)および管理者の資格情報。
- [Azure Blob Storage アカウント](/azure/storage/blobs/create-data-lake-storage-account) 名とアカウント キー。 名前とキーを見つけるには、[Azure portal で Azure ストレージ アカウントを管理する](/azure/storage/common/storage-account-manage) を参照してください。
- InMobi データのエクスポート先の [Azure Blob Storage コンテナー](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。
- InMobi は、Blob Storageへの直接接続を作成し、InMobi へのデータの自動インポートを構成します。 InMobi の担当者に連絡して、プロセスを開始してください。

## <a name="known-limitations"></a>既知の制限

- Azure Blob Storage の場合、[標準パフォーマンスとプレミアム パフォーマンス レベル](/azure/storage/blobs/storage-blob-performance-tiers)のいずれかを選択します。 プレミアム パフォーマンス レベルを選択する場合は、[アカウント タイプとしてプレミアム ブロック BLOB を選択します](/azure/storage/common/storage-account-overview#types-of-storage-accounts)。

## <a name="set-up-connection-to-azure-blob-storage"></a>Azure Blob Storage への接続を設定する

[Azure Blob Storage への接続を設定します](export-azure-blob-storage.md)。

## <a name="configure-an-export"></a>エクスポートの構成

[エクスポートを構成します](export-azure-blob-storage.md#configure-an-export)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
