---
title: サードパーティ エンリッチメント HERE Technologies によるエンリッチメント
description: HERE Technologies サードパーティ エンリッチメントに関する一般情報。
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269520"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>HERE Technologies による顧客プロファイルの強化 (プレビュー)

HERE Technologies は、位置中心のデータとサービスを提供するロケーション プラットフォーム企業です。 HERE Technologies のデータ エンリッチメント サービスを使用すると、住所の正規化、緯度と経度の抽出などにより、顧客のより正確な位置情報を把握できます。

## <a name="prerequisites"></a>前提条件

HERE Technologies のエンリッチメントを構成するには、次の前提条件が満たされている必要があります:

- HERE Technologies のアクティブなサブスクリプションがあります。 サブスクリプションを取得するには、[ここでサインアップ](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic)、または直接 [HERE Technologies に連絡](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) することができます。 [HERE Technologies 位置情報エンリッチメントの詳細。](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE Technologies API キーがあります。

- [管理者](permissions.md#administrator) のアクセス許可があります。

## <a name="configuration"></a>構成

1. **データ** > **エンリッチメント** に移動します。

1. HERE Technologies タイルで **データの強化** を選択します。

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies タイル](media/HERE-tile.png "HERE Technologies タイル")

1. アクティブな **HERE Technologies API キー** を入力します。 内容を確認し、**同意する** チェックボックスを選択して、**データのプライバシーとコンプライアンス** に同意してください。 

1. **HERE に接続** を選択して両方の入力を確認します。

1.  **データを追加する** を選択して、HERE Technologies の場所データをエンリッチさせる **顧客データ セット** を選択します。 **顧客** エンティティを選択してすべての顧客プロファイルをエンリッチするか、セグメント エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="顧客データ セットを選択するときのスクリーンショット。":::

1. フィールドを住所 1 または住所 2、あるいはその両方にマップするかどうかを選択します。 両方の住所 (例えば、自宅と会社の住所) のフィールド マッピングを指定し、両方の住所のプロファイルを個別に強化できます。 **次へ** を選択します。

1. HERE Technologies から一致する位置データを検索するために、統合プロファイルのどのフィールドを使用するかを定義します。 **番地 1** と **郵便番号** フィールドは、住所 1 または住所 2、あるいはその両方に必要です。 一致精度を高めるために、より多くのフィールドを追加できます。

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies エンリッチメント構成ページ](media/enrichment-HERE-configuration.png "HERE Technologies エンリッチメント構成ページ")

1. **適用** を選択して、フィールド マッピングを完了します。

## <a name="enrichment-results"></a>強化の結果

エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。 [スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。 処理時間は、顧客データのサイズと HERE Technologies からの API 応答時間によって異なります。

エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイル データを確認できます。 さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。

**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。

## <a name="next-steps"></a>次の手順

エンリッチされた顧客データの上に構築します。 [セグメント](segments.md)、[メジャー](measures.md) を作成し、[データをエクスポート](export-destinations.md) して、顧客にパーソナライズされたエクスペリエンスを提供します。

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による HERE Technologies へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、HERE Technologies がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエンリッチメントはいつでも削除できます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]