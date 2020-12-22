---
title: Microsoft Teams 用ボット
description: ボットのヘルプを使用して、Microsoft Teams で統合顧客プロファイルを検索します。
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406182"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="ae9b8-103">Dynamics 365 Customer Insights 用 Teams ボット (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="ae9b8-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="ae9b8-104">Microsoft Teams に接続して、ボットが Teams チャネルで統合顧客プロファイルを検索できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ae9b8-105">![顧客レコードを表示する Teams ボット](media/teams-bot.png "顧客レコードを表示する Teams ボット")</span><span class="sxs-lookup"><span data-stu-id="ae9b8-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ae9b8-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="ae9b8-106">Prerequisites</span></span>

<span data-ttu-id="ae9b8-107">ボットを設定して構成するには、次の前提条件を満たす必要があります:</span><span class="sxs-lookup"><span data-stu-id="ae9b8-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="ae9b8-108">少なくとも 1 つの [追加されたデータ ソース](data-sources.md) があります。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="ae9b8-109">[統合プロセス](data-unification.md) が完了しました。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="ae9b8-110">フィールドが [検索とフィルター インデックス](search-filter-index.md) に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="ae9b8-111">Customer Insights と Teams は同じ組織内にあります。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="ae9b8-112">ボットの構成</span><span class="sxs-lookup"><span data-stu-id="ae9b8-112">Configure the bot</span></span>

1. <span data-ttu-id="ae9b8-113">対象者に関するインサイトで、**管理** > **エクスポート先** に移動します。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="ae9b8-114">Microsoft Teams タイルで、**設定** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="ae9b8-115">Teams の **アプリ** 領域にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="ae9b8-116">Teams を開いて、左下隅にある **アプリ** を選択するか、直接 [AppSource から取得](https://go.microsoft.com/fwlink/?linkid=2124104) することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="ae9b8-117">**Customer Insights** を検索して、アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="ae9b8-118">**追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-118">Select **Add**.</span></span>
1. <span data-ttu-id="ae9b8-119">Teams で Customer Insights にサインインすると、ウェルカム メッセージが表示され、開始できます。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="ae9b8-120">ボットでできること</span><span class="sxs-lookup"><span data-stu-id="ae9b8-120">Things you can do with the bot</span></span>

<span data-ttu-id="ae9b8-121">ボットは、統合された顧客プロファイルの検索機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="ae9b8-122">検索とフィルターのインデックスに追加された統合された顧客プロファイルで、**検索** に続けて名前、メール アドレス、またはその他のフィールドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="ae9b8-123">得られた顧客プロファイルから、最大 15 フィールドを持つカードを取得します。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="ae9b8-124">複数の一致は、プロファイルを選択できる結果の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="ae9b8-125">検索語句を二重引用符で囲んで、完全一致を検索できます。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="ae9b8-126">組織が同じ組織内に複数の Customer Insights 環境を維持している場合は、**switchinstance** を入力し、ボットを接続する環境を選択できます。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="ae9b8-127">**ヘルプ** と入力して、ボットで使用できるコマンドのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="ae9b8-127">Enter **help** to see a list of available commands for the bot.</span></span>  
