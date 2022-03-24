---
title: 環境の作成および管理
description: サービスにサインアップする方法と環境を管理する方法について説明します。
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376882"
---
# <a name="manage-environments"></a>環境の管理

## <a name="switch-environments"></a>環境の切り替え

ページ右上隅にある **環境** コントロールを選択肢て、環境を変更します。

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="環境を切り替えるコントロールのスクリーンショット。":::

管理者は環境の[作成](create-environment.md)と管理ができます。

## <a name="edit-an-existing-environment"></a>既存の環境を編集する

既存の環境について詳細な部分を編集できます。

1.  アプリのヘッダーにある **環境** ピッカーを選択します。

2.  **編集** アイコンを選択します。

3. **環境の編集** ボックスで、環境設定を更新できます。

環境設定の詳細については、[新しい環境を作成する](create-environment.md)をご覧ください。

## <a name="connect-to-microsoft-dataverse"></a>Microsoft Dataverse への接続
   
**Microsoft Dataverse** ステップを使用すると、Customer Insights を Dataverse 環境に接続できます。

[すぐに使用できる予測モデル](predictions-overview.md#out-of-box-models)を使用するには、Dataverse とのデータ共有を構成します。 または、オンプレミスのデータ ソースからのデータ取り込みを有効にして、組織が管理する Microsoft Dataverse 環境 URL を提供します。

> [!IMPORTANT]
> データ共有を有効にするには、Customer Insights と Dataverse が同じリージョンにある必要があります。

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Microsoft Dataverse とのデータ共有を有効にする構成オプション。":::

> [!NOTE]
> Customer Insights では、次のデータ共有シナリオがサポートされていません。
> - すべてのデータを自分の Azure Data Lake Storage に保存する場合、Dataverse - マネージド データ レイクとのデータ共有を有効にすることはできません。
> - Dataverse とのデータ共有を有効にした場合、[エンティティに予測値または欠落値を作成する](predictions.md) ことができなくなります。

## <a name="copy-the-environment-configuration"></a>環境の構成をコピーする

新しい環境を作成するときに、既存の環境から構成をコピーすることを選択できます。 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="環境設定の設定オプションのスクリーンショット。":::

データのコピー元となる組織の、利用可能なすべての環境のリストが表示されます。

以下の構成設定がコピーされます：

- 取り込んだ/インポートされたデータ ソース
- データ統合 (マッピング、一致、マージ) の構成
- セグメント
- メジャー
- 顧客間関係
- 活動 
- 検索/フィルターのインデックス
- エクスポート先
- スケジュールされた更新
- エンリッチメント
- モデル管理
- ロールの割り当て

以下のデータはコピー *されません*:

- 顧客のプロファイル。
- データ ソースの資格情報。 すべてのデータ ソースの認証情報を提供し、データソースを手動で更新する必要があります。

- Common Data Model フォルダーと Dataverse- マネージド Data Lake からのデータ ソース。 これらのデータ ソースは、ソース環境と同じ名前で手動で作成する必要があります。

環境をコピーすると、新たな環境が作成されたことを示す確認メッセージが表示されます。 **データソースに移動する** を選択してデータ ソースのリストを表示します。

すべてのデータソースの状態が **資格情報が必須** となっています。 データソースを編集し、資格情報を入力して更新します。

:::image type="content" source="media/data-sources-copied.png" alt-text="コピーされた、認証が必要なデータソースのリスト。":::

データソースの更新後、**データ** > **統一** に移動します。 ここには、ソース環境に由来する設定があります。 必要に応じて編集するか、**実行** を選択してデータ統合プロセスを開始し、統合された顧客エンティティを作成します。

データ統合の完了後は、**計測** と **セグメント** に移動し、それらを更新します。

## <a name="change-the-owner-of-an-environment"></a>環境の所有者を変更する

Customer Insights では複数のユーザーが管理者権限を持つことができますが、環境の所有者は 1 人のユーザーのみです。 既定では、最初に環境を作成するのは管理者です。 環境の管理者は、管理者権限を持つ別のユーザーに所有権を割り当てることができます。

1. アプリのヘッダーにある **環境** ピッカーを選択します。

1. **編集** アイコンを選択します。

1. **環境の編集** ボックスで、**基本情報** ステップに移動します。

1. **環境の所有者を変更する** フィールドで、環境の新しい所有者を選択します。  

1. **レビューと完了**、**更新** の順に選択して、変更を適用します。 

## <a name="claim-ownership-of-an-environment"></a>環境の所有権を要求する

環境の所有者が組織を離れるか、ユーザー アカウントが削除された場合、環境には所有者がいなくなります。 管理者権限を持つユーザーは、所有権を要求して新しい所有者になることができます。 環境を所有し続けることも、[所有権を別の管理者に変更](#change-the-owner-of-an-environment) することもできます。 

所有権を要求するには、元の所有者が組織を離れたときに Customer Insights の各ページの上部に表示される **所有権を取得** ボタンを選択します。

## <a name="reset-an-existing-environment"></a>既存の環境のリセット

環境の所有者は、すべての構成を削除して取り込んだデータを削除する場合、環境を空の状態にリセットできます。

1.  アプリのヘッダーにある **環境** ピッカーを選択します。 

2.  リセットする環境を選択し、省略記号 (**...**) を選択します。 

3. **リセット** オプションを選択してください。 

4.  削除を確認するには、環境名を入力して、**リセット** を選択します。

## <a name="delete-an-existing-environment"></a>既存の環境を削除する

環境の所有者は、管理する環境を削除できます。

1.  アプリのヘッダーにある **環境** ピッカーを選択します。

2.  リセットする環境を選択し、省略記号 (**...**) を選択します。 

3. **削除** オプションを選択してください。 

4.  削除の確認をするには、当該環境の名前を入力して **削除** を選択します。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
