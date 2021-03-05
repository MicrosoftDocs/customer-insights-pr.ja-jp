---
title: Customer Insights のデータを Dynamics 365 Sales にエクスポートする
description: Dynamics 365 Sales への接続を構成する方法について説明します。
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269014"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="7ddd6-103">Dynamics 365 Sales のコネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7ddd6-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="7ddd6-104">Dynamics 365 Sales で顧客データを使用して、マーケティング リストの作成、ワークフローのフォローアップ、プロモーションの送信を行います。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="7ddd6-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="7ddd6-105">Prerequisite</span></span>

1. <span data-ttu-id="7ddd6-106">Customer Insights から Sales にセグメントをエクスポートする前に、取引先担当者レコードが Dynamics 365 Sales に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="7ddd6-107">取引先担当者を取り込む方法の詳細については、[Common Data Services を使った Dynamics 365 Sales](connect-power-query.md) を読んでください。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="7ddd6-108">対象者インサイトから Sales にセグメントをエクスポートしても、Sales インスタンスに新しい取引先担当者レコードは作成されません。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="7ddd6-109">Sales からの取引先担当者レコードは、対象者インサイトに取り込まれ、データ ソースとして使用される必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="7ddd6-110">また、セグメントをエクスポートする前に、顧客 ID を取引先担当者 ID にマッピングするために、統合された顧客エンティティに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="7ddd6-111">Sales 用のコネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="7ddd6-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="7ddd6-112">対象者に関するインサイトで、**管理** > **エクスポート先** に移動します。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7ddd6-113">**Dynamics 365 Sales** で **設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="7ddd6-114">**表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7ddd6-115">**サーバー アドレス** フィールドに組織の Sales URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="7ddd6-116">**サーバー管理者アカウント** セクションで、**サインイン** を選択し、Dynamics 365 Sales アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="7ddd6-117">顧客 ID フィールドを Dynamics 365 取引先担当者 ID にマップします。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="7ddd6-118">**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-118">Select **Next**.</span></span>

1. <span data-ttu-id="7ddd6-119">1つ、または複数のセグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="7ddd6-120">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7ddd6-121">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="7ddd6-121">Export the data</span></span>

<span data-ttu-id="7ddd6-122">[オンデマンドでデータをエクスポート](export-destinations.md) できます。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7ddd6-123">エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="7ddd6-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]