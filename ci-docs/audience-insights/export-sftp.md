---
title: Customer Insights のデータを SFTP ホストにエクスポートする
description: SFTP ホストへの接続の構成方法を説明します。
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598391"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="12498-103">SFTP のコネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="12498-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="12498-104">顧客データをセキュリティで保護されたファイル転送プロトコル (SFTP) ホストにエクスポートして、サード パーティ アプリケーションで使用します。</span><span class="sxs-lookup"><span data-stu-id="12498-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="12498-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="12498-105">Prerequisites</span></span>

- <span data-ttu-id="12498-106">SFTP ホストと対応する資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="12498-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="12498-107">SFTP に接続する</span><span class="sxs-lookup"><span data-stu-id="12498-107">Connect to SFTP</span></span>

1. <span data-ttu-id="12498-108">**管理** > **エクスポート先** へと移動します。</span><span class="sxs-lookup"><span data-stu-id="12498-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="12498-109">**SFTP** 配下で **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="12498-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="12498-110">出力先となる **表示名称** フィールドにはわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="12498-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="12498-111">SFTP アカウントの **ユーザー名**、**パスワード**、**ホスト名**、および **エクスポート フォルダー** を入力します。</span><span class="sxs-lookup"><span data-stu-id="12498-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="12498-112">**検証する** を選択して接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="12498-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="12498-113">検証が成功したら、データ **Gzip 圧縮** または **解凍** をエクスポートするかどうか選択し、エクスポートされたファイルに対して **フィールド区切り文字** を選択します。</span><span class="sxs-lookup"><span data-stu-id="12498-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="12498-114">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="12498-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="12498-115">**次へ** を選択して、エクスポートの構成を開始します。</span><span class="sxs-lookup"><span data-stu-id="12498-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="12498-116">エクスポートを構成する</span><span class="sxs-lookup"><span data-stu-id="12498-116">Configure the export</span></span>

1. <span data-ttu-id="12498-117">エクスポートするエンティティ (セグメントなど) を選択します。</span><span class="sxs-lookup"><span data-stu-id="12498-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="12498-118">選択した各エンティティは、エクスポート時に最大 5 つの出力ファイルになります。</span><span class="sxs-lookup"><span data-stu-id="12498-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="12498-119">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="12498-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="12498-120">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="12498-120">Export the data</span></span>

<span data-ttu-id="12498-121">[オンデマンドでデータをエクスポート](export-destinations.md) できます。</span><span class="sxs-lookup"><span data-stu-id="12498-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="12498-122">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="12498-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="12498-123">既知の制限</span><span class="sxs-lookup"><span data-stu-id="12498-123">Known limitations</span></span>

- <span data-ttu-id="12498-124">エクスポートの実行時間は、システムのパフォーマンスによって異なります。</span><span class="sxs-lookup"><span data-stu-id="12498-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="12498-125">サーバーの最小構成としては、2 つの CPU コアと 1Gb のメモリをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="12498-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="12498-126">2 つの CPU コアと 1Gb のメモリの推奨される最小構成を使用する場合、最大 1 億件の顧客プロファイルを持つエンティティのエクスポートには 90 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="12498-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="12498-127">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="12498-127">Data privacy and compliance</span></span>

<span data-ttu-id="12498-128">Dynamics 365 Customer Insights による SFTP 経由のデータ転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="12498-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="12498-129">Microsoft ではこのようなデータをお客様の指示により転送しますが、エクスポート先がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="12498-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="12498-130">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12498-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="12498-131">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="12498-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]