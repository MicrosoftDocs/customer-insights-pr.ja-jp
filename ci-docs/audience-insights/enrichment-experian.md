---
title: サードパーティ エンリッチメント Experian によるエンリッチメント
description: Experian サードパーティ エンリッチメントに関する一般情報。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896379"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Experian の人口統計で顧客プロファイルをエンリッチする (プレビュー)

Experian は、消費者および企業の信用調査およびマーケティング サービスの世界的リーダーです。 Experian のデータ エンリッチメント サービスを使用することで、世帯規模や収入などの人口統計データで顧客プロファイルをエンリッチさせ、より深い顧客理解を構築することができます。

## <a name="prerequisites"></a>前提条件

Experian を構成するには、次の前提条件が満たされている必要があります:

- Experian のサブスクリプションがアクティブです。 サブスクリプションを取得するには、直接 [Experian にお問い合わせください](https://www.experian.com/marketing-services/contact)。 [Experian データ エンリッチメントの詳細情報](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) を確認する。

- Experian 接続はすでに管理者によって構成されている、*または* [管理者](permissions.md#administrator) アクセス許可を所有していること。 また、Experian がユーザーのために作成した、SSH 対応セキュア トランスポート (ST) アカウントのユーザー ID、関係者 ID、およびモデル番号も必要です。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。

1. Experian タイルで **データのエンリッチ** を選択します。

   > [!div class="mx-imgBorder"]
   > ![Experian タイル](media/experian-tile.png "Experian タイル")
   > 

1. ドロップダウンから [接続](connections.md) を選択します。 接続できない場合は、管理者に連絡してください。 管理者の場合は、**つながりの追加** を選択し、ドロップダウンから Experian を選択することで、接続を作成できます。 

1. **Experian に接続する** を選択し、接続の選択内容を確認します。

1.  **次へ** を選択し、Experian の人口統計データで強化する **顧客データ セット** を選択します。 **顧客** エンティティを選択してすべての顧客プロファイルをエンリッチするか、セグメント エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="顧客データ セットを選択するときのスクリーンショット。":::

1. **次へ** を選択し、統合プロファイルからどの種類のフィールドを使用して、Experian から一致する人口統計データを検索するかを定義します。 **名前と住所**、**電話**、または **メール** フィールドの少なくとも 1 つが必要です。 一致精度を高めるために、他に最大 2 つのフィールドを追加できます。 この選択は、次の手順でアクセスできるマッピング フィールドに影響します。

    > [!TIP]
    > Experian に送信されるキー識別子属性が多いほど、一致率が高くなる可能性があります。

1. **次へ** を選択し、フィールド マッピングを開始します。

1. 統合プロファイルからどのフィールドを使用して、Experian から一致する人口統計データを検索するかを定義します。 必須フィールドはマークされます。

1. エンリッチメントの名前と出力エンティティの名前を指定します。

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。

## <a name="configure-the-connection-for-experian"></a>Experian の接続を構成する 

接続を構成するには、管理者である必要があります。 エンリッチメントの構成時に **つながりの追加** を選択するか、*または* **管理** > **接続** に移動し、Experian タイルで **設定** を選択します。

1. **開始する** を選択します。

1. **表示名** ボックスに接続の名前を入力します。

1. Experian セキュア トランスポート アカウントの有効なユーザー ID、関係者 ID、およびモデル番号を入力します。

1. **データのプライバシーとコンプライアンス** を確認し、**同意する** チェックボックスを選択して、同意します

1. **検証** を選択して、構成を検証します。

1. 検証が完了したら、**保存** を選択します。
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian 接続構成ペイン。":::

## <a name="enrichment-results"></a>強化の結果

エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。 [スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。 処理時間は、顧客データのサイズと Experian がカウントに設定したエンリッチメント プロセスによって異なります。

エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイル データを確認できます。 さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。

**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。

## <a name="next-steps"></a>次の手順

エンリッチされた顧客データの上に構築します。 [セグメント](segments.md)、[メジャー](measures.md) を作成し、[データをエクスポート](export-destinations.md) して、顧客にパーソナライズされたエクスペリエンスを提供します。

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Experian へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Experian がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエンリッチメントはいつでも削除できます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
