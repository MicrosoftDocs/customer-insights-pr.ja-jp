---
title: 住所拡張エンリッチメント
description: Microsoft のモデルを使用して、顧客プロファイルの住所情報をエンリッチおよび正規化します。
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965584"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>拡張住所による顧客プロファイルの強化

データ内のアドレスは、構造化されていない、不完全である、または正しくない可能性があります。 Microsoft のモデルを使用して、住所を [Common Data Model 形式](/common-data-model/schema/core/applicationcommon/address) に正規化およびエンリッチし、精度とインサイトを向上します。

## <a name="how-we-enhance-addresses"></a>住所の拡張方法

このモデルでは、住所を拡張するために 2 ステップのプロセスを行います。 まず、住所を解析してコンポーネントを識別し、構造化された形式にします。 次に、人工知能を使用して、住所の値を修正、補完、標準化します。

### <a name="example"></a>例

住所情報が非標準形式であり、スペルミスが含まれている可能性があります。 モデルでは、これらの問題を修正し、統合顧客プロファイルに一貫のある住所を作成できます。

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>制限

拡張住所は、取り込んだ住所データにすでに存在する値でのみ機能します。 モデルには、以下は含まれません: 

1. 住所が有効な住所であるかどうかを確認する。
2. 郵便番号や町名などの値のいずれかが有効かどうかを確認する。
3. 認識できない値を変更する。

モデルは、機械学習ベースの手法を使用して住所を拡張します。 ML ベースのモデルと同様に、モデルが入力値を変更するときに高い信頼性のしきい値を適用しますが、100% の精度は保証されません。

## <a name="supported-countries-or-regions"></a>サポートされている国または地域

現在、次の国または地域で住所のエンリッチ化をサポートしています: 

- オーストラリア
- カナダ
- イギリス
- 米国

住所には、国/地域の値が含まれている必要があります。 サポートされていない国または地域の住所、および国または地域が指定されていない住所は処理されません。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. **データ** > **エンリッチメント** に移動します。

1. **データのエンリッチ** を **拡張住所** タイルで選択します。

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="拡張住所タイルのスクリーンショット。":::

1. **顧客データ セット** を選択して、エンリッチする住所を含むエンティティを選択します。 *顧客* エンティティを選択して、すべての顧客プロファイルの住所をエンリッチするか、セグメント エンティティを選択して、そのセグメントに含まれる顧客プロファイルのみ住所をエンリッチすることができます。

1. データ セットでの住所の形式を選択します。 **1 つの属性を持つ住所** は、データ内の住所が 1 つのフィールドを使用する場合に選択します。 **複数の属性を持つ住所** は、データ内の住所が複数のデータ フィールドを使用する場合に選択します。

   > [!NOTE]
   > 国/地域は、1 つの属性を持つ住所と複数の属性を持つ住所の両方で必須です。 有効またはサポート対象の国/地域の値を含まない住所はエンリッチされません

1.  統合顧客エンティティから住所フィールドをマップします。

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="拡張住所フィールド マッピング ページ。":::

1. **次へ** を選択し、フィールド マッピングを完了します。

1. エンリッチメントと出力エンティティの名前を指定します。

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。

## <a name="enrichment-results"></a>強化の結果

エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。 [スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。 処理時間は、顧客データのサイズによって異なります。

エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイル データを確認できます。 さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。

**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。

## <a name="next-steps"></a>次の手順

エンリッチされた顧客データの上に構築します。 [セグメント](segments.md)、[メジャー](measures.md) を作成し、[データをエクスポート](export-destinations.md) して、顧客にパーソナライズされたエクスペリエンスを提供します。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
