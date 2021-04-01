---
title: エンティティとエンティティ パスの関連付け
description: 複数のデータ ソースからエンティティ間の関連付けを作成および管理します。
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595218"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="fb393-103">エンティティ間の関連付け</span><span class="sxs-lookup"><span data-stu-id="fb393-103">Relationships between entities</span></span>

<span data-ttu-id="fb393-104">リレーションシップは、エンティティを接続して、あるエンティティから別のエンティティに参照できる共通の識別子 (外部キー) をエンティティが共有する場合に、データのグラフを生成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fb393-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="fb393-105">接続されたエンティティにより、複数のデータ ソースに基づいてセグメントとメジャーが定義できるようになります。</span><span class="sxs-lookup"><span data-stu-id="fb393-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="fb393-106">リレーションシップには 2 種類あります。</span><span class="sxs-lookup"><span data-stu-id="fb393-106">There are two types of relationships.</span></span> <span data-ttu-id="fb393-107">自動的に作成される編集不可のシステムリレーションシップ、およびユーザーが作成および構成するカスタム リレーションシップです。</span><span class="sxs-lookup"><span data-stu-id="fb393-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="fb393-108">一致プロセスおよびマージ プロセス中に、裏でシステム リレーションシップがインテリジェント マッチングに基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="fb393-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="fb393-109">これらのリレーションシップは、顧客プロファイル レコードを他の対応するエンティティのレコードと関連付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fb393-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="fb393-110">次の図は、顧客エンティティが追加のエンティティと一致され最終的な顧客プロファイル エンティティを生成する場合に、3 つのシステム リレーションシップの作成を示しています。</span><span class="sxs-lookup"><span data-stu-id="fb393-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fb393-111">![リレーションシップ の作成](media/relationships-entities-merge.png "リレーションシップ の作成")</span><span class="sxs-lookup"><span data-stu-id="fb393-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="fb393-112">***CustomerToContact* リレーションシップ** は、顧客エンティティと取引先担当者エンティティとの間に作成されました。</span><span class="sxs-lookup"><span data-stu-id="fb393-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="fb393-113">顧客エンティティはキー フィールド **Contact_contactId** を、取引先担当者エンティティのキー フィールド **contactId** と関連付けます。</span><span class="sxs-lookup"><span data-stu-id="fb393-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="fb393-114">***CustomerToAccount* リレーションシップ** が、顧客エンティティと取引先企業エンティティとの間に作成されました。</span><span class="sxs-lookup"><span data-stu-id="fb393-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="fb393-115">顧客エンティティは、キー フィールド **Account_accountId** を、取引先企業エンティティのキー フィールド **accountId** と関連付けます。</span><span class="sxs-lookup"><span data-stu-id="fb393-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="fb393-116">***CustomerToWebAccount* リレーションシップ** が、顧客エンティティと WebAccount エンティティとの間に作成されました。</span><span class="sxs-lookup"><span data-stu-id="fb393-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="fb393-117">顧客エンティティは、キー フィールド **WebAccount_webaccountId** を、WebAccount エンティティのキー フィールド **webaccountId** と関連付けます。</span><span class="sxs-lookup"><span data-stu-id="fb393-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="fb393-118">関連付けの作成</span><span class="sxs-lookup"><span data-stu-id="fb393-118">Create a relationship</span></span>

<span data-ttu-id="fb393-119">**リレーションシップ** ページでカスタム リレーションシップを定義します。</span><span class="sxs-lookup"><span data-stu-id="fb393-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="fb393-120">それぞれの関連付けは、ソース エンティティ (外部キーを保持するエンティティ) とターゲット エンティティ (ソース エンティティの外部キーが指すエンティティ) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="fb393-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="fb393-121">対象者に関するインサイトで、**データ** > **関連付け** に移動します。</span><span class="sxs-lookup"><span data-stu-id="fb393-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="fb393-122">**新規リレーションシップ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb393-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="fb393-123">**新規リレーションシップ** ウィンドウで以下の情報を入力します :</span><span class="sxs-lookup"><span data-stu-id="fb393-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb393-124">![レコメンデーションの詳細を入力します](media/relationships-add.png "レコメンデーション詳細の入力")</span><span class="sxs-lookup"><span data-stu-id="fb393-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="fb393-125">**関係名**: 関係の目的を反映した名前（たとえば、**AccountWebLogs**）。</span><span class="sxs-lookup"><span data-stu-id="fb393-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="fb393-126">**説明**: リレーションシップの説明。</span><span class="sxs-lookup"><span data-stu-id="fb393-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="fb393-127">**ソース エンティティ** : リレーションシップのソースとして使用されるエンティティ (WebLog など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb393-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="fb393-128">**基数** : ソース エンティティ レコードの基数を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb393-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="fb393-129">たとえば、"多く" とは、複数の Weblog レコードが 1 つの WebAccount に関連付けられていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fb393-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="fb393-130">**ソース キー フィールド** : これは、ソース エンティティの外部キー フィールドを表します。</span><span class="sxs-lookup"><span data-stu-id="fb393-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="fb393-131">たとえば、WebLog には **accountId** 外部キー フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="fb393-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="fb393-132">**ターゲット エンティティ** : リレーションシップのターゲットとして使用されるエンティティ (WebLog など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb393-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="fb393-133">**ターゲット基数** : ターゲット エンティティ レコードの基数を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb393-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="fb393-134">たとえば、"1" とは、複数の Weblog レコードが 1 つの WebAccount に関連付けられていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fb393-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="fb393-135">**ターゲット キー フィールド** : このフィールドは、ターゲット エンティティのキー フィールドを表します。</span><span class="sxs-lookup"><span data-stu-id="fb393-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="fb393-136">たとえば、WebAccount には **accountId** キー フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="fb393-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="fb393-137">多対一および一対一のリレーションシップのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fb393-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="fb393-138">多対多のリレーションシップは、2 つの多対一のリレーションシップとリンク エンティティ (ソースエンティティとターゲットエンティティを接続するために使用されるエンティティ) を使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="fb393-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="fb393-139">リレーションシップの削除</span><span class="sxs-lookup"><span data-stu-id="fb393-139">Delete a relationship</span></span>

1. <span data-ttu-id="fb393-140">対象者に関するインサイトで、**データ** > **関連付け** に移動します。</span><span class="sxs-lookup"><span data-stu-id="fb393-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="fb393-141">削除するリレーションシップのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="fb393-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="fb393-142">**リレーションシップ** テーブルの上部にある **削除** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb393-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="fb393-143">削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="fb393-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="fb393-144">次の手順</span><span class="sxs-lookup"><span data-stu-id="fb393-144">Next step</span></span>

<span data-ttu-id="fb393-145">システムとカスタム リレーションシップは、サイロ化されなくなった複数のデータ ソースに基づいてセグメントを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb393-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="fb393-146">詳細については、[セグメント](segments.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb393-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]