---
title: 統合顧客プロファイルを強化する
description: 機能を使用して、顧客データを強化します。
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269474"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="08047-103">顧客プロファイルを拡充させる (プレビュー版)</span><span class="sxs-lookup"><span data-stu-id="08047-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="08047-104">Microsoft やその他のパートナーなどのソースからのデータを使用して、顧客データを拡充させます。</span><span class="sxs-lookup"><span data-stu-id="08047-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="エンリッチメント ハブ ページ":::

<span data-ttu-id="08047-106">対象者に関するインサイトで、**データ** > **エンリッチメント** に移動し、エンリッチメント オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="08047-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="08047-107">エンリッチメントを作成、編集するには、コントリビューターまたは管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="08047-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="08047-108">詳細については、[権限](permissions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08047-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="08047-109">**検出** タブでは、次のような拡充機能があります :</span><span class="sxs-lookup"><span data-stu-id="08047-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="08047-110">Microsoft Graph が提供する [ブランド](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="08047-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="08047-111">Microsoft Graph が提供する [関心](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="08047-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="08047-112">Leadspace が提供する [会社データ](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="08047-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="08047-113">Experian が提供する [人口統計](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="08047-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="08047-114">HERE Technologies が提供する [位置データ](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="08047-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="08047-115">セキュリティで保護されたファイル転送プロトコル (SFTP) による [カスタム データ](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="08047-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="08047-116">**自分のエンリッチメント** タブでは、設定した拡充を表示し、そのプロパティを編集することができます。</span><span class="sxs-lookup"><span data-stu-id="08047-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="08047-117">既存のエンリッチメントの管理</span><span class="sxs-lookup"><span data-stu-id="08047-117">Manage existing enrichments</span></span>

<span data-ttu-id="08047-118">**自分のエンリッチメント** に移動し、構成されたすべてのエンリッチメントを表示します。</span><span class="sxs-lookup"><span data-stu-id="08047-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="08047-119">各エンリッチメントは、エンリッチメントに関する追加情報を含む行として表されます。</span><span class="sxs-lookup"><span data-stu-id="08047-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="08047-120">エンリッチメントを選択して、利用可能なオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="08047-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="08047-121">または、リスト項目の省略記号 (...) を選択して、オプションを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="08047-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="エンリッチメントの一覧でエンリッチメントを管理するオプション":::

- <span data-ttu-id="08047-123">強化された顧客プロファイルの数を使用して、エンリッチメントの詳細を **表示** します。</span><span class="sxs-lookup"><span data-stu-id="08047-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="08047-124">エンリッチメント構成を **編集** します。</span><span class="sxs-lookup"><span data-stu-id="08047-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="08047-125">最新のデータで顧客プロファイルを更新するためのエンリッチメントを **実行** します。</span><span class="sxs-lookup"><span data-stu-id="08047-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="08047-126">既存のエンリッチメントを **非アクティブ化** して、スケジュールされた更新のたびに自動更新されないようにします。</span><span class="sxs-lookup"><span data-stu-id="08047-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="08047-127">最後に成功した更新のデータは引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="08047-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="08047-128">非アクティブなエンリッチメントを **活性化** し、スケジュールされた更新ごとに自動更新を再開します。</span><span class="sxs-lookup"><span data-stu-id="08047-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="08047-129">エンリッチメントを **削除** します。</span><span class="sxs-lookup"><span data-stu-id="08047-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="08047-130">リストで複数のエンリッチメントを選択して、一度に実行または非アクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="08047-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="08047-131">表示と編集のオプションは一括アクションとして使用できず、一度に 1 つのエンリッチメントに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="08047-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]