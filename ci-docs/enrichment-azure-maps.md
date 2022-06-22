---
title: Azure Maps の場所データを使用して、顧客プロファイルを強化する
description: Azure Maps のファーストパーティ エンリッチメントに関する一般情報。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a806b2d0c791972c967c90694527608b4def9f3f
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953634"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Azure Maps による顧客プロファイルの強化 (プレビュー)

Azure Maps は、位置情報を中心としたデータとサービスを提供し、位置情報インテリジェンスを組み込んだ地理空間データに基づくエクスペリエンスを提供します。 Azure Maps のデータ エンリッチメント サービスにより、顧客の位置情報の精度が向上します。 アドレスの正規化や緯度や経度の抽出などの機能を Dynamics 365 Customer Insights で使用できるようになります。

## <a name="prerequisites"></a>前提条件

- 有効な Azure Maps サブスクリプション。 サブスクリプションに登録するには、[新規登録、または無料試用版を取得します](https://azure.microsoft.com/services/azure-maps/)。

- Azure Maps [接続](connections.md) は、管理者によって[構成](#configure-the-connection-for-azure-maps)されます。

## <a name="configure-the-connection-for-azure-maps"></a>Azure Maps の接続を構成する

Customer Insights の[管理者](permissions.md#admin)で、有効な Azure Maps API キーを持っている必要があります。

1. エンリッチメントを構成する際に **接続の追加** を選択するか、または、Azure Maps タイルで、**管理者** > **接続** に移動し、**設定** を選択します。

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Maps の接続構成ページ。":::

1. 接続の名前と有効な Azure Maps API キーを入力します。

1. 確認して、**同意する** を選択して、[データのプライバシーとコンプライアンス](#data-privacy-and-compliance)に同意します。

1. **確認** を選択して設定を確認し、**保存** を選択します。

### <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights から Azure Maps へのデータ送信を可能にすると、Dynamics 365 Customer Insights のコンプライアンスの範囲を越えて、個人情報などの機密性の高い情報が潜在的に含まれるデータの転送を許可することになります。 Microsoft はそのようなデータをお客様の指示に従って転送しますが、Azure Maps がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシー ステートメント](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエンリッチメントはいつでも削除できます。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。

1. Microsoft Azure Maps タイルから **場所** で **データを充実させる** を選択します。

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps タイル。":::

1. 概要を確認し、**次へ** を選択します。

1. 接続を選択します。 接続できない場合は、管理者に連絡してください。

1. **次へ** を選択します。

1. **顧客データセット** を選択し、Microsoft からのデータでエンリッチするプロファイルまたはセグメントを選択します。 *顧客* エンティティは、すべての顧客プロファイルをエンリッチするのに対し、セグメントは、そのセグメントに含まれる顧客プロファイルのみをエンリッチします。

1. 照合に使用する統合プロファイルのフィールドのタイプ (プライマリおよび/またはセカンダリ アドレス) を定義します。 両方の住所のフィールド マッピングを指定し、、両方の住所のプロファイルを別々に強化できます。 たとえば、自宅の住所と会社の住所の場合。 **次へ** を選択します。

1. Azure Maps の位置情報にフィールドをマッピングします。 **番地 1** と **郵便番号** フィールドは、住所 1 または住所 2、あるいはその両方に必要です。 一致の精度を高めるには、フィールドを追加します。

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Maps の属性マッピング。":::

1. **次へ** を選択し、フィールド マッピングを完了します。

1. 高度なユース ケースに対応するため、最大限の柔軟性を備えた **高度な設定** を見直します。 ただし、通常、次の規定の値を変更する必要はありません。

   - **アドレスの種類**: 不完全な場合でも、最適なアドレス一致が返されます。 完全なアドレスのみを取得するには、&mdash;たとえば、家番号を含む住所の場合、&mdash;**ポイント アドレス** 以外のチェックボックスはすべてクリアされます。
   - **言語**: アドレスは、アドレス領域に基づいた言語で返されます。 標準化された住所の言語を適用するには、ドロップダウン メニューから言語を選択します。 たとえば、**英語** を選択すると、**København、Danmark** ではなく、 **Copenhagen, Denmark** が返されます。
   - **結果の最大数**: アドレスごとの結果の数です。

1. **次へ** を選択します。

1. エンリッチメントと **出力エンティティ名** の **名前** を指定します。

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。

1. **実行** を選択してエンリッチメント処理を開始するか、閉じるを選択して **エンリッチメント** ページに戻ります。

## <a name="enrichment-results"></a>強化の結果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**エンリッチされた顧客のフィールドごとの数** 各エンリッチフィールドのカバー範囲をドリルダウンで表示します。

## <a name="next-steps"></a>次の手順

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
