---
title: Customer Insights データを InMobi にエクスポートする
description: InMobi への接続とエクスポートを構成する方法を説明します。
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056545"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>セグメントリストおよびその他のデータを  InMobi (プレビュー) にエクスポートする

セグメント リストまたはその他のデータを Customer Insights インスタンスから [InMobi](https://www.inmobi.com/) にエクスポートします。

## <a name="prerequisites"></a>前提条件

1. [InMobi アカウント](https://www.inmobi.com/)および管理者の資格情報を持っていること。
1. Azure Blob ストレージ アカウント名と対応するアカウント キーを持っていること。 詳細については、[Azure portal で Azure ストレージ アカウントを管理する](/azure/storage/common/storage-account-manage) を参照してください。 ストレージ アカウントに、inMobi データのエクスポート先のコンテナーがあること。 詳細については、[コンテナーの作成](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)を参照してください。
1. InMobi は、Blob Storageへの直接接続を作成し、InMobi へのデータの自動インポートを構成します。 InMobi の担当者に連絡して、プロセスを開始してください。

## <a name="known-limitations"></a>既知の制限

1. Azure Blob Storage の場合、[標準パフォーマンスとプレミアム パフォーマンス レベル](/azure/storage/blobs/storage-blob-performance-tiers)のいずれかを選択できます。 プレミアム パフォーマンス レベルを選択する場合は、[アカウント タイプとしてプレミアム ブロック BLOB を選択します](/azure/storage/common/storage-account-overview#types-of-storage-accounts)。

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Azure Blob Storage への接続をセットアップし、エクスポートを構成します

1. 指示に従って [Azure Blob Storage への接続を設定します](export-azure-blob-storage.md)。
2. 指示に従って[エクスポートを構成します](export-azure-blob-storage.md#configure-an-export)。

[!INCLUDE [footer-include](includes/footer-banner.md)]
