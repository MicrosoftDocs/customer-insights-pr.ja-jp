---
title: エンティティとエンティティ パスの関連付け
description: 複数のデータ ソースからエンティティ間の関連付けを作成および管理します。
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: e622e5fa0b5738e31db1c668d95312adbc4f7d36
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183569"
---
# <a name="relationships-between-entities-and-entity-paths"></a>エンティティとエンティティ パスの関連付け

関連付けは、エンティティを結びつけ、エンティティが共通の識別子である外部キーを共有する場合にデータのグラフを定義します。 この外部キーは、あるエンティティから別のエンティティへ参照することができます。 接続されたエンティティにより、複数のデータ ソースに基づいたセグメントとメジャーの定義が可能になります。

関連付けには次の 3 つのタイプがあります: 
- 編集不可能なシステム定義の関連付け、データの統合プロセスの一部としてシステムによって作成
- 編集不可能な継承された関連付け、データ ソースの取り込みから自動的に作成
- 編集可能なユーザー定義の関連付け、ユーザーが作成および構成

## <a name="non-editable-system-relationships"></a>編集不可能なシステム定義の関連付け

データの統合時に、システム定義の関連付けがインテリジェント マッチングに基づいて自動的に作成されます。 これらの関連付けは、顧客プロファイル レコードを対応するレコードと関連付けるのに役立ちます。 次の図は、3 つのシステム ベースの関連付けの作成を示しています。 顧客エンティティは他のエンティティと照合され、統合された *Customer* エンティティを生成します。

:::image type="content" source="media/relationships-entities-merge.png" alt-text="3 つの 1-n の関連付けを持つ顧客エンティティの関係パスの図。":::

- ***CustomerToContact* の関連付け** は、*Customer* エンティティと *Contact* エンティティとの間に作成されました。 *Customer* エンティティはキー フィールド **Contact_contactID** を取得し、*Contact* エンティティのキー フィールド **contactID** に関連付けます。
- ***CustomerToAccount* の関連付け** が、*Customer* エンティティと *Account* エンティティの間に作成されました。 *Customer* エンティティは、キー フィールド **Account_accountID** を取得し、*Account* エンティティのキー フィールド **accountID** と関連付けます。
- ***CustomerToWebAccount* の関連付け** が、*Customer* エンティティと *WebAccount* エンティティとの間に作成されました。 *Customer* エンティティは、キー フィールド **WebAccount_webaccountID** を取得し、*WebAccount* エンティティのキー フィールド **webaccountID** と関連付けます。

## <a name="non-editable-inherited-relationships"></a>編集不可能な継承された関連付け

データ取り込みプロセス時に、システムは既存の関連付けについてデータ ソースを確認します。 関連付けが存在しない場合、システムが自動的に作成します。 これらの関連付けは、下流プロセスでも使用されます。

## <a name="create-a-custom-relationship"></a>ユーザー定義の関連付けの作成

関連付けは、外部キーを含む *ソース エンティティ* と ソース エンティティの外部キーが指す *対象エンティティ* で構成されます。 

1. **データ** > **リレーションシップ** に移動します。

2. **新規リレーションシップ** を選択します。

3. **新しい関連付け** ペインで以下の情報を入力します:

   :::image type="content" source="media/relationship-add.png" alt-text="空の入力フィールドを持つ新しい関連付けサイド ペイン。":::

   - **関連付け名**: 関連付けの目的を反映する名前。 例: CustomerToSupportCase。
   - **説明**: リレーションシップの説明。
   - **ソース エンティティ**: 関連付けのソースとして使用されるエンティティ。 例: SupportCase。
   - **対象エンティティ**: 関連付けの対象として使用されるエンティティ。 例: Customer。
   - **ソースの基数**: ソース エンティティの基数。 基数は、セット内の可能な要素の数を表します。 常に対象の基数に関連します。 **一** と **多** から選択できます。 多対一および一対一のリレーションシップのみがサポートされています。  
     - 多対一: 複数のソース レコードを 1 つの対象レコードに関連付けることができます。 例: 1 人の顧客からの複数のサポート案件。
     - 一対一: 1 つのソース レコードが、1 つの対象レコードに関連付けられます。 例: 1 人の顧客に対して 1 つのロイヤルティ ID。

     > [!NOTE]
     > 多対多の関連付けは、2 つの多対一の関連付けと、ソース エンティティと対象エンティティを接続するリンク エンティティを使用して作成できます。

   - **ターゲット基数** : ターゲット エンティティ レコードの基数。
   - **ソース キー フィールド**: ソース エンティティの外部キー フィールド。 例: SupportCase は **CaseID** を外部キー フィールドとして使用します。
   - **ターゲット キー フィールド**: 対象エンティティのキー フィールド。 例: Customer は **CustomerID** をキー フィールドとして使用します。

4. **保存** を選択して、ユーザー定義の関連付けを作成します。

## <a name="set-up-account-hierarchies"></a>アカウントの階層を設定する

ビジネス アカウントをプライマリ ターゲット対象ユーザーとして使用するように構成された環境は、関連するビジネス アカウントのアカウント階層を構成できます。 たとえば、別々の部署を持つ会社です。

組織はアカウント階層を作成して、アカウントとそのリレーションシップをお互い適切に管理します。 Customer Insights は、取り込んだ顧客データにすでに存在する親子アカウント階層をサポートします。 たとえば、Dynamics 365 Sales のアカウントです。 これらの階層は、**リレーションシップ** ページで構成できます。

1. **データ** > **リレーションシップ** に移動します。
1. **アカウント階層** タブを選択します。
1. **新しいアカウント階層** を選択します。
1. **アカウント階層** ペインで、階層の名前を指定します。 システムは出力エンティティの名前を作成しますが、変更することができます。
1. アカウント階層を含むエンティティを選択します。 通常、アカウントを含むエンティティと同じエンティティにあります。
1. 選択したエンティティから **Account UID** と **Parent UID** を選択します。
1. **保存** を選択してアカウント階層を完成させます。

## <a name="manage-existing-relationships"></a>既存の関連付けの管理

**リレーションシップ** ページに移動し、作成されたすべてのリレーションシップ、そのソース エンティティ、ターゲット エンティティ、および基数を表示するページ。

:::image type="content" source="media/relationships-list.png" alt-text="関連付けページのアクション バーにある関係とオプションの一覧。":::

特定のリレーションシップを見つけるための **フィルター** または **リレーションシップを検索** オプション。 既存の関連付けとその基数のネットワーク図を表示するには、[**ビジュアライザー**](#explore-the-relationship-visualizer) を選択します。

リレーションシップを選択して、使用可能なアクションを表示できます。
- **編集**: 編集ペインでユーザー定義の関連付けのプロパティを更新し、変更を保存します。
- **削除**: ユーザー定義の関連付けを削除します。
- **表示**: システムで作成および継承された関連付けを表示します。

### <a name="explore-the-relationship-visualizer"></a>関連ビジュアライザーの確認

関連ビジュアライザーは、接続されたエンティティ間の既存の関連付けとその基数のネットワーク図を示します。 また、リレーションシップ パスを視覚化します。

:::image type="content" source="media/relationship-visualizer.png" alt-text="関連するエンティティ間のつながりを含む関連ビジュアライザーのネットワーク図のスクリーンショット。":::

ビューをカスタマイズするには、ボックスをキャンバス上でドラッグして、位置を変更します。 次のオプションがあります。 
- **画像としてエクスポート**: 現在のビューを画像ファイルとして保存します。
- **水平/垂直レイアウトに変更**: エンティティと関連付けの配置を変更します。
- **編集**: 編集ペインでユーザー定義の関連付けのプロパティを更新し、変更を保存します。

## <a name="relationship-paths"></a>関連付けパス

関連付けパスは、ソース エンティティとターゲット エンティティの間の関係で結ばれたエンティティを記述します。 統合プロファイル エンティティ以外のエンティティを含むセグメント、またはメジャーを作成し、統一されたプロファイル エンティティに到達する複数のオプションがある場合に使用されます。 リレーションシップ パスが異なれば、結果も異なる可能性があります。

エンティティ *eCommerce_eCommercePurchases* は、統合プロファイルの *顧客* エンティティと以下の関係にあります:

- eCommerce_eCommercePurchases > 顧客
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > 顧客
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > 顧客

関連付けパスは、メジャーやセグメントのルールを作成する際に、どのエンティティを使用するかを決定します。 一致するレコードがすべてのエンティティの一部である必要があるため、最も長いリレーションシップ パスを持つオプションを選択すると、結果が少なくなる可能性があります。 この例では、顧客は電子商取引 (eCommerce_eCommercePurchases) を通じて販売時点管理 (POS_posPurchases) で商品を購入し、当社のロイヤルティ プログラム (loyaltyScheme_loyCustomers) に参加する必要があります。 1 つ目のオプションを選択した場合、顧客は 1 つの追加されたエンティティに存在するだけでよいため、より多くの結果を得られる可能性があります。

### <a name="direct-relationship"></a>直接的な関連付け

ソース エンティティーがターゲット エンティティーと 1 つの関連付けだけで関連している場合、その関係は **直接的な関連付け** に分類されます。

たとえば、*eCommerce_eCommercePurchases* という活動エンティティが *ContactId* のみでターゲット エンティティ *eCommerce_eCommerceContacts* のエンティティに接続している場合、これは直接的な関連付けです。

:::image type="content" source="media/direct_Relationship.png" alt-text="ソース エンティティはターゲット エンティティに直接的に接続します。":::

#### <a name="multi-path-relationship"></a>複数パスの関連付け

**マルチパスの関連付け** は、ソース エンティティを複数のターゲット エンティティに接続する特別なタイプの直接的な関連付けです。

たとえば、*eCommerce_eCommercePurchases* という活動エンティティが、*eCommerce_eCommerceContacts* と *loyaltyScheme_loyCustomers* という 2 つのターゲット エンティティに関係している場合、それはマルチパスの関連付けです。

:::image type="content" source="media/multi-path_relationship.png" alt-text="ソース エンティティは、マルチホップの関連付けを介して複数のターゲット エンティティに直接的に接続します。":::

### <a name="indirect-relationship"></a>間接的な関連付け

ソース エンティティーがターゲット エンティティーに関連付けられる前に、1 つまたは複数の追加エンティティーに関係する場合、その関係性は **間接的な関連付け** に分類されます。

#### <a name="multi-hop-relationship"></a>複数ホップの関連付け

**マルチホップ関係** は、ソース エンティティとターゲット エンティティを、1 つ以上の他の仲介エンティティを介して接続することができる *間接的な関連付け* です。

たとえば、*eCommerce_eCommercePurchasesWest* という活動エンティティが *eCommerce_eCommercePurchasesEast* という中間エンティティに接続し、さらに *eCommerce_eCommerceContacts* というターゲット エンティティに接続した場合、それはマルチホップの関連付けです。

:::image type="content" source="media/multi-hop_relationship.png" alt-text="ソース エンティティが、中間エンティティを使用してターゲット エンティティに直接的に接続している。":::

### <a name="multi-hop-multi-path-relationship"></a>複数ホップ、複数パスの関連付け

複数ホップと複数パスの関連付けを一緒に使用して **複数ホップの関連付け、複数パスの関連付け** を作成できます。 この特殊なタイプは、**複数ホップ** と **複数パスの関連付け** の機能を兼ね備えています。 中間エンティティを使用しながら、複数のターゲット エンティティに接続できます。

*eCommerce_eCommercePurchasesWest* という活動エンティティが *eCommerce_eCommercePurchasesEast* という中間エンティティに接続し、さらに *eCommerce_eCommerceContacts* と *loyaltyScheme_loyCustomers* という 2 つのターゲット エンティティに接続した場合、これは複数ホップ、複数パスの関連付けとなります。

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="ソース エンティティは 1 つのターゲット エンティティに直接的に接続し、中間エンティティを介して別のターゲット エンティティに接続します。":::

## <a name="next-step"></a>次のステップ

システムやカスタムの関連付けを利用して、サイロ化から解き放たれた複数のデータソースに基づいて [セグメントの作成](segments.md) と [対策](measures.md) を行います。

[!INCLUDE [footer-include](includes/footer-banner.md)]
