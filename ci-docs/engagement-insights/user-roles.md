---
title: ロールとアクセス許可
description: ワークスペース メンバーに使用可能なロールとアクセス許可の概要。
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645543"
---
# <a name="roles-and-permissions"></a>ロールとアクセス許可

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

ワークスペースとは、イベントやレポートを保存、管理する場所です。 詳細については、[ワークスペースを作成してメンバーを追加する](create-workspace.md)を参照してください。 

ワークスペースには、次の役割とアクセス許可を含めることができます。

- *メンバー* ロールは、ワークスペースにアクセスできるユーザーです。 メンバーをワークスペースに割り当て、ロールとアクセス許可を定義できます。 
- *管理者* ロールでは、ワークスペースと環境を管理し、他のユーザーのエンゲージメント分析情報を構成できます。 
- *投稿者* 役割は、エンゲージメント分析情報を構成する必要はないが、独自のレポート、じょうご、またはセグメントを作成したいアナリストを対象としています。

## <a name="permissions"></a>権限
  
次のテーブルでは、各役割のアクセス許可を示します。 

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
