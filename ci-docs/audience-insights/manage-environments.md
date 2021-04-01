---
title: 環境の作成および管理
description: サービスにサインアップする方法と環境を管理する方法について説明します。
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598299"
---
# <a name="manage-environments"></a>環境の管理

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

この記事では、新しい組織を作成する方法と環境をプロビジョニングする方法について説明します。

## <a name="sign-up-and-create-an-organization"></a>サインアップと組織の作成

1. [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) Web サイトに移動します。

2. **使用開始** を選択します。

3. お好みの新規登録のシナリオを選択し、該当のリンクを選択します。

4. 利用条件に同意して、**続行** を選択し、組織の作成を開始します。

5. 環境が作成されると、[Customer Insights](https://home.ci.ai.dynamics.com) にリダイレクトされます。

6. デモ環境を使用してアプリを探索するか、次のセクションに示す手順に従って新しい環境を作成してください。

7. 環境の設定を指定した後、**作成する** を選択します。

8. 環境が正常に作成された後、サインインします。

## <a name="create-an-environment-in-an-existing-organization"></a>既存の組織で環境を作成する

新規環境を作成するには、次の 2 つの方法があります。 まったく新たな構成を指定することも、既存の環境から一部の構成設定をコピーすることも可能です。

環境の作成方法 :

1. アプリのヘッダーにある **環境** ピッカーを選択します。

1. **新規** をクリックします。

   > [!div class="mx-imgBorder"]
   > ![環境の設定](media/environment-settings-dialog.png)

1. **新しい環境の作成** ダイアログで **新しい環境** を選択します。

   [現在の環境からデータをコピー](#additional-considerations-for-copy-configuration-preview) する場合は、**既存の環境からコピー** を選択します。 データのコピー元となる組織の、利用可能なすべての環境のリストが表示されます。

1. 次の詳細を入力します:
   - **名前**: この環境の名前。 既存の環境からコピーする場合は、このフィールドには既にに入力されていますが、変更することもできます。
   - **リージョン** : サービスが展開、ホストされるリージョンを示します。
   - **タイプ**: 実稼働環境、またはサンドボックス環境のどちらを作成するかを選択します。

2. オプションで、**詳細設定** を選択できます:

   - **すべてのデータを保存する** : Customer Insights から生成された出力データを保存する場所を指定します。 次の2つの選択肢があります: **Customer Insights ストレージ** (Customer Insights チームが管理する Azure Data Lake) と **Azure Data Lake Storage Gen2** (ユーザーが管理する Azure Data Lake Storage) です。 既定では、Customer Insights のストレージが選択されています。

   > [!NOTE]
   > Azure Data Lake Storage にデータを保存することで、その Azure Storage のアカウントに対して適切な地理的位置にデータが転送され、保存されることに同意したことになります。これは、 Dynamics 365 Customer Insights におけるデータの保存場所とは異なる場合があります。 [Microsoft Trust Center を詳しく知る。](https://www.microsoft.com/trust-center)
   >
   > 現在、取り込まれたエンティティは常に Customer Insights が管理するデータレイクに保存されます。
   > 環境の作成時に選択したのと同じ Azure リージョンの Azure Data Lake Gen2 ストレージ アカウントのみをサポートします。
   > Azure Data Lake Gen2 Hierarchical Name Space (HNS) が有効となっているストレージ アカウントのみに対応しています。

   - Azure Data Lake Storage Gen2 オプションの場合、認証にリソース ベースのオプションとサブスクリプション ベースのオプションのどちらかを選択できます。 詳細については、[対象者に関するインサイトを Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。 **コンテナー** 名は変更できず、"customerinsights" になります。
   
   - [予測](predictions.md)を使う場合、または Microsoft Dataverse に基づいてアプリケーションやソリューションとのデータ共有を構成する場合は、**Microsoft Dataverse とのデータ共有を構成して、追加機能を有効にする** の下に Microsoft Dataverse 環境 URL を入力します。 **データ共有を有効にする** を選択して、Customer Insights 出力データを Microsoft Dataverse マネージド Data Lake と共有します。

     > [!NOTE]
     > - Microsoft Dataverse マネージド Data Lake とのデータ共有は、すべてのデータを自分の Azure Data Lake Storage に保存する場合、現在サポートされていません。
     > - [エンティティの欠落値の予測](predictions.md)は、Microsoft Dataverse マネージド Data Lake とのデータ共有を有効にした場合、現在はサポートされていません。

     > [!div class="mx-imgBorder"]
     > ![Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png) とのデータ共有を可能にする構成オプション

   データ インジェストやセグメントの作成などのプロセスを実行すると、対応するフォルダーが上記で指定したストレージ アカウントに作成されます。 データ ファイルと model.json ファイルが作成され、実行するプロセスに基づいてそれぞれのサブ フォルダーに追加されます。

   Customer Insights の複数の環境を作成し、それらの環境からの出力エンティティをストレージ アカウントに保存することを選択した場合、コンテナーに ci_<environmentid> が含まれる環境ごとに個別のフォルダーが作成されます。

### <a name="additional-considerations-for-copy-configuration-preview"></a>コピー構成に関する追加の考慮事項 (プレビュー)

以下の構成設定がコピーされます：

- 機能の構成
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

以下の構成設定はコピー *されません*：

- 顧客のプロファイル。
- データ ソースの資格情報。 すべてのデータ ソースの認証情報を提供し、データソースを手動で更新する必要があります。
- Common Data Model フォルダーのデータソース、および Common Data Service マネージド レイク。 これらのデータ ソースは、ソース環境と同じ名前で手動で作成する必要があります。

環境をコピーすると、新たな環境が作成されたことを示す確認メッセージが表示されます。 **データソースに移動する** を選択してデータ ソースのリストを表示します。

すべてのデータソースの状態が **資格情報が必須** となっています。 データソースを編集し、資格情報を入力して更新します。

> [!div class="mx-imgBorder"]
> ![コピーされたデータ ソース](media/data-sources-copied.png)

データソースの更新後、**データ** > **統一** に移動します。 ここには、ソース環境に由来する設定があります。 必要に応じて編集するか、**実行** を選択してデータ統合プロセスを開始し、統合された顧客エンティティを作成します。

データ統合の完了後は、**計測** と **セグメント** に移動し、それらを更新します。

## <a name="edit-an-existing-environment"></a>既存の環境を編集する

既存の環境について詳細な部分を編集できます。

1.  アプリのヘッダーにある **環境** ピッカーを選択します。

2.  **編集** アイコンを選択します。

3. **環境の編集** ボックスで、環境の **表示名** は更新できますが、**リージョン** または **タイプ** を変更することはできません。

4. 環境がデータを Azure Data Lake Storage Gen2 に保存するように構成されている場合は、 **アカウントキー** を更新することができます。 ただし、**アカウント名** または **コンテナー** 名前を変更することはできません。

5. オプションで、アカウント キー ベースの接続から、リソース ベースまたはサブスクリプション ベースの接続に更新できます。 一度アップグレードすると、アップグレード後にアカウント キーに戻すことはできません。 詳細については、[対象者に関するインサイトを Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。 接続の更新時に、**コンテナー** 情報を変更することはできません。

## <a name="reset-an-existing-environment"></a>既存の環境のリセット

管理者の場合、すべての構成を削除し、取り込んだデータを削除する場合は、環境を空の状態にリセットできます。

1.  アプリのヘッダーにある **環境** ピッカーを選択します。 

2.  リセットする環境を選択し、省略記号 **...** を選択します。 

3. **リセット** オプションを選択してください。 

4.  削除を確認するには、環境名を入力して、**リセット** を選択します。

## <a name="delete-an-existing-environment-available-only-for-admins"></a>既存の環境を削除する (管理者のみ利用可能)

管理者の場合、管理している環境を削除できます。

1.  アプリのヘッダーにある **環境** ピッカーを選択します。

2.  リセットする環境を選択し、省略記号 **...** を選択します。 

3. **削除** オプションを選択してください。 

4.  削除の確認をするには、当該環境の名前を入力して **削除** を選択します。


[!INCLUDE[footer-include](../includes/footer-banner.md)]