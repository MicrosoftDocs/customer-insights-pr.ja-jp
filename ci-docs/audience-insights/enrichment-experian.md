---
title: サードパーティ エンリッチメント Experian によるエンリッチメント
description: Experian サードパーティ エンリッチメントに関する一般情報。
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668818"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Experian の人口統計で顧客プロファイルをエンリッチする (プレビュー)

Experian は、消費者および企業の信用調査およびマーケティング サービスの世界的リーダーです。 Experian のデータ エンリッチメント サービスを使用することで、世帯規模や収入などの人口統計データで顧客プロファイルをエンリッチさせ、より深い顧客理解を構築することができます。

## <a name="prerequisites"></a>前提条件

Experian を構成するには、次の前提条件が満たされている必要があります:

- Experian のサブスクリプションがアクティブです。 サブスクリプションを取得するには、直接 [Experian にお問い合わせください](https://www.experian.com/marketing-services/contact)。 [Experian データ エンリッチメントの詳細情報](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) を確認する。
- Experian が作成した SSH 対応のセキュア トランスポート (ST) アカウントのユーザー ID、パーティ ID、およびモデル番号があります。
- 対象者に関するインサイトに [管理者](permissions.md#administrator) のアクセス許可があります。

## <a name="configuration"></a>構成

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。

1. Experian タイルで **データのエンリッチ** を選択します。

   > [!div class="mx-imgBorder"]
   > ![Experian タイル](media/experian-tile.png "Experian タイル")

1. **開始する** を選択して、Experian セキュア トランスポート アカウントのユーザー ID、パーティ ID、およびモデル番号を入力します。 内容を確認し、**同意する** チェックボックスを選択して、**データのプライバシーとコンプライアンス** に同意してください。 **適用** を選択して、すべての入力を確認します。

## <a name="map-your-fields"></a>フィールドのマップ

1. **データの追加** を選択して、**名前と住所**、**電子メール**、または **電話** からキー識別子を選択し、ID 解決のために Experian に送信します。

   > [!TIP]
   > Experian に送信されるキー識別子属性が多いほど、一致率が高くなる可能性があります。

1. **次へ** を選択して、選択したキー識別子フィールドの統合顧客エンティティから対応する属性をマップします。

1. **属性の追加** を選択して、Experian に送信する追加属性をマップします。

1.  **保存** を選択して、フィールドのマッピングを完了します。

   > [!div class="mx-imgBorder"]
   > ![Experian フィールド マッピング](media/experian-field-mapping.png "Experian フィールド マッピング")

## <a name="enrichment-results"></a>強化の結果

エンリッチ プロセスを開始するには、コマンド バーから **実行** を選択します。 [スケジュールされた更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。 処理時間は、顧客データのサイズと Experian がカウントに設定したエンリッチメント プロセスによって異なります。

エンリッチメント プロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイル データを確認できます。 さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。

**拡充したデータの表示** を選択することで、それぞれの拡充されたプロファイルの詳細ビューにアクセスできます。

## <a name="next-steps"></a>次の手順

エンリッチされた顧客データの上に構築します。 [セグメント](segments.md)、[メジャー](measures.md) を作成し、[データをエクスポート](export-destinations.md) して、顧客にパーソナライズされたエクスペリエンスを提供します。

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Experian へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Experian がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエンリッチメントはいつでも削除できます。
