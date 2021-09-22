---
title: ロールとアクセス許可
description: ワークスペース メンバーに使用可能なロールとアクセス許可の概要。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036699"
---
# <a name="roles-and-permissions"></a>ロールとアクセス許可

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

ワークスペースは、イベントとレポートを保存および管理する方法です。 メンバーは、ワークスペースにアクセスできるユーザーです。 メンバーをワークスペースに割り当て、ロールとアクセス許可を定義できます。 管理者ロールでは、ワークスペースと環境を管理し、他のユーザーのエンゲージメントインサイトを構成できます。 共同作成者は、エンゲージメント インサイトを設定する必要はないが、独自のレポート、じょうご、セグメントを作成したいと考えているアナリストを対象としています。

## <a name="permissions"></a>権限
  
次のグラフは、各ロールのアクセス許可を示しています。 

| アクセス許可 | 環境管理者 | ワークスペース管理者 | 環境の共同作成者 | ワークスペースの共同作成者 | 
|--|--|--|--|--|
| 環境の作成 (作成者は自動的に環境管理者) | X* | X* | X* | X* |  
| 環境の構成 (環境メンバー、環境の削除) | X |  |  |  |  
| ワークスペースの作成 | X |  |  |  |  
| ワークスペースの構成 (ワークスペース メンバー、ワークスペースの削除) | X | X |  |  |  
| イベントと絞り込まれたイベントの構成 | X | X | |  |  
| ワークスペース イベントと絞り込まれたイベントの表示 | X | X | |  |  
| ワークスペース リソース (レポート、セグメント、およびメトリック) の表示| X | X | X | X |  
| カスタム レポートとじょうご作成する | X | X | X | X |  
| 基本指標と分析コードを作成する| X | X |  |  |  
| セグメントの作成| X | X | X | X |  

*プレビューでのみ試用環境を作成できます。 

## <a name="add-members"></a>メンバーを追加

ワークスペースおよび環境からメンバーを追加および削除できます。 詳細については、[環境とワークスペース](manage-environments-workspaces.md) を参照してください。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
