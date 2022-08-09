---
title: Adobe Experience Platform にセグメントをエクスポートする (プレビュー)
description: Adobe Experience Platform で Customer Insights セグメントを使用する方法について説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195296"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Adobe Experience Platform にセグメントをエクスポートする (プレビュー)

関連するオーディエンスをターゲットとするセグメントをエクスポートする Adobe Experience Platform。

:::image type="content" source="media/AEP-flow.png" alt-text="この記事で概説されているステップのプロセス図。":::

## <a name="prerequisites"></a>前提条件

- Adobe Experience Platform のライセンス。
- Adobe Campaign Standard のライセンス。
- [Azure Blob Storage アカウント](/azure/storage/blobs/create-data-lake-storage-account) 名とアカウント キー。 名前とキーを見つけるには、[Azure portal で Azure ストレージ アカウントを管理する](/azure/storage/common/storage-account-manage) を参照してください。
- [Azure Blob Storage コンテナー](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

## <a name="campaign-overview"></a>キャンペーン概要

Adobe Experience Platform で Customer Insights からのセグメントをどのように使用できるかをよりよく理解するためには、架空のサンプル キャンペーンを見てみましょう。

あなたの会社が、米国の顧客に月次サブスクリプション ベースのサービスを提供していると仮定します。 今後 8 日以内にサブスクリプションの更新が予定されているが、サブスクリプションをまだ更新していない顧客を特定します。 これらの顧客を維持するために、Adobe Experience Platform を使って、メールでキャンペーン情報を送信します。

この例では、メールのプロモーション キャンペーンを 1 回実行します。 この記事では、キャンペーンを複数回実行するユース ケースについては説明しません。

## <a name="identify-your-target-audience"></a>対象ユーザーの特定

このシナリオでは、顧客のメール アドレスが Customer Insights で利用可能であり、セグメントのメンバーを特定するために顧客のプロモーション設定が分析されたと想定しています。

[Customer Insights で定義したセグメント](segments.md) は、**ChurnProneCustomers** と呼ばれ、あなたはこれらの顧客に電子メール プロモーションを送ることを計画しています。

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers セグメントが作成されたセグメント ページのスクリーンショット。":::

送信するキャンペーン メールには、名、姓、顧客のサブスクリプション終了日が含まれます。 サブスクリプションが終了する前に更新した場合に得られる割引について顧客に通知します。

## <a name="export-your-target-audience"></a>対象ユーザーのエクスポート

Customer Insights から Azure Blob Storage アカウントへのエクスポートを構成します。

### <a name="set-up-connection-to-azure-blob-storage"></a>Azure Blob Storage への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **接続を追加** を選択し、**Azure Blob Storage** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. セグメントをエクスポートする Blob Storage アカウントの **アカウント名**、**アカウント キー**、および **コンテナー** を入力します。  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="ストレージ アカウント構成のスクリーンショット。":::

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **保存** を選択して、接続を完了します。

### <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、Azure Blob Storage セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. エクスポートするセグメントを選択します。 この例では、**ChurnProneCustomers** です。

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers セグメントが選択されたセグメント選択ユーザー インターフェイスのスクリーンショット。":::

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> エクスポートされたセグメントのレコード数が、ご利用の Adobe Campaign Standard のライセンスの許容範囲内であることを確認してください。

エクスポートされたデータは、構成した Azure Blob Storage コンテナーに保存されます。 以下のフォルダー パスが自動的にコンテナーに作成されます。

- システムによって生成されたソース エンティティとエンティティの場合:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  例: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- エクスポートされたエンティティの *model.json* は、*%ExportDestinationName%* レベルにあります。

  例: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Adobe Experience Platform でエクスペリエンス データモデル (XDM) を定義する

Customer Insights からエクスポートされたデータを Adobe Experience Platform 内で使用する前に、エクスペリエンス データ モデル スキーマを定義して、[リアルタイム顧客プロファイルのデータを構成します](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials)。

[XDM とは何か](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) を学び、[スキーマ構成の基本](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) について理解します。

## <a name="import-data-into-adobe-experience-platform"></a>データを Adobe Experience Platform にインポートする

準備した対象者データを Customer Insights から Adobe Experience Platform にインポートします。

1. [Azure Blob Storage のソース接続を作成](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started) します。

1. Customer Insights からのセグメント出力を Adobe Experience Platform にインポートするクラウド ストレージ バッチ接続の [データ フローを構成します](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials)。

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard で対象ユーザーを作成する

このキャンペーンのメールを送信するには、Adobe Campaign Standard を使用します。

1. Adobe Experience Platform でデータを使用して、Adobe Campaign Standard で[対象者を作成](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission)します。

1. Adobe Campaign Standard の[セグメント ビルダーを使って](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html)、Adobe Experience Platform のデータに基づいてオーディエンスを定義します。

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard を使用してメールを作成して送信する

メール コンテンツを作成し、メールを [テストおよび送信](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) します。

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard からの更新オファーを含むサンプル メール。":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
