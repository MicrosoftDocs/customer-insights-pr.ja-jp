---
title: Customer Insights のデータを SFTP ホストにエクスポートする
description: SFTP ホストへの接続の構成方法を説明します。
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268004"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="dd61e-103">SFTP のコネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="dd61e-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="dd61e-104">顧客データをセキュリティで保護されたファイル転送プロトコル (SFTP) ホストにエクスポートして、サード パーティ アプリケーションで使用します。</span><span class="sxs-lookup"><span data-stu-id="dd61e-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dd61e-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="dd61e-105">Prerequisites</span></span>

- <span data-ttu-id="dd61e-106">SFTP ホストと対応する資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="dd61e-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="dd61e-107">SFTP に接続する</span><span class="sxs-lookup"><span data-stu-id="dd61e-107">Connect to SFTP</span></span>

1. <span data-ttu-id="dd61e-108">**管理** > **エクスポート先** へと移動します。</span><span class="sxs-lookup"><span data-stu-id="dd61e-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="dd61e-109">**SFTP** 配下で **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dd61e-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="dd61e-110">出力先となる **表示名称** フィールドにはわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="dd61e-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="dd61e-111">SFTP アカウントの **ユーザー名**、**パスワード**、**ホスト名**、および **エクスポート フォルダー** を入力します。</span><span class="sxs-lookup"><span data-stu-id="dd61e-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="dd61e-112">**検証する** を選択して接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="dd61e-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="dd61e-113">検証が成功したら、データ **Gzip 圧縮** または **解凍** をエクスポートするかどうか選択し、エクスポートされたファイルに対して **フィールド区切り文字** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dd61e-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="dd61e-114">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="dd61e-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="dd61e-115">**次へ** を選択して、エクスポートの構成を開始します。</span><span class="sxs-lookup"><span data-stu-id="dd61e-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="dd61e-116">エクスポートを構成する</span><span class="sxs-lookup"><span data-stu-id="dd61e-116">Configure the export</span></span>

1. <span data-ttu-id="dd61e-117">エクスポートするエンティティ (セグメントなど) を選択します。</span><span class="sxs-lookup"><span data-stu-id="dd61e-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="dd61e-118">選択した各エンティティは、エクスポート時に最大 5 つの出力ファイルになります。</span><span class="sxs-lookup"><span data-stu-id="dd61e-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="dd61e-119">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dd61e-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="dd61e-120">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="dd61e-120">Export the data</span></span>

<span data-ttu-id="dd61e-121">[オンデマンドでデータをエクスポート](export-destinations.md) できます。</span><span class="sxs-lookup"><span data-stu-id="dd61e-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="dd61e-122">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="dd61e-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="dd61e-123">既知の制限</span><span class="sxs-lookup"><span data-stu-id="dd61e-123">Known limitations</span></span>

- <span data-ttu-id="dd61e-124">エクスポートの実行時間は、システムのパフォーマンスによって異なります。</span><span class="sxs-lookup"><span data-stu-id="dd61e-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="dd61e-125">サーバーの最小構成としては、2 つの CPU コアと 1Gb のメモリをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dd61e-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="dd61e-126">2 つの CPU コアと 1Gb のメモリの推奨される最小構成を使用する場合、最大 1 億件の顧客プロファイルを持つエンティティのエクスポートには 90 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd61e-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dd61e-127">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="dd61e-127">Data privacy and compliance</span></span>

<span data-ttu-id="dd61e-128">Dynamics 365 Customer Insights による SFTP 経由のデータ転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="dd61e-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dd61e-129">Microsoft ではこのようなデータをお客様の指示により転送しますが、エクスポート先がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="dd61e-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dd61e-130">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd61e-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dd61e-131">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="dd61e-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]