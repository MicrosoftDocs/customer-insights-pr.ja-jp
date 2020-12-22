---
title: エンティティとデータセット
description: エンティティ ページにデータを表示します。
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406160"
---
# <a name="entities-in-audience-insights"></a>対象者に関するインサイトのエンティティ

[データソースの構成](data-sources.md) 後、**エンティティ** ページに移動して、取り込んだデータの品質を評価します。 エンティティはデータセットと見なされます。 Dynamics 365 Customer Insights の複数の機能は、これらのエンティティを中心に構築されています。 それらを綿密に確認すると、これらの機能の出力を検証するのに役立ちます。

**エンティティ** ページにはエンティティがリストされ、次のいくつかの列が含まれます。

- **名前**: プロジェクトの名前です。 エンティティ名の横に警告記号が表示されている場合、そのエンティティのデータが正常にロードされていないことを意味します。
- **ソース**: エンティティを取得したデータ ソースのタイプ
- **作成者** : エンティティを作成した人の名前
- **作成した**：エンティティ作成の日付と時刻
- **更新者** : エンティティを更新した人の名前
- **最終更新日** : エンティティを最後に更新した日付と時刻
- **最新情報に更新した日** : 最後に最新の情報に更新した日付と時刻

## <a name="exploring-a-specific-entitys-data"></a>特定エンティティのデータを調べる

エンティティを選択して、そのエンティティに含まれるさまざまなフィールドとレコードを調べます。

> [!div class="mx-imgBorder"]
> ![エンティティの選択](media/data-manager-entities-data.png "エンティティの選択")

- **データ** タブはデフォルトで選択されており、エンティティの個々のレコードに関する詳細をリストするテーブルを表示します。

> [!div class="mx-imgBorder"]
> ![フィールド テーブル](media/data-manager-entities-fields.PNG "フィールド テーブル")

- **フィールド** タブには、フィールド名、データ タイプ、種類など、選択したエンティティの詳細をレビューするためのテーブルが表示されます。 **種類** 列は、Common Data Model に関連した種類を表示し、これはシステムによって自動識別されるか、ユーザーによって[手動でマッピング](map-entities.md) されます。 これらは、属性のデータ型とは異なるセマンティック型です。たとえば、フィールド *メール* の下には、データ型 *テキスト* がありますが、その (セマンティック型の) Common Data Model の種類は、*メール* または *メールアドレス* である場合があります。

> [!NOTE]
> 両方のテーブルには、エンティティのデータのサンプルのみが表示されます。 完全なデータセットを表示するには、**データ ソース** ページに移動して、エンティティを選択し、**編集** を選択して、その後[データ ソース](data-sources.md) で説明した通り、このエンティティのデータを Power Query エディターで表示します。

エンティティに取り込まれたデータの詳細については、**概要** 列は、データに適用可能なヌル、欠損値、一意の値、カウント、分布など、データの重要な特性を提供します。

グラフ アイコンを選択して、データの概要を表示します。

> [!div class="mx-imgBorder"]
> ![概要記号](media/data-manager-entities-summary.png "データ概要テーブル")

### <a name="next-step"></a>次の手順

[統一](data-unification.md) トピックで、取り込んだデータを *マップ*、*一致*、そして *マージ* する方法をご覧ください。
