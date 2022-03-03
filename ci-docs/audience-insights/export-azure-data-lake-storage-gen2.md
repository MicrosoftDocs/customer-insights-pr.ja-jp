---
title: Customer Insights のデータを Azure Data Lake Storage Gen2 にエクスポートする
description: Azure Data Lake Storage Gen2 への接続を構成する方法を説明します。
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: cc0b3aac11a33facc366e9c57071d1fb8be4ecc4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231680"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>セグメントリストおよびその他のデータを Azure Data Lake Storage Gen2 (プレビュー) にエクスポートする

Customer Insights データを Data Lake Storage Gen2 アカウントに保存するか、それを使用してデータを他のアプリケーションに転送します。

## <a name="known-limitations"></a>既知の制限

1. Azure Data Lake Storage Gen2 の場合、データレイクのストレージアカウントを作成するとき、[標準パフォーマンスとプレミアム パフォーマンス レベル](/azure/storage/blobs/create-data-lake-storage-account)のいずれかを選択できます。 プレミアム パフォーマンス レベルを選択する場合は、アカウント タイプとしてプレミアム ブロック BLOB を選択します。 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Azure Data Lake Storage Gen2 への接続を設定する 


1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**Azure Data Lake Storage Gen2** を選択して接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. Azure Data Lake Storage Gen2 の **アカウント名**、**アカウント キー**、および **コンテナ** を入力します。
    - Azure Data Lake Storage Gen2 で使うストレージ アカウントを作成する方法を学ぶには、[ストレージアカウントを作成する](/azure/storage/blobs/create-data-lake-storage-account)を参照します。 
    - Azure Data Lake Gen2 のストレージ アカウント名とアカウント キーの詳細については、[Azure ポータルでストレージ アカウントの設定を管理する](/azure/storage/common/storage-account-manage) を参照してください。

1. **保存** を選択して、接続を完了します。 

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、**Azure Data Lake** セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. エクスポートの出力先とする各エンティティの横にあるボックスを選択します。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 

エクスポート データは、構成した Azure Data Lake Gen 2 のストレージ コンテナーに保存されます。 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
