---
title: Customer Insights データを  Adobe Campaign Standard にエクスポートする
description: Adobe Campaign Standard で Customer Insights セグメントを使用する方法について学びます。
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 2a62d2f889f199222eeb8cc969fce62fa89fa6f0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646973"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Adobe Campaign Standard で Customer Insights のセグメントを使用する (プレビュー)

ユーザー Dynamics 365 Customer Insights として、関連するオーディエンスをターゲットにすることで、マーケティング キャンペーンをより効率的にするためのセグメントを作成した可能性があります。 Adobe Experience Platform や Adobe Campaign Standard のようなアプリケーションで Customer Insights からのセグメントを使用するには、この記事で概説されているいくつかの手順に従う必要があります。

:::image type="content" source="media/ACS-flow.png" alt-text="この記事で概説されているステップのプロセス図。":::

## <a name="prerequisites"></a>前提条件

-   Dynamics 365 Customer Insights ライセンス
-   Adobe Campaign Standard のライセンス
-   Azure Blob Storage アカウント

## <a name="campaign-overview"></a>キャンペーン 概要

Adobe Experience Platform で Customer Insights からのセグメントをどのように使用できるかをよりよく理解するためには、架空のサンプル キャンペーンを見てみましょう。

あなたの会社が、米国の顧客に月次サブスクリプション ベースのサービスを提供していると仮定します。 今後 8 日以内にサブスクリプションの更新が予定されているが、サブスクリプションをまだ更新していない顧客を特定します。 これらの顧客を維持するために、Adobe Campaign Standard を使って、メールでキャンペーン情報を送信します。

この例では、メールのプロモーション キャンペーンを 1 回実行します。 この記事では、キャンペーンを複数回実行するユース ケースについては説明しません。 ただし、 Customer Insights と Adobe Campaign Standard は、定期的なキャンペーン シナリオでも機能するように構成できます。

## <a name="identify-your-target-audience"></a>対象ユーザーの特定

このシナリオでは、顧客のメール アドレスが利用可能であり、セグメントのメンバーを特定するために顧客のプロモーション設定が分析されたと想定しています。

[Customer Insights で定義したセグメント](segments.md) は、**ChurnProneCustomers** と呼ばれ、あなたはこれらの顧客に電子メール プロモーションを送ることを計画しています。

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers セグメントが作成されたセグメント ページのスクリーンショット。":::

送信するキャンペーン メールには、名、姓、顧客のサブスクリプション終了日が含まれます。 サブスクリプションが終了する前に更新した場合に得られる割引について顧客に通知します。

## <a name="export-your-target-audience"></a>対象ユーザーのエクスポート

### <a name="configure-a-connection"></a>接続の構成

ターゲット対象者を特定したら、Azure Blob Storage アカウントへのエクスポートを構成できます。

1. Customer Insights で、**管理者** > **接続** に移動します。

1. **接続の追加** を選択して **Adobe Campaign** を選択して接続を構成、または **Adobe Campaign** タイルの **設定** を選択します。

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard の構成タイル。":::

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. セグメントをエクスポートする Azure Blob Storage アカウントの **アカウント名**、**アカウント キー**、および **コンテナー** を入力します。  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="ストレージ アカウント構成のスクリーンショット。"::: 

   - Azure Blob Storage アカウント名とアカウント キーを見つける方法の詳細については、[Azure portal でストレージ アカウント設定を管理する](/azure/storage/common/storage-account-manage) を参照してください。

   - コンテナの作成方法については、[コンテナを作成する](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)を参照してください。

1. **保存** を選択して、接続を完了します。

### <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポートの追加** を選択します。

1. **エクスポート用の接続** フィールドで、Adobe Campaign セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は利用できません。

1. エクスポートするセグメントを選択します。 この例では、**ChurnProneCustomers** です。

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers セグメントが選択されたセグメント選択ユーザー インターフェイスのスクリーンショット。":::

1. **次へ** を選択します。

1. 今、私たちは Customer Insights セグメントからの **ソース** を  Adobe Campaign Standard プロファイル スキーマで **ターゲット** フィールドにマップします。

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard コネクタのフィールド マッピング。":::

   属性をさらに追加する場合は、**属性の追加** を選択します。 ターゲット名はソース フィールド名とは異なる場合があるため、2つのシステムでフィールドの名前が同じでない場合は、Customer Insights からのセグメント出力を Adobe Campaign Standard にまだマップできます。

   > [!NOTE]
   > メールアドレスは ID フィールドとして使用されますが、顧客プロファイルの他の識別子を使用してデータを Adobe Campaign Standard にマップできます。

1. **保存** を選択します。

エクスポート先を保存した後、**データ** > **エクスポート** に表示されます。

これで、[セグメントをオンデマンドでエクスポート](export-destinations.md#run-exports-on-demand) できるようになりました。 エクスポートは、[スケジュールされた更新](system.md) ごとに実行されます。

> [!NOTE]
> エクスポートされたセグメントのレコード数が、ご利用の Adobe Campaign Standard のライセンスの許容範囲内であることを確認してください。

エクスポートされたデータは、上記で構成した Azure Blob Storage コンテナーに格納されます。 次のフォルダー パスがコンテナーに自動的に作成されます:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

例: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard を構成する

エクスポートされたセグメントには、前の手順でエクスポート先を定義するときに選択した列が含まれています。 このデータは、[Adobe Campaign Standard でのプロファイル作成](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)に使用できます。

Adobe Campaign Standard でセグメントを使用するには、Adobe Campaign Standard のプロファイル スキーマを拡張して、2 つのフィールドを追加する必要があります。 Adobe Campaign Standard で新しいフィールドを使用して[プロファイル リソースを拡張する](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing)方法について説明します。

この例では、これらのフィールドは *セグメント名とセグメント日付 (オプション)* です。

これらのフィールドを使って、このキャンペーンで対象とする Adobe Campaign Standard のプロファイルを特定します。

Adobe Campaign Standard に、インポートするレコード以外のレコードがない場合は、このステップは省略できます。

## <a name="import-data-into-adobe-campaign-standard"></a>Adobe Campaign Standard にデータをインポートする

すべてが整ったので、準備した対象者データを Customer Insights から Adobe  Campaign Standard にインポートしてプロファイルを作成する必要があります。 ワークフローを使って[Adobe Campaign Standard でプロファイルをインポートする方法](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences)を説明します。

次の画像のインポート ワークフローは、8 時間ごとに実行され、エクスポートされた Customer Insights セグメント (Azure Blob Storage の.csvファイル) を探すように構成されています。 ワークフローは、指定された列の順序で .csv ファイルのコンテンツを抽出します。 このワークフローは、基本的なエラー処理を行い、各レコードのメールアドレスを確認してから、Adobe Campaign Standard にデータをハイドレートするように作られています。 ワークフローは、Adobe Campaign Standard プロファイル データにアップサートする前に、ファイル名からセグメント名も抽出します。

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard のユーザーインターフェイスでのインポートワークフローのスクリーンショット。":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard で対象ユーザーを取得する

Adobe Campaign Standard にデータが取り込まれた後に、[ワークフローを作成](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data)し、*セグメント名* と *セグメントの日付* に基づいて顧客に[問い合わせ](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data)、サンプルキャンペーンで特定されたプロファイルを選択することができます。

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard を使用してメールを作成して送信する

メール コンテンツを作成し、メールを [テストおよび送信](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) します。

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard からの更新オファーを含むサンプル メール。":::
