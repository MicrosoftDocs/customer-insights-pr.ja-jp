---
title: GDPR におけるデータ主体の権利 (DSR) | Microsoft Docs
description: Dynamics 365 Customer Insights の対象者に関するインサイト機能についてデータ主体の要求に対応します。
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268692"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="0d229-103">GDPR におけるデータ主体の権利 (DSR)</span><span class="sxs-lookup"><span data-stu-id="0d229-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="0d229-104">Dynamics 365 Customer Insights の対象者に関するインサイト機能に対する GDPR データ主体の削除要求への対応</span><span class="sxs-lookup"><span data-stu-id="0d229-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="0d229-105">組織の顧客情報から個人データを削除する「削除する権利」は、一般データ保護規則 (GDPR) における主要な保護となっています。</span><span class="sxs-lookup"><span data-stu-id="0d229-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="0d229-106">個人データの削除では、監査ログ情報を除くすべての個人データとシステム生成ログが削除されます。</span><span class="sxs-lookup"><span data-stu-id="0d229-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="0d229-107">データ主体の削除要求の管理</span><span class="sxs-lookup"><span data-stu-id="0d229-107">Manage data subject delete requests</span></span>

<span data-ttu-id="0d229-108">対象者に関するインサイトは、特定の顧客またはユーザーの個人データを削除するために、次の製品内エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0d229-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="0d229-109">**顧客データの削除要求を管理する** : Customer Insights の顧客データは、Customer Insights 外部の元のデータ ソースから取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="0d229-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="0d229-110">すべての GDPR 削除要求は、元のデータ ソースで実行しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="0d229-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="0d229-111">**Customer Insights ユーザー データの削除要求の管理**: ユーザーのデータは Customer Insights によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="0d229-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="0d229-112">すべての GDPR 削除要求は、Customer Insights で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d229-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="0d229-113">顧客データの削除要求の管理</span><span class="sxs-lookup"><span data-stu-id="0d229-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="0d229-114">Customer Insights の管理者は、次の手順に従って、データ ソースで削除された顧客データを 取り除くことができます。</span><span class="sxs-lookup"><span data-stu-id="0d229-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="0d229-115">Dynamics 365 Customer Insights にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0d229-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="0d229-116">対象者に関するインサイトで、**データ** > **データ ソース** に移動します</span><span class="sxs-lookup"><span data-stu-id="0d229-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="0d229-117">削除された顧客データを含むリスト内の各データ ソースについて :</span><span class="sxs-lookup"><span data-stu-id="0d229-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="0d229-118">(...) を選択し、続いて **更新** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d229-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="0d229-119">**状態** 下のデータ ソースの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="0d229-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="0d229-120">チェックマークが付いていると、更新が成功したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0d229-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="0d229-121">警告の三角形は、何かがうまくいかなかったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0d229-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="0d229-122">警告の三角形が表示された場合は、D365CI@microsoft.com にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="0d229-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0d229-123">![顧客データのGDPR 削除要求の処理](media/gdpr-data-sources.png "顧客データの GDPR 削除要求の処理")</span><span class="sxs-lookup"><span data-stu-id="0d229-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="0d229-124">ユーザー データの削除要求の管理</span><span class="sxs-lookup"><span data-stu-id="0d229-124">Manage delete requests for user data</span></span>

<span data-ttu-id="0d229-125">Customer Insights 管理者は、次の手順に従って Customer Insights ユーザー データを削除できます。</span><span class="sxs-lookup"><span data-stu-id="0d229-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="0d229-126">Dynamics 365 Customer Insights にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0d229-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="0d229-127">対象者に関するインサイトで、**管理** > **アクセス許可** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0d229-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="0d229-128">削除するユーザーのチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d229-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="0d229-129">**Remove** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d229-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0d229-130">![ユーザー データの GDPR 削除要求の処理](media/gdpr-permissions.png "ユーザー データの GDPR 削除要求の処理")</span><span class="sxs-lookup"><span data-stu-id="0d229-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="0d229-131">GDPR データ主体のエクスポート要求に対応する</span><span class="sxs-lookup"><span data-stu-id="0d229-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="0d229-132">一般データ保護規則 (GDPR) への道のりであなたのパートナーとなるという当社のコミットメントの一環として、準備に役立つドキュメントを開発しました。</span><span class="sxs-lookup"><span data-stu-id="0d229-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="0d229-133">このドキュメントでは、対象者に関するインサイトを使用するときに GDPR 準拠をサポートするために、現時点で実行可能な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d229-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="0d229-134">要求のエクスポートおよび表示の管理</span><span class="sxs-lookup"><span data-stu-id="0d229-134">Manage export and view requests</span></span>

<span data-ttu-id="0d229-135">データ可搬性の権限では、データ サブジェクトが、他のデータコントローラに送信ができる個人データを電子フォーマット (「構造化され、一般的に使用され、機械可読で、相互運用可能なフォーマット」) で要求することができます。</span><span class="sxs-lookup"><span data-stu-id="0d229-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="0d229-136">顧客データのエクスポート (テナント管理者)</span><span class="sxs-lookup"><span data-stu-id="0d229-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="0d229-137">テナント管理者は、これらの手順に従ってデータをエクスポートします :</span><span class="sxs-lookup"><span data-stu-id="0d229-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="0d229-138">要求で顧客のメールアドレスを指定して、D365CI@microsoft.com にメールを送ります。</span><span class="sxs-lookup"><span data-stu-id="0d229-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="0d229-139">Customer Insights チームは、登録されたテナント管理者のメール アドレスにメールを送信し、データのエクスポートの確認を求めます。</span><span class="sxs-lookup"><span data-stu-id="0d229-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="0d229-140">要求された顧客のデータをエクスポートするにあたっての確認をします。</span><span class="sxs-lookup"><span data-stu-id="0d229-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="0d229-141">テナント管理者のメールアドレスからエクスポートされたデータを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0d229-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="0d229-142">ユーザー データのエクスポート (テナント管理者)</span><span class="sxs-lookup"><span data-stu-id="0d229-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="0d229-143">要求でユーザーのメールアドレスを指定して、D365CI@microsoft.com にメールを送ります。</span><span class="sxs-lookup"><span data-stu-id="0d229-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="0d229-144">Customer Insights チームは、登録されたテナント管理者のメール アドレスにメールを送信し、データのエクスポートの確認を求めます。</span><span class="sxs-lookup"><span data-stu-id="0d229-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="0d229-145">要求されたユーザーのデータをエクスポートするにあたっての確認をします。</span><span class="sxs-lookup"><span data-stu-id="0d229-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="0d229-146">テナント管理者のメールアドレスからエクスポートされたデータを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0d229-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]