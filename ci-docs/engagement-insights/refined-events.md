---
title: 絞り込まれたイベントを作成および変更する
description: 絞り込まれたイベントを作成および変更する方法。
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034780"
---
# <a name="create-and-modify-refined-events"></a>絞り込まれたイベントを作成および変更する

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


イベントは、Web サイトでのアクティビティなど、ユーザーの行動を表すデータです。

- *基本* イベントは、ユーザーがページを表示したとき (イベントの表示)、またはコンテンツとやり取りしたとき (アクション イベント) に記録します。
- *絞り込まれた* イベントは、基本イベントの仮想ビューです。 プロパティを削除および追加するか、プロパティ値に基づいてイベントをフィルターすることにより、絞り込まれたイベントを定義します。

絞り込まれたイベントを使用して、[エクスポート](export-events.md) の基本イベントのスコープを縮小したり、公開に必要のないプロパティを削除します。

## <a name="create-refined-events"></a>詳細なイベントの作成

基本イベントから 絞り込まれたイベントを作成するには、3 つの方法があります。 

1. **データ**> **イベント** に移動し、次のいずれかのオプションを選択します:
    - **新しいイベント** を選択し、**絞り込まれたイベンの作成** を選択します。
    - 基本イベントを選択して詳細ビューを開き、トップメニューから **絞り込まれたイベンの作成** を選択します。
    - **その他 [...]** を選択し、基本イベントのショートカット メニューを開きます。 次に、**絞り込まれたイベンの作成** を選択します。
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="絞り込まれたイベントを作成するためのオプション。":::

1. **絞り込まれたイベント** ダイアログに次の情報を入力します:

- 新しいイベントを作成する場合は、**基本イベント** ドロップダウンからイベントを選択します。
- **絞り込まれたイベント表示名** ボックスに名前を入力します。
- 必要に応じて、スペースを使用せずに提案された **実際の名前** を更新します。

3. **作成** を選択して、設定を適用します。

1. 絞り込まれたイベントの詳細ビューで、**プロパティの追加と削除** を選択し、**プロパティの編集** ペインを開きます。 

1. チェック ボックスを使用して、表示するプロパティと非表示にするプロパティを選択します。 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="絞り込まれたイベントのプロパティを編集する。":::

1. **確定** を選択して、選択を適用します。

1. 構成を保存するには、**保存** を選択します。

## <a name="edit-refined-events"></a>絞り込まれたイベントの編集

絞り込まれたイベントの名前とプロパティを変更できます。

### <a name="edit-event-name"></a>イベント名の編集

1. **データ** > **イベント** に移動します。 
1. イベントの **その他 [...]** を選択し、**名前の編集** を選択します。
1. イベント名を更新して、**名前の変更** を選択します。

### <a name="edit-selected-properties"></a>選択されたプロパティの編集

1. **データ** > **イベント** に移動し、絞り込まれたイベントを選択して、詳細ビューを開きます。
1. **プロパティの追加と削除** を選択します。 
1. チェック ボックスの選択を編集します。
1. **確定**、**保存** の順に選択して、変更を適用します。

イベントのエクスポートについては、[イベントのエクスポート](export-events.md) を参照してください。
[!INCLUDE[footer-include](../includes/footer-banner.md)]
