---
title: LiveRamp からの ID データで顧客プロファイルをエンリッチする (プレビュー)
description: LiveRamp データで顧客プロファイルをエンリッチします。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 334440493c50448005ec90d0cfac11358d677b73
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081280"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>LiveRamp からの ID データで顧客プロファイルをエンリッチする (プレビュー)

LiveRamp は、確定的なオフライン ID の解決と顧客データの統合を提供します。 顧客データの個人 ID を AbiliTec ID グラフにマッピングし、AbiliTec ID を受け取ることができます。 その後、これらの ID を使用して、顧客データをより適切に統合できます。

## <a name="supported-countriesregions"></a>サポートされている国/地域

現在、米国でのみ LiveRamp データを使用して顧客プロファイルをエンリッチすることをサポートしています。

## <a name="prerequisites"></a>前提条件

- 有効な LiveRamp サブスクリプションがある。 サブスクリプションを取得するには、LiveRamp アカウン トチーム、または [dynamics@liveramp.com](mailto:dynamics@liveramp.com) にお問い合わせください。

- API にアクセスするためのクライアント ID とシークレットを持つアクティブな AbiliTec サブスクリプション。 詳細については、[AbiliTec API 開発者ハブ](https://developers.liveramp.com/abilitec-api/) を参照してください。

- LiveRamp [接続](connections.md)は、管理者が[構成](#configure-the-connection-for-liveramp)します。

## <a name="configure-the-connection-for-liveramp"></a>LiveRamp の接続を構成する

Customer Insights の[管理者](permissions.md#admin)であり、LiveRamp のクライアント ID とシークレットが有効であることが必要です。

1. エンリッチメントの構成時に **つながりの追加** を選択するか、**管理** > **接続** に移動して、**設定** を LiveRamp タイルで選択します。

   :::image type="content" source="media/liveramp-connection.png" alt-text="LiveRamp AbiliTec サービスへの接続を設定するための構成ペイン。":::

1. 接続の名前と有効な LiveRamp クライアント ID とシークレットを入力します。

1. 確認して、**同意する** を選択して、[データのプライバシーとコンプライアンス](#data-privacy-and-compliance)に同意します。

1. **確認** を選択して設定を確認し、**保存** を選択します。

### <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による LiveRamp へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft はそのようなデータをお客様の指示に従って転送しますが、LiveRamp がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシー ステートメント](https://go.microsoft.com/fwlink/?linkid=396732) を確認してください。 Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエンリッチメントはいつでも削除できます。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。

1. LiveRamp タイルの **ID** で **データのエンリッチ** を選択します。

   :::image type="content" source="media/liveramp-tile.png" alt-text="エンリッチメント概要ページの ID タイル。":::

1. 概要を確認し、**次へ** を選択します。

1. 接続を選択します。 利用できない場合は、管理者に連絡してください。

1. **次へ** を選択します。

1. **顧客データセット** を選択し、LiveRamp から ID データでエンリッチするプロファイルまたはセグメントを選択します。 *顧客* エンティティは、すべての顧客プロファイルをエンリッチするのに対し、セグメントは、そのセグメントに含まれる顧客プロファイルのみをエンリッチします。

1. LiveRamp からの ID データのマッチングに使用する、統一プロファイルのフィールドの種類を定義します。 フィールド **名前と住所**、**電子メール**、または **電話** のいずれかが必要です。 一致の精度を高めるには、フィールドを追加します。 **次へ** を選択します。

1. LiveRamp の識別データにフィールドをマッピングします。

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRamp エンリッチメントのデータ マッピング オプション。":::

1. **次へ** を選択し、フィールド マッピングを完了します。

1. エンリッチメントと **出力エンティティ名** の **名前** を指定します。

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。

1. **実行** を選択してエンリッチメント処理を開始するか、閉じるを選択して **エンリッチメント** ページに戻ります。

## <a name="view-enrichment-results"></a>エンリッチメントの結果の表示

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**エンリッチされた顧客のフィールドごとの数** 各エンリッチフィールドのカバー範囲をドリルダウンで表示します。

## <a name="next-steps"></a>次の手順

エンリッチされた顧客データの上に構築します。 AbiliTec ID を使用して、顧客プロファイルを個人ベースのビューに統合します。
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
