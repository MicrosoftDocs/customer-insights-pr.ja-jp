---
title: '顧客プロファイル: 検索とフィルターのインデックス'
description: 統一された顧客プロファイルに関する情報をすばやく検索し、指定された属性をフィルタ―します。
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: fc076e341f744ac2922dcacdf5f20ae8ecbdbaa0
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050815"
---
# <a name="customer-profiles-search--filter-index"></a>顧客プロファイル: 検索とフィルターのインデックス

顧客データを統合した結果は、顧客ベース全体に統一されたビューを提供する顧客プロファイル エンティティです。 迅速に [特定の顧客または顧客グループに関する情報を見つける](customer-profiles.md) には、**検索** と **フィルタ** 機能を **顧客** ページで構成できます。 ユーザーが検索とフィルタリングに使用できる **検索およびフィルター インデックス** ページを読んで、管理者がどのように属性を編集できるかを学んください。

   :::image type="content" source="media/search-filter.png" alt-text="検索フィルター":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>フィールドを追加して属性を指定する

検索可能な属性を管理者として初めて定義する場合、最初にインデックス付きフィールドを定義する必要があります。 **顧客** ページでユーザーが顧客を検索してフィルタ―できるすべての属性を選択することをお勧めします。 データ統合プロセス中に作成した Customer Profile エンティティに存在する属性のみを指定できます。

1. **顧客** ページを開き、**インデックスの検索とフィルター** を選択します。

2. **+ 追加** を選択して、インデックス フィールドを指定します。

3. インデックス付きフィールドとして追加するリスト内の属性を選択します。 **追加** を選択することで属性をいつでも追加できます。 また、選択した属性を削除するには、**削除** 記号を選択します。

## <a name="explore-the-indexed-customer-fields-table"></a>インデックス付き顧客フィールドのテーブルの説明

次の情報は、このテーブルにあります。

- **名前** : Customer Profile エンティティに表示される属性の名前を表します。
- **データの種類** : データ型が文字列、数値、または日付のいずれであるかを指定します。
- **検索に含まれる** : **顧客** ページで **検索** フィールドを使用して、この属性を使用して顧客の検索に使用できるかどうかを指定します。
- **フィルターを追加** : この属性が **顧客** ページでフィルタ―を使用できる方法を定義するコントロール。

## <a name="editing-filtering-options-for-a-given-attribute"></a>特定の属性のフィルタ―オプションの編集

**Customers** ページの **フィルタ―** メニューには、さまざまな数の属性レベル (たとえば、顧客をフィルターするためのさまざまな年齢グループ) を含めることができます。

1.  **検索およびフィルタ― インデックス** ページで特定の属性に対して **フィルタ―の追加** を選択します。 結果の数とそれらを整理する順序を定義できます。 属性のデータ型に応じて、次のウィンドウのいずれかが表示されます。

- 文字列タイプの属性： **文字列フィルター オプション** ウィンドウで希望する結果の数と、それらの結果を整理する順序のポリシーを指定します。

- 数値タイプの属性： **数値フィルター オプション** ウィンドウに含まれる間隔と、それらが整理される順序のポリシーを指定します。

- データタイプの属性： **データ フィルター オプション** ウィンドウに含まれる間隔と、それらを整理する順序のポリシーを指定します。

2. **保存** を選択して変更を適用します。

3. 設定を適用する準備ができたら **実行** を選択します。 変更が処理された後は、[顧客ページの顧客カード](customer-profiles.md)に表示されます。 

## <a name="next-steps"></a>次のステップ

[統一されたプロファイルのページ](customer-profiles.md)では、プロファイルを検索したり、インデックス付きのフィールドを使ってすべての統合プロファイルのサブセットを表示します。


[!INCLUDE [footer-include](includes/footer-banner.md)]
