---
title: Customer Insights データを Adobe Experience Platform にエクスポートする
description: Adobe Experience Platform で対象ユーザー インサイトのセグメントを使用する方法を説明します。
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fac976a49b1b5c5485b75e1262135738c913bd2230be7df8aa0ec12c59734053
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032123"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Adobe Experience Platform で Customer Insights のセグメントを使用する (プレビュー)

Dynamics 365 Customer Insights の対象者に関するインサイトのユーザーとして、関連する対象ユーザーをターゲットにすることで、マーケティング キャンペーンをより効率的にするためのセグメントが作成された可能性があります。 Adobe Experience Platform や Adobe Campaign Standard などのアプリケーションで対象ユーザーインサイトのセグメントを使用するには、この記事で紹介しているいくつかの手順に従う必要があります。

:::image type="content" source="media/AEP-flow.png" alt-text="この記事で概説されているステップのプロセス図。":::

## <a name="prerequisites"></a>前提条件

-   Dynamics 365 Customer Insights ライセンス
-   Adobe Experience Platform ライセンス
-   Adobe Campaign Standard のライセンス
-   Azure Blob Storage アカウント

## <a name="campaign-overview"></a>キャンペーン概要

Adobe Experience Platform で対象ユーザーインサイトからのセグメントの利用方法を理解するために、架空のサンプル キャンペーンを見てみましょう。

あなたの会社が、米国の顧客に月次サブスクリプション ベースのサービスを提供していると仮定します。 今後 8 日以内にサブスクリプションの更新が予定されているが、サブスクリプションをまだ更新していない顧客を特定します。 これらの顧客を維持するために、Adobe Experience Platform を使って、メールでキャンペーン情報を送信します。

この例では、メールのプロモーション キャンペーンを 1 回実行します。 この記事では、キャンペーンを複数回実行するユース ケースについては説明しません。

## <a name="identify-your-target-audience"></a>対象ユーザーの特定

このシナリオでは、顧客の電子メール アドレスが対象者に関するインサイトで利用可能であり、セグメントのメンバーを特定するために顧客のプロモーションの好みが分析されたと仮定します。

[対象者に関するインサイトで定義したセグメント](segments.md) は **ChurnProneCustomers** と呼ばれ、これらの顧客に電子メール プロモーションを送信する予定です。

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers セグメントが作成されたセグメント ページのスクリーンショット。":::

送信するキャンペーン メールには、名、姓、顧客のサブスクリプション終了日が含まれます。 サブスクリプションが終了する前に更新した場合に得られる割引について顧客に通知します。

## <a name="export-your-target-audience"></a>対象ユーザーのエクスポート

対象ユーザーを特定した上で、対象者に関するインサイトから Azure Blob Storage アカウントへのエクスポートを構成できます。

### <a name="configure-a-connection"></a>接続の構成

1. **管理** > **接続** に移動します。

1. 接続を構成するには、**接続の追加** を選択し、**Azure Blob Storage** を選ぶか、**Azure Blob Storage** タイルで **設定** を選択します。

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob Storage の構成タイル。"::: 

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. セグメントをエクスポートする Blob Storage アカウントの **アカウント名**、**アカウント キー**、および **コンテナー** を入力します。  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="ストレージ アカウント構成のスクリーンショット。"::: 
   
    - Blob Storage アカウント名とアカウント キーを検索する方法の詳細については、[Azure portal でストレージ アカウントの設定を管理する](/azure/storage/common/storage-account-manage) を参照してください。
    - コンテナの作成方法については、[コンテナを作成する](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)を参照してください。

1. **保存** を選択して、接続を完了します。 

### <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、Azure Blob Storage セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は利用できません。

1. エクスポートするセグメントを選択します。 この例では、**ChurnProneCustomers** です。

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers セグメントが選択されたセグメント選択ユーザー インターフェイスのスクリーンショット。":::

1. **保存** を選択します。

エクスポート先を保存した後、**データ** > **エクスポート** に表示されます。

これで、[セグメントをオンデマンドでエクスポート](export-destinations.md#run-exports-on-demand) できるようになりました。 エクスポートは、[スケジュールされた更新](system.md) ごとに実行されます。

> [!NOTE]
> エクスポートされたセグメントのレコード数が、ご利用の Adobe Campaign Standard のライセンスの許容範囲内であることを確認してください。

エクスポートされたデータは、上記で構成した Azure Blob Storage コンテナーに格納されます。 次のフォルダー パスがコンテナーに自動的に作成されます:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

例: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

エクスポートされたエンティティの *model.json* は、*%ExportDestinationName%* レベルにあります。

例: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Adobe Experience Platform でエクスペリエンス データモデル (XDM) を定義する

対象ユーザーインサイトからエクスポートしたデータを Adobe Experience Platform で使用する前に、エクスペリエンス データモデルのスキーマを定義し、[リアルタイム顧客プロファイルのデータを構成する](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials)必要があります。

[XDM とは何か](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) を学び、[スキーマ構成の基本](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) について理解します。

## <a name="import-data-into-adobe-experience-platform"></a>データを Adobe Experience Platform にインポートする

以上ですべての準備が完了ですが、準備した対象ユーザーのデータを対象ユーザーインサイトから Adobe Experience Platform にインポートする必要があります。

まず、[Azure Blob Storage のソース接続を作成](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started) します。    

ソース接続を定義した後、対象ユーザーインサイトのセグメント出力を Adobe Experience Platform にインポートするために、クラウドストレージのバッチ接続用の[データフローを構成](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials)します。

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard で対象ユーザーを作成する

このキャンペーンのメールを送信するには、Adobe Campaign Standard を使用します。 Adobe Experience Platform にデータをインポートした後、Adobe Experience Platform のデータを使って Adobe Campaign Standard に[対象ユーザーを作成する](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission)必要があります。


Adobe Campaign Standard の[セグメント ビルダーを使って](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html)、Adobe Experience Platform のデータに基づいてオーディエンスを定義する方法を説明します。

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard を使用してメールを作成して送信する

メール コンテンツを作成し、メールを [テストおよび送信](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) します。

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard からの更新オファーを含むサンプル メール。":::
