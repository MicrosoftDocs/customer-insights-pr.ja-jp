---
title: Azure Maps の場所データを使用して、顧客プロファイルを強化する
description: Azure Maps のファーストパーティ エンリッチメントに関する一般情報。
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 2cc44f7b453d2aca328c397b14787c8a02c5e490
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376652"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Azure Maps による顧客プロファイルの強化 (プレビュー)

Azure Maps は、ロケーション中心のデータとサービスを提供し、ロケーション インテリジェンスを備えた地理空間データに基づくエクスペリエンスを提供します。 Azure Maps のデータ エンリッチメント サービスにより、顧客の位置情報の精度が向上します。 アドレスの正規化や緯度や経度の抽出などの機能を Dynamics 365 Customer Insights で使用できるようになります。

## <a name="prerequisites"></a>前提条件

Azure Maps のデータ エンリッチメントを構成するには、次の前提条件が満たされている必要があります:

- Azure Maps のサブスクリプションを所有していること。 サブスクリプションは、[新規登録、または無料試用版の取得](https://azure.microsoft.com/services/azure-maps/)で資格を得ることができます。

- Azure Maps [接続](connections.md)が利用可能、*または*[管理者](permissions.md#admin)権限とアクティブな Azure Maps API キーを持っていること。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. **データ** > **エンリッチメント** に移動します。 

1. **場所** タイルで、**データのエンリッチ** を選択します。

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps タイル。":::

1. ドロップダウン リストから [接続](connections.md) を選択してください。 Azure Maps 接続が利用できない場合は、管理者に連絡してください。 管理者であれば、[Azure Maps の接続を構成する](#configure-the-connection-for-azure-maps)ことができます。 

1. **次へ** を選択してを選択内容を確認します。

1. Azure Maps の場所データでエンリッチする **顧客データセット** を選択します。 また、セグメント エンティティを選択すると、そのセグメントに含まれる **顧客** のプロファイルのみをエンリッチできます。

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="顧客データセットを選択するときのスクリーンショット。":::

1. フィールドをプライマリ アドレスまたはセカンダリ アドレス、あるいはその両方にマッピングするかどうかを選択します。 両方の住所でフィールド マッピングを住所を (&mdash;たとえば、自宅と勤務先の住所) 特定し、両方の住所のプロファイルを別々にエンリッチ可能です。 **次へ** を選択します。

1. 統合されたプロファイルのどのフィールドを使用して、Azure Maps から一致する位置情報データを検索するかを定義します。 **住所 1** と **郵便番号** フィールドは、選択されたプライマリまたはセカンダリ ドレスに必要です。 より正確な一致を得るには、多くのフィールドを追加します。

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Azure Maps のエンリッチメント構成ページ。":::

1. **次へ** を選択し、フィールド マッピングを完了します。

1. **高度な設定** を変更するかどうかを評価します。 これらは、高度なユースケースに対応できるよう最大限の柔軟性を持たせていますが、ほとんどの場合は既定値のままで十分です。
   - **アドレスの種類**: 既定の動作では、エンリッチメントが不完全であっても最適なアドレス一致を返します。 完全なアドレスのみを取得するには、&mdash;たとえば、家番号を含む住所の場合、&mdash;**ポイント アドレス** 以外のチェックボックスはすべてクリアされます。 
   - **言語**: 既定では、住所は、住所が属すると判断された地域の言語で返されます。 標準化された住所の言語を適用するには、ドロップダウン メニューから言語を選択します。 たとえば、**英語** を選択すると、 **København、Danmark** ではなく、**Copenhagen、Denmark** が返されます。

1. エンリッチメントの名前を入力します。

1. 設定を確認し、**保存エンリッチメント** を選択します。

## <a name="configure-the-connection-for-azure-maps"></a>Azure Maps の接続を構成する

接続を構成するには、対象ユーザーインサイトの管理者である必要があります。 エンリッチメントを構成する際に **接続の追加** を選択するか、または、Azure Maps タイルで、**管理者** > **接続** に移動し、**設定** を選択します。

1. **表示名** ボックスに、接続の名前を入力します。

1. 有効な Azure Maps API キーを入力します。

1. **データのプライバシーとコンプライアンス** を確認し、**同意する** チェックボックスを選択して、同意します

1. **検証** を選択して、構成を検証します。

1. 検証が完了したら、**保存** を選択します。

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Maps の接続構成ページ。":::

## <a name="enrichment-results"></a>強化の結果

エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。 [スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。 処理時間は、顧客データのサイズと API 応答時間によって異なります。

エンリッチメント プロセスの完了後は、**マイ エンリッチメント** 配下で新たにエンリッチメントされた顧客プロファイル データを確認できます。 さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。

**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。

## <a name="next-steps"></a>次のステップ

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights から Azure Maps へのデータ送信を可能にすると、Dynamics 365 Customer Insights のコンプライアンスの範囲を越えて、個人情報などの機密性の高い情報が潜在的に含まれるデータの転送を許可することになります。 マイクロソフトはお客様の指示で当該データを送信する場合がありますが、お客様は Azure Maps がお客様のプライバシーまたはセキュリティに関する義務を確実に満たす責任を負います。 詳細については、[Microsoft プライバシー ステートメント](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエンリッチメントはいつでも削除できます。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
