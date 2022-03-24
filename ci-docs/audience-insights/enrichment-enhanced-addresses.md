---
title: アドレス エンハンスメント エンリッチメント (ビデオを含む)
description: Microsoft のモデルを使用して、顧客プロファイルの住所情報をエンリッチおよび正規化します。
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 2ab550e83a4969c1f547e66bcbf6ddb96d7789df
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376303"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>拡張住所による顧客プロファイルの強化

データ内のアドレスは、構造化されていない、不完全である、または正しくない可能性があります。 Microsoft のモデルを使用して、住所を [Common Data Model 形式](/common-data-model/schema/core/applicationcommon/address) に正規化およびエンリッチし、精度とインサイトを向上します。

また、[データ ソースのアドレスをエンリッチ](data-sources-enrichment.md) して、データ統合プロセスでの一致精度を向上させることもできます。 

## <a name="how-we-enhance-addresses"></a>住所の拡張方法

このモデルでは、住所を拡張するために 2 ステップのプロセスを行います。 まず、住所を解析してコンポーネントを特定し、それらを構造化された形式にします。 次に、AI を使用して、住所の値を修正して完成させ、標準化します。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

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

拡張住所は、取り込んだ住所データにすでに存在する値でのみ機能します。 モデルは以下を実行しません: 

1. 住所が有効な住所かどうかを確認する。
2. 郵便番号や番地名などの値が有効かどうかを確認する。
3. 認識しない値を変更する。

モデルは、機械学習ベースの手法を使用して住所を拡張します。 他の機械学習ベースのモデルと同様に、モデルが入力値を変更するときには信頼性の高いしきい値を適用しますが、100％ の精度は保証されません。

## <a name="supported-countries-or-regions"></a>サポートされている国または地域

現在、次の国または地域では、住所のエンリッチがサポートされています。 

- オーストラリア
- カナダ
- フランス
- ドイツ
- イタリア
- 日本
- イギリス
- 米国

住所には国/地域の値が含まれている必要があります。 サポートされていない国または地域の住所、および国または地域が指定されていない住所は処理されません。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. **データ** > **エンリッチメント** に移動します。

1. **データのエンリッチ** を **拡張住所** タイルで選択します。

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="拡張住所タイルのスクリーンショット。":::

1. **顧客データ セット** を選択して、エンリッチする住所を含むエンティティを選択します。 *顧客* エンティティを選択して、すべての顧客プロファイルの住所をエンリッチするか、セグメント エンティティを選択して、そのセグメントに含まれる顧客プロファイルのみ住所をエンリッチすることができます。

1. データ セットでの住所の形式を選択します。 **1 つの属性を持つ住所** は、データ内の住所が 1 つのフィールドを使用する場合に選択します。 **複数の属性を持つ住所** は、データ内の住所が複数のデータ フィールドを使用する場合に選択します。

   > [!NOTE]
   > 国/地域は、1 つの属性を持つ住所と複数の属性を持つ住所の両方で必須です。 有効またはサポート対象である国/地域の値を含まない住所はエンリッチされません。

1.  統合顧客エンティティから住所フィールドをマップします。

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="拡張住所フィールド マッピング ページ。":::

1. **次へ** を選択し、フィールド マッピングを完了します。

1. エンリッチメントと出力エンティティの名前を指定します。

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。

## <a name="enrichment-results"></a>強化の結果

エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。 [スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。 処理時間は、顧客データのサイズによって異なります。

エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイル データを確認できます。 さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。

エンリッチされたデータのサンプルは、**エンリッチされた顧客プレビュー** タイルで確認できます。 **さらに表示** を選択し、**データ** タブを選択して、エンリッチされた各プロファイルの詳細ビューにアクセスします。

### <a name="overview-card"></a>概要カード

概要カードには、エンリッチメントの対応範囲に関する詳細が表示されます。 

* **処理済かつ変更済の住所**: 正常にエンリッチされた住所を持つ顧客プロファイルの数。

* **処理済かつ未変更の住所**: 認識されているが変更されていない住所を持つ顧客プロファイルの数。 これは通常、入力データが有効で、エンリッチメントによって改善できない場合に起こります。

* **未処理かつ未変更の住所**: 認識されなかった住所を持つプロファイルの数。 通常は、エンリッチメントで無効またはサポートされていない入力データの場合です。

## <a name="next-steps"></a>次の手順

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
