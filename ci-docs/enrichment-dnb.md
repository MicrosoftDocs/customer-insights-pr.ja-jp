---
title: Dun ＆ Bradstreet で企業プロファイルをエンリッチする (プレビュー)
description: Dun ＆ Bradstreet のサードパーティ エンリッチメントに関する一般的な情報。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 51f2e4e46aa25d10502d0feb5ea42eb7d2d637b9
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081435"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Dun ＆ Bradstreet で企業プロファイルをエンリッチする (プレビュー)

Dun ＆ Bradstreet は、企業向けの商用データ、分析、およびインサイトを提供します。 これを使用することで、企業の顧客プロファイルが統一された顧客は、データを充実させることができます。 エンリッチメントには、DUNS 番号、会社の規模、業界などの属性が含まれます。

## <a name="prerequisites"></a>前提条件

- アクティブな [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) ライセンスの所有。
- [統一された顧客プロファイル](customer-profiles.md) 企業向け。
- Dun & Bradstreet の [プロジェクト](#set-up-your-dun--bradstreet-project)が設定されている。
- Dun & Bradstreet [接続](connections.md) は、管理者によって[構成](#configure-a-connection-for-dun--bradstreet)されます。

## <a name="set-up-your-dun--bradstreet-project"></a>Dun ＆ Bradstreet プロジェクトを設定する

Dun ＆ Bradstreet のライセンス ユーザーとして、[Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights) でプロジェクトを設定できます。

1. [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights) にサインインします。 資格情報を取得するには、[パスワードを復元します](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights)。

1. Customer Insights フィールドを、対応する Dun ＆ Bradstreet フィールドにマップするために使用される [csv テンプレート ファイル](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv)をダウンロードします。

1. Dun ＆ Bradstreet プロジェクト作成体験の **データのアップロード** ステップにファイルをアップロードします。

1. 新しく作成された Dun ＆ Bradstreet プロジェクトで関連する **ソース** 下の水平ドットを選択して、利用可能なオプションを確認します。

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Dun ＆ Bradstreet プロジェクトのドットのスクリーン ショット。":::

1. **S3 の詳細を取得する** を選択します。 この情報は安全な場所に保管してください。 それは、Customer Insights で[エンリッチメントの接続を設定](#configure-a-connection-for-dun--bradstreet)するために必要です。

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Dun ＆ Bradstreet プロジェクトでの s3 情報の選択のスクリーンショット。":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Dun ＆ Bradstreet の接続を構成する

Customer Insights の [管理者](permissions.md#admin)で、Dun & Bradstreet Connect の資格情報を持っている必要があります。

1. エンリッチメントを設定する際に **つながりの追加** を選択するか、**管理** > **接続** に移動して Dun & Bradstreet タイルの **設定** を選択します。

1. 接続の名前を入力します。

1. 有効な Dun ＆ Bradstreet の資格情報と Dun ＆ Bradstreet プロジェクトの詳細 *リージョン、ドロップ フォルダー パス、ドロップ フォルダー名* を提供します。 Dun ＆ Bradstreet プロジェクトから、[この情報を入手します](#set-up-your-dun--bradstreet-project)。

1. 確認して、**同意する** を選択して、[データのプライバシーとコンプライアンス](#data-privacy-and-compliance)に同意します。

1. **確認** を選択して設定を確認し、**保存** を選択します。

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun ＆ Bradstreet 接続の構成ページ":::

### <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dun & Bradstreet へのデータを転送するために Dynamics 365 Customer Insights を有効にすると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft はそのようなデータをお客様の指示に従って転送しますが、Dun & Bradstreet がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、いつでもエンリッチメントを削除して、この機能の使用を中止することができます。

## <a name="supported-countries-or-regions"></a>サポートされている国または地域

現在、次の国/地域オプションをサポートしています: カナダ (英語) または米国 (英語)。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。

1. **会社データ** タイルで、Dun & Bradstreet タイルの **データのエンリッチ** を選択します。

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Dun ＆ Bradstreet タイルのスクリーンショット。":::

1. 概要を確認し、**次へ** を選択します。

1. 接続を選択して確認します。 利用できない場合は、管理者に連絡してください。

1. **次へ** を選択します。

1. **顧客データセット** を選択し、Dun & Bradstreet の企業データでエンリッチするプロファイルまたはセグメントを選択します。 *顧客* エンティティは、すべての顧客プロファイルをエンリッチするのに対し、セグメントは、そのセグメントに含まれる顧客プロファイルのみをエンリッチします。

1. Dun & Bradstreet からの企業データとのマッチングに使用する統一プロファイルのフィールドの種類を定義します。 **名前と住所**、**電話**、または **メール** フィールドの少なくとも 1 つが必要です。

1. **次へ** を選択します。

1. Dun & Bradstreet の企業データにフィールドをマッピングします。 **DUNS 番号** または **会社名** と **国** のフィールドのいずれかは必須です。

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun ＆ Bradstreet フィールド マッピング ウィンドウ。":::

1. **次へ** を選択し、フィールド マッピングを完了します。

1. エンリッチメントと **出力エンティティ名** の **名前** を指定します。

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。

1. **実行** を選択してエンリッチメント処理を開始するか、閉じるを選択して **エンリッチメント** ページに戻ります。

## <a name="view-enrichment-results"></a>エンリッチメントの結果の表示

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>次の手順

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
