---
title: 新しいワークスペースの作成
description: ワークスペースの目的と新しいワークスペースの作成方法。
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 76b3466afd84aa439ea55afe90ae037825884f2d
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229083"
---
# <a name="create-a-new-workspace-and-add-members"></a>新しいワークスペースから作成してメンバーを追加する

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

ワークスペースでは、ユーザーのアクティビティをリアルタイムで確認し、対象ユーザーに対する理解を深めることができます。 ここで、イベントとレポートを保存、管理します。

ワークスペースの作成時には、対象となるデータの種類を選択します。 既存のワークスペースには、いつでも他のユーザーまたはメンバーを追加できます。 

## <a name="create-a-new-workspace"></a>新しいワークスペースの作成

ワークスペースを作るプロセスには、ワークスペースの整理に必要な *環境* を整えることも含まれます。 環境とは、1つまたは複数のワークスペースを含むことができるスペースです。 環境を使用して、ワークスペースと対象者分析情報機能への接続を管理できます。

1. ワークスペース スイッチャーから **+ 新規** を選択します。

   :::image type="content" source="media/new-workspace.png" alt-text="ナビゲーション ウィンドウと説明にコールアウトがある Customer Insights ページ。":::

1. **ワークスペース** ペインで、**ワークスペース名** を入力します。

   :::image type="content" source="media/workspace-name.png" alt-text="ワークスペース名を入力します。":::

1. 測定するプラットフォーム タイプ (Web またはモバイル) を選択します。

1. **詳細設定を表示する** を選択して、これらのオプション設定を有効または無効にします:

   - **不明から既知** を「有効」に切り替えて、以前に認証したユーザーに Web イベントを関連付けます。 詳細については、[以前に認証された訪問者からの Web イベントを認識する](unknown-to-known.md)を参照してください。
   - **ボット トラフィックをフィルタリングする** を「有効」に切り替えて、このワークスペースのボットによる Web トラフィックを削除します。 

1. 完了したら、**完了** を選択します。 

1. コード スニペットをインストールしてデータの受信を開始し、**終了** を選択して、ワークスペースを作成します。 詳細については、[開発者リソースの概要](developer-resources.md)を参照してください。

> [!NOTE]
> これで、メンバーを追加して、**役割** リストからのアクセス許可レベルを割り当てることができます。 詳細については、[ロールとアクセス許可](user-roles.md) を参照してください。 

詳細については、[環境の管理とワークスペース](manage-environments-workspaces.md) を参照してください。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
