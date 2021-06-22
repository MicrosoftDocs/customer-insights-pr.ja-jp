---
title: Customer Insights のデータを SFTP ホストにエクスポートする
description: SFTP ロケーションへの接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 000b44dc8e5cc419132bd17e359fbdd5879caf1b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124325"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a><span data-ttu-id="9e84b-103">セグメントとその他のデータを SFTP にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9e84b-103">Export segments and other data to SFTP (preview)</span></span>

<span data-ttu-id="9e84b-104">顧客データをセキュリティで保護されたファイル転送プロトコル (SFTP) ロケーションにエクスポートし、サード パーティ アプリケーションで使用します。</span><span class="sxs-lookup"><span data-stu-id="9e84b-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="9e84b-105">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="9e84b-105">Prerequisites for connection</span></span>

- <span data-ttu-id="9e84b-106">SFTP ホストと対応する資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="9e84b-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9e84b-107">既知の制限</span><span class="sxs-lookup"><span data-stu-id="9e84b-107">Known limitations</span></span>

- <span data-ttu-id="9e84b-108">エクスポートの実行時間は、システムのパフォーマンスによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9e84b-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="9e84b-109">サーバーの最小構成としては、2 つの CPU コアと 1Gb のメモリをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9e84b-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="9e84b-110">2 つの CPU コアと 1Gb のメモリの推奨される最小構成を使用する場合、最大 1 億件の顧客プロファイルを持つエンティティのエクスポートには 90 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e84b-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="9e84b-111">SFTP への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="9e84b-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="9e84b-112">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="9e84b-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9e84b-113">**つながりの追加** を選択し、**SFTP** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="9e84b-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="9e84b-114">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="9e84b-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9e84b-115">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="9e84b-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9e84b-116">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9e84b-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9e84b-117">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e84b-117">Choose who can use this connection.</span></span> <span data-ttu-id="9e84b-118">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="9e84b-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9e84b-119">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e84b-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9e84b-120">SFTP アカウントの **ユーザー名**、**パスワード**、**ホスト名**、および **エクスポート フォルダー** を入力します。</span><span class="sxs-lookup"><span data-stu-id="9e84b-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="9e84b-121">**検証する** を選択して接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="9e84b-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="9e84b-122">データを **Gzip 形式** または **解凍済み** のどちらでエクスポートするか、およびエクスポートされたファイルの **フィールド区切り記号** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e84b-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="9e84b-123">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="9e84b-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9e84b-124">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="9e84b-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9e84b-125">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="9e84b-125">Configure an export</span></span>

<span data-ttu-id="9e84b-126">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="9e84b-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9e84b-127">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e84b-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9e84b-128">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="9e84b-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9e84b-129">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e84b-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9e84b-130">**エクスポートの接続** フィールドで、SFTP セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e84b-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="9e84b-131">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="9e84b-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9e84b-132">エクスポートするエンティティ (セグメントなど) を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e84b-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9e84b-133">選択した各エンティティは、エクスポート時に最大 5 つの出力ファイルに分割されます。</span><span class="sxs-lookup"><span data-stu-id="9e84b-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="9e84b-134">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e84b-134">Select **Save**.</span></span>

<span data-ttu-id="9e84b-135">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="9e84b-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9e84b-136">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="9e84b-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9e84b-137">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="9e84b-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9e84b-138">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="9e84b-138">Data privacy and compliance</span></span>

<span data-ttu-id="9e84b-139">Dynamics 365 Customer Insights による SFTP 経由のデータ転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="9e84b-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9e84b-140">Microsoft ではこのようなデータをお客様の指示により転送しますが、エクスポート先がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="9e84b-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9e84b-141">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e84b-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9e84b-142">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="9e84b-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
