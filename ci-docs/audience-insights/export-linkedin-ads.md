---
title: Customer Insights データを LinkedIn Ads にエクスポート
description: LinkedIn Ads への接続とエクスポートを構成する方法を説明します。
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124512"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="da981-103">セグメントを LinkedIn Ads にエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="da981-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="da981-104">統合された顧客プロファイルのセグメントを LinkedIn Ads にエクスポートして、Matched Audiences を作成します。</span><span class="sxs-lookup"><span data-stu-id="da981-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="da981-105">Matched Audiences を会社のターゲット設定と連絡先のターゲット設定に使用します。</span><span class="sxs-lookup"><span data-stu-id="da981-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="da981-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="da981-106">Prerequisites</span></span>

-   <span data-ttu-id="da981-107">[LinkedIn Campaign Manager アカウント](https://business.linkedin.com/marketing-solutions/ads) と対応する管理者資格情報があります。</span><span class="sxs-lookup"><span data-stu-id="da981-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="da981-108">対象者に関するインサイトで [セグメントを構成](segments.md) しました。</span><span class="sxs-lookup"><span data-stu-id="da981-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="da981-109">エクスポートされたセグメントの顧客プロファイルには、メール アドレスのあるフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="da981-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="da981-110">既知の制限</span><span class="sxs-lookup"><span data-stu-id="da981-110">Known limitations</span></span>

- <span data-ttu-id="da981-111">LinkedIn Ads には、エクスポートごとに最大 10 万件のプロファイルをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="da981-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="da981-112">LinkedIn Ads へのエクスポートはセグメントに限定されています。</span><span class="sxs-lookup"><span data-stu-id="da981-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="da981-113">最大 10 万件のプロファイルを LinkedIn Ads にエクスポートすると、完了するまでに最大 10 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="da981-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="da981-114">LinkedIn Ads への接続を設定する</span><span class="sxs-lookup"><span data-stu-id="da981-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="da981-115">対象者に関するインサイトで、**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="da981-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="da981-116">**つながりの追加** を選択し、**LinkedIn Ads** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="da981-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="da981-117">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="da981-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="da981-118">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="da981-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="da981-119">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da981-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="da981-120">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="da981-120">Choose who can use this connection.</span></span> <span data-ttu-id="da981-121">アクションを実行しない場合、既定は管理者です。</span><span class="sxs-lookup"><span data-stu-id="da981-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="da981-122">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da981-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="da981-123">[LinkedIn Campaign Manager アカウント ID](https://www.linkedin.com/help/lms/answer/a424270) を入力します。</span><span class="sxs-lookup"><span data-stu-id="da981-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="da981-124">**同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。</span><span class="sxs-lookup"><span data-stu-id="da981-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="da981-125">**接続** を選択して、Campaign Monitor への接続を初期化します。</span><span class="sxs-lookup"><span data-stu-id="da981-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="da981-126">**LinkedIn による認証** を選択して、LinkedIn Campaign Manager の管理者資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="da981-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="da981-127">**エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="da981-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="da981-128">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="da981-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="da981-129">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="da981-129">Configure an export</span></span>

<span data-ttu-id="da981-130">この種類の接続にアクセスできる場合は、エクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="da981-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="da981-131">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da981-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="da981-132">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="da981-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="da981-133">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="da981-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="da981-134">**エクスポートの接続** フィールドで、LinkedIn Ads セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="da981-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="da981-135">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="da981-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="da981-136">データをエクスポートして、LinkedInで [連絡先のターゲット設定](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) または [会社のターゲット設定](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) を行うかを選択します。</span><span class="sxs-lookup"><span data-stu-id="da981-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="da981-137">**データ一致** セクションで、顧客のメール アドレスを表す統合された顧客プロファイルのフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="da981-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="da981-138">セグメントを LinkedIn Ads にエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da981-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="da981-139">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="da981-139">Select the segments you want to export.</span></span> <span data-ttu-id="da981-140">LinkedIn Campaign Manager の Matched Audiences は、エクスポートするために選択したセグメントの名前で自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="da981-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="da981-141">各セグメントは、個別の Matched Audience になります。</span><span class="sxs-lookup"><span data-stu-id="da981-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="da981-142">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="da981-142">Select **Save**.</span></span>

<span data-ttu-id="da981-143">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="da981-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="da981-144">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="da981-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="da981-145">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="da981-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="da981-146">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="da981-146">Data privacy and compliance</span></span>

<span data-ttu-id="da981-147">Dynamics 365 Customer Insights による LinkedIn Ads へのデータの転送を有効にすると、Dynamics 365 Customer Insights のコンプライアンスの境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可することになります。</span><span class="sxs-lookup"><span data-stu-id="da981-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="da981-148">Microsoft ではこのようなデータをお客様の指示により転送しますが、LinkedIn Ads がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="da981-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="da981-149">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da981-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="da981-150">Dynamics 365 Customer Insights の管理者は、このエクスポート先を、この機能の使用を停止するために、いつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="da981-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
