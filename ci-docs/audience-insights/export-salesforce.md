---
title: Customer Insights データを Salesforce Marketing Cloud にエクスポートする
description: 接続を構成して、Salesforce Marketing Cloud にエクスポートする方法を学びます。
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314633"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="bdfd0-103">セグメントおよびその他のデータを Salesforce Marketing Cloud にエクスポートする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="bdfd0-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="bdfd0-104">セキュリティで保護されたファイル転送プロトコル (SFTP) の場所を介して顧客データをエクスポートすることにより、Salesforce Marketing Cloudで顧客データを使用します。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="bdfd0-105">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="bdfd0-105">Prerequisites for connection</span></span>

- <span data-ttu-id="bdfd0-106">SFTP ホストと対応する管理者の資格情報が利用できること。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="bdfd0-107">Salesforce Marketing Cloud の SFTP ロケーションを設定する方法</span><span class="sxs-lookup"><span data-stu-id="bdfd0-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="bdfd0-108">既知の制限</span><span class="sxs-lookup"><span data-stu-id="bdfd0-108">Known limitations</span></span>

- <span data-ttu-id="bdfd0-109">エクスポートの実行時間は、システムのパフォーマンスによって異なります。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="bdfd0-110">サーバーの最小構成としては、2 つの CPU コアと 1Gb のメモリをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="bdfd0-111">推奨される最小構成を使用する場合、最大 1 億の顧客プロファイルを持つエンティティをエクスポートするには、90 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="bdfd0-112">Salesforce Marketing Cloud への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="bdfd0-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="bdfd0-113">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bdfd0-114">**接続の追加** を選択し、**Salesforce Marketing Cloud** を選んで、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="bdfd0-115">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bdfd0-116">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bdfd0-117">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bdfd0-118">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-118">Choose who can use this connection.</span></span> <span data-ttu-id="bdfd0-119">アクションを実行しない場合、既定は管理者になります。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bdfd0-120">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bdfd0-121">SFTP アカウントの **ユーザー名**、**パスワード**、**ホスト名**、および **エクスポート フォルダー** を入力します。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="bdfd0-122">**検証する** を選択して接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="bdfd0-123">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bdfd0-124">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bdfd0-125">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="bdfd0-125">Configure an export</span></span>

<span data-ttu-id="bdfd0-126">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bdfd0-127">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bdfd0-128">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bdfd0-129">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bdfd0-130">**エクスポートの接続** フィールドで、SFTP セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="bdfd0-131">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bdfd0-132">データを **Gzip 形式** または **解凍済み** のどちらでエクスポートするか、およびエクスポートされたファイルの **フィールド区切り記号** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="bdfd0-133">エクスポートするエンティティ (セグメントなど) を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bdfd0-134">選択した各エンティティは、エクスポート時に最大 5 つの出力ファイルに分割されます。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="bdfd0-135">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-135">Select **Save**.</span></span>

<span data-ttu-id="bdfd0-136">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bdfd0-137">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bdfd0-138">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="bdfd0-139">Customer Insights データを SFTP の場所から、Salesforce Marketing Cloud にインポートする</span><span class="sxs-lookup"><span data-stu-id="bdfd0-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="bdfd0-140">[Salesforce Marketing Cloud のデータ拡張](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) を作成して、SFTP の場所から Customer Insights データ ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="bdfd0-141">Salesforce Marketing Cloud データ拡張機能に [SFTP の場所からデータをインポートします](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5)。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="bdfd0-142">データをデータ拡張機能にインポートするようにオートメーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="bdfd0-143">[ファイル ドロップのオートメーションとスケジュールされたオートメーション](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5) の詳細情報。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="bdfd0-144">[ファイル ドロップのオートメーション](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5)、または [スケジュールされたオートメーション](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5) を定義します。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="bdfd0-145">[SFTP によるオートメーション](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5) の例はこちらです。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bdfd0-146">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="bdfd0-146">Data privacy and compliance</span></span>

<span data-ttu-id="bdfd0-147">Dynamics 365 Customer Insights による SFTP 経由のデータ転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bdfd0-148">Microsoft ではこのようなデータをお客様の指示により転送しますが、エクスポート先がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bdfd0-149">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bdfd0-150">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="bdfd0-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
