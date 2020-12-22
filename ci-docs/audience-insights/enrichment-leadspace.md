---
title: サードパーティ エンリッチメント Leadspace による会社プロファイルのエンリッチメント
description: Leadspace サードパーティ エンリッチメントに関する一般情報。
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668729"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Leadspace を使用した企業プロファイルの拡充 (プレビュー)

Leadspace は、B2B の顧客データ プラットフォームを提供するデータ サイエンス企業です。 これを使用することで、企業の顧客プロファイルが統一された顧客は、データを充実させることができます。 エンリッチメントには、会社の規模、所在地、業種などの追加属性が含まれます。

## <a name="prerequisites"></a>前提条件

Leadspace を構成するには、次の前提条件が満たしている必要があります :

- アクティブな Leadspace ライセンスと "永久キー" (**Leadspace トークン** と呼ばれる) があります。 製品の詳細について、[Leadspace](https://www.leadspace.com/products/leadspace-on-demand/)に直接に問い合わせます。
- [管理者](permissions.md#administrator) のアクセス許可があります。
- 企業向けの[統一された顧客プロファイル](customer-profiles.md)を持っていること。

## <a name="configuration"></a>構成

1. 対象者に関するインサイトで、**データ** > **エンリッチメント** に移動します。

1. Leadspace のタイル上で、**データを充実させる** を選択します 。

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace タイルのスクリーンショット。":::

1. **開始する** を選択し、アクティブな **Leadspace トークン** (永久キー) を入力します。 内容を確認し、**同意する** チェックボックスを選択して、**データのプライバシーとコンプライアンス** に同意してください。 **Leadspace に接続** を選択して両方の入力を確認します。

1. **データのマップ** を選択し、統合プロファイルのどのフィールドを使用して、Leadspace から一致する会社データを検索するかを定義します。 **会社名** フィールドは必須です。 一致精度を高めるために、**会社の Web サイト** と **会社所在地** の 2 つのフィールドまで追加できます。

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace フィールド マッピング ペイン。":::
   
1. **適用** を選択して、フィールド マッピングを完了します。

1. **実行** を選択して会社のプロフィールを拡充します。 エンリッチメントにかかる時間は、統合顧客プロファイルの数によって異なります。

## <a name="enrichment-results"></a>強化の結果

エンリッチメントを更新した後、[自分のエンリッチメント](enrichment-hub.md) で新しくエンリッチされた会社データを確認できます。 最終更新時刻と、エンリッチされたプロファイル数を確認できます。

**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。

詳細については、[Leadspace の API](https://support.leadspace.com/hc/en-us/sections/201997649-API) を参照してください。

## <a name="next-steps"></a>次の手順

エンリッチされた顧客データの上に構築します。 [セグメント](segments.md)、[メジャー](measures.md) を作成し、[データをエクスポート](export-destinations.md) して、顧客にパーソナライズされたエクスペリエンスを提供します。

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Leadspace へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Leadspace がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエンリッチメントはいつでも削除できます。