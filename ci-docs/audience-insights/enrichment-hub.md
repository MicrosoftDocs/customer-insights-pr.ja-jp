---
title: 統合顧客プロファイルを強化する
description: 機能を使用して、顧客データを強化します。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305254"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="50dd9-103">顧客プロファイルを拡充させる (プレビュー版)</span><span class="sxs-lookup"><span data-stu-id="50dd9-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="50dd9-104">Microsoft やその他のパートナーなどのソースからのデータを使用して、顧客データを拡充させます。</span><span class="sxs-lookup"><span data-stu-id="50dd9-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="エンリッチメント ハブ ページ":::

<span data-ttu-id="50dd9-106">対象者に関するインサイトで、**データ** > **エンリッチメント** に移動し、エンリッチメント オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="50dd9-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="50dd9-107">エンリッチメントを作成、編集するには、コントリビューターまたは管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="50dd9-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="50dd9-108">詳細については、[権限](permissions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50dd9-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="50dd9-109">**検出** タブでは、次のような拡充機能があります :</span><span class="sxs-lookup"><span data-stu-id="50dd9-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="50dd9-110">Microsoft が提供する [ブランド](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="50dd9-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="50dd9-111">Microsoft が提供する [関心](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="50dd9-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="50dd9-112">Microsoft が提供する [拡張住所](enrichment-enhanced-addresses.md)</span><span class="sxs-lookup"><span data-stu-id="50dd9-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="50dd9-113">Leadspace が提供する [会社データ](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="50dd9-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="50dd9-114">Experian が提供する [人口統計情報](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="50dd9-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="50dd9-115">HERE Technologies が提供する [位置データ](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="50dd9-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="50dd9-116">セキュリティで保護されたファイル転送プロトコル (SFTP) による [カスタム データ](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="50dd9-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="50dd9-117">**自分のエンリッチメント** タブでは、設定した拡充を表示し、そのプロパティを編集することができます。</span><span class="sxs-lookup"><span data-stu-id="50dd9-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="50dd9-118">既存のエンリッチメントの管理</span><span class="sxs-lookup"><span data-stu-id="50dd9-118">Manage existing enrichments</span></span>

<span data-ttu-id="50dd9-119">**自分のエンリッチメント** タブに移動し、構成されているすべてのエンリッチメントを表示します。</span><span class="sxs-lookup"><span data-stu-id="50dd9-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="50dd9-120">各エンリッチメントは、エンリッチメントに関する追加情報を含む行として表されます。</span><span class="sxs-lookup"><span data-stu-id="50dd9-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="50dd9-121">エンリッチメントを選択して、利用可能なオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="50dd9-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="50dd9-122">リスト項目の省略記号 (...) を選択して、オプションを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="50dd9-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="エンリッチメントの一覧でエンリッチメントを管理するオプション":::

- <span data-ttu-id="50dd9-124">強化された顧客プロファイルの数を使用して、エンリッチメントの詳細を **表示** します。</span><span class="sxs-lookup"><span data-stu-id="50dd9-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="50dd9-125">エンリッチメント構成を **編集** します。</span><span class="sxs-lookup"><span data-stu-id="50dd9-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="50dd9-126">最新のデータで顧客プロファイルを更新するためのエンリッチメントを **実行** します。</span><span class="sxs-lookup"><span data-stu-id="50dd9-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="50dd9-127">既存のエンリッチメントを **非アクティブ化** して、スケジュールされた更新のたびに自動更新されないようにします。</span><span class="sxs-lookup"><span data-stu-id="50dd9-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="50dd9-128">最後に成功した更新のデータは引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="50dd9-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="50dd9-129">非アクティブなエンリッチメントを **活性化** し、スケジュールされた更新ごとに自動更新を再開します。</span><span class="sxs-lookup"><span data-stu-id="50dd9-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="50dd9-130">エンリッチメントを **削除** します。</span><span class="sxs-lookup"><span data-stu-id="50dd9-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="50dd9-131">リストで複数のエンリッチメントを選択して、一度に実行または非アクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="50dd9-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="50dd9-132">表示と編集のオプションは一括アクションとして使用できず、一度に 1 つのエンリッチメントに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="50dd9-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="50dd9-133">エンリッチメントと接続</span><span class="sxs-lookup"><span data-stu-id="50dd9-133">Enrichments and connections</span></span>

<span data-ttu-id="50dd9-134">サード パーティのエンリッチメントは、管理者が資格情報を使用して設定し、データ転送の同意を提供する [接続](connections.md) を使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="50dd9-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="50dd9-135">管理者と共同作成者は接続を使用して、エンリッチメントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="50dd9-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="50dd9-136">同じ種類の複数のエンリッチメント</span><span class="sxs-lookup"><span data-stu-id="50dd9-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="50dd9-137">強化されるエンティティは、エンリッチメントの構成中に指定され、プロファイルのサブセットのみを強化できます。</span><span class="sxs-lookup"><span data-stu-id="50dd9-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="50dd9-138">たとえば、特定のセグメントのデータのみをエンリッチします。</span><span class="sxs-lookup"><span data-stu-id="50dd9-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="50dd9-139">同じ種類の複数のエンリッチメントを構成し、同じ接続を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="50dd9-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="50dd9-140">一部のエンリッチメントには、作成できる同じ種類のエンリッチメントの数に制限があります。</span><span class="sxs-lookup"><span data-stu-id="50dd9-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="50dd9-141">制限と現在の使用状況は **エンリッチメント** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="50dd9-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
