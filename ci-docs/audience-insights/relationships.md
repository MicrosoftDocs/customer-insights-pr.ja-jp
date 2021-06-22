---
title: エンティティとエンティティ パスの関連付け
description: 複数のデータ ソースからエンティティ間の関連付けを作成および管理します。
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171170"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="72fb3-103">エンティティ間の関連付け</span><span class="sxs-lookup"><span data-stu-id="72fb3-103">Relationships between entities</span></span>

<span data-ttu-id="72fb3-104">関連付けは、エンティティを結びつけ、エンティティが共通の識別子である外部キーを共有する場合にデータのグラフを定義します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="72fb3-105">この外部キーは、あるエンティティから別のエンティティへ参照することができます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="72fb3-106">接続されたエンティティにより、複数のデータ ソースに基づいたセグメントとメジャーの定義が可能になります。</span><span class="sxs-lookup"><span data-stu-id="72fb3-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="72fb3-107">関連付けには次の 3 つのタイプがあります:</span><span class="sxs-lookup"><span data-stu-id="72fb3-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="72fb3-108">編集不可能なシステム定義の関連付け、データの統合プロセスの一部としてシステムによって作成</span><span class="sxs-lookup"><span data-stu-id="72fb3-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="72fb3-109">編集不可能な継承された関連付け、データ ソースの取り込みから自動的に作成</span><span class="sxs-lookup"><span data-stu-id="72fb3-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="72fb3-110">編集可能なユーザー定義の関連付け、ユーザーが作成および構成</span><span class="sxs-lookup"><span data-stu-id="72fb3-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="72fb3-111">編集不可能なシステム定義の関連付け</span><span class="sxs-lookup"><span data-stu-id="72fb3-111">Non-editable system relationships</span></span>

<span data-ttu-id="72fb3-112">データの統合時に、システム定義の関連付けがインテリジェント マッチングに基づいて自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="72fb3-113">これらの関連付けは、顧客プロファイル レコードを対応するレコードと関連付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="72fb3-114">次の図は、3 つのシステム ベースの関連付けの作成を示しています。</span><span class="sxs-lookup"><span data-stu-id="72fb3-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="72fb3-115">顧客エンティティは他のエンティティと照合され、統合された *Customer* エンティティを生成します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="3 つの 1-n の関連付けを持つ顧客エンティティの関係パスの図。":::

- <span data-ttu-id="72fb3-117">***CustomerToContact* の関連付け** は、*Customer* エンティティと *Contact* エンティティとの間に作成されました。</span><span class="sxs-lookup"><span data-stu-id="72fb3-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="72fb3-118">*Customer* エンティティはキー フィールド **Contact_contactID** を取得し、*Contact* エンティティのキー フィールド **contactID** に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="72fb3-119">***CustomerToAccount* の関連付け** が、*Customer* エンティティと *Account* エンティティの間に作成されました。</span><span class="sxs-lookup"><span data-stu-id="72fb3-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="72fb3-120">*Customer* エンティティは、キー フィールド **Account_accountID** を取得し、*Account* エンティティのキー フィールド **accountID** と関連付けます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="72fb3-121">***CustomerToWebAccount* の関連付け** が、*Customer* エンティティと *WebAccount* エンティティとの間に作成されました。</span><span class="sxs-lookup"><span data-stu-id="72fb3-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="72fb3-122">*Customer* エンティティは、キー フィールド **WebAccount_webaccountID** を取得し、*WebAccount* エンティティのキー フィールド **webaccountID** と関連付けます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="72fb3-123">編集不可能な継承された関連付け</span><span class="sxs-lookup"><span data-stu-id="72fb3-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="72fb3-124">データ取り込みプロセス時に、システムは既存の関連付けについてデータ ソースを確認します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="72fb3-125">関連付けが存在しない場合、システムが自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="72fb3-126">これらの関連付けは、下流プロセスでも使用されます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="72fb3-127">ユーザー定義の関連付けの作成</span><span class="sxs-lookup"><span data-stu-id="72fb3-127">Create a custom relationship</span></span>

<span data-ttu-id="72fb3-128">関連付けは、外部キーを含む *ソース エンティティ* と ソース エンティティの外部キーが指す *対象エンティティ* で構成されます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="72fb3-129">対象者に関するインサイトで、**データ** > **関連付け** に移動します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="72fb3-130">**新規リレーションシップ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="72fb3-131">**新しい関連付け** ペインで以下の情報を入力します:</span><span class="sxs-lookup"><span data-stu-id="72fb3-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="空の入力フィールドを持つ新しい関連付けサイド ペイン。":::

   - <span data-ttu-id="72fb3-133">**関連付け名**: 関連付けの目的を反映する名前。</span><span class="sxs-lookup"><span data-stu-id="72fb3-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="72fb3-134">例: CustomerToSupportCase。</span><span class="sxs-lookup"><span data-stu-id="72fb3-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="72fb3-135">**説明**: リレーションシップの説明。</span><span class="sxs-lookup"><span data-stu-id="72fb3-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="72fb3-136">**ソース エンティティ**: 関連付けのソースとして使用されるエンティティ。</span><span class="sxs-lookup"><span data-stu-id="72fb3-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="72fb3-137">例: SupportCase。</span><span class="sxs-lookup"><span data-stu-id="72fb3-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="72fb3-138">**対象エンティティ**: 関連付けの対象として使用されるエンティティ。</span><span class="sxs-lookup"><span data-stu-id="72fb3-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="72fb3-139">例: Customer。</span><span class="sxs-lookup"><span data-stu-id="72fb3-139">Example: Customer.</span></span>
   - <span data-ttu-id="72fb3-140">**ソースの基数**: ソース エンティティの基数を指定します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="72fb3-141">基数は、セット内の可能な要素の数を表します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="72fb3-142">常に対象の基数に関連します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="72fb3-143">**一** と **多** から選択できます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="72fb3-144">多対一および一対一のリレーションシップのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="72fb3-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="72fb3-145">多対一: 複数のソース レコードを 1 つの対象レコードに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="72fb3-146">例: 1 人の顧客からの複数のサポート案件。</span><span class="sxs-lookup"><span data-stu-id="72fb3-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="72fb3-147">一対一: 1 つのソース レコードが、1 つの対象レコードに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="72fb3-148">例: 1 人の顧客に対して 1 つのロイヤルティ ID。</span><span class="sxs-lookup"><span data-stu-id="72fb3-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="72fb3-149">多対多の関連付けは、2 つの多対一の関連付けと、ソース エンティティと対象エンティティを接続するリンク エンティティを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="72fb3-150">**ターゲット基数** : ターゲット エンティティ レコードの基数を選択します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="72fb3-151">**ソース キー フィールド**: ソース エンティティの外部キー フィールド。</span><span class="sxs-lookup"><span data-stu-id="72fb3-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="72fb3-152">例: SupportCase は CaseID を外部キー フィールドとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="72fb3-153">**ターゲット キー フィールド**: 対象エンティティのキー フィールド。</span><span class="sxs-lookup"><span data-stu-id="72fb3-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="72fb3-154">例 Customer は **CustomerID** キー フィールドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="72fb3-155">**保存** を選択して、ユーザー定義の関連付けを作成します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="72fb3-156">関連付けの表示</span><span class="sxs-lookup"><span data-stu-id="72fb3-156">View relationships</span></span>

<span data-ttu-id="72fb3-157">関連付けページには、作成されたすべての関連付けが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="72fb3-158">各行は関係を表し、ソース エンティティ、対象エンティティ、基数の詳細も含まれます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="関連付けページのアクション バーにある関係とオプションの一覧。":::

<span data-ttu-id="72fb3-160">このページには、既存および新規の関連付けに対する一連のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="72fb3-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="72fb3-161">**新しい関連付け**: [ユーザー定義の関連付けの作成](#create-a-custom-relationship)。</span><span class="sxs-lookup"><span data-stu-id="72fb3-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="72fb3-162">**ビジュアライザー**: [関連ビジュアライザーを確認](#explore-the-relationship-visualizer) して、既存の関連付けとその基数のネットワーク図を表示します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="72fb3-163">**フィルター**: 一覧に表示する関連付けの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="72fb3-164">**関係の検索**: 関連付けのプロパティでテキスト ベースの検索を使用します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="72fb3-165">関連ビジュアライザーの確認</span><span class="sxs-lookup"><span data-stu-id="72fb3-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="72fb3-166">関連ビジュアライザーは、接続されたエンティティ間の既存の関連付けとその基数のネットワーク図を示します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="72fb3-167">ビューをカスタマイズするには、ボックスをキャンバス上でドラッグして、位置を変更します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="関連するエンティティ間のつながりを含む関連ビジュアライザーのネットワーク図のスクリーンショット。":::

<span data-ttu-id="72fb3-169">使用できるオプション:</span><span class="sxs-lookup"><span data-stu-id="72fb3-169">Available options:</span></span> 
- <span data-ttu-id="72fb3-170">**画像としてエクスポート**: 現在のビューを画像ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="72fb3-171">**水平/垂直レイアウトに変更**: エンティティと関連付けの配置を変更します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="72fb3-172">**編集**: 編集ペインでユーザー定義の関連付けのプロパティを更新し、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="72fb3-173">既存の関連付けの管理</span><span class="sxs-lookup"><span data-stu-id="72fb3-173">Manage existing relationships</span></span> 

<span data-ttu-id="72fb3-174">関連付けページでは、各関係は行で表されます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="72fb3-175">関係を選択し、次のオプションのいずれかを選択します:</span><span class="sxs-lookup"><span data-stu-id="72fb3-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="72fb3-176">**編集**: 編集ペインでユーザー定義の関連付けのプロパティを更新し、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="72fb3-177">**削除**: ユーザー定義の関連付けを削除します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="72fb3-178">**表示**: システムで作成および継承された関連付けを表示します。</span><span class="sxs-lookup"><span data-stu-id="72fb3-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="72fb3-179">次のステップ</span><span class="sxs-lookup"><span data-stu-id="72fb3-179">Next step</span></span>

<span data-ttu-id="72fb3-180">システムとユーザー定義の関連付けは、サイロ化されなくなった複数のデータ ソースに基づいて [セグメントを作成](segments.md) するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="72fb3-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
