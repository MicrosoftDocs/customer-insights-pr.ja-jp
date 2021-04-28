---
title: サードパーティ エンリッチメント HERE Technologies によるエンリッチメント
description: HERE Technologies サードパーティ エンリッチメントに関する一般情報。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896057"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>HERE Technologies による顧客プロファイルの強化 (プレビュー)

HERE Technologies は、位置中心のデータとサービスを提供するロケーション プラットフォーム企業です。 HERE Technologies のデータ エンリッチメント サービスを使用すると、住所の正規化、緯度と経度の抽出などにより、顧客のより正確な位置情報を把握できます。

## <a name="prerequisites"></a>前提条件

HERE Technologies のエンリッチメントを構成するには、次の前提条件が満たされている必要があります:

- HERE Technologies のアクティブなサブスクリプションがあります。 サブスクリプションを取得するには、[ここでサインアップ](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic)、または直接 [HERE Technologies に連絡](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) することができます。 [HERE Technologies 位置情報エンリッチメントの詳細。](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [接続](connections.md) が可能であるか、*または* [管理者](permissions.md#administrator) アクセス許可とHERE Technologies API キーを所有していること。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. **データ** > **エンリッチメント** に移動します。 

1. HERE Technologies タイルで **データのエンリッチ** を選択し、**開始する** を選択します。

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies タイル](media/HERE-tile.png "HERE Technologies タイル")

1. ドロップダウンから [接続](connections.md) を選択します。 接続できない場合は、管理者に連絡してください。 管理者の場合は、**つながりの追加** を選択して接続を作成できます。 ドロップダウンから **HERE Technologies** を選択します。 

1. **HERE Technologies に接続する** を選択し、選択内容を確認します。

1.  **次へ** を選択し、HERE Technologies の位置情報データで強化する **顧客データ セット** を選択します。 **顧客** エンティティを選択してすべての顧客プロファイルをエンリッチするか、セグメント エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="顧客データ セットを選択するときのスクリーンショット。":::

1. フィールドを住所 1 または住所 2、あるいはその両方にマップするかどうかを選択します。 両方の住所のフィールド マッピングを指定し、、両方の住所のプロファイルを別々に強化できます。 たとえば、自宅と会社の住所がある場合です。 **次へ** を選択します。

1. HERE Technologies から一致する位置データを検索するために、統合プロファイルのどのフィールドを使用するかを定義します。 **番地 1** と **郵便番号** フィールドは、住所 1 または住所 2、あるいはその両方に必要です。 一致精度を高めるために、より多くのフィールドを追加できます。

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies エンリッチメント構成ページ](media/enrichment-HERE-configuration.png "HERE Technologies エンリッチメント構成ページ")

1. **次へ** を選択し、フィールド マッピングを完了します。

1. エンリッチメントの名前を入力します。 

1.選択内容を確認した後、**エンリッチメントの保存** を選択します。

## <a name="configure-the-connection-for-here-technologies"></a>HERE Technologies の接続を構成する 

接続を構成するには、管理者である必要があります。 エンリッチメントの構成時に **つながりの追加** を選択するか、*または* **管理** > **接続** に移動し、HERE Technologies タイルで **設定** を選択します。

1. **表示名** ボックスに接続の名前を入力します。

1. 有効な HERE Technologies API キーを入力します。

1. **データのプライバシーとコンプライアンス** を確認し、**同意する** チェックボックスを選択して、同意します

1. **検証** を選択して、構成を検証します。

1. 検証が完了したら、**保存** を選択します。

> [!div class="mx-imgBorder"]
   > ![HERE Technologies 接続構成ページ](media/enrichment-HERE-connection.png "HERE Technologies 接続構成ページ")

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
