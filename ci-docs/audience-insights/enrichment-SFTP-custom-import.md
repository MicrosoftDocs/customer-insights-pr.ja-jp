---
title: SFTP カスタム インポートによるエンリッチメント
description: SFTP カスタム インポート エンリッチメントに関する一般情報。
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269612"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="95a6f-103">カスタム データで顧客プロファイルを強化する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="95a6f-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="95a6f-104">セキュリティで保護されたファイル転送プロトコル (SFTP) カスタム インポートを使用すると、データ統合のプロセスを行う必要のないデータをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="95a6f-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="95a6f-105">これは、データを取り込むための柔軟で安全かつ簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="95a6f-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="95a6f-106">SFTP カスタム インポートは、エンリッチメントに必要な顧客プロファイル データをエクスポートできる [SFTP エクスポート](export-sftp.md) と組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="95a6f-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="95a6f-107">次に、データを処理して強化し、SFTP カスタム インポートを使用して、エンリッチしたデータを Dynamics 365 Customer Insights の対象者に関するインサイト機能に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="95a6f-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="95a6f-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="95a6f-108">Prerequisites</span></span>

<span data-ttu-id="95a6f-109">SFTP カスタム インポートを構成するには、次の前提条件が満たされている必要があります:</span><span class="sxs-lookup"><span data-stu-id="95a6f-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="95a6f-110">データのインポート元となる SFTP の場所に、ユーザー資格情報 (ユーザー名とパスワード) があります。</span><span class="sxs-lookup"><span data-stu-id="95a6f-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="95a6f-111">STFP ホストに URL とポート番号 (通常は22) があります。</span><span class="sxs-lookup"><span data-stu-id="95a6f-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="95a6f-112">SFTP ホストにインポートするファイルのファイル名と場所があります。</span><span class="sxs-lookup"><span data-stu-id="95a6f-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="95a6f-113">インポートするデータのスキーマを指定する *model.json* ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="95a6f-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="95a6f-114">このファイルは、インポートするファイルと同じディレクトリにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="95a6f-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="95a6f-115">[管理者](permissions.md#administrator) のアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="95a6f-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="95a6f-116">構成</span><span class="sxs-lookup"><span data-stu-id="95a6f-116">Configuration</span></span>

1. <span data-ttu-id="95a6f-117">**データ** > **エンリッチメント** に移動し、**検出** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="95a6f-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="95a6f-118">**SFTP カスタム インポート タイル** で **データの強化** を選択します。</span><span class="sxs-lookup"><span data-stu-id="95a6f-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="95a6f-119">![SFTP カスタム インポート タイル](media/SFTP_Custom_Import_tile.png "SFTP カスタム インポート タイル")</span><span class="sxs-lookup"><span data-stu-id="95a6f-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="95a6f-120">**開始する** を選択し、SFTP サーバーの資格情報とアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="95a6f-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="95a6f-121">たとえば、sftp://mysftpserver.com:22 です。</span><span class="sxs-lookup"><span data-stu-id="95a6f-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="95a6f-122">データを含むファイルの名前と、ルート フォルダーにない場合は、SFTP サーバー上のファイルへのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="95a6f-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="95a6f-123">**カスタム インポート への接続** を選択して、すべての入力を確認します。</span><span class="sxs-lookup"><span data-stu-id="95a6f-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="95a6f-124">![SFTP カスタム インポート構成ポップアップ](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP カスタム インポート構成ポップアップ")</span><span class="sxs-lookup"><span data-stu-id="95a6f-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="95a6f-125">フィールド マッピングの定義</span><span class="sxs-lookup"><span data-stu-id="95a6f-125">Defining field mappings</span></span> 

<span data-ttu-id="95a6f-126">SFTP サーバーにインポートするファイルを含むディレクトリには、*model.json* ファイルも含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="95a6f-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="95a6f-127">このファイルは、データのインポートに使用するスキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="95a6f-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="95a6f-128">スキーマは、[Common Data Model](https://docs.microsoft.com/common-data-model/) を使用して、フィールド マッピングを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95a6f-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="95a6f-129">model.json ファイルの簡単な例は次のようになります:</span><span class="sxs-lookup"><span data-stu-id="95a6f-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="95a6f-130">強化の結果</span><span class="sxs-lookup"><span data-stu-id="95a6f-130">Enrichment results</span></span>

<span data-ttu-id="95a6f-131">エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="95a6f-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="95a6f-132">[スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。</span><span class="sxs-lookup"><span data-stu-id="95a6f-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="95a6f-133">処理時間は、インポートするデータのサイズと SFTP サーバーへの接続によって異なります。</span><span class="sxs-lookup"><span data-stu-id="95a6f-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="95a6f-134">エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくインポートしたカスタム エンリッチメント データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="95a6f-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="95a6f-135">さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="95a6f-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="95a6f-136">**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="95a6f-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="95a6f-137">次の手順</span><span class="sxs-lookup"><span data-stu-id="95a6f-137">Next steps</span></span>

<span data-ttu-id="95a6f-138">エンリッチされた顧客データの上に構築します。</span><span class="sxs-lookup"><span data-stu-id="95a6f-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="95a6f-139">[セグメント](segments.md)、[メジャー](measures.md)、[データのエクスポート](export-destinations.md) を作成し、パーソナライズされたエクスペリエンスを顧客に提供します。</span><span class="sxs-lookup"><span data-stu-id="95a6f-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]