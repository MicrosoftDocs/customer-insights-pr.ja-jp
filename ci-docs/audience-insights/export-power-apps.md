---
title: Power Apps コネクタ
description: Power Apps と Power Automate に接続します。
ms.date: 10/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 985e6c85795fba8ca3063cdffc7f9012e798856a
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623229"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Appsコネクタ (プレビュー)

統合された顧客プロファイルを Power Apps でパーソナライズされたアプリに取り込みます。

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Apps と Dynamics 365 Customer Insights の接続

Customer Insights は、多くの [Power Apps でデータの利用可能なソース](/powerapps/maker/canvas-apps/working-with-data-sources) のうちの 1 つです。

Power Apps ドキュメントを参照して、[アプリにデータ接続を追加する](/powerapps/maker/canvas-apps/add-data-connection) 方法を学んでください。 また、[Power Apps が委任を使用し、キャンバス アプリで大規模なデータセットを処理する方法](/powerapps/maker/canvas-apps/delegation-overview) を確認することをお勧めします。

## <a name="available-entities"></a>使用可能なエンティティ

Customer Insights をデータ接続として追加した後、Power Apps で次のエンティティを選択できます。

- **顧客**: [統合された顧客プロファイル](customer-profiles.md)からのデータを使用します。
- **UnifiedActivity**: アプリで[活動のタイムライン](activities.md)を表示する場合。
- **ContactProfile**: 顧客の連絡先を表示する場合。 このエンティティは、ビジネス アカウントの対象者分析情報環境でのみ使用できます。

## <a name="limitations"></a>制限

### <a name="retrievable-entities"></a>取得可能なエンティティ

Power Apps コネクタ経由で取得できるのは、**Customer**、**UnifiedActivity**、**Segments**、および **ContactProfile** エンティティのみです。 ContactProfile は、ビジネス アカウントの対象者分析情報インスタンスでのみ使用できます。 その他のエンティティは、基礎となるコネクタが Power Automate のトリガーを介してサポートしているため、表示されています。

### <a name="delegation"></a>委任

委任は、**Customer** エンティティと **UnifiedActivity** エンティティで動作します。 

- **顧客** エンティティへの委任: このエンティティに委任を使用するには、[インデックスの検索およびフィルター処理](search-filter-index.md) でフィールドにインデックスを付ける必要があります。  
- **UnifiedActivity** の委任 : このエンティティに対する委任は、フィールド **ActivityId** と **CustomerId** に対してのみ機能します。  
- **ContactProfile** の委任: このエンティティの委任は、フィールド **ContactId** と **CustomerId** に対してのみ機能します。 ContactProfile は、ビジネス アカウントの対象者分析情報環境でのみ使用できます。

委任の詳細については、[Power Apps 委任可能な機能と操作](/powerapps/maker/canvas-apps/delegation-overview)にアクセスしてください。 

## <a name="example-gallery-control"></a>ギャラリー コントロールの例

顧客プロファイルを[ギャラリー コントロール](/powerapps/maker/canvas-apps/add-gallery)に追加できます。

1. **ギャラリー** コントロールを、構築しているアプリに追加します。

    > [!div class="mx-imgBorder"]
    > ![ギャラリー要素を追加する。](media/connector-powerapps9.png "ギャラリー要素を追加します。")

2. **顧客** をアイテムのデータ ソースとして選択します。

    > [!div class="mx-imgBorder"]
    > ![データ ソースを選択。](media/choose-datasource-powerapps.png "データ ソースを選択します。")

3. 右側のデータパネルを変更して、ギャラリーに表示する顧客エンティティのフィールドを選択できます。

4. 選択した顧客のフィールドをギャラリーに表示する場合は、**{Name_of_the_gallery}.Selected.{property_name}** を使って、ラベルの **テキスト** プロパティに入力します。  
    - 例: _Gallery1.Selected.address1_city_

5. 顧客の統合されたタイムラインを表示するには、ギャラリー要素を追加し、次の **項目** プロパティを追加します: **Filter ('UnifiedActivity', CustomerId = {Customer_Id})**  
    - 例: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE[footer-include](../includes/footer-banner.md)]
