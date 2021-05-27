---
title: Customer Insights データを Azure Blob Storage にエクスポートする
description: Blob Storage への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976187"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>セグメント リストとその他のデータを Azure Blob Storage にエクスポートする (プレビュー)

Customer Insights データを Blob Storage に保存するか、それを使用してユーザーのデータを他のアプリケーションに転送します。

## <a name="set-up-the-connection-to-blob-storage"></a>Blob Storage への接続を設定する

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**Azure Blob Storage** を選択して接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. Blob Storage アカウントに **アカウント名**、**アカウント キー**、**コンテナー** を入力します。
    - Blob Storage アカウント名とアカウント キーを検索する方法の詳細については、[Azure ポータルでストレージ アカウントの設定を管理する](/azure/storage/common/storage-account-manage) を参照してください。
    - コンテナの作成方法については、[コンテナを作成する](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)を参照してください。

1. **保存** を選択して、接続を完了します。 

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、Azure Blob Storage セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. エクスポートの出力先とする各エンティティの横にあるボックスを選択します。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。     
[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 

エクスポート データは、構成した Blob Storage コンテナーに保存されます。 以下のフォルダー パスが自動的にコンテナーに作成されます。

- システムによって生成されたソース エンティティとエンティティの場合: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - 例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- エクスポートされたエンティティの model.json は、%ExportDestinationName% レベルです
  - 例: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
