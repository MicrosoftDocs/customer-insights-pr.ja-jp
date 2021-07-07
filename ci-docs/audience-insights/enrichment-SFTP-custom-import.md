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
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304656"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="e193f-103">カスタム データで顧客プロファイルを強化する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e193f-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="e193f-104">セキュリティで保護されたファイル転送プロトコル (SFTP) カスタム インポートを使用すると、データ統合のプロセスを行う必要のないデータをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="e193f-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="e193f-105">これは、データを取り込むための柔軟で安全かつ簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="e193f-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="e193f-106">SFTP カスタム インポートは、エンリッチメントに必要な顧客プロファイル データをエクスポートできる [SFTP エクスポート](export-sftp.md) と組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="e193f-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="e193f-107">次に、データを処理してエンリッチし、SFTP カスタム インポートを使用して、エンリッチされたデータを Dynamics 365 Customer Insights の対象ユーザー分析機能に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="e193f-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e193f-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="e193f-108">Prerequisites</span></span>

<span data-ttu-id="e193f-109">SFTP カスタム インポートを構成するには、次の前提条件が満たされている必要があります:</span><span class="sxs-lookup"><span data-stu-id="e193f-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e193f-110">SFTP ホストにインポートするファイルのファイル名と場所 (パス) があること。</span><span class="sxs-lookup"><span data-stu-id="e193f-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="e193f-111">インポートするデータの [Common Data Model スキーマ](/common-data-model/) を指定する *model.json* ファイルがある。</span><span class="sxs-lookup"><span data-stu-id="e193f-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="e193f-112">このファイルは、インポートするファイルと同じディレクトリにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="e193f-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="e193f-113">SFTP 接続は既に管理者によって構成されている、*または* [管理者](permissions.md#administrator) アクセス許可を所有していること。</span><span class="sxs-lookup"><span data-stu-id="e193f-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="e193f-114">データのインポート元となる SFTP ロケーションに対して、ユーザー資格情報、URL、およびポート番号が必要です。</span><span class="sxs-lookup"><span data-stu-id="e193f-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="e193f-115">インポートの構成</span><span class="sxs-lookup"><span data-stu-id="e193f-115">Configure the import</span></span>

1. <span data-ttu-id="e193f-116">**データ** > **エンリッチメント** に移動し、**検出** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="e193f-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="e193f-117">**SFTP カスタム インポート タイル** で **データのエンリッチ** を選択し、**開始する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e193f-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP カスタム インポート タイル。":::

1. <span data-ttu-id="e193f-119">ドロップダウン リストから [接続](connections.md) を選択してください。</span><span class="sxs-lookup"><span data-stu-id="e193f-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="e193f-120">接続できない場合は、管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="e193f-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="e193f-121">管理者の場合は、**接続の追加** を選択して、ドロップダウン リストから **SFTP カスタム インポート** を選択することで、接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e193f-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="e193f-122">**カスタム インポートに接続する** を選択し、選択した接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="e193f-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="e193f-123">**次へ** を選択して、インポートするデータファイルの **パス** および **ファイル名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="e193f-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="データの場所を入力する際のスクリーンショット。":::

1. <span data-ttu-id="e193f-125">**次へ** を選択し、エンリッチメントの名前と出力エンティティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e193f-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="e193f-126">選択内容を確認した後、**エンリッチメントの保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e193f-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="e193f-127">SFTP カスタム インポートの接続を構成する</span><span class="sxs-lookup"><span data-stu-id="e193f-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="e193f-128">接続を構成するには、管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e193f-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="e193f-129">エンリッチメントの構成時に **つながりの追加** を選択するか、*または* **管理** > **接続** に移動し、カスタム インポート タイルで **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e193f-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="e193f-130">**表示名** ボックスに接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e193f-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="e193f-131">インポートするデータが存在する SFTP サーバーの有効なユーザー名、パスワード、およびホスト URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="e193f-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="e193f-132">内容を確認し、**同意する** チェックボックスを選択して、**データのプライバシーとコンプライアンス** に同意してください。</span><span class="sxs-lookup"><span data-stu-id="e193f-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="e193f-133">**検証** を選択して、構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="e193f-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="e193f-134">確認が完了したら、**保存** を選択して接続を保存できます。</span><span class="sxs-lookup"><span data-stu-id="e193f-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e193f-135">![Experian 接続の構成ページ](media/enrichment-SFTP-connection.png "Experian 接続の構成ページ")</span><span class="sxs-lookup"><span data-stu-id="e193f-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="e193f-136">フィールド マッピングの定義</span><span class="sxs-lookup"><span data-stu-id="e193f-136">Defining field mappings</span></span> 

<span data-ttu-id="e193f-137">SFTP サーバーにインポートするファイルを含むディレクトリには、*model.json* ファイルも含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e193f-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="e193f-138">このファイルは、データのインポートに使用するスキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="e193f-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="e193f-139">スキーマは、フィールド マッピングを指定するため、[共通データ モデル](/common-data-model/) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e193f-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="e193f-140">model.json ファイルの簡単な例は次のようになります:</span><span class="sxs-lookup"><span data-stu-id="e193f-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="e193f-141">強化の結果</span><span class="sxs-lookup"><span data-stu-id="e193f-141">Enrichment results</span></span>

<span data-ttu-id="e193f-142">エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e193f-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e193f-143">[スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。</span><span class="sxs-lookup"><span data-stu-id="e193f-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e193f-144">処理時間は、インポートするデータのサイズと SFTP サーバーへの接続によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e193f-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="e193f-145">エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくインポートしたカスタム エンリッチメント データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e193f-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="e193f-146">さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e193f-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e193f-147">**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e193f-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e193f-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="e193f-148">Next steps</span></span>

<span data-ttu-id="e193f-149">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="e193f-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e193f-150">[セグメント](segments.md) および [メジャー](measures.md) を作成し、[データのエクスポート](export-destinations.md) を行って、パーソナライズされたエクスペリエンスを顧客に提供します。</span><span class="sxs-lookup"><span data-stu-id="e193f-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
