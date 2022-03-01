---
title: 改良したイベントをエクスポートする
description: 改良したイベントとベースイベントをエクスポートする方法。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032391"
---
# <a name="export-events"></a>イベントのエクスポート

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

イベントはユーザーの行動を表すものです。 ユーザーがページを表示したとき (イベントの表示)、またはコンテンツとやり取りしたタイミング (アクション イベント) で記録します。 レポートに表示するデータのプロパティを決めることができる場合、このデータの仮想ビューは *改良されたイベント* と呼ばれます。 

- イベントと改良されたイベントは、外部ストレージにエクスポートできます。 
- エクスポートはフォワード データ ストリームです。 ストリームは補充できません。 
- エクスポートには固定のスキーマがあります。 イベントにカスタム プロパティを追加した場合、それらは含まれません。 新しいエクスポートを作成する必要があります。

## <a name="prerequisites"></a>前提条件

エクスポートを設定する前に、Azure ポータルへのアクセスとアクティブなサブスクリプションが必要です。 エクスポートの際には、ストレージのアカウント情報が必要になります。 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Azure Data Lake Storage の Gen 2 アカウントを作成する

1. Azure ポータルにログインし、[新しいストレージ アカウントを作成](/azure/storage/common/storage-account-create)します。 

1. **詳細** タブで、**階層型名前空間** を有効化していることを確認してください。 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="詳細ブで階層型名前空間を有効にする。":::

1. デプロイ後は、新しく作成したストレージ アカウントに移動します。 ナビゲーション ウィンドウで、**設定** > **アクセス キー** を選択します。 

1. **アカウント名** と **キー** ををコピーし、新しいエクスポートの作成時に使用します。
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="ストレージ アカウントのアクセス キー。":::

## <a name="export-events"></a>イベントをエクスポート

イベントのエクスポートには、次の 2 つの方法があります: 
- **データ** > **エクスポート** に移動し、**新規エクスポート** を選択します。
- **データ** > **イベント** に移動して、エクスポートするイベントの横にある **その他 [...]** を選択し、ドロップダウン メニューから **エクスポート** を選択します。 

エクスポートを作成する手順をガイドします:

1. **エクスポート名** を入力します。

1. **イベントの選択** ドロップダウン リストで、エクスポートに含める基本イベントと絞り込んだイベントを選択します。 

1. **ファイル構造** 配下で、ケイデンスを選択して、宛先ストレージに新しいファイルを作成します。 イベントが到着すると継続的にエクスポートされます。

1. エクスポートの形式を選択します。 **Common Data Model**、**CSV**、**JSON** フォーマットから選択できます。 エクスポートを他の Dynamics 365 アプリケーションで使用する場合は、Common Data Model フォーマットの使用を推奨します。

1. **対象を選択** ステップで、Azure Data Lake Storage Gen 2 の場所を指定します。
    1. **ADLS Gen2 アカウント名** は、エクスポートを保存するストレージ アカウントの名前です。 
    1. **フォルダ パス** は、ストレージ アカウントのファイル システムとディレクトリ構造のどこにエクスポートを保存するかを定義します。
    1. **共有キー** は、そのストレージ アカウントの Azure ポータルから利用できます。

1. 選択した内容を確認し、確定します。

## <a name="view-and-manage-exports"></a>エクスポートの表示と管理

エクスポートの設定後は、**データ** > **エクスポート** に移動して表示します。 既存のエクスポートを編集または削除するには、**その他 [...]** を選択します。


[!INCLUDE[footer-include](../includes/footer-banner.md)]