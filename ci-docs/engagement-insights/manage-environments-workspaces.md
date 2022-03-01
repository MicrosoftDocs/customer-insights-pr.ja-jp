---
title: ワークスペースと環境の管理
description: ワークスペースと環境の作成、名前変更、削除をする方法。
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 279af24358a1d6ea2b4cc75d5496042af73a7cae
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645452"
---
# <a name="manage-environments-and-workspaces"></a>環境とワークスペースの管理

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>概要

このトピックでは、作成済みのワークスペースと環境を管理する方法について説明します。 

- *ワークスペース* とは、イベントやレポートを保存、管理するためのスペースです。 ここでは、ユーザーの活動をリアルタイムで確認することができます。 ワークスペースの作成時には、ワークスペースに送信するデータの種類を選択します。 現在、Web データとモバイル アプリがサポートされています。 詳細については、[ワークスペースを作成してメンバーを追加する](create-workspace.md)を参照してください。

- *環境* とは、ワークスペースや接続を管理するスペースです。 詳しくは、[新しい環境を作成する](create-new-environment.md)をご覧ください。

## <a name="manage-an-existing-workspace"></a>既存ワークスペースの管理

環境内では複数のワークスペースを同時に管理することができます。 [ロール](user-roles.md)は、どのような作業ができるかを特定します。 

 - ワークスペースを管理するには、環境管理者、またはワークスペース管理者である必要があります。
 - ワークスペース管理者は、既存のワークスペースの名前を変更したり、削除したりできます。 

:::image type="content" source="media/workspace-edit.png" alt-text="ワークスペース管理センター":::

### <a name="edit-a-workspace-name"></a>ワークスペース名を編集する

1. **管理者** > **ワークスペース** に移動し、**設定** を選択します。

1. **ワークスペース名** ボックスに新しい名前を入力します。

1. **保存** を選択して変更を適用します。

### <a name="delete-a-workspace"></a>ワークスペースの削除

ワークスペースを削除すると、そのすべてのコンテンツ、データ、設定、およびアクセス許可が完全に削除されます。 これは元に戻せません。

1. **管理者** > **ワークスペース** に移動し、**設定** を選択します。

1. **ワークスペース の削除** を選択します。 

1. **ワークスペースを削除する** ダイアログに、すべて大文字で **CONFIRM DELETE** と入力します。 

1. **削除** を選択して、ワークスペースを完全に削除します。

### <a name="manage-workspace-members"></a>ワークスペースのメンバーを管理する

1. **管理者** > **ワークスペース** に移動し、**メンバー** を選択します。

1. **メンバーの追加** を選択してアクセスを許可し、[役割を割り当て](user-roles.md)ます。 現在、**ワークスペース管理者** のみが使用できます。

1. **メンバーの追加** を選択し、ワークスペースに追加します。

## <a name="manage-an-existing-environment"></a>既存環境の管理

環境の管理者は、左側のナビゲーション ペインから環境にアクセスできます。 環境設定、その他の環境管理者、ワークスペースを構成できます。 管理センターの異なる領域間を移動するには、タブを選択します。

:::image type="content" source="media/environment-edit.png" alt-text="環境の管理センター。":::

### <a name="rename-an-environment"></a>環境の名称変更

1. **管理者** > **環境** に移動し、**設定** を選択します。

1. **環境名** を更新し、**保存** を選択して変更を適用します。

### <a name="manage-environment-members"></a>環境のメンバーを管理する

1. **管理者** > **環境** に移動し、**メンバー** を選択します。

1. **メンバーの追加** を選択してメンバーを更新し、[役割を割り当て](user-roles.md)ます。 現在、**環境管理者** のみが使用できます。

1. **メンバーの追加** を選択し、環境に追加します。

### <a name="delete-an-environment"></a>環境の削除

環境の管理者は環境を削除できます。 環境を削除する前に、その配下にあるすべてのワークスペースを削除する必要があります。

1. **管理者** > **環境** に移動し、**設定** を選択します。

1. **環境の削除** を選択します。 

1. **ワークスペースを削除する** ダイアログに、すべて大文字で **CONFIRM DELETE** と入力します。 

1. **削除** を選択して、環境を恒久的に削除します。

## <a name="manage-connections"></a>接続の管理

対象ユーザー分析情報への接続を確立することで、統一された顧客プロファイルに基づいたエンゲージメント分析情報のレポートを見ることができます。 

詳細情報については、[対象ユーザー インサイトとエンゲージメント インサイトの間にリンクを作成する](integrate-audience-insights-engagement-insights.md)を参照してください。

## <a name="manage-personal-data"></a>個人データの管理

顧客の個人情報を保護するために、エンドユーザーを特定できるデータを削除したり、エクスポートしたりすることができます。

詳細については、[個人情報を含むイベントデータの削除とエクスポート](delete-export-personal-data.md)を参照してください。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
