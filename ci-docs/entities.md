---
title: Customer Insights のエンティティ
description: エンティティ ページにデータを表示します。
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610104"
---
# <a name="entities-in-customer-insights"></a>Customer Insights のエンティティ

[データソースの構成](data-sources.md) 後、**エンティティ** ページに移動して、取り込んだデータの品質を評価します。 エンティティはデータセットと見なされます。 Dynamics 365 Customer Insights の複数の機能は、これらのエンティティを中心に構築されています。 それらを綿密に確認すると、これらの機能の出力を検証するのに役立ちます。

Customer Insights でデータをエンリッチさせたり、セグメント、メジャー、アクティビティを作成したりすると、これらのアクションから作成されたエンティティが **エンティティ** ページに表示されます。

## <a name="view-a-list-of-entities"></a>エンティティのリストの表示

**データ** > **エンティティ** に移動し、エンティティのリストを表示します。 次の情報がエンティティごとに表示されます。

- **名前**: データ エンティティの名前。 エンティティ名の横に警告記号が表示されている場合、そのエンティティのデータが正常にロードされていないことを意味します。
- **ソース**: エンティティを取り込んだデータ ソースの種類。
- **更新済み**: エンティティが最後に更新された時刻。
- **状態**: エンティティの最終更新に関する詳細。

## <a name="explore-a-specific-entitys-data"></a>特定エンティティのデータを調べる

1. **データ** > **エンティティ** に移動します。
1. エンティティを選択して、詳細ページを開きます。  
1. そのエンティティ向けに含まれるさまざまなフィールドとレコードを調べます。

- **属性** タブは既定で選択されており、フィールド名、データ型、種類など、選択したエンティティの詳細が表示されます。 **種類** 列は、Common Data Model に関連した種類を表示し、これはシステムによって自動識別されるか、ユーザーによって[手動でマッピング](map-entities.md) されます。 これらの型は、属性のデータ型とは異なる意味的な型です。 たとえば、以下のフィールド *メール* はデータ型が *文字列* ですが、その (意味的な) 共通データモデルの型は *Email*、*EmailAddress*、または *Identity.Service.Email* かもしれません。

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="フィールド テーブル。":::

   > [!NOTE]
   > このページには、エンティティのデータのサンプルのみが表示されます。 完全なデータセットを表示するには、**データ ソース** ページに移動して、エンティティを選択し、**編集** を選択して、その後[データ ソース](data-sources.md) で説明した通り、このエンティティのデータを Power Query エディターで表示します。

   エンティティに取り込まれたデータの詳細については、**概要** 列は、何であれデータに適用可能なヌル、欠損値、一意の値、カウント、分布など、重要なデータ特性を提供します。 グラフ アイコンを選択して、データの概要を表示します。

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="データ概要テーブル。":::

- **データ** タブには、エンティティの個々のレコードに関する詳細が表示されます。 リストされる詳細は、エンティティのデータ型によって異なります。

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="エンティティを選択します。":::

- **レポート** タブ (一部のエンティティで使用可能) を使用すると、レポートを作成してデータを視覚化でき、次の列が含まれます。

  - **レポート名**: レポートの名前。
  - **作成者**: エンティティを作成した人の名前。
  - **作成済み**: エンティティ作成の日付と時刻。
  - **編集者**: エンティティを変更した人の名前。
  - **編集済み**: エンティティ変更の日付と時刻。

[!INCLUDE [footer-include](includes/footer-banner.md)]
