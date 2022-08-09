---
title: Adobe Campaign Standard で Customer Insights セグメントをエクスポートする (プレビュー)
description: Adobe Campaign Standard で Customer Insights セグメントを使用する方法について学びます。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195526"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Adobe Campaign Standard で Customer Insights セグメントをエクスポートする (プレビュー)

関連するオーディエンスをターゲットとするセグメントをエクスポートする Adobe Campaign Standard。

:::image type="content" source="media/ACS-flow.png" alt-text="この記事で概説されているステップのプロセス図。":::

## <a name="prerequisites"></a>前提条件

- Adobe Campaign Standard のライセンス。
- [Azure Blob Storage アカウント](/azure/storage/blobs/create-data-lake-storage-account) 名とアカウント キー。 名前とキーを見つけるには、[Azure portal で Azure ストレージ アカウントを管理する](/azure/storage/common/storage-account-manage) を参照してください。
- [Azure Blob Storage コンテナー](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)。

## <a name="campaign-overview"></a>キャンペーン 概要

Adobe Experience Platform で Customer Insights からのセグメントをどのように使用できるかをよりよく理解するためには、架空のサンプル キャンペーンを見てみましょう。

あなたの会社が、米国の顧客に月次サブスクリプション ベースのサービスを提供していると仮定します。 今後 8 日以内にサブスクリプションの更新が予定されているが、サブスクリプションをまだ更新していない顧客を特定します。 これらの顧客を維持するために、Adobe Campaign Standard を使って、メールでキャンペーン情報を送信します。

この例では、メールのプロモーション キャンペーンを 1 回実行します。 この記事では、キャンペーンを複数回実行するユース ケースについては説明しません。 ただし、 Customer Insights と Adobe Campaign Standard は、定期的なキャンペーン シナリオでも機能するように構成できます。

## <a name="identify-your-target-audience"></a>対象ユーザーの特定

このシナリオでは、顧客のメール アドレスが Customer Insights で利用可能であり、セグメントのメンバーを特定するために顧客のプロモーション設定が分析されたと想定しています。

[Customer Insights で定義したセグメント](segments.md) は、**ChurnProneCustomers** と呼ばれ、あなたはこれらの顧客に電子メール プロモーションを送ることを計画しています。

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="ChurnProneCustomers セグメントが作成されたセグメント ページのスクリーンショット。":::

送信するキャンペーン メールには、名、姓、顧客のサブスクリプション終了日が含まれます。 サブスクリプションが終了する前に更新した場合に得られる割引について顧客に通知します。

## <a name="export-your-target-audience"></a>対象ユーザーのエクスポート

### <a name="set-up-connection-to-adobe-campaign"></a>Adobe Campaign への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**Adobe Campaign** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. Blob Storage アカウントに **アカウント名**、**アカウント キー**、**コンテナー** を入力します。  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="ストレージ アカウント構成のスクリーンショット。":::

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **保存** を選択して、接続を完了します。

### <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポート用の接続** フィールドで、Adobe Campaign セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. エクスポートするセグメントを選択します。 この例では、**ChurnProneCustomers** です。

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="ChurnProneCustomers セグメントが選択されたセグメント選択ユーザー インターフェイスのスクリーンショット。":::

1. **次へ** を選択します。

1. Customer Insights セグメントからの **ソース** を Adobe Campaign Standard プロファイル スキーマで **ターゲット** フィールドにマップします。

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard コネクタのフィールド マッピング。":::

   属性をさらに追加する場合は、**属性の追加** を選択します。 ターゲット名はソース フィールド名とは異なる場合があるため、2つのシステムでフィールドの名前が同じでない場合は、Customer Insights からのセグメント出力を Adobe Campaign Standard にまだマップできます。

   > [!NOTE]
   > メールアドレスは ID フィールドとして使用されますが、顧客プロファイルの他の識別子を使用してデータを Adobe Campaign Standard にマップできます。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> エクスポートされたセグメントのレコード数が、ご利用の Adobe Campaign Standard のライセンスの許容範囲内であることを確認してください。

エクスポートされたデータは、上記で構成した Azure Blob Storage コンテナーに格納されます。 次のフォルダー パスがコンテナーで自動的に作成されます: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

例: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard を構成する

エクスポートされたセグメントには、エクスポートを構成するときに選択した列が含まれています。 このデータは、[Adobe Campaign Standard でのプロファイル作成](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles)に使用できます。

Adobe Campaign Standard でセグメントを使用するには、Adobe Campaign Standard の[プロファイル スキーマを拡張](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) して、2 つのフィールドを追加する必要があります。

この例では、これらのフィールドは セグメント名とセグメント日付です。 これらのフィールドを使って、このキャンペーンで対象とする Adobe Campaign Standard のプロファイルを特定します。

Adobe Campaign Standard に、インポートするレコード以外のレコードがない場合は、このステップは省略します。

## <a name="import-data-into-adobe-campaign-standard"></a>Adobe Campaign Standard にデータをインポートする

準備した対象者データを Customer Insights から Adobe Campaign Standard にインポートし、[ワークフローを使用してプロファイルを作成する](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) 必要があります。

次の画像のインポート ワークフローは、8 時間ごとに実行され、エクスポートされた Customer Insights セグメント (Azure Blob Storage の.csvファイル) を探すように構成されています。 ワークフローは、指定された列の順序で .csv ファイルのコンテンツを抽出します。 このワークフローは、基本的なエラー処理を行い、各レコードのメールアドレスを確認してから、Adobe Campaign Standard にデータをハイドレートするように作られています。 ワークフローは、Adobe Campaign Standard プロファイル データにアップサートする前に、ファイル名からセグメント名も抽出します。

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard のユーザーインターフェイスでのインポートワークフローのスクリーンショット。":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard で対象ユーザーを取得する

Adobe Campaign Standard にデータが取り込まれた後に、[ワークフローを作成](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data)し、セグメント名とセグメントの日付に基づいて顧客に[問い合わせ](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data)、サンプルキャンペーンで特定されたプロファイルを選択することができます。

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard を使用してメールを作成して送信する

メール コンテンツを作成し、メールを [テストおよび送信](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) します。

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard からの更新オファーを含むサンプル メール。":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
