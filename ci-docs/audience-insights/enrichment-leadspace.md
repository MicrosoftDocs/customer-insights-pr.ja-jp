---
title: サードパーティ エンリッチメント Leadspace による会社プロファイルのエンリッチメント
description: Leadspace サードパーティ エンリッチメントに関する一般情報。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 34b73b37670ed45e2c31ea164c0788b793bee433829ce21317c83903f3fca1fe
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031709"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Leadspace を使用した企業プロファイルの拡充 (プレビュー)

Leadspace は、B2B の顧客データ プラットフォームを提供するデータ サイエンス企業です。 これを使用することで、企業の顧客プロファイルが統一された顧客は、データを充実させることができます。 エンリッチメントには、会社の規模、所在地、業界など、より多くの属性が含まれます。

## <a name="prerequisites"></a>前提条件

Leadspace を構成するには、次の前提条件が満たしている必要があります :

- アクティブな Leadspace ライセンスを所有していること。
- 企業向けの[統一された顧客プロファイル](customer-profiles.md)を持っていること。
- Leadspace 接続は、管理者によって既に構成されているか、[管理者](permissions.md#administrator) アクセス許可と "永続キー" (**Leadspace トークン** と呼ばれます) を所有していること。 製品の詳細については、[Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) に直接お問い合わせください。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. 対象者に関するインサイトで、**データ** > **エンリッチメント** に移動します。

1. Leadspace タイルで **データのエンリッチ** を選択し、**開始する** を選択します。

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace タイルのスクリーンショット。":::

1. ドロップダウン リストから [接続](connections.md) を選択してください。 接続できない場合は、管理者に連絡してください。 管理者の場合は、**つながりの追加** を選択し、**Leadspace** を選択することで、接続を作成できます。 

1. **Leadspace に接続する** を選択し、接続を確定します。

1. **次へ** を選択し、Leadspace の企業データで強化する **顧客データ セット** を選択します。 **顧客** エンティティを選択してすべての顧客プロファイルをエンリッチするか、セグメント エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="顧客データ セットを選択するときのスクリーンショット。":::

1. **次へ** を選択し、統合プロファイルからどのフィールドを使用して、Leadspace から一致する企業データを検索するかを定義します。 **会社名** フィールドは必須です。 一致精度を高めるために、**会社の Web サイト** と **会社所在地** の 2 つのフィールドまで追加できます。

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace フィールド マッピング ペイン。":::

1. **次へ** を選択し、フィールド マッピングを完了します。

1. エンリッチメントの名前を入力して、選択内容を確認した後 **エンリッチメントの保存** を選択します。


## <a name="configure-the-connection-for-leadspace"></a>Leadspace の接続を構成する 

接続を構成するには、管理者である必要があります。 エンリッチメントの構成時に **つながりの追加** を選択するか、*または* **管理** > **接続** に移動し、Leadspace タイルで **設定** を選択します。

1. **開始する** を選択します。 

1. **表示名** ボックスに接続の名前を入力します。

1. 有効な Leadspace トークンを指定します。

1. 確認して、**同意する** を選択して、**データのプライバシーとコンプライアンス** に同意します。

1. **検証** を選択して、構成を検証します。

1. 検証が完了したら、**保存** を選択します。
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace 接続構成ページ。":::

## <a name="enrichment-results"></a>強化の結果

エンリッチメントを更新した後、[自分のエンリッチメント](enrichment-hub.md) で新しくエンリッチされた会社データを確認できます。 最終更新時刻と、エンリッチされたプロファイル数を確認できます。

**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。

詳細については、[Leadspace の API](https://support.leadspace.com/hc/en-us/sections/201997649-API) を参照してください。

## <a name="next-steps"></a>次の手順

エンリッチされた顧客データの上に構築します。 [セグメント](segments.md) および [メジャー](measures.md) を作成し、さらに [データのエクスポート](export-destinations.md) を行って、パーソナライズされたエクスペリエンスを顧客に提供します。

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Leadspace へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Leadspace がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、いつでもエンリッチメントを削除して、この機能の使用を中止することができます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
