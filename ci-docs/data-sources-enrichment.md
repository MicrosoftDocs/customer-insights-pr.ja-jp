---
title: データ ソースのエンリッチメント (プレビュー)
description: データ統合プロセスを実行する前に、データ ソースをエンリッチします。
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207189"
---
# <a name="enrichment-for-data-sources-preview"></a>データ ソースのエンリッチメント (プレビュー)

Microsoft や他のパートナーなどのソースからのデータを使用して、データ統合前に顧客データをエンリッチします。 データ ソース エンリッチメントは、データを統合するとより良い結果を達成するのに役立つ、より高いデータの完全性と品質を生み出すのに役立ちます。 たとえば、アドレスに正規化および標準化された形式を使用すると、一致結果の品質が向上します。 サポートされているエンリッチメントのリストについては、[サポートされているデータ ソース エンリッチメント オプション](#supported-data-source-enrichments) を参照してください。

## <a name="enrich-a-data-source"></a>データ ソースをエンリッチする

エンリッチメントを作成または編集するには、共同作成者または管理者[権限](permissions.md) が必要です。  

1. **データ** > **統合** に移動します。 エンリッチするエンティティを選択し、エンティティの[主キー](map-entities.md#select-primary-key-and-semantic-type-for-attributes)として 1 つの属性を選択します。

1. **データ** > **データ ソース** にアクセスします。

1. エンリッチするデータ ソースの横にある垂直の省略記号 (&vellip;) を選択して、**エンリッチ** を選択します。

   :::image type="content" source="media/data_sources_enrich.png" alt-text="エンリッチが強調表示されたデータ ソース ページ":::

   **検出** タブに [サポートされているデータ ソース エンリッチメント オプション](#supported-data-source-enrichments) が表示されます。

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="データ ソースのエンリッチメント ページ。":::

1. **データのエンリッチ** を選択し、データ ソース エンリッチメントを構成します。 出力エンティティ名は自動的に設定されます。

## <a name="supported-data-source-enrichments"></a>サポートされているデータ ソース エンリッチメント

現在、データ ソースで次のエンリッチメントが使用可能です。 エンリッチメントの詳細な手順を確認して、エンリッチメントの構成方法を確認します。

- [拡張住所](enrichment-enhanced-addresses.md)
- [拡張された会社データ](enrichment-enhanced-company-data.md)
- [LiveRamp による ID データ](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>既存のデータ ソース エンリッチメントを管理する

**データ** > **エンリッチメント** に移動します。 **自分のエンリッチメント** タブに、構成されたエンリッチメント、それらのステータス、エンリッチされた顧客の数、およびデータが最後に更新された時刻が表示されます。 エンリッチメントのリストを任意の列で並べ替えたり、検索ボックスを使用して管理するエンリッチメントを検索したりできます。

エンリッチメントを選択して、使用可能なオプションを確認します。 また、リスト項目の垂直省略記号 (&vellip;) を選択しても、オプションを表示できます。

データ ソース エンリッチメントを表示、編集、実行、または削除できます。 詳細については、[既存のエンリッチメントを管理する](enrichment-hub.md#manage-existing-enrichments) を参照してください。
