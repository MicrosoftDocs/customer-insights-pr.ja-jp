---
title: 会社データの拡張
description: Microsoft のモデルを使用して、会社のデータをエンリッチし、正規化します。
ms.date: 11/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9bfb96d47de4ec98325e644c60752fc7cab2706c
ms.sourcegitcommit: 6efcba688d1db1a5d6343c229f292a26c48fc007
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2021
ms.locfileid: "7770176"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>強化された会社データで会社プロファイルのエンリッチメント

Microsoftの モデルとコンパイルされた会社データを使用して、会社のプロファイルを修正、補足、および標準化します。 より正確で、分析情報のために、[Common Data Model 形式](/common-data-model/schema/core/applicationcommon/account) を使用します。

## <a name="how-we-enhance-company-data"></a>会社データを拡張する方法

モデルは、会社プロファイルを強化する 2 つのステップからなるプロセスを実行します。 まず、会社名を正規化します。 例えば、*Microsoft Corp* は修正され、*Microsoft Corporation* に標準化されます。 Microsoft のコンパイルされた会社データで、一致するものを見つけようとします。 一致するものが見つかった場合、会社名など、コンパイルされた会社データからの情報で会社プロファイルをエンリッチします。


### <a name="example"></a>例

会社情報が標準化された形式に準拠しておらず、スペル エラーが含まれている可能性があります。 モデルはこれらの問題を修正し、一貫した情報を作成しようとします。

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>制限

強化されたデータにはいくつかの制限があります。 以下のリストの項目は、モデルでサポートされていません。

1.  会社の ID を確認します。 入力が既存の組織であるかどうか、または会社が標準名として出力を使用しているかどうかは確認しません。
2.  世界中の会社を包括的にカバーします。 Microsoft のコンパイルされた会社データはグローバルなカバーがありますが、オーストラリア、カナダ、英国、および米国でほとんどのカバーを提供しています。
3.  データの正確性または鮮度を保証します。 ビジネス情報は頻繁に変更されるため、提供される強化された会社データが常に正確または最新であることを保証することはできません。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. **データ** > **エンリッチメント** に移動します。

1. **強化された会社データ** タイルで、**データのエンリッチ** を選択します。

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="会社データのエンリッチメント ハブのエンリッチメント タイル。":::

1. **顧客データ セット** を選択して、エンリッチする住所を含むエンティティを選択します。 *顧客* エンティティを選択して、すべての顧客プロファイルの住所をエンリッチするか、セグメント エンティティを選択して、そのセグメントに含まれる顧客プロファイルのみ住所をエンリッチすることができます。

1. 会社のプロファイルから、Microsoft のコンパイルされた会社データとの照合に使用するフィールドのタイプを選択します。 この選択は、次の手順でアクセスできるマッピング フィールドに影響します。

1.  統合された顧客エンティティから会社フィールドをマップします。 マップするキー識別子とフィールドが多いほど、一致率が高くなる可能性が高くなります。

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="会社のエンリッチメントを構成する場合のデータ マッピング手順。":::

1. **次へ** を選択し、フィールド マッピングを完了します。

1. エンリッチメントと出力エンティティの名前を指定します。

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。

## <a name="enrichment-results"></a>強化の結果

エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。 [スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。 処理時間は、顧客データのサイズによって異なります。

エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイル データを確認できます。 さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。

**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。

## <a name="next-steps"></a>次のステップ

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
