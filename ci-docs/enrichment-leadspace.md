---
title: Leadspace で企業プロファイルをエンリッチする (プレビュー)
description: Leadspace サードパーティ エンリッチメントに関する一般情報。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b58532a541ee22a5e34d0af1a3334ccbd53627b2
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081352"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Leadspace で企業プロファイルをエンリッチする (プレビュー)

Leadspace は、B-to-B 顧客データ プラットフォームを提供するデータ サイエンス企業です。 これにより、取引先企業に基づいて統一された顧客プロファイルを持つ環境でデータを充実させることができます。 *顧客プロファイル* を、会社の規模、場所、業界などの属性でエンリッチします。 *取引先担当者プロファイル* を、タイトル、ペルソナ、メール確認などの属性でエンリッチします。

## <a name="prerequisites"></a>前提条件

- アクティブな Leadspace ライセンス。
- アカウントに基づく、[Unified customer profile](customer-profiles.md)。
- Leadspace [接続](connections.md)は、管理者が[構成](#configure-the-connection-for-leadspace)します。 製品の詳細については、[Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) に直接お問い合わせください。

## <a name="configure-the-connection-for-leadspace"></a>Leadspace の接続を構成する

Customer Insights の [管理者で](permissions.md#admin)、「永続キー」 (**Leadspace トークン**) を持っている必要があります 。

1. エンリッチメントの構成時に **つながりの追加** を選択するか、または **管理** > **接続**  に移動し、Leadspace タイルで **設定** を選択します。

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace 接続構成ページ。":::

1. 接続の名前と有効な Leadspace トークンを入力します。

1. 確認して、**同意する** を選択して、[データのプライバシーとコンプライアンス](#data-privacy-and-compliance)に同意します。

1. **確認** を選択して設定を確認し、**保存** を選択します。

### <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Leadspace へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Leadspace がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、いつでもエンリッチメントを削除して、この機能の使用を中止することができます。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。

1. Leadspace タイルの **会社データ** で、**データのエンリッチ** を選択します。

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace タイルのスクリーンショット。":::

1. 概要を確認し、**次へ** を選択します。

1. 接続を選択します。 利用できない場合は、管理者に連絡してください。

1. **次へ** を選択します。

1. **顧客データセット** を選択し、Leadspace の企業データでエンリッチするプロファイルまたはセグメントを選択します。 *顧客* エンティティは、すべての顧客プロファイルをエンリッチするのに対し、セグメントは、そのセグメントに含まれる顧客プロファイルのみをエンリッチします。

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="顧客データ セットを選択するときのスクリーンショット。":::

1. 照合に使用する統合プロファイルのフィールドのタイプ (プライマリおよび/またはセカンダリ アドレス) を定義します。 両方の住所のフィールド マッピングを指定し、、両方の住所のプロファイルを別々に強化できます。 たとえば、自宅の住所と会社の住所の場合。 **次へ** を選択します。

1. Leadspace の企業データにフィールドをマッピングします。 **会社名** フィールドは必須です。 一致精度を高めるために、**会社の Web サイト** と **会社所在地** の 2 つのフィールドまで追加できます。

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace フィールドマッピング ペイン。":::

1. **次へ** を選択し、フィールド マッピングを完了します。

1. エンリッチする *取引先担当者プロファイル* がある場合は、チェックボックスを選択します。 Customer Insights は、必要なフィールドを自動的にマッピングします。

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="リードスペース取引先担当者レコードのエンリッチメント。":::

1. **次へ** を選択します。

1. エンリッチメントと **出力エンティティ名** の **名前** を指定します。

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。

1. **実行** を選択してエンリッチメント処理を開始するか、閉じるを選択して **エンリッチメント** ページに戻ります。

## <a name="view-enrichment-results"></a>エンリッチメントの結果の表示

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

詳細については、[Leadspace の API](https://support.leadspace.com/hc/en-us/sections/201997649-API) を参照してください。

## <a name="next-steps"></a>次の手順

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
