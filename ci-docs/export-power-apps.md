---
title: Power Appsコネクタ (プレビュー)
description: Power Apps と Power Automate に接続します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196906"
---
# <a name="power-apps-connector-preview"></a>Power Appsコネクタ (プレビュー)

統合された顧客プロファイルを Microsoft Power Apps でパーソナライズされたアプリに取り込みます。

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Power Apps と Dynamics 365 Customer Insights の接続

Customer Insights は、多くの [Power Apps でデータの利用可能なソース](/powerapps/maker/canvas-apps/working-with-data-sources) のうちの 1 つです。

Power Apps ドキュメントを参照して、[アプリにデータ接続を追加する](/powerapps/maker/canvas-apps/add-data-connection) 方法を学んでください。 また、[Power Apps が委任を使用し、キャンバス アプリで大規模なデータセットを処理する方法](/powerapps/maker/canvas-apps/delegation-overview) を確認することをお勧めします。

## <a name="available-entities"></a>使用可能なエンティティ

Customer Insights をデータ接続として追加した後、Power Apps で次のエンティティを選択します。

- **顧客**: [統合された顧客プロファイル](customer-profiles.md)からのデータを使用します。
- **UnifiedActivity**: アプリで[活動のタイムライン](activities.md)を表示する場合。
- **ContactProfile**: 顧客の連絡先を表示する場合。 このエンティティは、ビジネス アカウントの Customer Insights 環境でのみ使用できます。

## <a name="limitations"></a>制限

### <a name="retrievable-entities"></a>取得可能なエンティティ

Power Apps コネクタ経由で取得できるのは、**Customer**、**UnifiedActivity**、**Segments**、および **ContactProfile** エンティティのみです。 ContactProfile は、ビジネス アカウントの Customer Insights 環境でのみ使用できます。 その他のエンティティは、基礎となるコネクタが Power Automate のトリガーを介してサポートしているため、表示されています。

60 秒あたり最大 100 回の呼び出しを実行できます。 $skip パラメーターを使用して、API エンドポイントを複数回呼び出すことができます。 [$skip パラメーターの詳細](/connectors/customerinsights/#get-items-from-an-entity)。

### <a name="delegation"></a>委任

委任は、**Customer** エンティティと **UnifiedActivity** エンティティで動作します。

- **顧客** エンティティへの委任: このエンティティに委任を使用するには、[インデックスの検索およびフィルター処理](search-filter-index.md) でフィールドにインデックスを付ける必要があります。  
- **UnifiedActivity** の委任 : このエンティティに対する委任は、フィールド **ActivityId** と **CustomerId** に対してのみ機能します。  
- **ContactProfile** の委任: このエンティティの委任は、フィールド **ContactId** と **CustomerId** に対してのみ機能します。 ContactProfile は、ビジネス アカウントの Customer Insights 環境でのみ使用できます。

委任の詳細については、[Power Apps 委任可能な機能と操作](/powerapps/maker/canvas-apps/delegation-overview)にアクセスしてください。

## <a name="example-gallery-control"></a>ギャラリー コントロールの例

オプションで、顧客プロファイルを[ギャラリー コントロール](/powerapps/maker/canvas-apps/add-gallery)に追加します。

1. **ギャラリー** コントロールを、構築しているアプリに追加します。
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="ギャラリー要素を追加する。":::

1. **顧客** をアイテムのデータ ソースとして選択します。

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="データ ソースを選択。":::

1. 右側のデータパネルを変更して、ギャラリーに表示する顧客エンティティのフィールドを選択します。

1. 選択した顧客のフィールドをギャラリーに表示する場合は、**{Name_of_the_gallery}.Selected.{property_name}** を使って、ラベルの **テキスト** プロパティに入力します。  
    - 例: _Gallery1.Selected.address1_city_

1. 顧客の統合されたタイムラインを表示するには、ギャラリー要素を追加し、次の **項目** プロパティを追加します: **Filter ('UnifiedActivity', CustomerId = {Customer_Id})**  
    - 例: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
