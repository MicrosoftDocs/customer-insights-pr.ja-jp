---
title: 環境の作成および管理
description: サービスにサインアップする方法と環境を管理する方法について説明します。
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e3f99f8f151aea5f120084382babd5e46e109545a4f63aafc51c3ecb1400cc33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034183"
---
# <a name="manage-environments"></a>環境の管理

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>環境の切り替え

ページ右上隅にある **環境** コントロールを選択肢て、環境を変更します。

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="環境を切り替えるコントロールのスクリーンショット。":::

管理者は環境の[作成](get-started-paid.md)と管理ができます。

## <a name="edit-an-existing-environment"></a>既存の環境を編集する

既存の環境について詳細な部分を編集できます。

1.  アプリのヘッダーにある **環境** ピッカーを選択します。

2.  **編集** アイコンを選択します。

3. **環境の編集** ボックスで、環境の **表示名** は更新できますが、**リージョン** または **タイプ** を変更することはできません。

4. Azure Data Lake Storage にデータを格納するように環境が構成されている場合、**アカウント キー** を更新できます。 ただし、**アカウント名** または **コンテナー** 名前を変更することはできません。

5. 必要に応じて、アカウント キー ベースの接続から、リソース ベースまたはサブスクリプション ベースの接続に更新できます。 一度アップグレードすると、アップグレード後にアカウント キーに戻すことはできません。 詳細については、[対象者に関するインサイトを Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。 接続の更新時に、**コンテナー** 情報を変更することはできません。

6. オプションで、**Microsoft Dataverse とのデータ共有を構成し、追加の機能を有効にする** の下にある Microsoft Dataverse 環境の URL を指定できます。 これらの機能には、Microsoft Dataverse に基づくアプリケーションおよびソリューションとのデータ共有、オンプレミスのデータ ソースからのデータ インジェスト、または使用 [予測](predictions.md) が含まれます。 **データ共有の有効化** を選択して、Customer Insights 出力データを Microsoft Dataverse Managed Data Lake と共有します。

   > [!NOTE]
   > - Microsoft Dataverse マネージド Data Lake とのデータ共有は、すべてのデータを自分の Azure Data Lake Storage に保存する場合、現在サポートされていません。
   > - [エンティティの欠落値の予測](predictions.md)および対象ユーザーインサイトの PowerBI Embedded レポート (ご利用の環境で有効になっている場合) は、Microsoft Dataverse マネージド Data Lake とのデータ共有を有効にした場合、現在サポートされていません。

   Microsoft Dataverse でデータ共有を有効にすると、データ ソースやその他のプロセスの完全更新が開始されます。 プロセスが現在実行中の場合は、Microsoft Dataverse とのデータ共有を有効にするオプションは表示されません。 これらのプロセスが完了するのを待つか、キャンセルして、データ共有を有効にします。 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Microsoft Dataverse とのデータ共有を有効にする構成オプション。":::
   
   データ インジェストやセグメントの作成などのプロセスを実行すると、対応するフォルダーが上記で指定したストレージ アカウントに作成されます。 実行するプロセスに応じて、データ ファイルと model.json ファイルが作成され、それぞれのサブフォルダーに追加されます。

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
- Common Data Model フォルダと Dataverse マネージド Data Lake のデータ ソース。 これらのデータ ソースは、ソース環境と同じ名前で手動で作成する必要があります。

環境をコピーすると、新たな環境が作成されたことを示す確認メッセージが表示されます。 **データソースに移動する** を選択してデータ ソースのリストを表示します。

すべてのデータソースの状態が **資格情報が必須** となっています。 データソースを編集し、資格情報を入力して更新します。

:::image type="content" source="media/data-sources-copied.png" alt-text="コピーされた、認証が必要なデータソースのリスト。":::

データソースの更新後、**データ** > **統一** に移動します。 ここには、ソース環境に由来する設定があります。 必要に応じて編集するか、**実行** を選択してデータ統合プロセスを開始し、統合された顧客エンティティを作成します。

データ統合の完了後は、**計測** と **セグメント** に移動し、それらを更新します。

## <a name="reset-an-existing-environment"></a>既存の環境のリセット

管理者の場合、すべての構成を削除し、取り込んだデータを削除する場合は、環境を空の状態にリセットできます。

1.  アプリのヘッダーにある **環境** ピッカーを選択します。 

2.  リセットする環境を選択し、省略記号 (**...**) を選択します。 

3. **リセット** オプションを選択してください。 

4.  削除を確認するには、環境名を入力して、**リセット** を選択します。

## <a name="delete-an-existing-environment"></a>既存の環境を削除する

管理者の場合、管理している環境を削除できます。

1.  アプリのヘッダーにある **環境** ピッカーを選択します。

2.  リセットする環境を選択し、省略記号 (**...**) を選択します。 

3. **削除** オプションを選択してください。 

4.  削除の確認をするには、当該環境の名前を入力して **削除** を選択します。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
