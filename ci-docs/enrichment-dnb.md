---
title: Dun ＆ Bradstreet による企業プロファイルのエンリッチメント
description: Dun ＆ Bradstreet のサードパーティ エンリッチメントに関する一般的な情報。
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653724"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Dun ＆ Bradstreet による企業プロファイルのエンリッチメント (プレビュー)

Dun ＆ Bradstreet は、企業向けの商用データ、分析、およびインサイトを提供します。 これを使用することで、企業の顧客プロファイルが統一された顧客は、データを充実させることができます。 エンリッチメントには、DUNS 番号、会社の規模、業界などの属性が含まれます。

## <a name="prerequisites"></a>前提条件

Dun & Bradstreet エンリッチメントを構成するには、次の前提条件が満たされている必要があります。

- アクティブな [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) ライセンスを所有していること。
- 企業向けの[統一された顧客プロファイル](customer-profiles.md)を持っていること。
- Dun & Bradstreet [接続](connections.md) は、管理者によって構成されます。 あなたが [管理者](permissions.md#admin) のアクセス権と Dun＆Bradstreet Connect からの資格を持っている場合はそれを作成できます。 

## <a name="setting-up-your-dun--bradstreet-project"></a>Dun ＆ Bradstreet プロジェクトを設定する

Dun ＆ Bradstreet のライセンス ユーザーとして、[Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights) でプロジェクトを設定できます。 


1. [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights) にサインインします。 資格情報を取得するには、[パスワードを復元します](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights)。

1. 対象ユーザーの分析情報フィールドを対応する Dun ＆ Bradstreet フィールドにマップするために使用される [csv テンプレート ファイル](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) をダウンロードします。 

1. Dun ＆ Bradstreet プロジェクト作成体験の **データのアップロード** ステップにファイルをアップロードします。 

1. 新しく作成された Dun ＆ Bradstreet プロジェクトで関連する **ソース** 下の水平ドットを選択して、利用可能なオプションを確認します。

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Dun ＆ Bradstreet プロジェクトのドットのスクリーン ショット。":::

1. **S3 の詳細を取得する** を選択します。 この情報は安全な場所に保管してください。 それを対象者分析情報で [エンリッチメントのための接続を設定](#configure-a-connection-for-dun--bradstreet) する必要があります。 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Dun ＆ Bradstreet プロジェクトでの s3 情報の選択のスクリーンショット。":::



## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. 対象者に関するインサイトで、**データ** > **エンリッチメント** に移動します。

1. Dun ＆ Bradstreet タイルで **データをエンリッチメントする** を選択して、**始める** を選択します。

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Dun ＆ Bradstreet タイルのスクリーンショット。":::

1. ドロップダウン リストから [接続](connections.md) を選択してください。 接続できない場合は、管理者に連絡してください。 あなたが管理者の場合は、接続を作成できます。 **つながりの追加** を選択して、**Dun & Bradstreet** を選択します。 

1. **Dun ＆ Bradstreet に接続する** を選択して、接続を確認します。

1. **次へ** を選択し、Dun & Bradstreet からの会社 データでエンリッチする **顧客データ セット** を選択します。 **顧客** エンティティを選択して、すべての顧客プロファイルをエンリッチメントするか、セグメント エンティティを選択してそのセグメントに含まれる統合顧客プロファイルのみをエンリッチします。

1. **次へ** を選択し、統合プロファイルからどのタイプのフィールドを使用して、Dun & Bradstreet から一致する会社データを検索するかを定義します。 **DUNS 番号** または **会社名** と **国** のフィールドのいずれかは必須です。 国フィールドは [2 文字または 3 文字の国コード](https://www.iso.org/iso-3166-country-codes.html)、英語の国名、母国語の国名、および電話プレフィックスをサポートします。 一般的な国のバリエーションには、次のものがあります。

   * US: アメリカ合衆国、米国、USA、アメリカ。
   * CA: カナダ。
   * GB: 英国、UK、Great Britain、GB、グレートブリテンおよび北部アイルランド連合王国、グレートブリテン王国。
   * AU: オーストラリア、オーストラリア連邦。
   * FR: フランス、フランス共和国。
   * DE: ドイツ、ドイツ語、Deutschland、アレマーニュ、ドイツ連邦共和国、ドイツ共和国。

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun ＆ Bradstreet フィールド マッピング ウィンドウ。":::

1. **次へ** を選択し、フィールド マッピングを完了します。

1. エンリッチメントの名前を入力して、選択内容を確認した後 **エンリッチメントの保存** を選択します。


## <a name="configure-a-connection-for-dun--bradstreet"></a>Dun ＆ Bradstreet の接続を構成する 

接続を構成するには、管理者である必要があります。 エンリッチメントを構成する *もしくは* **管理** > **接続** に移動して、Dun & Bradstreet タイルで **設定** を選択して、**つながりの追加** を選択します。

1. **開始する** を選択します。 

1. **表示名** ボックスに接続の名前を入力します。

1. 有効な Dun ＆ Bradstreet の資格情報と Dun ＆ Bradstreet プロジェクトの詳細 *リージョン、ドロップ フォルダー パス、ドロップ フォルダー名* を提供します。 Dun ＆ Bradstreet プロジェクトから、[この情報を入手します](#setting-up-your-dun--bradstreet-project)。

1. 確認して、**同意する** を選択して、**データのプライバシーとコンプライアンス** に同意します。

1. **検証** を選択して、構成を検証します。

1. 検証が完了したら、**保存** を選択します。
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun ＆ Bradstreet 接続の構成ページ":::

## <a name="enrichment-results"></a>強化の結果

エンリッチメントを更新した後、[自分のエンリッチメント](enrichment-hub.md) で新しくエンリッチされた会社データを確認できます。 最終更新時刻と、エンリッチされたプロファイル数を確認できます。

**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。

## <a name="next-steps"></a>次のステップ

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dun & Bradstreet へのデータを転送するために Dynamics 365 Customer Insights を有効にすると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft はそのようなデータをお客様の指示に従って転送しますが、Dun & Bradstreet がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、いつでもエンリッチメントを削除して、この機能の使用を中止することができます。


[!INCLUDE[footer-include](includes/footer-banner.md)]
