---
title: ユーザーのアクセス許可を管理する
description: アクセス許可とユーザー ロールについて説明します。
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7de78c0ef71ec5b83870d396de36a7dcabbd14e5
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689226"
---
# <a name="user-permissions"></a><span data-ttu-id="aa7f5-103">ユーザーのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="aa7f5-103">User permissions</span></span>

<span data-ttu-id="aa7f5-104">**アクセス許可** ページでは、対象者に関するインサイトを使用するための役割とアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="aa7f5-105">ページを見るには、管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="aa7f5-106">対象者に関するインサイトの権限ページにアクセスするには、**管理** > **アクセス許可** に移動します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="aa7f5-107">ロールには、次の 3 種類があります:</span><span class="sxs-lookup"><span data-stu-id="aa7f5-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="aa7f5-108">閲覧者</span><span class="sxs-lookup"><span data-stu-id="aa7f5-108">Viewer</span></span>

- <span data-ttu-id="aa7f5-109">**ホーム** と **セグメント** ページ内でインサイトとセグメントを探索します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="aa7f5-110">**顧客** ページを使用して顧客プロファイルを検索およびフィルタ―します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="aa7f5-111">フィールドは検索可能となっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-111">Fields must be searchable.</span></span>
- <span data-ttu-id="aa7f5-112">**強化** ページを確認し、探索します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="aa7f5-113">**エンティティ** ページを使用してエンティティを探索およびエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="aa7f5-114">**システム** ページを使用してシステムプロセスのステータスを表示します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="aa7f5-115">**セグメント** ページからセグメントをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-115">Export segments from the **Segments** page.</span></span>
- <span data-ttu-id="aa7f5-116">**Power BI Customer Insights** ダッシュボードをインストールして使用します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="aa7f5-117">共同作成者</span><span class="sxs-lookup"><span data-stu-id="aa7f5-117">Contributor</span></span>

- <span data-ttu-id="aa7f5-118">ビューアーが使用できるすべてのアクセス権限。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="aa7f5-119">**データ ソース** ページを使用してデータを読み込み、変換をします。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="aa7f5-120">*データ統合* セクション (**マップ**、**照合**、**マージ**) を完了すると、統合顧客プロファイル エンティティが得られます。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="aa7f5-121">**リレーションシップ** と **活動** を定義します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="aa7f5-122">**セグメント** ページを使用してセグメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="aa7f5-123">**メジャー** ページを使用してメジャーを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="aa7f5-124">構成を管理し、顧客プロファイルを **エンリッチメント** ページから拡充します (ファースト パーティのエンリッチメントのみ)。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>

## <a name="administrator"></a><span data-ttu-id="aa7f5-125">管理者</span><span class="sxs-lookup"><span data-stu-id="aa7f5-125">Administrator</span></span>

- <span data-ttu-id="aa7f5-126">共同制作者が使用できるすべてのアクセス権限。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-126">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="aa7f5-127">作業言語とシステム プロセスの更新スケジュールを含む、**システム** ページの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-127">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="aa7f5-128">**アクセス許可** ページを使用して、アクセス許可を表示および追加します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-128">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="aa7f5-129">**インデックスの検索およびフィルター処理** ページ (**顧客** ページからアクセス可能) を使用して、顧客ページの検索およびフィルターの定義を設定します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-129">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="aa7f5-130">**エクスポート先** ページを使用して Dynamics 365 Sales セグメントの保存先を定義します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-130">Define Dynamics 365 Sales segment destinations using the **Export destinations** page.</span></span>
- <span data-ttu-id="aa7f5-131">構成を管理し、顧客プロファイルを **エンリッチメント** ページから拡充します (すべてのエンリッチメントが対象)。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-131">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="aa7f5-132">**顧客カード アドイン** をインストールして使用します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-132">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="aa7f5-133">**Power Apps コネクタ** を追加して使用します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-133">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="aa7f5-134">[Customer Insights API](apis.md) の使用を有効にします。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-134">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="aa7f5-135">アクセス許可とロールの割り当て</span><span class="sxs-lookup"><span data-stu-id="aa7f5-135">Assign roles and permissions</span></span>

1. <span data-ttu-id="aa7f5-136">対象者に関するインサイトで、**管理** > **アクセス許可** に移動します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-136">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="aa7f5-137">**ユーザーの追加** を選択し、**アクセス許可の追加/編集** ペインを開きます。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-137">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="aa7f5-138">**検索** フィールドを使用して、権限を調整するAzure Active Directoryのユーザーまたはグループを検索します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-138">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="aa7f5-139">**ロール** を選択して、ユーザーまたはグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-139">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="aa7f5-140">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-140">Select **Save**.</span></span> <span data-ttu-id="aa7f5-141">現在の環境は、アクセス許可を変更したユーザーまたはグループのメンバーと自動的に共有されます。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-141">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="aa7f5-142">ユーザーは Customer Insights アプリにアクセスして、指定された役割に従って作業できます。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-142">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="aa7f5-143">現在のアクセス権限を表示する</span><span class="sxs-lookup"><span data-stu-id="aa7f5-143">View current permissions</span></span>

<span data-ttu-id="aa7f5-144">対象者に関するインサイトで、**管理** > **アクセス許可** に移動し、現在アクティブなロールの割り当てを確認します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-144">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="aa7f5-145">**種類** 列は、単一のユーザー、グループ、またはアプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-145">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="aa7f5-146">システムは、個々のユーザーとグループに対応しています。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-146">The system supports individual users and groups.</span></span>
- <span data-ttu-id="aa7f5-147">ロールは **ロール** 列で指定します。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-147">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="aa7f5-148">列タイトルを選択して、その列内の値で結果をソートします。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-148">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="aa7f5-149">ページ上部の **検索** フィールドを使用して、特定のユーザーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="aa7f5-149">Use the **Search** field at the top of the page to locate specific users.</span></span>
