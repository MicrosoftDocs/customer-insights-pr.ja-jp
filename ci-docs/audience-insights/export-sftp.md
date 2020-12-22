---
title: Customer Insights のデータを SFTP ホストにエクスポートする
description: SFTP ホストへの接続の構成方法を説明します。
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643509"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="02bfc-103">SFTP のコネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="02bfc-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="02bfc-104">顧客データをセキュリティで保護されたファイル転送プロトコル (SFTP) ホストにエクスポートして、サード パーティ アプリケーションで使用します。</span><span class="sxs-lookup"><span data-stu-id="02bfc-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="02bfc-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="02bfc-105">Prerequisites</span></span>

- <span data-ttu-id="02bfc-106">SFTP ホストと対応する資格情報の可用性。</span><span class="sxs-lookup"><span data-stu-id="02bfc-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="02bfc-107">SFTP に接続</span><span class="sxs-lookup"><span data-stu-id="02bfc-107">Connect to SFTP</span></span>

1. <span data-ttu-id="02bfc-108">**管理** > **エクスポート先** へと移動します。</span><span class="sxs-lookup"><span data-stu-id="02bfc-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="02bfc-109">**SFTP** 配下で **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="02bfc-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="02bfc-110">出力先となる **表示名称** フィールドにはわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="02bfc-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="02bfc-111">SFTP アカウントの **ユーザー名**、**パスワード**、**ホスト名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="02bfc-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="02bfc-112">例: SFTP サーバーのルート フォルダーが /root/folder であり、データを /root/folder/ci_export_destination_folder にエクスポートする場合、ホストを sftp://<server_address>/ci_export_destination_folder" にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="02bfc-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="02bfc-113">**検証する** を選択して接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="02bfc-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="02bfc-114">検証が正常に終了したら、データのエクスポート形式 (**圧縮** または **非圧縮**) を選択し、**フィールド区切り文字** を選択します。</span><span class="sxs-lookup"><span data-stu-id="02bfc-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="02bfc-115">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="02bfc-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="02bfc-116">**次へ** を選択して、エクスポートの構成を開始します。</span><span class="sxs-lookup"><span data-stu-id="02bfc-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="02bfc-117">接続を構成する</span><span class="sxs-lookup"><span data-stu-id="02bfc-117">Configure the connection</span></span>

1. <span data-ttu-id="02bfc-118">エクスポートをする **顧客の属性** を選択します。</span><span class="sxs-lookup"><span data-stu-id="02bfc-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="02bfc-119">1つまたは複数の属性をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="02bfc-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="02bfc-120">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="02bfc-120">Select **Next**.</span></span>

1. <span data-ttu-id="02bfc-121">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="02bfc-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="02bfc-122">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="02bfc-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="02bfc-123">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="02bfc-123">Export the data</span></span>

<span data-ttu-id="02bfc-124">[オンデマンドでデータをエクスポート](export-destinations.md) できます。</span><span class="sxs-lookup"><span data-stu-id="02bfc-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="02bfc-125">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="02bfc-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="02bfc-126">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="02bfc-126">Data privacy and compliance</span></span>

<span data-ttu-id="02bfc-127">Dynamics 365 Customer Insights による SFTP 経由のデータ転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="02bfc-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="02bfc-128">Microsoft ではこのようなデータをお客様の指示により転送しますが、エクスポート先がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="02bfc-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="02bfc-129">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02bfc-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="02bfc-130">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="02bfc-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
