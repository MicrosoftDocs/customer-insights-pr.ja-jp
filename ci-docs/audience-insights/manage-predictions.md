---
title: 予測シナリオの共有タスク
description: 予測を管理、トラブルシューティング、調整する方法を説明します。
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095724"
---
# <a name="manage-predictions"></a><span data-ttu-id="a957f-103">予測の管理</span><span class="sxs-lookup"><span data-stu-id="a957f-103">Manage predictions</span></span>

<span data-ttu-id="a957f-104">この記事では、ほとんどの予測シナリオが共有するいくつかのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a957f-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="a957f-105">失敗した予測のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a957f-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="a957f-106">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a957f-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="a957f-107">エラー ログを表示する予測の横にある縦の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="a957f-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="a957f-108">**ログ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a957f-108">Select **Logs**.</span></span>

1. <span data-ttu-id="a957f-109">すべてのエラーをレビューします。</span><span class="sxs-lookup"><span data-stu-id="a957f-109">Review all the errors.</span></span> <span data-ttu-id="a957f-110">発生するエラーにはいくつかの種類があり、どのような状態でエラーが発生したかを記載しています。</span><span class="sxs-lookup"><span data-stu-id="a957f-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="a957f-111">たとえば、正確に予測するための十分なデータがない、というエラーは、多くの場合で Customer Insights に追加のデータをロードすることで解決されます。</span><span class="sxs-lookup"><span data-stu-id="a957f-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="a957f-112">入力データのユーザビリティ レポート</span><span class="sxs-lookup"><span data-stu-id="a957f-112">Input data usability report</span></span>

<span data-ttu-id="a957f-113">入力データのユーザビリティ レポートは、すぐに使用できる予測で生成される可能性のあるエラーと警告の統合ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="a957f-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="a957f-114">また、モデルのパフォーマンスを向上させる方法についても推奨します。</span><span class="sxs-lookup"><span data-stu-id="a957f-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="a957f-115">レポートは、モデルがトレーニング プロセスを完了した後で利用できます。</span><span class="sxs-lookup"><span data-stu-id="a957f-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="a957f-116">正常に完了したかどうかに関係なく、モデルごとに個別に作成されます。</span><span class="sxs-lookup"><span data-stu-id="a957f-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="a957f-117">現在、この機能はトランザクション離反モデルでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="a957f-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="a957f-118">入力データ ユーザビリティ レポートの表示</span><span class="sxs-lookup"><span data-stu-id="a957f-118">View the input data usability report</span></span>

<span data-ttu-id="a957f-119">すぐに使用できるモデルがトレーニング ステップを完了したら、レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="a957f-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="a957f-120">モデル名の横にある楕円を選択し、**入力データ ユーザビリティ レポート** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a957f-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="a957f-121">モデルの状態を選択し、サイド ペインにある **入力データ ユーザビリティ レポートを表示する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a957f-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="a957f-122">一覧でモデルの 1 つを選択し、コマンド バーで **入力データ ユーザビリティ レポート** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a957f-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="a957f-123">モデルの結果ページを開き、コマンド バーで **入力データ ユーザビリティ レポート** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a957f-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="a957f-124">入力データ ユーザビリティ レポートの情報</span><span class="sxs-lookup"><span data-stu-id="a957f-124">Information in the input data usability report</span></span>

<span data-ttu-id="a957f-125">レポートの次の列には、モデルのデータを改善するために役立つ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a957f-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="エラー、警告、および推奨事項を含むテーブルを示す入力データ ユーザビリティ レポートの例。":::

- <span data-ttu-id="a957f-127">名前: エラー、警告、または推奨事項の内容を示す名前。</span><span class="sxs-lookup"><span data-stu-id="a957f-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="a957f-128">ステップ: 情報が参照するモデル フェーズ、トレーニングまたはスコア。</span><span class="sxs-lookup"><span data-stu-id="a957f-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="a957f-129">状態: 情報の重要度 (エラー、警告、推奨事項)。</span><span class="sxs-lookup"><span data-stu-id="a957f-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="a957f-130">列名: モデルのパフォーマンスを向上させるために変更が必要なエンティティの列。</span><span class="sxs-lookup"><span data-stu-id="a957f-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="a957f-131">エンティティ名: モデルのパフォーマンスを向上させるために変更が必要なエンティティの名前。</span><span class="sxs-lookup"><span data-stu-id="a957f-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="a957f-132">詳細: エラー、警告、または推奨事項に関する詳細。</span><span class="sxs-lookup"><span data-stu-id="a957f-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="a957f-133">予測を更新する</span><span class="sxs-lookup"><span data-stu-id="a957f-133">Refresh a prediction</span></span>

<span data-ttu-id="a957f-134">予測は、設定で構成されているとおり、同一の[データ更新スケジュール](system.md#schedule-tab)に基づいて自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="a957f-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="a957f-135">手動で更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="a957f-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="a957f-136">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a957f-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="a957f-137">更新する予測の横に配置されている縦型の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="a957f-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="a957f-138">**最新の情報に更新** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a957f-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="a957f-139">予測を削除する</span><span class="sxs-lookup"><span data-stu-id="a957f-139">Delete a prediction</span></span>

<span data-ttu-id="a957f-140">予測を削除すると、その出力エンティティも削除されます。</span><span class="sxs-lookup"><span data-stu-id="a957f-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="a957f-141">**インテリジェンス** > **予測** に移動し、**自分の予測** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a957f-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="a957f-142">削除する予測の横に配置されている縦型の省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="a957f-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="a957f-143">**削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a957f-143">Select **Delete**.</span></span>
