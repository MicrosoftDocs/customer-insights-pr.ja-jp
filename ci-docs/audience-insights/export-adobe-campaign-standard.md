---
title: Customer Insights データを Adobe Campaign Standard にエクスポート
description: Adobe CampaignStandard で対象者に関するインサイト セグメントを使用する方法について説明します。
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760287"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Adobe CampaignStandard で Customer Insights セグメントの使用 (プレビュー)

Dynamics 365 Customer Insights の対象者インサイトのユーザーとして、関連する対象ユーザーをターゲットにすることで、マーケティング キャンペーンをより効率的にするためのセグメントを作成している可能性があります。 Adobe Experience Platform および Adobe Campaign Standardなどのアプリケーションで対象者に関するインサイトのセグメントを使用するには、この記事で概説するいくつかの手順に従う必要があります。

:::image type="content" source="media/ACS-flow.png" alt-text="この記事で概説されているステップのプロセス図。":::

## <a name="prerequisites"></a>前提条件

-   Dynamics 365 Customer Insights ライセンス
-   Adobe Campaign Standard ライセンス
-   Azure Blob Storage アカウント

## <a name="campaign-overview"></a>キャンペーン概要

Adobe Experience Platform で対象者に関するインサイトのセグメントを使用する方法をよりよく理解するために、架空のサンプル キャンペーンを見てみましょう。

あなたの会社が、米国の顧客に月次サブスクリプション ベースのサービスを提供していると仮定します。 今後 8 日以内にサブスクリプションの更新が予定されているが、サブスクリプションをまだ更新していない顧客を特定します。 これらの顧客を維持するために、Adobe Campaign Standard を使用して、電子メールでプロモーション オファーを送信します。

この例では、メールのプロモーション キャンペーンを 1 回実行します。 この記事では、キャンペーンを複数回実行するユース ケースについては説明しません。 ただし、対象者に関するインサイトと Adobe Campaign Standard は、定期的なキャンペーン シナリオでも機能するように構成できます。

## <a name="identify-your-target-audience"></a>対象ユーザーの特定

このシナリオでは、顧客の電子メール アドレスが対象者に関するインサイトで利用可能であり、セグメントのメンバーを特定するために顧客のプロモーションの好みが分析されたと仮定します。

[対象者に関するインサイトで定義したセグメント](segments.md) は **ChurnProneCustomers** と呼ばれ、これらの顧客に電子メール プロモーションを送信する予定です。

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers セグメントが作成されたセグメント ページのスクリーンショット。":::

送信するキャンペーン メールには、名、姓、顧客のサブスクリプション終了日が含まれます。 サブスクリプションが終了する前に更新した場合に得られる割引について顧客に通知します。

## <a name="export-your-target-audience"></a>対象ユーザーのエクスポート

### <a name="configure-a-connection"></a>接続の構成

対象ユーザーを特定した上で、対象者に関するインサイトから Azure Blob Storage アカウントへのエクスポートを構成できます。

1. 対象者に関するインサイトで、**管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**Adobe Campaign** を選択して接続を構成するか、**Adobe Campaign** タイルで **設定** を選択します

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard の構成タイル。":::

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. セグメントをエクスポートする Azure Blob Storage アカウントの **アカウント名**、**アカウント キー**、および **コンテナー** を入力します。  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="ストレージ アカウント構成のスクリーンショット。"::: 

   - Azure Blob ストレージアカウント名とアカウントキーを見つける方法の詳細については、[Azure ポータルでストレージ アカウント設定を管理する](/azure/storage/common/storage-account-manage)を参照してください。

   - コンテナの作成方法については、[コンテナを作成する](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)を参照してください。

1. **保存** を選択して、接続を完了します。

### <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、Adobe Campaign セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. エクスポートするセグメントを選択します。 この例では、**ChurnProneCustomers** です。

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers セグメントが選択されたセグメント選択ユーザー インターフェイスのスクリーンショット。":::

1. **次へ** を選択します。

1. 次に、対象者に関するインサイト セグメントの **ソース** フィールドを Adobe Campaign Standard プロファイル スキーマの **ターゲット** フィールド名にマップします。

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard コネクタのフィールド マッピング。":::

   属性をさらに追加する場合は、**属性の追加** を選択します。 ターゲット名はソース フィールド名と異なることがあるため、2 つのシステムでフィールド名が同じでない場合でも、対象者に関するインサイトからのセグメント出力を Adobe Campaign Standard にマップできます。

   > [!NOTE]
   > メール アドレスは ID フィールドとして使用されますが、対象者に関するインサイトの顧客プロファイルからその他の識別子を使用して、データを Adobe Campaign Standard にマップできます。

1. **保存** を選択します。

エクスポート先を保存した後、**データ** > **エクスポート** に表示されます。

これで、[セグメントをオンデマンドでエクスポート](export-destinations.md#run-exports-on-demand) できるようになりました。 エクスポートは、[スケジュールされた更新](system.md) ごとに実行されます。

> [!NOTE]
> エクスポートされたセグメントのレコード数が、Adobe Campaign Standard ライセンスの許可された制限内にあることを確認してください。

エクスポートされたデータは、上記で構成した Azure Blob Storage コンテナーに格納されます。 次のフォルダー パスがコンテナーに自動的に作成されます:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

例: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard の構成

対象者に関するインサイトのセグメントをエクスポートすると、前の手順でエクスポート先を定義するときに選択した列が含まれます。 このデータを使用して、[Adobe Campaign Standard でプロファイルを作成](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles) できます。

Adobe Campaign Standard でセグメントを使用するには、Adobe Campaign Standard のプロファイル スキーマを拡張して、2 つの追加フィールドを含める必要があります。 Adobe Campaign Standard の新しいフィールドを使用して [プロファイル リソースを拡張](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) する方法を説明します。

この例では、これらのフィールドは *セグメント名とセグメント日付 (オプション)* です。

これらのフィールドを使用して、このキャンペーンのターゲットとする Adobe Campaign Standard のプロファイルを識別します。

インポートするもの以外に Adobe Campaign Standard に他のレコードがない場合は、この手順をスキップできます。

## <a name="import-data-into-adobe-campaign-standard"></a>Adobe Campaign Standard にデータをインポート

すべてが整ったので、準備した対象ユーザー データを対象者に関するインサイトから Adobe Campaign Standard にインポートして、プロファイルを作成する必要があります。 ワークフローを使用して、[Adobe Campaign Standard でプロファイルをインポートする方法](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) について説明します。

次の図のインポート ワークフローは、8 時間ごとに実行するように構成されており、エクスポートされた対象者に関するインサイト セグメント (Azure Blob Storage の .csv ファイル) を検索します。 ワークフローは、指定された列の順序で .csv ファイルのコンテンツを抽出します。 このワークフローは、基本的なエラー処理を実行し、Adobe Campaign Standard でデータをハイドレートする前に、各レコードに電子メール アドレスがあることを確認するために構築されています。 ワークフローは、ACS プロファイル データにアップサートする前に、ファイル名からセグメント名も抽出します。

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard ユーザー インターフェイスのインポート ワークフローのスクリーンショット。":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard で対象ユーザーの取得

データが Adobe Campaign Standard にインポートされると、[ワークフローを作成](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) し、*セグメント名* と *セグメント日付* に基づいて顧客に対して [クエリ](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) を実行し、サンプル キャンペーンで特定されたプロファイルを選択できます。

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard を使用したメールの作成と送信

メール コンテンツを作成し、メールを [テストおよび送信](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) します。

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard からの更新キャンペーンを含むサンプル メール。":::
