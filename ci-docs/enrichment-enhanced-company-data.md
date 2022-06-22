---
title: 会社データの拡張
description: Microsoft のモデルを使用して、会社のデータをエンリッチし、正規化します。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4247d59806468907d93fc7848231ec5a2985580e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953955"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>強化された会社データで会社プロファイルのエンリッチメント

Microsoftの モデルとコンパイルされた会社データを使用して、会社のプロファイルを修正、補足、および標準化します。 より正確で、分析情報のために、[Common Data Model 形式](/common-data-model/schema/core/applicationcommon/account) を使用します。

また、[データ ソースの会社データを拡張](data-sources-enrichment.md) して、データ統合プロセスでの一致精度を向上させることもできます。

米国の公開企業については、収益、株式相場表示、業界などの情報を利用できます。  

## <a name="how-we-enhance-company-data"></a>会社データを拡張する方法

モデルは、会社プロファイルを強化する 2 つのステップからなるプロセスを実行します。 まず、会社名を正規化します。 例えば、*Microsoft Corp* は修正され、*Microsoft Corporation* に標準化されます。 Microsoft のコンパイルされた会社データで、一致するものを見つけようとします。 一致するものが見つかった場合、会社名など、コンパイルされた会社データからの情報で会社プロファイルをエンリッチします。

### <a name="example"></a>例

会社情報が標準化された形式に準拠しておらず、スペル エラーが含まれている可能性があります。 モデルはこれらの問題を修正し、一貫した情報を作成します。

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

モデルは以下を実行しません:

- 会社の ID を確認します。 入力が既存の組織であるかどうか、または会社が標準名として出力を使用しているかどうかは確認しません。
- 世界中の会社を包括的にカバーします。 Microsoft のコンパイルされた会社データはグローバルなカバーがありますが、オーストラリア、カナダ、英国、および米国でほとんどのカバーを提供しています。
- 会社の住所をグローバルに標準化します。 現在、以下の国または地域で住所の標準化をサポートしています: オーストラリア、カナダ、フランス、ドイツ、イタリア、日本、英国、米国。
- データの正確性または鮮度を保証します。 ビジネス情報は頻繁に変更されるため、提供される強化された会社データが常に正確または最新であることを保証することはできません。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。

1. **強化された会社データ** タイルで、**データのエンリッチ** を選択します。

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="会社データのエンリッチメント ハブのエンリッチメント タイル。":::

1. 概要を確認し、**次へ** を選択します。

1. **顧客データセット** を選択し、エンリッチするプロファイルまたはセグメントを選択します。 *顧客* エンティティは、すべての顧客プロファイルをエンリッチするのに対し、セグメントは、そのセグメントに含まれる顧客プロファイルのみをエンリッチします。

1. 会社のプロファイルから、Microsoft のコンパイルされた会社データとの照合に使用するフィールド タイプを選択します。 この選択は、次の手順でアクセスできるマッピング フィールドに影響します。

1. **次へ** を選択します。

1. Microsoft の企業データにフィールドをマッピングします。 一致の精度を高めるには、フィールドを追加します。

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="会社のエンリッチメントを構成する場合のデータ マッピング手順。":::

1. **次へ** を選択し、フィールド マッピングを完了します。

1. エンリッチメントと **出力エンティティ** の **名前** を指定します。

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。

1. **実行** を選択してエンリッチメント処理を開始するか、閉じるを選択して **エンリッチメント** ページに戻ります。

## <a name="enrichment-results"></a>強化の結果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>概要カード

**顧客変更の概要** タイルには、エンリッチメントの対応範囲に関する詳細が表示されます

- **処理済かつ変更済の会社**: 正常にエンリッチされた顧客の会社プロファイルの数。
- **処理済かつ未変更の会社**: 認識されているが変更されていない顧客の会社プロファイルの数。 これは通常、入力データが有効で、エンリッチメントによって改善できない場合に起こります。
- **未処理かつ未変更の会社**: 認識されていない顧客の会社プロファイルの数です。 これは通常は、エンリッチメントで無効またはサポートされていない入力データで発生します。

## <a name="next-steps"></a>次の手順

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
