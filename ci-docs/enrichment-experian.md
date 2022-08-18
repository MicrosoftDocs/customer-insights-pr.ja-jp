---
title: Experian からの人口統計情報で顧客プロファイルをエンリッチする (プレビュー)
description: Experian サードパーティのエンリッチメントに関する一般情報。
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fccb37cde3f05a70009c18b6c52db01a5ede094d
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238002"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Experian からの人口統計情報で顧客プロファイルをエンリッチする (プレビュー)

Experian は、消費者および企業のクレジットのレポートおよびマーケティング サービスにおけるグローバル リーダーです。 Experian のデータ エンリッチメント サービスを使用して、世帯規模、収入などの人口統計データで顧客プロファイルのエンリッチメントを行うことで、顧客をより深く理解していくことができます。

## <a name="supported-countriesregions"></a>サポートされている国/地域

現在、米国でのみ顧客プロファイルのエンリッチメントをサポートしています。

## <a name="prerequisites"></a>前提条件

- アクティブな Experian サブスクリプション。 サブスクリプションを取得するには、[Experian へのお問い合わせ](https://www.experian.com/marketing-services/contact) から直接お問い合わせください。 [Experian データ エンリッチメントの詳細](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)。

- Experian [ 接続](connections.md) は、管理者によって[構成](#configure-the-connection-for-experian)されます。

- Experian が作成した SSH 対応の Secure Transport (ST) アカウントの Experian ユーザー ID、パーティ ID、モデル番号。

## <a name="configure-the-connection-for-experian"></a>Experian の接続を構成する

Customer Insights の[管理者](permissions.md#admin)であり、Experian ユーザー ID、パーティ ID、モデル番号が必要です。

1. エンリッチメントを構成するときに **つながりの追加** を選択するか、または、Experian タイルで、**管理者** > **接続** に移動し、**設定** を選択します。

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian 接続の構成ペイン。":::

1. 接続の名前と、Experian  Secure Transport アカウントの有効なユーザー ID、パーティー ID、モデル番号を入力します。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **確認** を選択して設定を確認し、**保存** を選択します。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。

1. Experian  タイルから **デモグラフィック** で **データを充実させる** を選択します。

   :::image type="content" source="media/experian-tile.png" alt-text="エンリッチメント概要ページの Experian タイル。":::

1. 概要を確認し、**次へ** を選択します。

1. 接続を選択します。 接続できない場合は、管理者に連絡してください。

1. **次へ** を選択します。

1. **顧客データセット** を選択し、Experian からのデモグラフィックでエンリッチするプロファイルまたはセグメントを選択します。 *顧客* エンティティは、すべての顧客プロファイルをエンリッチするのに対し、セグメントは、そのセグメントに含まれる顧客プロファイルのみをエンリッチします。

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="顧客データ セットを選択するときのスクリーンショット。":::

1. Experian からのデモグラフィック データとのマッチングに使用する統一プロファイルのフィールドの種類を定義します。 **名前と住所**、**電話**、または **メール** フィールドの少なくとも 1 つが必要です。 一致の精度を高めるには、フィールドを追加します。 **次へ** を選択します。

1. Experian のデモグラフィック データにフィールドをマッピングします。

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
