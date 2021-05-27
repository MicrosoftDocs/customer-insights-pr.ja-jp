---
title: Customer Insights のデータを Facebook 広告マネージャーにエクスポートする
description: Facebook 広告マネージャへの接続とエクスポートを構成する方法を説明します。
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976048"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="e88ef-103">セグメント リストを Facebook 広告マネージャにエクスポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e88ef-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="e88ef-104">統合された顧客プロファイルのセグメントを Facebook 広告マネージャにエクスポートして Facebook と Instagram でキャンペーンを作成する。</span><span class="sxs-lookup"><span data-stu-id="e88ef-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e88ef-105">接続の前提条件</span><span class="sxs-lookup"><span data-stu-id="e88ef-105">Prerequisites for connection</span></span>

- <span data-ttu-id="e88ef-106">[**Facebook ビジネス アカウント**](https://business.facebook.com/) を含む [**Facebook 広告アカウント**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) が必要です。</span><span class="sxs-lookup"><span data-stu-id="e88ef-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="e88ef-107">[**Facebook 広告アカウント**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) の管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e88ef-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e88ef-108">既知の制限</span><span class="sxs-lookup"><span data-stu-id="e88ef-108">Known limitations</span></span>

- <span data-ttu-id="e88ef-109">Facebook 広告マネージャへのエクスポートごとに最大 1,000 万件の顧客プロファイルまでとなります。</span><span class="sxs-lookup"><span data-stu-id="e88ef-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="e88ef-110">Facebook 広告マネージャへのエクスポートはセグメントに限定されます。</span><span class="sxs-lookup"><span data-stu-id="e88ef-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="e88ef-111">Facebook でカスタム対象者を作成または更新する場合は、*顧客リスト* の種類のみです。</span><span class="sxs-lookup"><span data-stu-id="e88ef-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="e88ef-112">合計 1,000 万件のプロファイルを持つセグメントのエクスポートには、完了までに最大 90 分間かかります。</span><span class="sxs-lookup"><span data-stu-id="e88ef-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="e88ef-113">Facebook 広告マネージャへの接続を設定する</span><span class="sxs-lookup"><span data-stu-id="e88ef-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="e88ef-114">ユーザーがエクスポートを作成する前に、管理者はサービスへの接続を構成し、共同作成者が接続を使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e88ef-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="e88ef-115">**管理** > **接続** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e88ef-116">**つながりの追加** を選択し、**Facebook 広告マネージャ** を選択して、接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="e88ef-117">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="e88ef-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e88ef-118">接続の表示名と種類は、この接続を説明します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e88ef-119">接続の目的とターゲットを説明する名前を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e88ef-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e88ef-120">この接続を使用できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-120">Choose who can use this connection.</span></span> <span data-ttu-id="e88ef-121">アクションを実行しない場合、既定は **管理者** になります。</span><span class="sxs-lookup"><span data-stu-id="e88ef-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="e88ef-122">詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e88ef-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e88ef-123">Facebook Ads による認証:</span><span class="sxs-lookup"><span data-stu-id="e88ef-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="e88ef-124">**Facebook で続ける** を選択して、Facebook 広告アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="e88ef-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="e88ef-125">Facebook で認証した後、**ads_management** アクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="e88ef-126">作業する **Facebook 広告アカウント** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="e88ef-127">**既存のカスタム対象ユーザー** ドロップダウン リストから選択するか、または **新しいカスタム対象ユーザー** を作成します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="e88ef-128">詳細については、[**Facebook 広告マネージャの対象ユーザー**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e88ef-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="e88ef-129">このエクスポートでは、Facebook で *顧客リスト* の種類のカスタム対象者のみを作成または更新できます。</span><span class="sxs-lookup"><span data-stu-id="e88ef-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="e88ef-130">場合によっては、ドロップダウン リストにさまざまな種類のカスタム対象者が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e88ef-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="e88ef-131">*顧客リスト* とは異なる種類を選択すると、エクスポートに失敗します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="e88ef-132">**データのプライバシーとコンプライアンス** を確認し、**同意する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="e88ef-133">**保存** を選択して、接続を完了します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e88ef-134">エクスポートの構成</span><span class="sxs-lookup"><span data-stu-id="e88ef-134">Configure an export</span></span>

<span data-ttu-id="e88ef-135">この種類の接続にアクセスできる場合は、このエクスポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e88ef-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e88ef-136">詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e88ef-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e88ef-137">**データ** > **エクスポート** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e88ef-138">新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="e88ef-139">**エクスポートの接続** で、**Facebook 広告マネージャ** セクションから接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="e88ef-140">このセクション名が表示されない場合、この種類の接続は使用できません。</span><span class="sxs-lookup"><span data-stu-id="e88ef-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e88ef-141">**キー識別子のフィールドを選択する** にて、**E メール**、**名前と住所**、または **電話** を選択して、Facebook 広告マネージャに送信します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="e88ef-142">接続にわかりやすい名前を **表示名** フィールドに付けます。</span><span class="sxs-lookup"><span data-stu-id="e88ef-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e88ef-143">選択したキー識別子に対応する統合顧客エンティティの対応する属性をマッピングします。</span><span class="sxs-lookup"><span data-stu-id="e88ef-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="e88ef-144">[ヒント] キー識別子に **E メール** を選択すると、一致する可能性が最も高くなります。</span><span class="sxs-lookup"><span data-stu-id="e88ef-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="e88ef-145">識別子を追加すると、マッチングが向上する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e88ef-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="e88ef-146">**属性の追加** を選択し、送信する属性をさらに Facebook 広告マネージャにマップします。</span><span class="sxs-lookup"><span data-stu-id="e88ef-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="e88ef-147">Facebook 広告マネージャの属性は、以下のユーザー フレンドリ名にマッピングされます: **FN** = **名**、**LN** = **姓**、**FI** = **最初の頭文字**、**PHONE** = **電話**、**GEN** = **性別**、**DOB** = **生年月日**、**ST** = **状態**、**CT** = **市**、**ZIP** = **郵便番号**、**COUNTRY** = **国 / 地域**</span><span class="sxs-lookup"><span data-stu-id="e88ef-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="e88ef-148">エクスポートするセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="e88ef-149">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e88ef-149">Select **Save**.</span></span>

<span data-ttu-id="e88ef-150">エクスポートを保存しても、エクスポートはすぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="e88ef-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e88ef-151">エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="e88ef-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e88ef-152">[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。</span><span class="sxs-lookup"><span data-stu-id="e88ef-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e88ef-153">データのプライバシーとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="e88ef-153">Data privacy and compliance</span></span>

<span data-ttu-id="e88ef-154">Dynamics 365 Customer Insights による Facebook 広告マネージャーへのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。</span><span class="sxs-lookup"><span data-stu-id="e88ef-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e88ef-155">Microsoft ではこのようなデータをお客様の指示により転送しますが、Facebook 広告がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。</span><span class="sxs-lookup"><span data-stu-id="e88ef-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="e88ef-156">詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e88ef-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e88ef-157">Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="e88ef-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
