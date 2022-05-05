---
title: データ ソース エンリッチメント
description: データ統合プロセスを実行する前に、データ ソースをエンリッチします。
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 56f6a8ad20224922f9968f0ad3b6a0e0a400214b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646574"
---
# <a name="enrichment-for-data-sources-preview"></a>データ ソースのエンリッチメント (プレビュー)

Microsoft や他のパートナーなどのソースからのデータを使用して、データ統合前に顧客データをエンリッチします。 データ ソース エンリッチメントは、データを統合するとより良い結果を達成するのに役立つ、より高いデータの完全性と品質を生み出すのに役立ちます。 たとえば、アドレスに正規化および標準化された形式を使用すると、一致結果の品質が向上します。 サポートされているエンリッチメントのリストについては、[サポートされているデータ ソース エンリッチメント オプション](#supported-data-source-enrichments) を参照してください。

## <a name="enrich-a-data-source"></a>データ ソースをエンリッチする

エンリッチメントを作成または編集するには、共同作成者または管理者権限が必要です。 詳細については、[権限](permissions.md)を参照してください。  

1. **データ** > **統合** に移動します。 エンリッチするエンティティを選択し、エンティティの主キーとして 1 つの属性を選択します。 詳細については、[主キーの選択](map-entities.md#select-primary-key-and-semantic-type-for-attributes) を参照してください。

1. **データ** > **データ ソース** にアクセスします。
 
1. エンリッチするデータ ソースの横にある垂直の省略記号を選択して、**エンリッチ** を選択します。

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="データ ソースのエンリッチメント ページ。":::

   **検出** タブに [サポートされているデータ ソース エンリッチメント オプション](#supported-data-source-enrichments) が表示されます。

1. **データのエンリッチ** を選択し、データ ソース エンリッチメントを構成します。 出力エンティティ名は自動的に設定されます。

## <a name="supported-data-source-enrichments"></a>サポートされているデータ ソース エンリッチメント

現在、データ ソースで次のエンリッチメントが使用可能です。 エンリッチメントの詳細な手順を確認して、エンリッチメントの構成方法を確認します。

- [拡張住所](enrichment-enhanced-addresses.md)
- [拡張された会社データ](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>既存のデータ ソース エンリッチメントを管理する

**自分のエンリッチメント** タブに移動し、構成されているすべてのエンリッチメントを表示します。

エンリッチメントを選択して、使用可能なオプションを確認します。 リスト項目の省略記号 (...) を選択して、オプションを表示することもできます。 複数のエンリッチメントを構成した場合は、検索ボックスを使用して簡単に見つけることができます。

データ ソース エンリッチメントを表示、編集、実行、または削除できます。 詳細については、[既存のエンリッチメントを管理する](enrichment-hub.md) を参照してください。
