---
title: Customer Insights のデータを Azure Data Lake Storage Gen2 にエクスポートする
description: Azure Data Lake Storage Gen2 への接続を構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: c4408e52550b6648e2a001041dc0acdb5063d6a6ef1b8e4bba3321bf25fefcfc
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031985"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a>Azure Data Lake Storage Gen2 への接続を設定する (preview)

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
