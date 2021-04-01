---
title: サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する
description: 対象者に関するインサイトの Azure サービス プリンシパルを使用して、対象者に関するインサイトに接続するときに、独自のデータ レイクに接続します。
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596505"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="ea75c-103">対象者に関するインサイトの Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する</span><span class="sxs-lookup"><span data-stu-id="ea75c-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="ea75c-104">Azure サービスを使用する自動ツールは、常に制限されたアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ea75c-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="ea75c-105">Azureは、完全な権限を持つユーザーとしてアプリケーションにサインインさせる代わりに、サービス プリンシパルを提供します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="ea75c-106">ストレージ アカウント キーの代わりに、Azure サービス プリンシパルを使用して、対象者に関するインサイトを Azure Data Lake Storage Gen2 アカウントに接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="ea75c-107">サービス プリンシパルを使用して、安全に [Common Data Model フォルダーをデータ ソースとして追加または編集](connect-common-data-model.md) したり、[新しい環境を作成、または既存の環境を更新](manage-environments.md#create-an-environment-in-an-existing-organization) したりできます。</span><span class="sxs-lookup"><span data-stu-id="ea75c-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="ea75c-108">サービス プリンシパルを使用する予定の Azure Data Lake Gen2 ストレージ アカウントでは、[階層名前空間 (HNS) が有効](/azure/storage/blobs/data-lake-storage-namespace)である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea75c-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="ea75c-109">サービス プリンシパルを作成するには、Azure サブスクリプションに対する管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ea75c-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="ea75c-110">対象者に関するインサイトに Azure サービス プリンシパルを作成する</span><span class="sxs-lookup"><span data-stu-id="ea75c-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="ea75c-111">対象者に関するインサイトに新しいサービス プリンシパルを作成する前に、組織にすでに存在するかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ea75c-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="ea75c-112">既存のサービス プリンシパルの検索</span><span class="sxs-lookup"><span data-stu-id="ea75c-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="ea75c-113">[Azure 管理ポータル](https://portal.azure.com) に移動し、サインインにログインします。</span><span class="sxs-lookup"><span data-stu-id="ea75c-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="ea75c-114">Azure サービスから **Azure Active Directory** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="ea75c-115">**管理** で、**エンタープライズ アプリケーション** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="ea75c-116">対象者に関するインサイトのファースト パーティ アプリケーション ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` または 名前 `Dynamics 365 AI for Customer Insights` を検索します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="ea75c-117">一致するレコードが見つかった場合は、対象者に関するインサイトにサービス プリンシパルが存在することを意味します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="ea75c-118">再度作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ea75c-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="既存のサービス プリンシパルを示すスクリーンショット。":::
   
6. <span data-ttu-id="ea75c-120">結果が返されない場合は、新しいサービス プリンシパルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="ea75c-121">新しいサービス プリンシパルを作成する</span><span class="sxs-lookup"><span data-stu-id="ea75c-121">Create a new service principal</span></span>

1. <span data-ttu-id="ea75c-122">**Graph 用 Azure Active Directory PowerShell** の最新バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ea75c-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="ea75c-123">詳細については、[Graph 用 Azure Active Directory PowerShell のインストール](/powershell/azure/active-directory/install-adv2) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea75c-123">For more information, see [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="ea75c-124">PC で、キーボードの Windows キーを選択し、**Windows PowerShell** を検索して、**管理者として実行** します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="ea75c-125">開いた PowerShell ウィンドウで、`Install-Module AzureAD` を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="ea75c-126">Azure AD PowerShell モジュールを使用して、対象者に関するインサイトにサービス プリンシパルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="ea75c-127">PowerShell ウィンドウで、`Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="ea75c-128">"テナント ID" を、サービス プリンシパルを作成するテナントの実際の ID に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ea75c-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="ea75c-129">環境名パラメーター `AzureEnvironmentName` は任意です。</span><span class="sxs-lookup"><span data-stu-id="ea75c-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="ea75c-130">`New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="ea75c-131">このコマンドは、選択したテナントの対象者に関するインサイトにサービス プリンシパルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="ea75c-132">ストレージ アカウントにアクセスするためにアクセス許可をサービス プリンシパルに付与する</span><span class="sxs-lookup"><span data-stu-id="ea75c-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="ea75c-133">Azure portal に移動して、対象者に関するインサイトで使用するストレージ アカウントのサービス プリンシパルにアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="ea75c-134">[Azure 管理ポータル](https://portal.azure.com) に移動し、サインインにログインします。</span><span class="sxs-lookup"><span data-stu-id="ea75c-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="ea75c-135">対象者に関するインサイトのサービス プリンシパルにアクセスさせるストレージ アカウントを開きます。</span><span class="sxs-lookup"><span data-stu-id="ea75c-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="ea75c-136">ナビゲーション ウィンドウから **アクセス制御 (IAM)** を選択し、**追加** > **ロール割り当ての追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="ロール割り当てを追加中の Azure ポータルを示すスクリーンショット。":::
   
1. <span data-ttu-id="ea75c-138">**ロール割り当ての追加** ペインで、次のプロパティを設定します:</span><span class="sxs-lookup"><span data-stu-id="ea75c-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="ea75c-139">ロール: *ストレージ Blob データ共同作成者*</span><span class="sxs-lookup"><span data-stu-id="ea75c-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="ea75c-140">アクセスの割当て先: *ユーザー、グループ、またはサービス プリンシパル*</span><span class="sxs-lookup"><span data-stu-id="ea75c-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="ea75c-141">選択: *Dynamics 365 AI for Customer Insights* ([作成したサービス プリンシパル](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="ea75c-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="ea75c-142">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-142">Select **Save**.</span></span>

<span data-ttu-id="ea75c-143">変更が反映されるまでに最大 15 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ea75c-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="ea75c-144">対象者に関するインサイトのストレージ アカウント添付ファイルに Azure リソース ID または Azure サブスクリプションの詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="ea75c-145">対象者に関するインサイトに Azure Data Lake ストレージ アカウントを添付し、[出力データを保存](manage-environments.md) または [データ ソースとして使用](connect-common-data-service-lake.md) します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="ea75c-146">Azure Data Lake オプションを選択すると、リソース ベースまたはサブスクリプション ベースのアプローチのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ea75c-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="ea75c-147">以下の手順に従って、選択したアプローチに関する必要な情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="ea75c-148">リソースベースのストレージ アカウント接続</span><span class="sxs-lookup"><span data-stu-id="ea75c-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="ea75c-149">[Azure 管理ポータル](https://portal.azure.com) に移動し、サブスクリプションにサインインし、ストレージ アカウントを開きます。</span><span class="sxs-lookup"><span data-stu-id="ea75c-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="ea75c-150">ナビゲーション ウィンドウで **設定** > **プロパティ** に移動します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="ea75c-151">ストレージ アカウントのリソース ID 値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="ea75c-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="ストレージ アカウントのリソース ID をコピーします。":::

1. <span data-ttu-id="ea75c-153">対象者に関するインサイトで、ストレージ アカウント接続画面に表示されるリソース フィールドに、リソース ID を挿入します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="ストレージ アカウントのリソース ID 情報を入力します。":::   
   
1. <span data-ttu-id="ea75c-155">対象者に関するインサイトの残りの手順を続行して、ストレージ アカウントを添付します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="ea75c-156">サブスクリプション ベースのストレージ アカウント接続</span><span class="sxs-lookup"><span data-stu-id="ea75c-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="ea75c-157">[Azure 管理ポータル](https://portal.azure.com) に移動し、サブスクリプションにサインインし、ストレージ アカウントを開きます。</span><span class="sxs-lookup"><span data-stu-id="ea75c-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="ea75c-158">ナビゲーション ウィンドウで **設定** > **プロパティ** に移動します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="ea75c-159">**サブスクリプション**、**リソース グループ**、ストレージ アカウントの **名前** を確認して、対象者に関するインサイトで適切な値を選択していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="ea75c-160">対象者に関するインサイトで、ストレージ アカウントを添付するときに、値または対応するフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="ea75c-161">対象者に関するインサイトの残りの手順を続行して、ストレージ アカウントを添付します。</span><span class="sxs-lookup"><span data-stu-id="ea75c-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]