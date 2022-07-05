---
title: HERE Technologies で顧客プロファイルをエンリッチする (プレビュー)
description: HERE Technologies サードパーティ エンリッチメントに関する一般情報。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d88085b6be156dd1c895e9e5b38cc9d77acbdb95
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052057"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>HERE Technologies で顧客プロファイルをエンリッチする (プレビュー)

HERE Technologies は、位置中心のデータとサービスを提供するロケーション プラットフォーム企業です。 HERE Technologies のデータエンリッチメントサービスは、顧客の位置情報の精度を向上させます。 住所の正規化、緯度・経度の抽出などを行います。

## <a name="prerequisites"></a>前提条件

- 有効な HERE Technologies のサブスクリプション。 購読をご希望の方は、[こちらからご登録](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic)いただくか、[HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) に直接お問い合わせください。 [HERE Technologies 位置情報エンリッチメントの詳細。](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [接続](connections.md)は、管理者が[構成](#configure-the-connection-for-here-technologies)します。

## <a name="configure-the-connection-for-here-technologies"></a>HERE Technologies の接続を構成する

Customer Insights の[管理者](permissions.md#admin)で、有効な HERE Technologies  API キーを持っている必要があります。

1. エンリッチメントの構成時に **つながりの追加** を選択するか、または **管理** > **接続**  に移動し、HERE Technologies タイルで **設定** を選択します。

1. 接続の名前と有効な HERE Technologies API キーを入力します。

1. 確認して、**同意する** を選択して、[データのプライバシーとコンプライアンス](#data-privacy-and-compliance)に同意します。

1. **確認** を選択して設定を確認し、**保存** を選択します。

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="HERE Technologies 接続構成ページ。":::

### <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による HERE Technologies へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、HERE Technologies がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、いつでもエンリッチメントを削除して、この機能の使用を中止することができます。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。

1. HERE Technologies タイルから **場所** で  **データを充実させる** を選択します。

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies タイル。":::

1. 概要を確認し、**次へ** を選択します。

1. 接続を選択します。 利用できない場合は、管理者に連絡してください。

1. **次へ** を選択します。

1. **顧客データセット** を選択し、HERE Technologies からのデータでエンリッチするプロファイルまたはセグメントを選択します。 *顧客* エンティティは、すべての顧客プロファイルをエンリッチするのに対し、セグメントは、そのセグメントに含まれる顧客プロファイルのみをエンリッチします。

1. 照合に使用する統合プロファイルのフィールドのタイプ (プライマリおよび/またはセカンダリ アドレス) を定義します。 両方の住所のフィールド マッピングを指定し、、両方の住所のプロファイルを別々に強化できます。 たとえば、自宅の住所と会社の住所の場合。 **次へ** を選択します。

1. HERE Technologies のデモグラフィック データにフィールドをマッピングします。 **番地 1** と **郵便番号** フィールドは、住所 1 または住所 2、あるいはその両方に必要です。 一致の精度を高めるには、フィールドを追加します。

1. **次へ** を選択し、フィールド マッピングを完了します。

1. エンリッチメントと **出力エンティティ名** の **名前** を指定します。

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。

1. **実行** を選択してエンリッチメント処理を開始するか、閉じるを選択して **エンリッチメント** ページに戻ります。

## <a name="view-enrichment-results"></a>エンリッチメントの結果の表示

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**エンリッチされた顧客のフィールドごとの数** 各エンリッチフィールドのカバー範囲をドリルダウンで表示します。

## <a name="next-steps"></a>次の手順

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
