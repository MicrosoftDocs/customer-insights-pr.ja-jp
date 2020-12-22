---
title: PowerQuery ベースのデータ ソースの増分更新
description: Power Query に基づいて、大規模なデータ ソースの新規および更新されたデータを更新します。
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406184"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="bea74-103">Power Query ベースのデータ ソースの増分更新</span><span class="sxs-lookup"><span data-stu-id="bea74-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="bea74-104">データ ソースの増分更新には、次の利点があります:</span><span class="sxs-lookup"><span data-stu-id="bea74-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="bea74-105">**更新速度の増強** - 変更のあったデータのみが更新されます。</span><span class="sxs-lookup"><span data-stu-id="bea74-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="bea74-106">例えば、履歴データセットの過去 5 日間だけを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="bea74-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="bea74-107">**安定性の増加** - 更新の規模を縮小化することで、揮発性のソース システムへの接続を長期間維持する必要がなくなり、接続の問題が発生するリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="bea74-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="bea74-108">**リソース消費の軽減** - データ全体の一部のみを更新することで、コンピューター上のリソース使用効率が向上し、環境への負荷が軽減します。</span><span class="sxs-lookup"><span data-stu-id="bea74-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="bea74-109">増分更新を構成する</span><span class="sxs-lookup"><span data-stu-id="bea74-109">Configure incremental refresh</span></span>

<span data-ttu-id="bea74-110">対象者に関するインサイトでは、増分取り込みをサポートする Power Query でインポートしたデータ ソースの増分更新が可能です。</span><span class="sxs-lookup"><span data-stu-id="bea74-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="bea74-111">たとえば、データ レコードが最後に更新された日付と時刻のフィールドを持つ Azure SQL データベースなどです。</span><span class="sxs-lookup"><span data-stu-id="bea74-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="bea74-112">[Power Query に基づいて新しいデータ ソースを作成します](connect-power-query.md)。</span><span class="sxs-lookup"><span data-stu-id="bea74-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="bea74-113">データ ソースの名称を入力してください。</span><span class="sxs-lookup"><span data-stu-id="bea74-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="bea74-114">Azure SQL データベースなどの、増分更新に対応するデータ ソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="bea74-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="bea74-115">取り込むエンティティまたはテーブルを選択します。</span><span class="sxs-lookup"><span data-stu-id="bea74-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="bea74-116">この変換の手順を完了し、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bea74-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="bea74-117">**増分更新を設定する** ダイアログ ボックスで、**設定** を選択して、**増分更新の設定** を開きます。</span><span class="sxs-lookup"><span data-stu-id="bea74-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="bea74-118">**スキップ** を選択すると、データソースがデータセット全体を更新します。</span><span class="sxs-lookup"><span data-stu-id="bea74-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="bea74-119">既存のデータ ソースを編集することで、増分更新を後から適用することも可能です。</span><span class="sxs-lookup"><span data-stu-id="bea74-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="bea74-120">**増分更新の設定** にて、データ ソースの作成時に選択したすべてのエンティティーの増分更新を構成します。</span><span class="sxs-lookup"><span data-stu-id="bea74-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bea74-121">![データソースのエンティティの増分更新を設定する](media/incremental-refresh-settings.png "データソースのエンティティの増分更新を設定する")</span><span class="sxs-lookup"><span data-stu-id="bea74-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="bea74-122">エンティティを選択し、次の詳細を指定します：</span><span class="sxs-lookup"><span data-stu-id="bea74-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="bea74-123">**主キーの設定**：エンティティまたはテーブルの主キーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bea74-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="bea74-124">**最終更新フィールドの設定**：このフィールドには、日付または時刻タイプの属性のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bea74-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="bea74-125">レコードが最後に更新された日時を示す属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="bea74-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="bea74-126">これは、増分更新概算時間枠内にあるレコードを識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bea74-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="bea74-127">**すべての更新を確認する**：増分更新の時間枠の長さを指定します。</span><span class="sxs-lookup"><span data-stu-id="bea74-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="bea74-128">**保存** を選択して、データ ソースの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="bea74-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="bea74-129">最初のデータ更新は全体の更新になります。</span><span class="sxs-lookup"><span data-stu-id="bea74-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="bea74-130">その後の更新からは、上記手順で設定したように増分の更新が行われます。</span><span class="sxs-lookup"><span data-stu-id="bea74-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
