---
title: LiveRamp ID データのエンリッチメント
description: LiveRamp データで顧客プロファイルをエンリッチします。
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0727818f6df565d9a031966a68d521ae7167e484
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646710"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>LiveRamp からの ID データで顧客プロファイルをエンリッチする (プレビュー) 

LiveRamp は、確定的なオフライン ID の解決と顧客データの統合を提供します。 顧客データの個人 ID を AbiliTec ID グラフにマッピングし、AbiliTec ID を受け取ることができます。 その後、これらの ID を使用して、顧客データをより適切に統合できます。 

## <a name="prerequisites"></a>前提条件 

エンリッチメントを構成するには、次の前提条件が満たされている必要があります: 

- 有効な LiveRamp サブスクリプションがある。 サブスクリプションを取得するには、LiveRamp アカウン トチーム、または [dynamics@liveramp.com](mailto:dynamics@liveramp.com) にお問い合わせください。   

- API にアクセスするためのクライアント ID とシークレットを持つアクティブな AbiliTec サブスクリプション。 詳細については、[AbiliTec API 開発者ハブ](https://developers.liveramp.com/abilitec-api/) を参照してください。 

## <a name="supported-countriesregions"></a>サポートされている国/地域 

現在、米国でのみ LiveRamp データを使用して顧客プロファイルをエンリッチすることをサポートしています。 

## <a name="configure-the-enrichment"></a>エンリッチメントの構成 

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。 

1. **ID** タイルで **データのエンリッチ** を選択します。 

   :::image type="content" source="media/liveramp-tile.png" alt-text="エンリッチメント概要ページの ID タイル。":::

1. ドロップダウン リストから [接続](connections.md) を選択してください。 接続できない場合は、管理者に連絡してください。 管理者の場合は、**接続の追加** を選択して接続を作成できます。 ドロップダウン リストから **LiveRamp** を選択します。 

1. **次へ** を選択し、LiveRamp からの ID データでエンリッチする **顧客データ セット** を選択します。 *顧客* エンティティを選択して、すべての顧客プロファイルをエンリッチするか、*セグメント* エンティティを選択してそのセグメントに含まれる顧客プロファイルのみをエンリッチします。 

1. **次へ** を選択し、統合プロファイルからどのタイプのフィールドを使用して、LiveRamp から一致する ID データを検索するかを定義します。 フィールド **名前と住所**、**電話**、または **メール** の少なくとも 1 つが必要です。 

   > [!TIP]
   > マップするキー識別子とフィールドが多いほど、一致率が高くなる可能性が高くなります 

1. LiveRamp の AbiliTec ID グラフとの照合に使用する、統合された *顧客* エンティティのフィールドをマップします。 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRamp エンリッチメントのデータ マッピング オプション。":::

1. **次へ** を選択し、フィールド マッピングを完了します。 

1. エンリッチメントと **出力エンティティ** の **名前** を指定します。 

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。 

## <a name="configure-the-connection-for-liveramp"></a>LiveRamp の接続を構成する 

[接続を構成](connections.md) するには、管理者である必要があります。 エンリッチメントの構成時に **接続の追加** を選択するか、**管理者** > **接続** に移動して、**設定** を **LiveRamp** タイルで選択します。 

:::image type="content" source="media/liveramp-connection.png" alt-text="LiveRamp AbiliTec サービスへの接続を設定するための構成ペイン。":::

1. **表示名** に接続の名前を入力します。 

1. 有効な LiveRamp クライアント ID とシークレットを指定します。 

1. 内容を確認し、**同意する** チェックボックスを選択して、**データのプライバシーとコンプライアンス** に同意してください。 

1. **検証** を選択して、構成を検証します。 

1. 接続を完了するには、**保存** を選択します。 

## <a name="enrichment-results"></a>強化の結果 

エンリッチ プロセスを開始するには、コマンド バーから 実行 を選択します。  [スケジュール更新](system.md#schedule-tab) の一部として、システムにエンリッチメントを自動的に実行させることもできます。 処理時間は、顧客データのサイズによって異なります。 

エンリッチメント プロセスが完了したら、 **自分のエンリッチメント** で新しくエンリッチメントされた顧客プロファイル データを確認できます。 さらに、最後の更新の時刻とエンリッチされたプロファイルの数が表示されます。 

 **ビューがエンリッチされた** データを選択することで、各エンリッチされたプロファイルの詳細ビューにアクセスできます。 

## <a name="next-steps"></a>次の手順

エンリッチされた顧客データの上に構築します。 AbiliTec ID を使用して、顧客プロファイルを個人ベースのビューに統合します。 
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス 

Dynamics 365 Customer Insights による LiveRamp へのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft はそのようなデータをお客様の指示に従って転送しますが、LiveRamp がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシー ステートメント](https://go.microsoft.com/fwlink/?linkid=396732) を確認してください。 Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエンリッチメントはいつでも削除できます。 


[!INCLUDE [footer-include](includes/footer-banner.md)]
