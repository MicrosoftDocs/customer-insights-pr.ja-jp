---
title: データ統合のためにエンティティをマップする
description: データをマップして、統合顧客プロファイルを作成します。
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406186"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="2b497-103">エンティティおよび属性のマッピング</span><span class="sxs-lookup"><span data-stu-id="2b497-103">Map entities and attributes</span></span>

<span data-ttu-id="2b497-104">**マップ** は、対象者に関するインサイトのデータ統合プロセスの最初のステージです。</span><span class="sxs-lookup"><span data-stu-id="2b497-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="2b497-105">マッピングは次の 3 つのフェーズから構成されます。</span><span class="sxs-lookup"><span data-stu-id="2b497-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="2b497-106">*エンティティの選択* : データセットにつながる組み合わせ可能なエンティティを特定し、顧客に関するより完全な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2b497-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="2b497-107">*属性選択* : 各エンティティについて、*一致* そして *マージ* フェーズで結合し、照合する列を決定します。</span><span class="sxs-lookup"><span data-stu-id="2b497-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="2b497-108">これらの列は、*属性* と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2b497-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="2b497-109">*主キーとセマンティック タイプの選択*: 各エンティティについて、そのエンティティの主キーとして定義する属性を特定し、各属性について、その属性を最もよく表すセマンティック タイプを特定します。</span><span class="sxs-lookup"><span data-stu-id="2b497-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="2b497-110">データ統合の一般的な流れの詳細については、[統合する](data-unification.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b497-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="2b497-111">最初のエンティティを選択する</span><span class="sxs-lookup"><span data-stu-id="2b497-111">Select the first entities</span></span>

1. <span data-ttu-id="2b497-112">対象者に関するインサイトで、**データ** > **統合** > **マップ** に移動します。</span><span class="sxs-lookup"><span data-stu-id="2b497-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="2b497-113">**エンティティの選択** を選択してマップ フェーズを開始します。</span><span class="sxs-lookup"><span data-stu-id="2b497-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="2b497-114">*一致* フェーズや *マージ* フェーズで使用するエンティティと属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b497-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="2b497-115">エンティティから必要な属性を個別に選択するか、エンティティレベルの　**すべてのフィールドを含める** チェックボックスを選択して、エンティティからすべての属性を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2b497-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="2b497-116">データ統合プロセスの恩恵を受けるには、少なくとも 2 つのエンティティを選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b497-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2b497-117">![エンティティの追加の例](media/data-manager-configure-map-add-entities-example.png "エンティティの追加の例")</span><span class="sxs-lookup"><span data-stu-id="2b497-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="2b497-118">この例では、**eCommerceContacts** エンティティや **loyCustomers** エンティティを追加しています。</span><span class="sxs-lookup"><span data-stu-id="2b497-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="2b497-119">これらのエンティティを選択することにより、どのオンライン ビジネス顧客がロイヤルティ プログラム メンバーであるかに関するインサイトを引き出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2b497-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="2b497-120">すべての属性およびエンティティ全体でキーワードを検索して、マップする必要な属性を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2b497-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2b497-121">![検索フィールドの例](media/data-manager-configure-map-search-fields-example.png "検索フィールドの例")</span><span class="sxs-lookup"><span data-stu-id="2b497-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="2b497-122">**適用** を選択して、選択を確認します。</span><span class="sxs-lookup"><span data-stu-id="2b497-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="2b497-123">属性の主キーとセマンティック タイプを選択します</span><span class="sxs-lookup"><span data-stu-id="2b497-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="2b497-124">エンティティを選択した後、**マップ** ページには、レビュー用に選択したエンティティが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b497-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="2b497-125">エンティティの主キーを定義し、エンティティの属性のセマンティック タイプを識別します。</span><span class="sxs-lookup"><span data-stu-id="2b497-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="2b497-126">**主キー** : 各エンティティの主キーとして 1 つの属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b497-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="2b497-127">属性を有効な主キーにするには、重複する値、欠落している値、または null 値を含めないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b497-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="2b497-128">文字列、整数、GUID データ型属性は主キーとしてサポートされており、フィールドに表示されて選択できます。</span><span class="sxs-lookup"><span data-stu-id="2b497-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="2b497-129">**属性セマンティックの種類**: メールアドレスや名前などの属性のカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="2b497-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="2b497-130">セマンティクスのスマートな予測に AI モデルを使用し、時間を節約して、精度を向上させるには、**インテリジェント マッピング** を **オン** に設定します。</span><span class="sxs-lookup"><span data-stu-id="2b497-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="2b497-131">インテリジェント マッピングは、**種類** フィールドでの AI ベースのセマンティクスの推奨事項を強調します。</span><span class="sxs-lookup"><span data-stu-id="2b497-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="2b497-132">**オフ** に設定した場合、定期的なマッピングの推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b497-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="2b497-133">使用可能なオプションのリストから任意のセマンティック タイプを選択し、提案された選択を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="2b497-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2b497-134">![属性の種類とセマンティック予測](media/data-manager-configure-map-add-attributes-semantic-prediction.png "属性の種類とセマンティック予測")</span><span class="sxs-lookup"><span data-stu-id="2b497-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="2b497-135">ユーザー定義セマンティック タイプを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b497-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="2b497-136">その属性の種類フィールドを選択し、カスタムのセマンティック タイプの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2b497-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="2b497-137">これにより、システムによって識別された属性の種類を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b497-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="2b497-138">セマンティック タイプが自動的に識別されるすべての属性は、**マップされたフィールドをレビューする** セクションでグループ化します。</span><span class="sxs-lookup"><span data-stu-id="2b497-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="2b497-139">これらの属性は、データ統合のマージ ステップでエンティティを組み合わせるために使用されるため、これらの属性とセマンティック タイプを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2b497-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="2b497-140">セマンティック タイプに自動的にマッピングされない属性は、**マップされていないフィールドにデータを定義する** セクションでグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="2b497-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="2b497-141">マップされていない属性のセマンティック タイプ フィールドを選択するか、カスタム属性タイプ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2b497-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2b497-142">![主キーと属性の種類](media/data-manager-configure-map-add-attributes.png "主キーと属性の種類")</span><span class="sxs-lookup"><span data-stu-id="2b497-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="2b497-143">顧客カードに顧客名を入力するために、1 つのフィールドをセマンティック タイプの Person.FullName にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b497-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="2b497-144">そうでない場合、顧客カードは名前が表示されません。</span><span class="sxs-lookup"><span data-stu-id="2b497-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="2b497-145">属性とエンティティを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="2b497-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="2b497-146">**統一** > **マップ** で、**フィールドの編集** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b497-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="2b497-147">**フィールドの編集** ペインで、属性とエンティティを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="2b497-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="2b497-148">検索またはスクロールを使用して、目的の属性とエンティティを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="2b497-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="2b497-149">属性またはエンティティが既に一致している場合、それらを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="2b497-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2b497-150">![属性の追加または削除](media/configure-data-map-edit.png "属性の追加または削除")</span><span class="sxs-lookup"><span data-stu-id="2b497-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="2b497-151">**適用** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b497-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="2b497-152">プロファイルに画像を追加する</span><span class="sxs-lookup"><span data-stu-id="2b497-152">Add images to profiles</span></span>

<span data-ttu-id="2b497-153">エンティティに公開されているプロフィール画像またはロゴへの URL が含まれている場合は、それらを統合カスタマー プロファイルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="2b497-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="2b497-154">エンティティを選択し、プロフィール画像への URL を含むフィールドを見つけます。</span><span class="sxs-lookup"><span data-stu-id="2b497-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="2b497-155">**種類** の入力フィールドに、手動で次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="2b497-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="2b497-156">人の場合: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="2b497-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="2b497-157">組織の場合: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="2b497-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="2b497-158">統合手順を続け、画像 URL を含む属性が [マージ](merge-entities.md) 手順にも追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2b497-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="2b497-159">組織の属性を設定する</span><span class="sxs-lookup"><span data-stu-id="2b497-159">Set attributes for organizations</span></span>

<span data-ttu-id="2b497-160">組織 (プレビュー) については、属性の種類は "Organization.Name" にマッピングする必要があります</span><span class="sxs-lookup"><span data-stu-id="2b497-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="2b497-161">![主キーと属性の種類 B2B](media/configure-data-map-edit-b2b.png "主キーと属性の種類 B2B")</span><span class="sxs-lookup"><span data-stu-id="2b497-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="2b497-162">次の手順</span><span class="sxs-lookup"><span data-stu-id="2b497-162">Next step</span></span>

<span data-ttu-id="2b497-163">データ統合プロセスの一環として、**一致**　ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="2b497-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="2b497-164">[**一致**](match-entities.md) に移動して、このフェーズについて学習します。</span><span class="sxs-lookup"><span data-stu-id="2b497-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="2b497-165">[はじめに : 統合された顧客プロファイルの作成](https://youtu.be/oBfGEhucAxs) のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2b497-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>
