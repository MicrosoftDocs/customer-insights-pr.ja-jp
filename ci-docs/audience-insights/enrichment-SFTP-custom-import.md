---
title: SFTP カスタム インポートによるエンリッチメント
description: SFTP カスタム インポート エンリッチメントに関する一般情報。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896287"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="2fc69-103">カスタム データで顧客プロファイルを強化する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2fc69-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="2fc69-104">セキュリティで保護されたファイル転送プロトコル (SFTP) カスタムインポートでは、データ統合のプロセスを必要としないデータをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="2fc69-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="2fc69-105">これは、データを取り込むための柔軟で安全かつ簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="2fc69-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="2fc69-106">SFTP カスタム インポートは、エンリッチメントに必要な顧客プロファイル データをエクスポートできる [SFTP エクスポート](export-sftp.md) と組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="2fc69-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="2fc69-107">次に、データを処理して強化し、SFTP カスタム インポートを使用して、エンリッチしたデータを Dynamics 365 Customer Insights の対象者に関するインサイト機能に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="2fc69-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2fc69-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="2fc69-108">Prerequisites</span></span>

<span data-ttu-id="2fc69-109">SFTP カスタム インポートを構成するには、次の前提条件が満たされている必要があります:</span><span class="sxs-lookup"><span data-stu-id="2fc69-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="2fc69-110">SFTP ホスト上に、インポートするファイルのファイル名とロケーション (パス) がある。</span><span class="sxs-lookup"><span data-stu-id="2fc69-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="2fc69-111">インポートするデータの [Common Data Model スキーマ](/common-data-model/) を指定する *model.json* ファイルがある。</span><span class="sxs-lookup"><span data-stu-id="2fc69-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="2fc69-112">このファイルは、インポートするファイルと同じディレクトリにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fc69-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="2fc69-113">SFTP 接続は既に管理者によって構成されている、*または* [管理者](permissions.md#administrator) アクセス許可を所有していること。</span><span class="sxs-lookup"><span data-stu-id="2fc69-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="2fc69-114">データのインポート元となる SFTP ロケーションに対して、ユーザー資格情報、URL、およびポート番号が必要です。</span><span class="sxs-lookup"><span data-stu-id="2fc69-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="2fc69-115">インポートの構成</span><span class="sxs-lookup"><span data-stu-id="2fc69-115">Configure the import</span></span>

1. <span data-ttu-id="2fc69-116">**データ** > **エンリッチメント** に移動し、**検出** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc69-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="2fc69-117">**SFTP カスタム インポート タイル** で **データのエンリッチ** を選択し、**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc69-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP カスタム インポート タイル。":::

1. <span data-ttu-id="2fc69-119">ドロップダウンから [接続](connections.md) を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc69-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="2fc69-120">接続できない場合は、管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="2fc69-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="2fc69-121">管理者の場合は、**つながりの追加** を選択し、ドロップダウンから **SFTP カスタム インポート** を選択することで、接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="2fc69-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="2fc69-122">**カスタム インポートに接続する** を選択し、選択した接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="2fc69-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="2fc69-123">**次へ** 選択し、インポートするデータファイルの **ファイル名** と **パス** を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fc69-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="データの場所を入力する際のスクリーンショット。":::

1. <span data-ttu-id="2fc69-125">**次へ** を選択し、エンリッチメントの名前と出力エンティティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2fc69-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="2fc69-126">選択内容を確認した後、**エンリッチメントの保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc69-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="2fc69-127">SFTP カスタム インポートの接続を構成する</span><span class="sxs-lookup"><span data-stu-id="2fc69-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="2fc69-128">接続を構成するには、管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fc69-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="2fc69-129">エンリッチメントの構成時に **つながりの追加** を選択するか、*または* **管理** > **接続** に移動し、カスタム インポート タイルで **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc69-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="2fc69-130">**表示名** ボックスに接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fc69-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="2fc69-131">インポートするデータが存在する STFP サーバーの有効なユーザー名、パスワード、およびホスト URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fc69-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="2fc69-132">内容を確認し、**同意する** チェックボックスを選択して、**データのプライバシーとコンプライアンス** に同意してください。</span><span class="sxs-lookup"><span data-stu-id="2fc69-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="2fc69-133">**検証** を選択して、構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="2fc69-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="2fc69-134">検証が完了したら、**保存** をクリックして接続を保存できます。</span><span class="sxs-lookup"><span data-stu-id="2fc69-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="2fc69-135">![Experian 接続構成ページ](media/enrichment-SFTP-connection.png "Experian 接続構成ページ")</span><span class="sxs-lookup"><span data-stu-id="2fc69-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="2fc69-136">フィールド マッピングの定義</span><span class="sxs-lookup"><span data-stu-id="2fc69-136">Defining field mappings</span></span> 

<span data-ttu-id="2fc69-137">SFTP サーバーにインポートするファイルを含むディレクトリには、*model.json* ファイルも含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fc69-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="2fc69-138">このファイルは、データのインポートに使用するスキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="2fc69-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="2fc69-139">スキーマは、[Common Data Model](/common-data-model/) を使用して、フィールド マッピングを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fc69-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="2fc69-140">model.json ファイルの簡単な例は次のようになります:</span><span class="sxs-lookup"><span data-stu-id="2fc69-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="2fc69-141">強化の結果</span><span class="sxs-lookup"><span data-stu-id="2fc69-141">Enrichment results</span></span>

<span data-ttu-id="2fc69-142">エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc69-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="2fc69-143">[スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。</span><span class="sxs-lookup"><span data-stu-id="2fc69-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2fc69-144">処理時間は、インポートするデータのサイズと SFTP サーバーへの接続によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2fc69-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="2fc69-145">エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくインポートしたカスタム エンリッチメント データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2fc69-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="2fc69-146">さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2fc69-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="2fc69-147">**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2fc69-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2fc69-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="2fc69-148">Next steps</span></span>

<span data-ttu-id="2fc69-149">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="2fc69-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2fc69-150">[セグメント](segments.md)、[メジャー](measures.md)、[データのエクスポート](export-destinations.md) を作成し、パーソナライズされたエクスペリエンスを顧客に提供します。</span><span class="sxs-lookup"><span data-stu-id="2fc69-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
