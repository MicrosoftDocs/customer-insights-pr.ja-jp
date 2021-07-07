---
title: サードパーティのエンリッチメント Experian によるエンリッチメント
description: Experian サードパーティのエンリッチメントに関する一般情報。
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309826"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Experian からの人口統計情報で顧客プロファイルをエンリッチする (プレビュー)

Experian は、消費者および企業のクレジットのレポートおよびマーケティング サービスにおけるグローバル リーダーです。 Experian のデータ エンリッチメント サービスを使用して、世帯規模、収入などの人口統計データで顧客プロファイルのエンリッチメントを行うことで、顧客をより深く理解していくことができます。

## <a name="prerequisites"></a>前提条件

Experian を構成するには、次の前提条件が満たされている必要があります:

- 有効な Experian サブスクリプションを所有していること。 サブスクリプションを取得するには、[Experian へのお問い合わせ](https://www.experian.com/marketing-services/contact) から直接お問い合わせください。 [Experian データ エンリッチメントの詳細](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。

- Experian 接続は既に管理者によって構成されている、*または* [管理者](permissions.md#administrator) 権限を所有していること。 また、Experian がユーザーのために作成した、SSH 対応セキュア トランスポート (ST) アカウントのユーザー ID、パーティ ID、およびモデル番号も必要です。

## <a name="supported-countriesregions"></a>サポートされている国/地域

現在、米国でのみ顧客プロファイルのエンリッチメントをサポートしています。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。

1. Experian タイルで、**データのエンリッチメント** を選択します。

   > [!div class="mx-imgBorder"]
   > ![Experian タイルを](media/experian-tile.png "Experian tile")
   > 

1. ドロップダウン リストから [接続](connections.md) を選択してください。 接続できない場合は、管理者に連絡してください。 管理者の場合は、**接続の追加** を選択して、ドロップダウン リストから Experian を選択することで、接続を作成できます。 

1. 選択した接続を確定するには、**Experian に接続** を選択します。

1.  **次へ** を選択し、Experian からの人口統計データでエンリッチメントしたい **顧客データ セット** を選択します。 **顧客** エンティティを選択してすべての顧客プロファイルをエンリッチするか、セグメント エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="顧客データ セットを選択するときのスクリーンショット。":::

1. **次へ** を選択し、統合されたプロファイルのどの種類のフィールドを使用して、Experian の一致する人口統計データを検索するかを定義します。 **名前と住所**、**電話**、または **メール** フィールドの少なくとも 1 つが必要です。 一致精度を高めるために、他に最大 2 つのフィールドを追加できます。 この選択は、次の手順でアクセスできるマッピング フィールドに影響します。

    > [!TIP]
    > Experian に送信される、その他のキー識別子属性の一致率が高くなる可能性があります。

1. **次へ** を選択し、フィールド マッピングを開始します。

1. 統合されたプロファイルのどの種類のフィールドを使用して、Experian の一致する人口統計データを検索するかを定義します。 必須フィールドはマークされます。

1. エンリッチメントの名前と出力エンティティの名前を指定します。

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。

## <a name="configure-the-connection-for-experian"></a>Experian の接続を構成する 

接続を構成するには、管理者である必要があります。 エンリッチメントを構成するときに **接続の追加** 選択するか、*または*、Experian タイルで、**管理者** > **接続** に移動し、**設定** を選択します。

1. **開始する** を選択します。

1. **表示名** ボックスに接続の名前を入力します。

1. Experian のセキュア トランスポート アカウントの、有効なユーザー ID、パーティ ID、モデル番号を入力します。

1. 確認して、**同意する** を選択して、**データのプライバシーとコンプライアンス** に同意します。

1. **検証** を選択して、構成を検証します。

1. 検証が完了したら、**保存** を選択します。
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian 接続の構成ペイン。":::

## <a name="enrichment-results"></a>強化の結果

エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。 [スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。 処理時間は、顧客データのサイズと、Experian でアカウントに設定されたエンリッチメント プロセスによって異なります。

エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイル データを確認できます。 さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。

**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。

## <a name="next-steps"></a>次の手順

エンリッチされた顧客データの上に構築します。 [セグメント](segments.md) および [メジャー](measures.md) を作成し、さらに [データのエクスポート](export-destinations.md) を行って、パーソナライズされたエクスペリエンスを顧客に提供します。

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights から Experian へのデータ送信を可能にすると、Dynamics 365 Customer Insights のコンプライアンスの範囲を越えて、個人情報などの機密性の高い情報が潜在的に含まれるデータの転送を許可することになります。 Microsoft はお客様の指示でそのようなデータを送信することがありますが、Experian が関係するプライバシーまたはセキュリティのすべての義務を満たすよう見届ける責任はお客様にあります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、いつでもエンリッチメントを削除して、この機能の使用を中止することができます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
