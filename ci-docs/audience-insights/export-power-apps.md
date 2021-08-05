---
title: Power Apps コネクタ
description: Power Apps と Power Automate に接続します。
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 2ab5a9059991611a2959a19cc688d232ec782e1e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554119"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Appsコネクタ (プレビュー)

統合された顧客プロファイルを Power Apps でパーソナライズされたアプリに取り込みます。

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Apps と Dynamics 365 Customer Insights の接続

Customer Insights は、多くの [Power Apps でデータの利用可能なソース](/powerapps/maker/canvas-apps/working-with-data-sources) のうちの 1 つです。

Power Apps ドキュメントを参照して、[アプリにデータ接続を追加する](/powerapps/maker/canvas-apps/add-data-connection) 方法を学んでください。 また、[Power Apps が委任を使用し、キャンバス アプリで大規模なデータセットを処理する方法](/powerapps/maker/canvas-apps/delegation-overview) を確認することをお勧めします。

## <a name="available-entities"></a>使用可能なエンティティ

Customer Insights をデータ接続として追加した後、Power Apps で次のエンティティを選択できます。

- 顧客: [統合された顧客プロファイル](customer-profiles.md) からのデータを使用します。
- 統合された活動: アプリに[活動タイムライン](activities.md)を表示します。

## <a name="limitations"></a>制限

### <a name="retrievable-entities"></a>取得可能なエンティティ

取得できるのは Power Apps コネクタを介した **顧客**、**UnifiedActivity**、**セグメント** エンティティのみです。 その他のエンティティは、基礎となるコネクタが Power Automate のトリガーを介してサポートしているため、表示されています。  

### <a name="delegation"></a>委任

委任は、Customer エンティティと UnifiedActivity エンティティで動作します。 

- **顧客** エンティティへの委任: このエンティティに委任を使用するには、[インデックスの検索およびフィルター処理](search-filter-index.md) でフィールドにインデックスを付ける必要があります。  

- **UnifiedActivity** の委任 : このエンティティに対する委任は、フィールド **ActivityId** と **CustomerId** に対してのみ機能します。  

- 委任の詳細については、[Power Apps で委任可能な機能と操作](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps)を参照してください。 

## <a name="example-gallery-control"></a>ギャラリー コントロールの例

たとえば、顧客プロファイルを [ギャラリー コントロール](/powerapps/maker/canvas-apps/add-gallery) に追加します。

1. **ギャラリー** コントロールを、構築しているアプリに追加します。

> [!div class="mx-imgBorder"]
> ![ギャラリー要素を追加する。](media/connector-powerapps9.png "ギャラリー要素を追加する")

1. **顧客** をアイテムのデータ ソースとして選択します。

    > [!div class="mx-imgBorder"]
    > ![データ ソースを選択。](media/choose-datasource-powerapps.png "データ ソースを選択")

1. 右側のデータパネルを変更して、ギャラリーに表示する顧客エンティティのフィールドを選択できます。

1. 選択した顧客のフィールドをギャラリーに表示する場合は、次のラベルのテキスト プロパティを入力します : **{Name_of_the_gallery}。選択済み。{property_name}**

    例 : Gallery1.Selected.address1_city

1. 顧客の統合されたタイムラインを表示するには、ギャラリー要素を追加し、次の項目プロパティを追加します : **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    例 : Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]