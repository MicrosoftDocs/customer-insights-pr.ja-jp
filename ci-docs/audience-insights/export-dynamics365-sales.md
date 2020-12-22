---
title: Customer Insights のデータを Dynamics 365 Sales にエクスポートする
description: Dynamics 365 Sales への接続を構成する方法について説明します。
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643824"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="a135c-103">Dynamics 365 Sales のコネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="a135c-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a135c-104">Dynamics 365 Sales で顧客データを使用して、マーケティング リストの作成、ワークフローのフォローアップ、プロモーションの送信を行います。</span><span class="sxs-lookup"><span data-stu-id="a135c-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="a135c-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="a135c-105">Prerequisite</span></span>

<span data-ttu-id="a135c-106">[Common Data Service を使用して取り込んだ Dynamics 365 Sales](connect-power-query.md) の取引先担当者レコード。</span><span class="sxs-lookup"><span data-stu-id="a135c-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="a135c-107">Sales 用のコネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="a135c-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="a135c-108">対象者に関するインサイトで、**管理** > **エクスポート先** に移動します。</span><span class="sxs-lookup"><span data-stu-id="a135c-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a135c-109">**Dynamics 365 Sales** で **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a135c-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="a135c-110">**表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="a135c-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a135c-111">**サーバー アドレス** フィールドに組織の Sales URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a135c-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a135c-112">**サーバー管理者アカウント** セクションで、**サインイン** を選択し、Dynamics 365 Sales アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="a135c-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="a135c-113">顧客 ID フィールドを Dynamics 365 取引先担当者 ID にマップします。</span><span class="sxs-lookup"><span data-stu-id="a135c-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a135c-114">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a135c-114">Select **Next**.</span></span>

1. <span data-ttu-id="a135c-115">1つ、または複数のセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="a135c-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="a135c-116">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a135c-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a135c-117">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="a135c-117">Export the data</span></span>

<span data-ttu-id="a135c-118">[オンデマンドでデータをエクスポート](export-destinations.md) できます。</span><span class="sxs-lookup"><span data-stu-id="a135c-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a135c-119">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="a135c-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
