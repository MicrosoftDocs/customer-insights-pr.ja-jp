---
title: 統合顧客プロファイルを強化する
description: 機能を使用して、顧客データを強化します。
ms.date: 03/29/2022
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
ms.openlocfilehash: 510a20306e793a5ba522a6ac0d9c7194f03472d2
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491964"
---
# <a name="enrichment-for-customer-profiles-preview"></a>顧客プロファイルを拡充させる (プレビュー版)

Microsoft やその他のパートナーなどのソースからのデータを使用して、顧客データを拡充させます。

:::image type="content" source="media/enrichment-hub-page.png" alt-text="エンリッチメント ハブ ページ。":::

対象者に関するインサイトで、**データ** > **エンリッチメント** に移動し、エンリッチメント オプションを使用します。  

エンリッチメントを作成、編集するには、コントリビューターまたは管理者権限が必要です。 詳細については、[権限](permissions.md)を参照してください。

**検出** タブには、サポートされているすべてのエンリッチメント オプションが表示されます。

# <a name="individual-consumers-b-to-c"></a>[個人消費者 (B2C)](#tab/b2c)

- Microsoft が提供する [ブランド](enrichment-microsoft.md)
- Microsoft が提供する [関心](enrichment-microsoft.md)
- Microsoft が提供する [拡張住所](enrichment-enhanced-addresses.md) 
- Experian が提供する [人口統計情報](enrichment-experian.md)
- セキュリティで保護されたファイル転送プロトコル (SFTP) による [カスタム データ](enrichment-SFTP-custom-import.md) 
- Microsoft が提供する [Azure Maps](enrichment-azure-maps.md)
- HERE Technologies が提供する [位置データ](enrichment-here.md) 
- LiveRamp AbiliTec が提供する [ID](enrichment-liveramp.md)

# <a name="business-accounts-b-to-b"></a>[事業取引先企業 (B2B)](#tab/b2b)

- Leadspace が提供する [会社データ](enrichment-leadspace.md)
- Microsoft が提供する [拡張住所](enrichment-enhanced-addresses.md) 
- Microsoft 提供による[強化された会社データ](enrichment-enhanced-company-data.md)
- HERE Technologies が提供する [位置データ](enrichment-here.md) 
- セキュリティで保護されたファイル転送プロトコル (SFTP) による [カスタム データ](enrichment-SFTP-custom-import.md) 
- Microsoft が提供する [Azure Maps](enrichment-azure-maps.md)
- Microsoft 提供の[アカウント エンゲージメント データ](enrichment-office.md)

---

**自分のエンリッチメント** タブでは、設定した拡充を表示し、そのプロパティを編集することができます。

## <a name="manage-existing-enrichments"></a>既存のエンリッチメントの管理

**自分のエンリッチメント** タブに移動し、構成されているすべてのエンリッチメントを表示します。 各エンリッチメントは、エンリッチメントに関する追加情報を含む行として表されます。

エンリッチメントを選択して、使用可能なオプションを確認します。 リスト項目の省略記号 (...) を選択して、オプションを表示することもできます。 複数のエンリッチメントを構成した場合は、検索ボックスを使用して簡単に見つけることができます。

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="エンリッチメントの一覧でエンリッチメントを管理するオプション。":::

- 強化された顧客プロファイルの数を使用して、エンリッチメントの詳細を **表示** します。
- エンリッチメント構成を **編集** します。
- 最新のデータで顧客プロファイルを更新するためのエンリッチメントを **実行** します。
- 既存のエンリッチメントを **非アクティブ化** して、スケジュールされた更新のたびに自動更新されないようにします。 最後に成功した更新のデータは引き続き使用できます。 非アクティブなエンリッチメントを **活性化** し、スケジュールされた更新ごとに自動更新を再開します。
- エンリッチメントを **削除** します。

リストで複数のエンリッチメントを選択して、一度に実行したり、解除したりすることができます。 表示と編集のオプションは、一括操作では利用できません。 一度に一つのエンリッチメントにしか機能しません。

## <a name="enrichments-and-connections"></a>エンリッチメントと接続

サード パーティのエンリッチメントは、管理者が資格情報を使用して設定し、データ転送の同意を提供する [接続](connections.md) を使用して構成されます。 この接続は、管理者と共同作成者がエンリッチメントを構成するのに使用できます。  

## <a name="multiple-enrichments-of-the-same-type"></a>同じ種類の複数のエンリッチメント

強化されるエンティティは、エンリッチメントの構成中に指定され、プロファイルのサブセットのみを強化できます。 たとえば、特定のセグメントのデータのみをエンリッチします。 同じ種類の複数のエンリッチメントを構成し、同じ接続を再利用できます。 一部のエンリッチメントには、作成できる同じ種類のエンリッチメントの数に制限があります。 制限と現在の使用状況は **エンリッチメント** ページで確認できます。

## <a name="enrich-data-sources-before-unification"></a>統合前にデータ ソースをエンリッチする

データ統合前に顧客データをエンリッチして、データ照合の品質を向上させることができます。 詳細については、[データ ソース エンリッチメント](data-sources-enrichment.md) を参照してください。

## <a name="see-the-progress-of-the-enrichment-process"></a>エンリッチメント プロセスの進捗状況を確認する

エンリッチメントの処理に関する詳細 (更新中または更新完了後のステータスや潜在的な問題など) を確認できます。 エンリッチメントを更新するためにどのようなプロセスがあり、そのプロセスの実行にどのくらいの時間がかかったのかを理解する。 エンリッチメントの状態は、Experian、Leadspace、HERE Technologies、SFTP Import、Azure Maps で確認できます。

エンリッチメントの状態を確認する方法

1. **データ** > **エンリッチメント** に移動します。 
1. **マイ エンリッチメント** タブで、エンリッチメントの状態を選択してサイド ペインを開きます。 
1. **進捗状況の詳細** ペインで、**エンリッチメント** セクションを展開します。 
1. 進行状況を確認するエンリッチメントの配下で、**詳細を表示する** を選択します。 
1. **タスクの詳細** ペインで、**詳細を表示する** を選択してエンリッチメントとその状態の更新に関連するプロセスを確認します。 

## <a name="enrichment-results"></a>強化の結果

エンリッチメントの実行が完了したら、エンリッチメントの結果を確認できます。

1. **データ** > **エンリッチメント** に移動します。 
1. 情報が必要なエンリッチメントを選択します。

すべてのエンリッチメントには、エンリッチメントされたプロファイルの数、生成されたエンリッチメント エンティティのプレビュー、一定期間のエンリッチメントされたプロファイルの数などの基本情報が表示されます。 可能な場合は、**エンリッチされた顧客のフィールドごとの数** に各エンリッチされたフィールドのカバレッジへのドリルダウンを提供します。

:::image type="content" source="media/enrichments-results.png" alt-text="エンリッチメントの結果ページ。":::

一部のエンリッチメントには、エンリッチメントのタイプに固有の情報も表示されます。 詳細については、関連するエンリッチメントのドキュメントを参照してください。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
