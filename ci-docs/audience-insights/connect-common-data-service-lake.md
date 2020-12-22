---
title: Common Data Service が管理するレイク内のエンティティへの接続
description: Common Data Service が管理する  Data Lake からデータをインポートする。
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643404"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="24757-103">Common Data Service の管理された Data Lake に接続する</span><span class="sxs-lookup"><span data-stu-id="24757-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="24757-104">この記事では、既存の Dynamics 365 のお客様が Common Data Service マネージド レイクの分析エンティティに素早く接続する方法をご紹介します。</span><span class="sxs-lookup"><span data-stu-id="24757-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="24757-105">これを進めるには、 Common Data Service 組織の管理者で、マネージド レイクで利用可能なエンティティのリストを見る還元が付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="24757-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="24757-106">重要な考慮事項</span><span class="sxs-lookup"><span data-stu-id="24757-106">Important considerations</span></span>

<span data-ttu-id="24757-107">Azure Data Lake Storage などのオンライン サービスに保存されるデータは、Dynamics 365 Customer Insights で処理や保存される場所とは異なる場所に保存される場合があります。</span><span class="sxs-lookup"><span data-stu-id="24757-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="24757-108">  オンライン サービスに保存されているデータをインポート、あるいは接続することで、 Dynamics 365 Customer Insights にデータの転送と保存がされることに同意するものとします。詳細については、 [Microsoft Trust Center](https://www.microsoft.com/trust-center) をご覧ください</span><span class="sxs-lookup"><span data-stu-id="24757-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="24757-109">Common Data Service マネージド レイクに接続する</span><span class="sxs-lookup"><span data-stu-id="24757-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="24757-110">対象者に関するインサイトで、**データ** > **データ ソース** に移動します。</span><span class="sxs-lookup"><span data-stu-id="24757-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="24757-111">**データソースの追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="24757-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="24757-112">**Common Data Serviceに接続する** を選択し、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="24757-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="24757-113">データソースの **名前** を入力し、 **次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="24757-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="24757-114">Common Data Service 組織の **サーバーアドレス** を入力し、**サイン イン** を選択します。</span><span class="sxs-lookup"><span data-stu-id="24757-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="24757-115">![Common Data Service のサーバーアドレスを入力するダイアログ ボックス](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="24757-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="24757-116">使用可能な一覧から取り込むエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="24757-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="24757-117">一部のエンティティが既に選択されている場合、それらは他の Dynamics 365 アプリケーション（Dynamics 365 Sales Insights や Customer Service Insights など）によって使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="24757-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="24757-118">この選択を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="24757-118">You can't change the selection.</span></span> <span data-ttu-id="24757-119">これらのエンティティは、データ ソースが作成されると利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="24757-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="24757-120">![組織のエンティティ リストを表示するダイアログ ボックスCommon Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="24757-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="24757-121">選択を保存して、選択したエンティティを Common Data Service マネージド レイクへの同期を開始します。</span><span class="sxs-lookup"><span data-stu-id="24757-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="24757-122">新しく追加された接続は、**データソース** ページで確認することができます。</span><span class="sxs-lookup"><span data-stu-id="24757-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="24757-123">すべてのエンティティが同期されるまでは、更新のキューに入れられ、エンティティの件数が 0 と表示されます。</span><span class="sxs-lookup"><span data-stu-id="24757-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="24757-124">環境のデータ ソース は 1 つだけで、同じ Common Data Service が管理するレイクを同時に使用できます。</span><span class="sxs-lookup"><span data-stu-id="24757-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="24757-125">Common Data Service マネージド レイク データ ソースを編集する</span><span class="sxs-lookup"><span data-stu-id="24757-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="24757-126">データ ソースを作成した後に、エンティティの選択を編集します。</span><span class="sxs-lookup"><span data-stu-id="24757-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="24757-127">例えば、Common Data Service に追加のエンティティが追加されており、これらもインポートしたいとします。</span><span class="sxs-lookup"><span data-stu-id="24757-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="24757-128">異なる Common Data Service に接続するには、[新規データ ソースを作成します](#connect-to-a-common-data-service-managed-lake)。</span><span class="sxs-lookup"><span data-stu-id="24757-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="24757-129">対象者に関するインサイトで、**データ** > **データ ソース** に移動します。</span><span class="sxs-lookup"><span data-stu-id="24757-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="24757-130">更新を行うデータ ソースの横にある省略記号を選択します。</span><span class="sxs-lookup"><span data-stu-id="24757-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="24757-131">リストから **編集** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="24757-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="24757-132">使用可能なエンティティのリストから追加するエンティティを選択し、**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="24757-132">Select additional entities from the available list of entities and select **Save**.</span></span>
