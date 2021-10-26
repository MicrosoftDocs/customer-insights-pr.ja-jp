---
title: 改良したイベントをエクスポートする
description: 改良したイベントとベースイベントをエクスポートする方法。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7881f8f63134170a7f76e3c75dcfc5fa8930754b
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606230"
---
# <a name="export-events"></a>イベントのエクスポート

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

イベントはユーザーの行動を表すものです。 ユーザーがページを表示したとき (イベントの表示)、またはコンテンツとやり取りしたタイミング (アクション イベント) で記録します。 レポートに表示するデータのプロパティを決めることができる場合、このデータの仮想ビューは *改良されたイベント* と呼ばれます。 詳細については、[イベントの作成と変更](refined-events.md)を参照してください。

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

**イベントのエクスポート** ダイアログを表示するには、2 通りの方法があります。 
- **データ** > **エクスポート** に移動し、**新規エクスポート** を選択します。
- **データ** > **イベント** に移動して、エクスポートするイベントの横にある **その他 [...]** を選択し、ドロップダウン メニューから **エクスポート** を選択します。 

:::image type="content" source="media/new-export.png" alt-text="新しいエクスポートの作成":::

エクスポートを作成する手順をガイドします:

1. **エクスポート名** を入力してから、次に **次へ** を選択します。

1. **イベントの選択** ドロップダウン リストで、エクスポートに含める基本イベントと絞り込んだイベントを選択します。 

1. **ファイル構造** セクションで、ケイデンス (毎時または毎日) を選択して、宛先ストレージに新しいファイルを作成してから、**次へ** を選択します。 イベントが到着すると継続的にエクスポートされます。

1. **フォーマットの選択** ダイアログで、エクスポートの形式を選択します。 **Common Data Model**、**CSV**、**JSON** フォーマットのいずれかを選択します。 他の Dynamics 365 アプリケーションでエクスポートを使用するには、**Common Data Model** フォーマットが推奨されます。

1. **宛先を選択する** ダイアログで、Azure Data Lake Storage Gen 2 の場所を指定します。
    1. **ADLS Gen2 アカウント名** は、エクスポートを保存するストレージ アカウントの名前です。 
    1. **フォルダ パス** は、ストレージ アカウントのファイル システムとディレクトリ構造のどこにエクスポートを保存するかを定義します。
    1. **共有キー** は、そのストレージ アカウントの Azure ポータルから利用できます。

1. 選択項目をレビューして確認し、終了します。

## <a name="view-and-manage-exports"></a>エクスポートの表示と管理

エクスポートの設定後は、**データ** > **エクスポート** に移動して表示します。 既存のエクスポートを編集または削除するには、**その他 [...]** を選択します。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
