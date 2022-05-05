---
title: 環境の作成および管理
description: サービスにサインアップする方法と環境を管理する方法について説明します。
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: fcdb7f073ff73322ff69d0a8684391819a809d00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647135"
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

自分の Microsoft Dataverse 環境を提供し、Dynamics 365 Marketing や Power Apps のモデル駆動型アプリケーションなどの Dataverse ベースのビジネス アプリケーションを使用してデータ (プロファイルと分析情報) を共有します。

[すぐに使用できる予測モデル](predictions-overview.md#out-of-box-models)を使用するには、Dataverse とのデータ共有を構成します。 または、オンプレミスのデータ ソースからのデータ取り込みを有効にして、組織が管理する Microsoft Dataverse 環境 URL を提供します。

データ共有チェックボックスを選択して Microsoft Dataverse とのデータ共有を有効にすると、データ ソースと他のすべてのプロセスの完全な更新が 1 回トリガーされます。

> [!IMPORTANT]
> 1. データ共有を有効にするには、Customer Insights と Dataverse が同じリージョンにある必要があります。
> 1. Dataverse 環境のグローバル管理者ロールが必要です。 特定のセキュリティ グループにこの [Dataverse 環境が関連付けられいる](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment)か確認して、それらのセキュリティ グループに自分が追加されていることを確認してください。
> 1. 既存の Customer Insights 環境はまだ Dataverse 環境に関連付けられていません。 [Dataverse 環境への既存の接続を削除する](#remove-an-existing-connection-to-a-dataverse-environment)方法について説明します。

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Microsoft Dataverse とのデータ共有を有効にする構成オプション。":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>独自の Azure Data Lake Storage から Dataverse とのデータ共有を有効にする (プレビュー)

独自の Azure Data Lake Storage 環境を使用して Customer Insights データを格納するように環境が構成されている場合、Microsoft Dataverse とのデータ共有を有効にするには、追加の構成がいくつか必要です。

1. Azure サブスクリプションに 2 つのセキュリティ グループを作成します。1 つは **閲覧者** セキュリティ グループで、もう 1 つは **共同作成者** セキュリティ グループです。さらに、Microsoft Dataverse サービスを両方のセキュリティ グループの所有者として設定します。
2. これらのセキュリティ グループを使用して、ストレージ アカウントの Customer Insights コンテナのアクセス制御リスト (ACL) を管理します。 Microsoft Dataverse サービスと、Dynamics 365 Marketing などの任意の Dataverse ベースのビジネスアプリケーションを、**読み取り専用** アクセス許可を持つ **閲覧者** セキュリティ グループに追加します。 Customers Insights アプリケーション *のみ* を **共同作成者** セキュリティ グループに追加して、プロファイルと分析情報を書き込むための **読み取りと書き込み** の両方のアクセス許可を付与します。
   
#### <a name="prerequisites"></a>前提条件

PowerShell スクリプトを実行するには、次の 3 つのモジュールをインポートする必要があります。 

1. 最新バージョンの [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) をインストールします。
   1. PC で、キーボードの Windows キーを選択し、**Windows PowerShell** を検索し、**管理者として実行** を選択します。
   1. 開いた PowerShell ウィンドウで、`Install-Module AzureAD` を入力します。
2. 3 つのモジュールをインポートします。
    1. PowerShell ウィンドウで `Install-Module -Name Az.Accounts` と入力してから次の手順に従います。 
    1. `Install-Module -Name Az.Resources` と `Install-Module -Name Az.Storage` に対して繰り返します。

#### <a name="configuration-steps"></a>構成手順

1. エンジニアの [GitHub リポジトリ](https://github.com/trin-msft/byol)から実行する必要のある 2 つの PowerShell スクリプトをダウンロードします。
    1. `CreateSecurityGroups.ps1`
       - この PowerShell スクリプトを実行するには、*テナント管理者* のアクセス許可が必要です。 
       - この PowerShell スクリプトは、Azure サブスクリプションに 2 つのセキュリティ グループを作成します。 1 つは閲覧者グループ用で、もう 1 つは共同作成者グループ用です。これらの両方のセキュリティ グループの所有者として Microsoft Dataverse サービスを作成します。
       - Azure Data Lake Storage を含む Azure サブスクリプション ID を指定して、Windows PowerShell でこの PowerShell スクリプトを実行します。 エディターで PowerShell スクリプトを開き、追加情報と実装されているロジックを確認します。
       - このスクリプトで生成された両方のセキュリティ グループ ID 値を、`ByolSetup.ps1` スクリプトで使用するために保存します。
       
        > [!NOTE]
        > テナントでのセキュリティ グループの作成を無効にできます。 その場合、手動セットアップが必要になり、Azure AD 管理者が[セキュリティ グループの作成を有効にする](/azure/active-directory/enterprise-users/groups-self-service-management)必要があります。

    2. `ByolSetup.ps1`
        - このスクリプトを実行するにはストレージアカウント/コンテナーレベルで *ストレージ BLOB データ所有者* のアクセス許可が必要です。または、このスクリプトによって自分のアクセス許可が作成されます。 スクリプトを正常に実行した後、ロールの割り当てを手動で削除できます。
        - この PowerShell スクリプトは、Microsoft Dataverse サービスおよび任意の Dataverse ベースのビジネス アプリケーションに必要なロールベースのアクセス制御 (RBAC) を追加します。 また、`CreateSecurityGroups.ps1` スクリプトで作成されたセキュリティ グループの Customer Insights コンテナのアクセス制御リスト (ACL) を更新します。 共同作成者グループには *rwx* アクセスが付与され、閲覧者グループには *r-x* アクセス許可のみ付与されます。
        - Azure Data Lake Storage を含む Azure サブスクリプション ID ストレージ アカウント名、リソース グループ名、および閲覧者および共同作成者のセキュリティ グループ ID 値を指定して、Windows PowerShell でこの PowerShell スクリプトを実行します。 エディターで PowerShell スクリプトを開き、追加情報と実装されているロジックを確認します。
        - スクリプトを正常に実行した後、出力文字列をコピーします。 出力スクリプトは次のようになります: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. 上からコピーした出力文字列を、Microsoft Dataverse の環境構成ステップの **アクセス許可の識別子** フィールドに入力します。

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="独自の Azure Data Lake Storage から Microsoft Dataverse とのデータ共有を有効にするための構成オプション。":::

Customer Insights では、次のデータ共有シナリオがサポートされていません。
- Dataverse とのデータ共有を有効にした場合、[エンティティに予測値または欠落値を作成する](predictions.md) ことができなくなります。
- Dataverse とのデータ共有を有効にした場合、Customer Insights 環境でオプションの PowerBI Embedded レポートを表示できなくなります。

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Dataverse 環境への既存の接続を削除する

Dataverse 環境に接続すると、**この CDS 組織は、すでに別の Customer Insights インスタンスに接続されています** というエラー メッセージが表示されます。これは、Dataverse 環境が Customer Insights 環境ですでに使用されていることを意味します。 Dataverse 環境のグローバル管理者として既存の接続を削除できます。 変更の反映に数時間かかる場合があります。

1. [Power Apps](https://make.powerapps.com) に移動します。
1. 環境ピッカーから環境を選択します。
1. **ソリューション** に移動します
1. **Dynamics 365 Customer Insights 顧客カード アドイン (プレビュー)** という名前のソリューションをアンインストールまたは削除します。

OR 

1. Dataverse 環境を開きます。
1. **詳細設定** > **ソリューション** に移動します。
1. **CustomerInsightsCustomerCard** ソリューションをアンインストールします。

## <a name="copy-the-environment-configuration"></a>環境の構成をコピーする

管理者は、新しい環境を作成するときに、既存の環境から構成をコピーする選択ができます。 

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

## <a name="set-up-a-copied-environment"></a>コピーした環境の設定

環境の構成をコピーする際に、次のデータは *コピーされません*:

- 顧客のプロファイル。
- データ ソースの資格情報。 すべてのデータ ソースの認証情報を提供し、データソースを手動で更新する必要があります。
- Common Data Model フォルダーと Dataverse- マネージド Data Lake からのデータ ソース。 これらのデータ ソースは、ソース環境と同じ名前で手動で作成する必要があります。
- エクスポートとエンリッチメントに使用される接続シークレット。 接続を再認証してから、エンリッチメントとエクスポートを再アクティブ化する必要があります。 

環境をコピーすると、新たな環境が作成されたことを示す確認メッセージが表示されます。 **データソースに移動する** を選択してデータ ソースのリストを表示します。

すべてのデータソースの状態が **資格情報が必須** となっています。 データソースを編集し、資格情報を入力して更新します。

:::image type="content" source="media/data-sources-copied.png" alt-text="コピーされた、認証が必要なデータソースのリスト。":::

データソースの更新後、**データ** > **統一** に移動します。 ここには、ソース環境に由来する設定があります。 必要に応じて編集するか、**実行** を選択してデータ統合プロセスを開始し、統合された顧客エンティティを作成します。

データ統合の完了後は、**計測** と **セグメント** に移動し、それらを更新します。

エクスポートとエンリッチメントを再度アクティブ化する前に、**管理者** > **接続** に移動して、新しい環境での接続を再認証します。

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

> [!NOTE]
> 環境を削除しても、Dataverse 環境への関連付けは削除されません。[Dataverse 環境への既存の接続を削除する](#remove-an-existing-connection-to-a-dataverse-environment)方法をご確認ください。


[!INCLUDE [footer-include](includes/footer-banner.md)]
