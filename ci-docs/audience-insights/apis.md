---
title: API に関する作業
description: API を使用し、制限を把握します。
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710466"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="dfdac-103">Customer Insights API の使用</span><span class="sxs-lookup"><span data-stu-id="dfdac-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="dfdac-104">Dynamics 365 Customer Insights は、Customer Insights のデータに基づいて、独自のアプリケーションを構築するための API を提供します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dfdac-105">これらの API の詳細は、[Customer Insights API リファレンス](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfdac-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="dfdac-106">これらには、操作、パラメーター、および応答に関する追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dfdac-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="dfdac-107">この記事では、Customer Insights API にアクセスし、Azure アプリの登録を作成して、利用可能なクライアント ライブラリの使用を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="dfdac-108">Customer Insights API の試用を開始する</span><span class="sxs-lookup"><span data-stu-id="dfdac-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="dfdac-109">Customer Insights に [サインイン](https://home.ci.ai.dynamics.com) します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="dfdac-110">まだサブスクリプションをお持ちでない場合は、[Customer Insights の試用版にサインアップ](https://aka.ms/tryci) します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="dfdac-111">Customer Insights 環境で API を有効にするには、**管理** > **アクセス許可** に移動します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="dfdac-112">これを行うには、管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="dfdac-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="dfdac-113">**API** タブに移動し、**有効** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="dfdac-114">API を有効にすると、API 要求で使用されるインスタンスに対してプライマリおよびセカンダリのサブスクリプション キーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dfdac-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="dfdac-115">キーを再生成するには、**管理** > **アクセス許可** > **API** で **プライマリの再生成** または **セカンダリの再生成** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights API を有効にする":::

1. <span data-ttu-id="dfdac-117">**API の詳細を確認** を選択して、[API を試してください](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)。</span><span class="sxs-lookup"><span data-stu-id="dfdac-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="dfdac-118">API 操作を選択して、**テスト** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="dfdac-119">サイド ペインで、**承認** ドロップダウン メニューの値を **暗黙** に設定します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="dfdac-120">`Authorization` ヘッダーは、ベアラー トークンが追加された状態で取得されます。</span><span class="sxs-lookup"><span data-stu-id="dfdac-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="dfdac-121">サブスクリプション キーは自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="dfdac-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="dfdac-122">必要に応じて、必要なすべてのクエリ パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="dfdac-123">サイド ペインの下までスクロールして、**送信** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="dfdac-124">HTTP 応答がすぐに下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfdac-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="API のテストを選択する方法を示すアニメーション gif。":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="dfdac-126">Azure portal で新しいアプリの登録を作成する</span><span class="sxs-lookup"><span data-stu-id="dfdac-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="dfdac-127">これらの手順は、委任されたアクセス許可を使用して、Azure アプリケーションで Customer Insights API の使用を開始するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dfdac-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="dfdac-128">最初に [「開始する」のセクション](#get-started-trying-the-customer-insights-apis) を完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dfdac-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="dfdac-129">Customer Insights データにアクセスできるアカウントで [Azure portal](https://portal.azure.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="dfdac-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="dfdac-130">左側で、**アプリの登録** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="dfdac-131">**新規登録** を選択して、アプリケーション名を入力し、アカウントの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="dfdac-132">必要に応じて、リダイレクト URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="dfdac-133">ローカル コンピュータでアプリケーションを開発するには、http://localhost で十分です。</span><span class="sxs-lookup"><span data-stu-id="dfdac-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="dfdac-134">新しいアプリの登録で、**API アクセス許可** に移動します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="アプリ登録で API アクセス許可を設定するためのアニメーション gif。":::

1. <span data-ttu-id="dfdac-136">**アクセス許可の追加** を選択し、サイド ペインで **Customer Insights** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="dfdac-137">**アクセス許可の種類** で **委任されたアクセス許可** を選択し、**user_impersonation** アクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="dfdac-138">**アクセス許可の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-138">Select **Add permissions**.</span></span> <span data-ttu-id="dfdac-139">ユーザーがログインせずに API にアクセスする必要がある場合は、[サーバー間アプリケーションのアクセス許可](#server-to-server-application-permissions) セクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dfdac-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="dfdac-140">**... に管理者の同意を付与する** を選択して、アプリの登録を完了します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="dfdac-141">Microsoft 認証ライブラリ (MSAL) でこのアプリの登録に使用されたアプリケーション/クライアント ID を使用して、API への要求とともに送信するベアラー トークンを取得できます。</span><span class="sxs-lookup"><span data-stu-id="dfdac-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="管理者の同意を与えるアニメーション gif。":::

<span data-ttu-id="dfdac-143">MSAL の詳細については、[Microsoft 認証ライブラリ (MSAL) の概要](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfdac-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="dfdac-144">Azure でのアプリの登録の詳細については、[新しい Azure portal アプリの登録エクスペリエンス](/azure/active-directory/develop/app-registration-portal-training-guide) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfdac-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="dfdac-145">クライアント ライブラリの API の使用については、[Customer Insights クライアント ライブラリ](#customer-insights-client-libraries) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfdac-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="dfdac-146">サーバー間アプリケーションのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="dfdac-146">Server-to-server application permissions</span></span>

<span data-ttu-id="dfdac-147">[アプリ登録セクション](#create-a-new-app-registration-in-the-azure-portal) では、ユーザーが認証のためにサインインする必要があるアプリを登録する方法の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="dfdac-148">ユーザーの操作を必要とせず、サーバー上で実行できるアプリ登録の作成方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="dfdac-149">Azure portal のアプリの登録で、**API アクセス許可** に移動します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="dfdac-150">**アクセス許可の追加** を選択し、サイド ペインで **Customer Insights** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-150">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="dfdac-151">**アクセス許可の種類** で **アプリケーションのアクセス許可** を選択し、**CustomerInsights.Api.All** アクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-151">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="dfdac-152">**アクセス許可の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-152">Select **Add permissions**.</span></span>

1. <span data-ttu-id="dfdac-153">このアプリケーションのアクセス許可に管理者の同意を付与するには、サービス プリンシパルを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfdac-153">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="dfdac-154">Azure Active Directory (AD) PowerShell モジュールをインストールします: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="dfdac-154">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="dfdac-155">AD アカウントに接続します: `Connect-AzureAD -TenantId <your tenant id>`。</span><span class="sxs-lookup"><span data-stu-id="dfdac-155">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="dfdac-156">テナント ID は **概要** > **Azure Active Directory** で確認できます。</span><span class="sxs-lookup"><span data-stu-id="dfdac-156">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="dfdac-157">次のコマンドを実行して、Azure AD サービス プリンシパルを追加します: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` AppId パラメーターは、Customer Insights API アプリに関連しています。</span><span class="sxs-lookup"><span data-stu-id="dfdac-157">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="サービス プリンシパル サンプル":::

1. <span data-ttu-id="dfdac-159">アプリの登録の **API アクセス許可** に戻ります。</span><span class="sxs-lookup"><span data-stu-id="dfdac-159">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="dfdac-160">**... に管理者の同意を付与する** を選択して、アプリの登録を完了します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-160">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="管理者の同意を与えるアニメーション gif。":::

1. <span data-ttu-id="dfdac-162">結論から言うと、アプリ登録の名前を Customer Insights でユーザーとして追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfdac-162">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="dfdac-163">Customer Insights を開き、**管理** > **アクセス許可** に移動し、**ユーザーの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-163">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="dfdac-164">アプリ登録の名前を検索し、検索結果から選択して、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-164">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="dfdac-165">Customer Insights クライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="dfdac-165">Customer Insights client libraries</span></span>

<span data-ttu-id="dfdac-166">このセクションは、Customer Insights API で使用可能なクライアント ライブラリを使い始めるときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dfdac-166">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="dfdac-167">すべてのライブラリ ソース コードとサンプル アプリケーションについては、[Customer Insights GitHub ページ](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfdac-167">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="dfdac-168">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="dfdac-168">C# NuGet</span></span>

<span data-ttu-id="dfdac-169">NuGet.org から C# クライアント ライブラリを使い始める方法を説明します。NuGet パッケージの詳細については、[Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfdac-169">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="dfdac-170">現在、このパッケージは netstandard2.0 と netcoreapp2.0 フレームワークを対象としています。</span><span class="sxs-lookup"><span data-stu-id="dfdac-170">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="dfdac-171">C# クライアント ライブラリを C# プロジェクトに追加する</span><span class="sxs-lookup"><span data-stu-id="dfdac-171">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="dfdac-172">Visual Studio で、プロジェクトのために **NuGet パッケージ マネージャー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="dfdac-172">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="dfdac-173">**Microsoft.Dynamics.CustomerInsights.Api** を検索します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-173">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="dfdac-174">**インストール** を選択し、プロジェクトにパッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-174">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="dfdac-175">または、次のコマンドを **NuGet パッケージ マネージャー コンソール** で実行します: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="dfdac-175">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="NuGet パッケージを Visual Studio プロジェクトに追加する":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="dfdac-177">C# クライアント ライブラリを使用する</span><span class="sxs-lookup"><span data-stu-id="dfdac-177">Use the C# client library</span></span>

1. <span data-ttu-id="dfdac-178">[Microsoft 認証ライブラリ (MSAL)](/azure/active-directory/develop/msal-overview) を使用し、既存の [Azure アプリの登録](#create-a-new-app-registration-in-the-azure-portal) を使用して `AccessToken` を取得します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-178">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="dfdac-179">トークンの認証と取得に成功したら、新しい `HttpClient` を作成するか、既存のものを使用して、追加の **DefaultRequestHeaders "Authorization"** を **ベアラー <access token>** に設定し、**Ocp-Apim-Subscription-Key** を [Customer Insights 環境の **サブスクリプション キー**](#get-started-trying-the-customer-insights-apis) に設定します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-179">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="dfdac-180">必要に応じて **Authorization** ヘッダーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="dfdac-180">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="dfdac-181">たとえば、トークンの有効期限が切れたときです。</span><span class="sxs-lookup"><span data-stu-id="dfdac-181">For example, when the token expired.</span></span>

1. <span data-ttu-id="dfdac-182">この `HttpClient` を `CustomerInsights` クライアントの構築に渡します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-182">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="httpclient のサンプル":::

1. <span data-ttu-id="dfdac-184">クライアントで、例えば `GetAllInstancesAsync` などの「拡張メソッド」を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-184">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="dfdac-185">基になる `Microsoft.Rest.HttpOperationResponse` へのアクセスが推奨される場合は、たとえば `GetAllInstancesWithHttpMessagesAsync` などの「HTTP メッセージ メソッド」を使用します。</span><span class="sxs-lookup"><span data-stu-id="dfdac-185">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="dfdac-186">メソッドは複数の型 (たとえば、`IList<InstanceInfo>` や `ApiErrorResult`) を返すことができるため、応答は `object` 型である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dfdac-186">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="dfdac-187">戻り値の型を確認するためには、その操作の [API 詳細ページ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) で指定した応答型にオブジェクトを安全にキャストできます。</span><span class="sxs-lookup"><span data-stu-id="dfdac-187">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="dfdac-188">要求に関する詳細情報が必要な場合は、**HTTP メッセージ メソッド** を使用して、未加工の応答オブジェクトにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="dfdac-188">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="dfdac-189">NodeJS パッケージ</span><span class="sxs-lookup"><span data-stu-id="dfdac-189">NodeJS package</span></span>

<span data-ttu-id="dfdac-190">NPM から入手できる NodeJS クライアント ライブラリを使用します: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="dfdac-190">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="dfdac-191">Python パッケージ</span><span class="sxs-lookup"><span data-stu-id="dfdac-191">Python package</span></span>

<span data-ttu-id="dfdac-192">PyPi から入手できる Python クライアント ライブラリを使用します: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="dfdac-192">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
