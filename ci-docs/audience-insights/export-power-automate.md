---
title: Power Automate コネクタ | Microsoft Docs
description: Dynamics 365 Customer Insights から Microsoft Power Automate のフローを作成します。
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305070"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="399f9-103">Power Automateコネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="399f9-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="399f9-104">データが変更されたときに特定のイベントを自動的にトリガーし、[Power Automate](https://flow.microsoft.com/) でより複雑なフローを直接管理します。</span><span class="sxs-lookup"><span data-stu-id="399f9-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="399f9-105">Power Automate のトリガー</span><span class="sxs-lookup"><span data-stu-id="399f9-105">Power Automate triggers</span></span>

<span data-ttu-id="399f9-106">トリガーを使用してクラウド フローを作成し、通知やより高度なアクションなどの反復的なタスクを自動化します。</span><span class="sxs-lookup"><span data-stu-id="399f9-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="399f9-107">データ ソースの更新が失敗したときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="399f9-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="399f9-108">データ ソースの更新が成功したときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="399f9-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="399f9-109">セグメントのしきい値を超えたときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="399f9-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="399f9-110">トリガーは、しきい値を超えると制限されます。</span><span class="sxs-lookup"><span data-stu-id="399f9-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="399f9-111">業務の計測値のしきい値を超えたときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="399f9-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="399f9-112">ディメンションのないビジネス メジャーのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="399f9-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="399f9-113">トリガーは、しきい値を超えると制限されます。</span><span class="sxs-lookup"><span data-stu-id="399f9-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="399f9-114">(データソース、セグメント、メジャーなど) の更新がすべて完了したときに、トリガーします。</span><span class="sxs-lookup"><span data-stu-id="399f9-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="399f9-115">統合プロセス (マップ、照合、結合) の更新が完了したときにトリガーします。</span><span class="sxs-lookup"><span data-stu-id="399f9-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="399f9-116">Power Automate でトリガーを構成する。</span><span class="sxs-lookup"><span data-stu-id="399f9-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="399f9-117">Power Automate  のアクション</span><span class="sxs-lookup"><span data-stu-id="399f9-117">Power Automate actions</span></span>

<span data-ttu-id="399f9-118">Power Automate のコネクタは、利用可能なトリガー以外のアクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="399f9-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="399f9-119">詳細については、『[Dynamics 365 Customer Insights Connector](/connectors/customerinsights/)』を参照してください。</span><span class="sxs-lookup"><span data-stu-id="399f9-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="399f9-120">Power Automate フローを作成する</span><span class="sxs-lookup"><span data-stu-id="399f9-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="399f9-121">対象者に関するインサイトで、**管理** > **エクスポート先** に移動します。</span><span class="sxs-lookup"><span data-stu-id="399f9-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="399f9-122">**Power Automate** タイルで、**設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="399f9-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="399f9-123">Power Automate で Customer Insights コネクタ (プレビュー) が開きます。</span><span class="sxs-lookup"><span data-stu-id="399f9-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="399f9-124">Power Automate に **サインイン** します。</span><span class="sxs-lookup"><span data-stu-id="399f9-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="399f9-125">使用可能なトリガーの 1 つを選択し、新しいフローにステップを追加します。</span><span class="sxs-lookup"><span data-stu-id="399f9-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="399f9-126">詳細については、[Power Automateでクラウド フローを作成する](/power-automate/get-started-logic-flow)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="399f9-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="399f9-127">フローの使用方法の例:</span><span class="sxs-lookup"><span data-stu-id="399f9-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="399f9-128">データ ソースの更新が失敗した場合、Microsoft Teams チャネルにメッセージを投稿します。</span><span class="sxs-lookup"><span data-stu-id="399f9-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="399f9-129">セグメントのしきい値を超えたときに、データ所有者に E メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="399f9-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
