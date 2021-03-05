---
title: Customer Insights のデータを Dynamics 365 Marketing にエクスポートする
description: Dynamics 365 Marketing への接続を構成する方法について説明します。
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269060"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="9dfc6-103">Dynamics 365 Marketing のコネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9dfc6-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9dfc6-104">[セグメント](segments.md) を使用してキャンペーンを生成し、Dynamics 365 Marketing を使用して特定の顧客グループに連絡します。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="9dfc6-105">詳しくは、[Dynamics 365 Marketing で Dynamics 365 Customer Insights のセグメントを使用する](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="9dfc6-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="9dfc6-106">Prerequisite</span></span>

- <span data-ttu-id="9dfc6-107">Customer Insights から Marketing にセグメントをエクスポートする前に、取引先担当者レコードが Dynamics 365 Marketing に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="9dfc6-108">取引先担当者を取り込む方法の詳細については、[Common Data Services を使った Dynamics 365 Marketing](connect-power-query.md) を読んでください。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="9dfc6-109">対象者インサイトから Marketing にセグメントをエクスポートしても、Marketing インスタンスに新しい取引先担当者レコードは作成されません。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="9dfc6-110">Marketing からの取引先担当者レコードは、対象者インサイトに取り込まれ、データ ソースとして使用される必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="9dfc6-111">また、セグメントをエクスポートする前に、顧客 ID を取引先担当者 ID にマッピングするために、統合された顧客エンティティに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="9dfc6-112">Marketing 用のコネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="9dfc6-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="9dfc6-113">対象者に関するインサイトで、**管理** > **エクスポート先** に移動します。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9dfc6-114">**Dynamics 365 Marketing** で **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="9dfc6-115">**表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9dfc6-116">**サーバー アドレス** フィールドに組織の Marketing URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="9dfc6-117">**サーバー管理者アカウント** セクションで、**サインイン** を選択し、Dynamics 365 Marketing アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="9dfc6-118">顧客 ID フィールドを Dynamics 365 取引先担当者 ID にマップします。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="9dfc6-119">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-119">Select **Next**.</span></span>

1. <span data-ttu-id="9dfc6-120">1つ、または複数のセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="9dfc6-121">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9dfc6-122">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="9dfc6-122">Export the data</span></span>

<span data-ttu-id="9dfc6-123">[オンデマンドでデータをエクスポート](export-destinations.md) できます。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9dfc6-124">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="9dfc6-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]