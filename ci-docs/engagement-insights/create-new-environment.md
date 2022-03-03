---
title: 新しい環境を作成する
description: 環境の目的と新しい環境の作成方法。
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f82ff588c2ffbe82c3ee7df2498ac2cca2bad31
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225432"
---
# <a name="create-a-new-environment"></a>新しい環境を作成する 

## <a name="overview"></a>概要

環境とは、ワークスペースや接続を管理するスペースです。 環境をどのように使用するかは、組織や用途によって異なります。 たとえば、以下を実行できます:

- 1 つの環境。
- テスト環境と運用環境を分けます。
- 組織内の特定のチームや部門ごとに環境を分け、それぞれの対象ユーザーに関連するイベントを用意します。
- グローバルに展開する支社ごとに環境を分けることができます。
- Customer Insights の対象ユーザーの分析情報機能への接続。

## <a name="create-a-new-environment"></a>新しい環境を作成する

1. メイン バナーの右側で、環境ピッカーを選択してから、**+新規** を選択します。

   :::image type="content" source="media/environment-picker.png" alt-text="環境ピッカーを選択します。":::

1. **セットアップ** ペインで、**環境名** を入力します。

1. プランの種類に応じて、アカウントの **タイプ** を選択します。

1. **領域** を選択し、**次へ** を選択します。 

1. **ワークスペース名** を入力します。これにより、特定の Web サイトまたはアプリのデータを収集できます。 詳細については、[ワークスペースの作成](create-workspace.md)を参照してください。

1. 作成する **ワークスペース タイプ** (Web またはモバイル) を選択します。 

1. **詳細設定を表示する** を選択して、これらのオプション設定を有効または無効にします:

   - **不明から既知** を「有効」に切り替えて、以前に認証したユーザーに Web イベントを関連付けます。 詳細については、[以前に認証された訪問者からの Web イベントを認識する](unknown-to-known.md)を参照してください。
   - **ボット トラフィックをフィルタリングする** を「有効」に切り替えて、このワークスペースのボットによる Web トラフィックを削除します。 

1. 完了したら、**完了** を選択します。 

1. コード スニペットをインストールしてデータの受信を開始し、**終了** を選択して、ワークスペースを作成します。 詳細については、[開発者リソースの概要](developer-resources.md)を参照してください。

> [!NOTE]
> これで、メンバーを追加して、**役割** リストからのアクセス許可レベルを割り当てることができます。 詳細については、[ロールとアクセス許可](user-roles.md) を参照してください。 

詳細については、[環境の管理とワークスペース](manage-environments-workspaces.md) を参照してください。

## <a name="work-with-your-new-environment"></a>新しい環境で作業する

- [ワークスペースを作成](../engagement-insights/create-workspace.md)し、メンバーを追加します。
- [Web サイトにコードを追加する](../engagement-insights/instrument-website.md)または[モバイル アプリ](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps)。
- [リアルタイム レポート](../engagement-insights/view-reports.md)を表示するか、または[カスタム レポート](../engagement-insights/custom-reports.md)を作成します。
- エクスポートする [改良されたイベントを作成](../engagement-insights/refined-events.md)します。
- Data Lake Storage に[データをエクスポート](../engagement-insights/export-events.md)します。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
