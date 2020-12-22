---
title: Power Automate コネクタ | Microsoft Docs
description: Dynamics 365 Customer Insights から Microsoft Power Automate でフローを作成します。
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406149"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="bfa64-103">Power Automateコネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="bfa64-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="bfa64-104">データが変更されたときに特定のイベントを自動的にトリガーし、[Power Automate](https://flow.microsoft.com/) でより複雑なフローを直接管理します。</span><span class="sxs-lookup"><span data-stu-id="bfa64-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="bfa64-105">Power Automate のトリガー</span><span class="sxs-lookup"><span data-stu-id="bfa64-105">Power Automate triggers</span></span>

<span data-ttu-id="bfa64-106">さまざまなトリガーを使用して、通知やその他の高度なアクションなどの反復タスクを自動化するフローを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bfa64-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="bfa64-107">データ ソースの更新が失敗したときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="bfa64-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="bfa64-108">データ ソースの更新が成功したときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="bfa64-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="bfa64-109">セグメントのしきい値を超えたときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="bfa64-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="bfa64-110">トリガーは、しきい値を超えると制限されます。</span><span class="sxs-lookup"><span data-stu-id="bfa64-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="bfa64-111">業務の計測値のしきい値を超えたときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="bfa64-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="bfa64-112">トリガーは、しきい値を超えると制限されます。</span><span class="sxs-lookup"><span data-stu-id="bfa64-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="bfa64-113">(データソース、セグメント、メジャーなど) の完全更新が完了したときに、トリガーします。</span><span class="sxs-lookup"><span data-stu-id="bfa64-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="bfa64-114">統合プロセス (マップ、照合、結合) の更新が完了したときにトリガーします。</span><span class="sxs-lookup"><span data-stu-id="bfa64-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="bfa64-115">[Power Automateでトリガーを構成する](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)。</span><span class="sxs-lookup"><span data-stu-id="bfa64-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="bfa64-116">Power Automate  のアクション</span><span class="sxs-lookup"><span data-stu-id="bfa64-116">Power Automate actions</span></span>
<span data-ttu-id="bfa64-117">Power Automate のコネクタは、利用可能なトリガー以外のアクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="bfa64-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="bfa64-118">詳細については、『[Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/)』を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfa64-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="bfa64-119">対象者に関するインサイトで Power Automate フローを作成する</span><span class="sxs-lookup"><span data-stu-id="bfa64-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="bfa64-120">対象者に関するインサイトで、**管理** > **システム** に移動します。</span><span class="sxs-lookup"><span data-stu-id="bfa64-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="bfa64-121">**システム** ページで、**状態** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa64-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="bfa64-122">**データソース** セクションの中に、**フロー** を選択し、ドロップダウンリストから **フローの作成** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa64-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bfa64-123">![フローアクションの作成を示す Power Automate コネクタ](media/power-automate-connector-create-flow.png "フロー アクションの作成を示す Power Automate コネクタ")</span><span class="sxs-lookup"><span data-stu-id="bfa64-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="bfa64-124">Power Automate で、使用可能なトリガーの 1 つを選択して、優先フローを作成します。</span><span class="sxs-lookup"><span data-stu-id="bfa64-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="bfa64-125">最初のフローを作成する場合は、最初に Power Automate コネクタで認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfa64-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
