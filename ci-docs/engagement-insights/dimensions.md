---
title: 分析コードの表示と作成
description: 分析コードを作成、編集、削除する方法。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034003"
---
# <a name="view-and-create-dimensions"></a>分析コードの表示と作成

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

分析コードとは、データを記述、フィルター、またはグループ化できるイベントの属性です。 Web サイトでマーケティング プロモーションを実行している場合は、分析コードを使用して、新規ユーザーとリピーターで訪問者を並べ替えることができます。  

エンゲージメント インサイトには、イベント プロパティのすぐに使用できる分析コードが含まれます。 以下に例を示します。

- ブラウザー名
- ページ名
- デバイス モデル
- オペレーティング システム
- 国

## <a name="view-dimensions"></a>分析コードの表示

分析コードは、既存のイベント プロパティに基づいています。 エンゲージメント インサイトに追跡コードを使用すると、システム分析コードが自動的に作成されます。

1. 左側のナビゲーション ウィンドウで、**データ** に移動します。 
1. **分析コード** を選択して、ワークスペース内のすべての分析コードの一覧を表示します。 
   > [!NOTE]
   > システムで生成された分析コードは読み取り専用です。 分析コードを編集できません。 カスタム分析コードの作成と編集のみが可能です。

## <a name="create-a-dimension"></a>ディメンションを作成する

システムで生成された分析コードに加えて、環境およびワークスペースの管理者は、カスタム分析コードを作成できます。 カスタム分析コードは、基本イベントの既定のプロパティに基づくか、[イベントのカスタム プロパティ](advanced-SDK-implementation.md) を使用できます。

1. **データ** > **分析コード** に移動します。
1. **分析コードの追加** を選択します。

   :::image type="content" source="media/add-dimension.png" alt-text="イベントに分析コードを追加する。":::

1. **分析コードの作成** ペインで、分析コードの基準となるプロパティを選択します。 プロパティの一覧には、分析コードに割り当てられていないワークスペース内のすべてのプロパティが表示されます。
1. **表示名** ボックスに名前を入力します。 必要に応じて、説明を追加できます。
1. **作成** を選択して、分析コードを保存します。 [カスタム レポート](custom-reports.md) または [セグメント](segments.md) で分析コードを使用できるようになるまで、最大 1 分かかる場合があります。 

## <a name="edit-a-dimension"></a>分析コードの編集

分析コードの名前と説明を変更できます。

1. **データ** > **分析コード** に移動します。
1. 削除する分析コードを選します。
1. **分析コードの編集** ペインで、分析コードを更新します。
1. **適用** を選択して、変更を適用します。

## <a name="delete-a-dimension"></a>分析コードの削除

ユーザーが作成した分析コードは削除できますが、システム分析コードを削除することはできません。

分析コードの削除は永続的です。 削除された分析コードを使用するレポートとセグメントは機能しなくなります。 

1. **データ** > **分析コード** に移動します。
1. 削除する分析コードを選します。
1. **分析コードの編集** ペインで、**分析コードの削除** を選択します。

   :::image type="content" source="media/delete-dimension.png" alt-text="イベントの分析コードを削除する。":::

1. **削除を確認** (すべて大文字で) を入力して、削除を確認します。 
1. **削除** を選択します。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
