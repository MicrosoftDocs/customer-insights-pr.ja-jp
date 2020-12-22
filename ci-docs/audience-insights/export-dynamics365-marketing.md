---
title: Customer Insights のデータを Dynamics 365 Marketing にエクスポートする
description: Dynamics 365 Marketing への接続を構成する方法について説明します。
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643779"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="c35da-103">Dynamics 365 Marketing のコネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="c35da-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c35da-104">[セグメント](segments.md) を使用してキャンペーンを生成し、Dynamics 365 Marketing を使用して特定の顧客グループに連絡します。</span><span class="sxs-lookup"><span data-stu-id="c35da-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="c35da-105">詳しくは、[Dynamics 365 Marketing で Dynamics 365 Customer Insights のセグメントを使用する](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c35da-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="c35da-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="c35da-106">Prerequisite</span></span>

<span data-ttu-id="c35da-107">[Dynamics 365 Marketing が取り込んだ Common Data Service](connect-power-query.md) の取引先担当者レコード。</span><span class="sxs-lookup"><span data-stu-id="c35da-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="c35da-108">Marketing 用のコネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="c35da-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="c35da-109">対象者に関するインサイトで、**管理** > **エクスポート先** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c35da-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c35da-110">**Dynamics 365 Marketing** で **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c35da-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="c35da-111">**表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="c35da-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c35da-112">**サーバー アドレス** フィールドに組織の Marketing URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="c35da-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="c35da-113">**サーバー管理者アカウント** セクションで、**サインイン** を選択し、Dynamics 365 Marketing アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="c35da-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="c35da-114">顧客 ID フィールドを Dynamics 365 取引先担当者 ID にマップします。</span><span class="sxs-lookup"><span data-stu-id="c35da-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="c35da-115">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c35da-115">Select **Next**.</span></span>

1. <span data-ttu-id="c35da-116">1つ、または複数のセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="c35da-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="c35da-117">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c35da-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c35da-118">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="c35da-118">Export the data</span></span>

<span data-ttu-id="c35da-119">[オンデマンドでデータをエクスポート](export-destinations.md) できます。</span><span class="sxs-lookup"><span data-stu-id="c35da-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c35da-120">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="c35da-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
