---
title: クイック スタート製品の紹介
description: エンゲージメント インサイト機能を設定するための初回実行エクスペリエンス。
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 11/05/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: eebe51d343f6afbed52a66c52ab6a60eb5cd410367fb2e4409eb8679f357c91e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033913"
---
# <a name="first-run-experience"></a>初回実行のエクスペリエンス

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights の機能であるエンゲージメント インサイトでは、Web サイト上の顧客の行動を収集および測定できます。 この記事では、エンゲージメント インサイトへのサインアップ、ワークスペースの設定、ワークスペースへのメンバーの追加、変更の方法について説明します。

## <a name="sign-up-for-a-demo-of-engagement-insights"></a>エンゲージメント インサイトのデモにサインアップする

アクティブな Microsoft Azure Active Directory ユーザー アカウントが必要です。 

1. [エンゲージメント インサイト](https://pi.dynamics.com/) Web サイトを開きます。 

1. 学校または職場のアカウントでサインインします。

1. お住まいの地域を選択し、チェックボックスを使用して、メールによる最新情報やオファーの受信を希望するかどうかを示します。

1. **エンゲージメント インサイト (プレビュー) 利用規約** と **プライバシーに関する声明** を確認し、**デモを試す** を選択して承認します。

1. サンプル データのセットを使用して製品を探索します。 

## <a name="set-up-your-first-workspace-in-engagement-insights"></a>エンゲージメント インサイトで最初のワークスペースを設定する

ワークスペースは、イベントとレポートを保存および管理する方法です。

最初のワークスペースを作成するには

1. エンゲージメント インサイトで、**データを接続** を選択してウィザードを開始します。 

:::image type="content" source="media/banner.png" alt-text="Customer Insights ページのデータ接続ボタン。":::

2. 新しいワークスペースで測定するアクティビティの種類を選択します。 現在、**Web サイト アクティビティ** のみ使用可能です。 **アプリのアクティビティ** と **デバイスのアクティビティ** は、今後のリリースで使用可能になる予定です。

1. **次へ** を選択して、ワークスペースを確認し作成します。

1. コード スニペットを Web サイトに追加して、エンゲージメント インサイトでデータの受信を開始します。 これをすぐに実装することも、コードや手順を Web サイト管理者と共有することもできます。後でコード スニペットを見つけるには、**管理** > **ワークスペース** > **インストール ガイド** に移動します。

   > [!IMPORTANT]
   > コードが Web サイトに実装されるまで、データはワークスペースに表示されません。

1. **完了** を選択し、新しいワークスペースを開きます。 

## <a name="add-members-to-an-existing-workspace"></a>既存のワークスペースにメンバーを追加する

既定では、ワークスペースを作成したユーザーのみがアクセスできます。 組織から他のユーザーをいつでも既存のワークスペースに追加できます。

:::image type="content" source="media/add-members.png" alt-text="メンバーの追加ボタンにコールアウトがあるメンバー ページ。":::

1. **管理** > **ワークスペース** > **メンバー** に移動します。

2. **メンバーの追加** を選択します。 **メンバー** ボックスを使用して、組織内の他のユーザーを追加します。 一度に複数のメンバーを追加できます。

3. **ロール** を選択して、新しいメンバーに割り当てます。 現在、使用できるのは **ワークスペース管理者** のみです。 その他のロールは、今後のリリースで追加される予定です。

4. **メンバーの追加** を選択して確定します。

ワークスペースからメンバーを削除するには、**メンバー** ページでメンバーの名前の横にある **...** を選択し、ドロップダウン メニューから **削除** を選択します。

## <a name="edit-a-workspace"></a>ワークスペースを編集する

既存のワークスペースの詳細はいつでも編集できます。

:::image type="content" source="media/change-workspace-settings.png" alt-text="ワークスペース名と説明にコールアウトがあるワークスペース設定ページ。":::

1. **管理** > **ワークスペース** > **設定** に移動します。

1. ワークスペースの **名前** を変更します。

1. **保存** を選択して変更を適用します。

## <a name="add-another-new-workspace"></a>新しいワークスペースを追加する

:::image type="content" source="media/workspace-switcher.png" alt-text="ナビゲーション ウィンドウと説明にコールアウトがある Customer Insights ページ。":::

追加のワークスペースを作成して、データを分類できます。

1. ワークスペースの選択で、**新しいワークスペース** を選択します。

1. **名前** とオプションの **説明** を入力します。

1. **作成** を選択します。

## <a name="switch-between-workspaces"></a>ワークスペースを切り替える

ワークスペースを切り替えるには、ワークスペース切り替え機能を選択します。 新しいワークスペースを作成することも、**Web サンプル** を選択してレポートを表示し、サンプル データを使用して機能を試すこともできます。 



[!INCLUDE[footer-include](../includes/footer-banner.md)]