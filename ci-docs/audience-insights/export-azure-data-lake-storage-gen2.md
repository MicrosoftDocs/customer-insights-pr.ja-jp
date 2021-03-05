---
title: Customer Insights のデータを Azure Data Lake Storage Gen2 にエクスポートする
description: Azure Data Lake Storage Gen2 への接続を構成する方法を説明します。
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477185"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Azure Data Lake Storage Gen2 用コネクタ (プレビュー)

Customer Insights データを Azure Data Lake Storage Gen2 に保存するか、それを使用してユーザーのデータを他のアプリケーションに転送します。

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Azure Data Lake Storage Gen2 のコネクタを構成する

1. 対象者に関するインサイトで、**管理** > **エクスポート先** に移動します。

1. **Azure Data Lake Storage Gen2** で **設定** を選択します。

1. 出力先となる **表示名称** フィールドにはわかりやすい名前を付けます。

1. Azure Data Lake Storage Gen2 の **アカウント名**、**アカウント キー**、および **コンテナ** を入力します。
    - Azure Data Lake Storage Gen2 で使うストレージ アカウントを作成する方法を学ぶには、[ストレージアカウントを作成する](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account)を参照します。 
    - Azure Data Lake Gen2 ストレージ アカウント名とアカウントキーを見つける方法の詳細については、[ Azure ポータルでストレージ アカウント設定を管理する](https://docs.microsoft.com/azure/storage/common/storage-account-manage)を参照してください。

1. **次へ** を選択します。

1. エクスポートの出力先とする各エンティティの横にあるボックスを選択します。

1. **保存** を選択します。

## <a name="export-the-data"></a>データをエクスポートする

[オンデマンドでデータをエクスポート](export-destinations.md#export-data-on-demand) できます。 エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。
