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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896011"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="da609-103">顧客プロファイルを拡充させる (プレビュー版)</span><span class="sxs-lookup"><span data-stu-id="da609-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="da609-104">Microsoft やその他のパートナーなどのソースからのデータを使用して、顧客データを拡充させます。</span><span class="sxs-lookup"><span data-stu-id="da609-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="エンリッチメント ハブ ページ":::

<span data-ttu-id="da609-106">対象者に関するインサイトで、**データ** > **エンリッチメント** に移動し、エンリッチメント オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="da609-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="da609-107">エンリッチメントを作成、編集するには、コントリビューターまたは管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="da609-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="da609-108">詳細については、[権限](permissions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da609-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="da609-109">**検出** タブでは、次のような拡充機能があります :</span><span class="sxs-lookup"><span data-stu-id="da609-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="da609-110">Microsoft が提供する [ブランド](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="da609-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="da609-111">Microsoft が提供する [関心](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="da609-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="da609-112">Leadspace が提供する [会社データ](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="da609-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="da609-113">Experian が提供する [人口統計](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="da609-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="da609-114">HERE Technologies が提供する [位置データ](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="da609-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="da609-115">セキュリティで保護されたファイル転送プロトコル (SFTP) による [カスタム データ](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="da609-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="da609-116">**自分のエンリッチメント** タブでは、設定した拡充を表示し、そのプロパティを編集することができます。</span><span class="sxs-lookup"><span data-stu-id="da609-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="da609-117">既存のエンリッチメントの管理</span><span class="sxs-lookup"><span data-stu-id="da609-117">Manage existing enrichments</span></span>

<span data-ttu-id="da609-118">**自分のエンリッチメント** に移動し、構成されたすべてのエンリッチメントを表示します。</span><span class="sxs-lookup"><span data-stu-id="da609-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="da609-119">各エンリッチメントは、エンリッチメントに関する追加情報を含む行として表されます。</span><span class="sxs-lookup"><span data-stu-id="da609-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="da609-120">エンリッチメントを選択して、利用可能なオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="da609-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="da609-121">リスト項目の省略記号 (...) を選択して、オプションを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="da609-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="エンリッチメントの一覧でエンリッチメントを管理するオプション":::

- <span data-ttu-id="da609-123">強化された顧客プロファイルの数を使用して、エンリッチメントの詳細を **表示** します。</span><span class="sxs-lookup"><span data-stu-id="da609-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="da609-124">エンリッチメント構成を **編集** します。</span><span class="sxs-lookup"><span data-stu-id="da609-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="da609-125">最新のデータで顧客プロファイルを更新するためのエンリッチメントを **実行** します。</span><span class="sxs-lookup"><span data-stu-id="da609-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="da609-126">既存のエンリッチメントを **非アクティブ化** して、スケジュールされた更新のたびに自動更新されないようにします。</span><span class="sxs-lookup"><span data-stu-id="da609-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="da609-127">最後に成功した更新のデータは引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="da609-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="da609-128">非アクティブなエンリッチメントを **活性化** し、スケジュールされた更新ごとに自動更新を再開します。</span><span class="sxs-lookup"><span data-stu-id="da609-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="da609-129">エンリッチメントを **削除** します。</span><span class="sxs-lookup"><span data-stu-id="da609-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="da609-130">リストで複数のエンリッチメントを選択して、一度に実行または非アクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="da609-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="da609-131">表示と編集のオプションは一括アクションとして使用できず、一度に 1 つのエンリッチメントに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="da609-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="da609-132">エンリッチメントと接続</span><span class="sxs-lookup"><span data-stu-id="da609-132">Enrichments and connections</span></span>

<span data-ttu-id="da609-133">サード パーティのエンリッチメントは、管理者が資格情報を使用して設定し、データ転送の同意を提供する [接続](connections.md) を使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="da609-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="da609-134">管理者と共同作成者は接続を使用して、エンリッチメントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="da609-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="da609-135">同じ種類の複数のエンリッチメント</span><span class="sxs-lookup"><span data-stu-id="da609-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="da609-136">強化されるエンティティは、エンリッチメントの構成中に指定され、プロファイルのサブセットのみを強化できます。</span><span class="sxs-lookup"><span data-stu-id="da609-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="da609-137">たとえば、特定のセグメントのデータのみを強化します。</span><span class="sxs-lookup"><span data-stu-id="da609-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="da609-138">同じ種類の複数のエンリッチメントを構成し、同じ接続を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="da609-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="da609-139">一部のエンリッチメントには、作成できる同じ種類のエンリッチメントの数に制限があります。</span><span class="sxs-lookup"><span data-stu-id="da609-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="da609-140">制限と現在の使用状況は **エンリッチメント** ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="da609-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
