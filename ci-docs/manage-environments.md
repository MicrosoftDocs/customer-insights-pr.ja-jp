---
title: 環境を管理する方法
description: 既存の Customer Insights 環境を管理者として管理する方法を説明します。"
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833498"
---
# <a name="how-to-manage-environments"></a>環境を管理する方法

管理者は環境の [作成](create-environment.md) と管理を行います。 また、既存の環境で一部の設定を変更できます。 ビジネス、種類、地域、ストレージ オプション、Dataverse の設定は、環境の作成後に修正します。 これらの設定を変更する場合は、環境のリセットか、新しい環境の作成を行います。

## <a name="edit-an-existing-environment"></a>既存の環境を編集する

既存の環境について詳細な部分を編集できます。

1. アプリのヘッダーにある **環境** ピッカーを選択します。

1. **編集** アイコンを選択します。

   :::image type="content" source="media/edit-environment.png" alt-text="環境の設定を編集するアイコン。":::

1. **環境の編集** ボックスで、環境設定を更新できます。

新しい環境で開始する場合は [新しい環境の作成](create-environment.md) を参照してください。

## <a name="change-the-owner-of-an-environment"></a>環境の所有者を変更する

管理者アクセス許可は複数のユーザーが持てますが、環境の所有者は 1 人のユーザーのみです。 既定では、最初に環境を作成するのは管理者です。 環境の管理者は、管理者権限を持つ別のユーザーに所有権を割り当てることができます。

1. アプリのヘッダーにある **環境** ピッカーを選択します。

1. **編集** アイコンを選択します。

1. **環境の編集** ボックスで、**基本情報** ステップに移動します。

1. **環境の所有者を変更する** フィールドで、環境の新しい所有者を選択します。  

1. **レビューと完了**、**更新** の順に選択して、変更を適用します。

## <a name="claim-ownership-of-an-environment"></a>環境の所有権を要求する

所有者のユーザー アカウントの削除や一時停止を行った場合、その環境には所有者がいません。 所有権を要求することで、すべての管理者ユーザーが新しい所有者になれます。 環境を所有し続けることも、[所有権を別の管理者に変更](#change-the-owner-of-an-environment) することもできます。

所有権を要求するには、元の所有者が組織を離れたときに Customer Insights の各ページの上部に表示される **所有権を取得** ボタンを選択します。

## <a name="reset-an-existing-environment-preview"></a>既存の環境をリセットする (プレビュー)

環境の所有者は、すべての構成を削除して取り込んだデータを削除する場合、環境を空の状態にリセットできます。

1. アプリのヘッダーにある **環境** ピッカーを選択します。

1. リセットする環境を選択し、垂直の省略記号 (&vellip;) を選択します。

1. **リセット** オプションを選択してください。

   :::image type="content" source="media/reset-environment.png" alt-text="環境をリセットするコントロール。":::

1. 環境全体、データ ソースを除くすべて、または Unified customer profile 上に構成したものを、リセットするかどうか選択します。

1. 確認する際は、環境名を入力して **リセット** を選択します。

## <a name="delete-an-existing-environment"></a>既存の環境を削除する

環境の所有者は、管理する環境を削除できます。

1. アプリのヘッダーにある **環境** ピッカーを選択します。

1. リセットする環境を選択し、垂直の省略記号 (&vellip;) を選択します。 

1. **削除** オプションを選択してください。

   :::image type="content" source="media/delete-environment.png" alt-text="環境を削除するコントロール。":::

1. 削除の確認をするには、当該環境の名前を入力して **削除** を選択します。

> [!IMPORTANT]
> 環境を削除しても、Dataverse 環境への接続は削除されません。 今後、同じ Dataverse 環境を新しい Customer Insights 環境に接続する計画の場合、その接続を削除する必要があります。詳細な方法は [Dataverse 環境への既存の接続を削除する](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment) を参照してください。

[!INCLUDE [footer-include](includes/footer-banner.md)]
