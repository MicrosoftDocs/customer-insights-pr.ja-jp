---
title: データのエンリッチメント (プレビュー) の概要
description: Microsoft およびその他のサードパーティ サービスの機能を使用して、顧客データをエンリッチします。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: fb747f7adc7d87f30f66c5d0ed20bbe238558fde
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304525"
---
# <a name="data-enrichment-preview-overview"></a>データのエンリッチメント (プレビュー) の概要

Microsoft やその他のパートナーなどのソースからのデータを使用して、顧客データを拡充させます。 サード パーティのエンリッチメントは、管理者が資格情報を使用して設定し、データ転送の同意を提供する [接続](connections.md) を使用して構成されます。 この接続は、管理者と共同作成者がエンリッチメントを構成するのに使用できます。  

## <a name="multiple-enrichments-of-the-same-type"></a>同じ種類の複数のエンリッチメント

強化されるエンティティは、エンリッチメントの構成中に指定され、プロファイルのサブセットのみを強化できます。 たとえば、特定のセグメントのデータのみをエンリッチします。 同じ種類の複数のエンリッチメントを構成し、同じ接続を再利用できます。 一部のエンリッチメントには、作成できる同じ種類のエンリッチメントの数に制限があります。 制限と現在の使用状況は、**エンリッチメント** ページの **検出** タブで各タイルに表示されます。

## <a name="enrich-data-sources-before-unification"></a>統合前にデータ ソースをエンリッチする

データ統合前に顧客データをエンリッチして、データ照合の品質を向上させることができます。 詳細については、[データ ソース エンリッチメント](data-sources-enrichment.md) を参照してください。

## <a name="create-an-enrichment"></a>エンリッチメントの作成

エンリッチメントを作成、編集するには、コントリビューターまたは管理者の[アクセス許可](permissions.md)が必要です。

**データ** > **エンリッチメント** に移動します。 **検出** タブには、サポートされているすべてのエンリッチメント オプションが表示されます。

:::image type="content" source="media/enrichment-hub-page.png" alt-text="エンリッチメント ハブ ページ。":::

# <a name="individual-consumers-b-to-c"></a>[個人消費者 (B2C)](#tab/b2c)

- LiveRamp AbiliTec が提供する [AbiliTec ID](enrichment-liveramp.md)
- Microsoft が提供する [ブランド](enrichment-microsoft.md)
- Experian が提供する [人口統計情報](enrichment-experian.md)
- Microsoft が提供する [拡張住所](enrichment-enhanced-addresses.md)
- Microsoft が提供する [関心](enrichment-microsoft.md)
- Microsoft Azure Maps が提供する [場所データ](enrichment-azure-maps.md)
- HERE Technologies が提供する [位置データ](enrichment-here.md)
- セキュリティで保護されたファイル転送プロトコル (SFTP) による [SFTP カスタム データ](enrichment-SFTP-custom-import.md)

# <a name="business-accounts-b-to-b"></a>[事業取引先企業 (B2B)](#tab/b2b)

- Microsoft 提供の[アカウント エンゲージメント データ](enrichment-office.md)
- Dun & Bradstreet が提供する [会社データ](enrichment-dnb.md)
- Leadspace が提供する [会社データ](enrichment-leadspace.md)
- Microsoft が提供する [拡張住所](enrichment-enhanced-addresses.md)
- Microsoft 提供による[強化された会社データ](enrichment-enhanced-company-data.md)
- Microsoft Azure Maps が提供する [場所データ](enrichment-azure-maps.md)
- HERE Technologies が提供する [位置データ](enrichment-here.md)
- セキュリティで保護されたファイル転送プロトコル (SFTP) による [SFTP カスタム データ](enrichment-SFTP-custom-import.md)

---

## <a name="manage-existing-enrichments"></a>既存のエンリッチメントの管理

**データ** > **エンリッチメント** に移動します。 **自分のエンリッチメント** タブに、構成されたエンリッチメント、それらのステータス、エンリッチされた顧客の数、およびデータが最後に更新された時刻が表示されます。 エンリッチメントのリストを任意の列で並べ替えたり、検索ボックスを使用して管理するエンリッチメントを検索したりできます。

エンリッチメントを選択して、使用可能なアクションを表示できます。

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="エンリッチメントの一覧でエンリッチメントを管理するオプション。":::

- 強化された顧客プロファイルの数を使用して、エンリッチメントの詳細を **表示** します。
- エンリッチメント構成を **編集** します。
- 最新のデータで顧客プロファイルを更新するためのエンリッチメントを [**実行**](#run-or-refresh-enrichments)します。 リストで複数のエンリッチメントを選択して一度に実行します。
- エンリッチメントを **アクティブ化** または **非アクティブ化** します。 非アクティブなエンリッチメントは、[スケジュールされた更新](schedule-refresh.md)時に更新されません。
- エンリッチメントを **削除** します。

また、エンリッチメントから[セグメント](segments.md)や[メジャー](measures.md)を作成することも可能です。

## <a name="run-or-refresh-enrichments"></a>エンリッチメントの実行または更新

実行すると、エンリッチメントを自動スケジュールで更新することも、オンデマンドで手動で更新することもできます。

1. 1 つ以上のエンリッチメントを手動で更新するには、それらを選択して **実行** を選択します。 [自動更新をスケジュールする](schedule-refresh.md)には、**管理者** > **システム** > **スケジュール** に移動します。 処理時間は、顧客データのサイズによって異なります。

1. オプションで、[エンリッチメントプロセスの進捗状況を確認](#see-the-progress-of-the-enrichment-process)します。

1. エンリッチメントプロセスが完了したら、**自分のエンリッチメント** で新しくエンリッチされた顧客プロファイルデータ、最終更新時刻、エンリッチされたプロファイルの数を確認できます。

1. エンリッチメントを選択すると、[エンリッチメントの結果](#view-enrichment-results)が表示されます。

### <a name="see-the-progress-of-the-enrichment-process"></a>エンリッチメント プロセスの進捗状況を確認する

エンリッチメントの処理に関する詳細 (更新中または更新完了後のステータスや潜在的な問題など) を確認できます。 エンリッチメントを更新するためにどのようなプロセスがあり、そのプロセスの実行にどのくらいの時間がかかったのかを理解する。 エンリッチメントの状態は、Experian、Leadspace、HERE Technologies、SFTP Import、Azure Maps で確認できます。

1. **データ** > **エンリッチメント** に移動します。
1. **自分のエンリッチメント** タブで、エンリッチメントのステータスを選択してサイド ペインを開きます。
1. **進捗状況の詳細** ペインで、**エンリッチメント** セクションを展開します。
1. 進行状況を確認するエンリッチメントの配下で、**詳細を表示する** を選択します。
1. **タスクの詳細** ペインで、**詳細を表示する** を選択してエンリッチメントとその状態の更新に関連するプロセスを確認します。

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>エンリッチメントの結果の表示

エンリッチメントの実行が完了したら、エンリッチメントの結果を確認できます。

1. **データ** > **エンリッチメント** に移動します。
1. **自分のエンリッチメント** タブで、表示するエンリッチメントを選択します。

すべてのエンリッチには、エンリッチされたプロファイルの数、時間経過によるエンリッチ プロファイルの数などの基本情報が表示されます。 **エンリッチされた顧客プレビュー** タイルには、生成されたエンリッチメント エンティティのサンプルが表示されます。 詳細表示を見るには、**その他** を選択し、**データ** タブを選択します。

:::image type="content" source="media/enrichments-results.png" alt-text="エンリッチメントの結果ページ。":::

可能な場合は、**エンリッチされた顧客のフィールドごとの数** に各エンリッチされたフィールドのカバレッジへのドリルダウンを提供します。

一部のエンリッチメントには、エンリッチメントのタイプに固有の情報も表示されます。 詳細については、関連するドキュメントを参照してください。

[!INCLUDE [footer-include](includes/footer-banner.md)]
