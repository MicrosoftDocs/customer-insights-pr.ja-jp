---
title: イベントの作成と変更
description: イベントを作成および変更する方法。
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228209"
---
# <a name="create-and-modify-events"></a>イベントの作成と変更

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

イベントは、Web サイトでのアクティビティなど、ユーザーの行動を表すデータです。

- *基本* イベントは、ユーザーがページを表示したとき (イベントの表示)、またはコンテンツとやり取りしたとき (アクション イベント) に記録します。
- *絞り込まれた* イベントは、基本イベントの仮想ビューです。 プロパティを削除および追加するか、プロパティ値に基づいてイベントをフィルターすることにより、絞り込まれたイベントを定義します。

## <a name="prerequisites"></a>前提条件

イベントを取得するには、コード スニペットを使用して、Web サイトのデータをエンゲージメント分析情報に接続する必要があります。 詳細については、[Web サイトに Web SDK をインストールする](instrument-website.md)を参照してください。

 :::image type="content" source="media/new-events-connect-data.png" alt-text="まずデータを接続します。":::

## <a name="create-refined-events"></a>絞り込まれたイベントを作成する

絞り込まれたイベントを使用して、[エクスポート](export-events.md) の基本イベントのスコープを縮小したり、公開に必要のないプロパティを削除します。

> [!NOTE]
> Web SDK を Web サイトに追加すると、基本イベントを表示して、絞り込まれたイベントを作成できます。 

基本イベントを表示するには:

1. 左側のナビゲーション ウィンドウで、**データ** に移動します。

1. **イベント** を選択して、ワークスペース内のすべてのイベントのリストを表示します。

    :::image type="content" source="media/data-events.png" alt-text="イベントを表示します。":::

基本イベントから絞り込まれたイベントを作成するには: 

1. **データ** > **イベント** と進み、画面の上部にある **+ 新しいイベント** を選択します。

1. **新しいイベント** ダイアログで、**絞り込まれたイベントを作成する** を選択して、**次へ** を選択します。
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="新しいイベント ウィザード。":::
     
1. **新しいエンティティ** ダイアログで、次の情報を入力します:

   - **基本イベント** ドロップダウンからイベントを選択します。
   - **絞り込まれたイベント表示名** ボックスに名前を入力します。
   - 必要に応じて、スペースを使用せずに提案された **実際の名前** を更新します。

1. **作成** を選択して、設定を適用します。

**イベント** リストに絞り込まれたイベントが表示されるようになります。

### <a name="edit-event-name"></a>イベント名の編集

基本イベントまたは絞り込まれたイベントの名前とプロパティを変更できます。

1. **データ** > **イベント** に移動します。 

1. イベントの **その他 [...]** を選択し、**名前の編集** を選択します。
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="絞り込まれたイベントを作成するためのオプション。":::

3. イベント名を更新して、**名前の変更** を選択します。

### <a name="view-the-details-of-a-refined-event"></a>絞り込まれたイベントの詳細を表示します:

1. **イベント** リストで、基本イベントまたは絞り込まれたイベントを選択します。 

1. 画面の上部にある **プロパティの追加と削除** を選択して、**プロパティを編集する** ペインを開きます。 

     :::image type="content" source="media/add-remove-properties.png" alt-text="プロパティの追加と削除を行います。":::

1. チェック ボックスを使用して、表示するプロパティと非表示にするプロパティを選択します。 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="絞り込まれたイベントのプロパティを編集する。":::

1. **確認** を選択して適用し、**保存** を選択します。


### <a name="edit-selected-properties-for-a-refined-event"></a>絞り込まれたイベントのために選択したプロパティを編集する

1. **データ** > **イベント** に移動し、絞り込まれたイベントを選択して、詳細ビューを開きます。
1. **プロパティの追加と削除** を選択します。 
1. チェック ボックスの選択を編集します。
1. **確定**、**保存** の順に選択して、変更を適用します。

イベントのエクスポートについては、[イベントのエクスポート](export-events.md) を参照してください。
[!INCLUDE[footer-include](../includes/footer-banner.md)]
