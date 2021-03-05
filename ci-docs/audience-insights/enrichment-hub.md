---
title: 統合顧客プロファイルを強化する
description: 機能を使用して、顧客データを強化します。
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269474"
---
# <a name="enrichment-for-customer-profiles-preview"></a>顧客プロファイルを拡充させる (プレビュー版)

Microsoft やその他のパートナーなどのソースからのデータを使用して、顧客データを拡充させます。

:::image type="content" source="media/enrichment-hub-page.png" alt-text="エンリッチメント ハブ ページ":::

対象者に関するインサイトで、**データ** > **エンリッチメント** に移動し、エンリッチメント オプションを使用します。    
エンリッチメントを作成、編集するには、コントリビューターまたは管理者権限が必要です。 詳細については、[権限](permissions.md)を参照してください。

**検出** タブでは、次のような拡充機能があります :

- Microsoft Graph が提供する [ブランド](enrichment-microsoft-graph.md)
- Microsoft Graph が提供する [関心](enrichment-microsoft-graph.md)
- Leadspace が提供する [会社データ](enrichment-leadspace.md)
- Experian が提供する [人口統計](enrichment-experian.md)
- HERE Technologies が提供する [位置データ](enrichment-here.md)
- セキュリティで保護されたファイル転送プロトコル (SFTP) による [カスタム データ](enrichment-SFTP-custom-import.md)

**自分のエンリッチメント** タブでは、設定した拡充を表示し、そのプロパティを編集することができます。

## <a name="manage-existing-enrichments"></a>既存のエンリッチメントの管理

**自分のエンリッチメント** に移動し、構成されたすべてのエンリッチメントを表示します。 各エンリッチメントは、エンリッチメントに関する追加情報を含む行として表されます。

エンリッチメントを選択して、利用可能なオプションを表示します。 または、リスト項目の省略記号 (...) を選択して、オプションを表示することもできます。

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="エンリッチメントの一覧でエンリッチメントを管理するオプション":::

- 強化された顧客プロファイルの数を使用して、エンリッチメントの詳細を **表示** します。
- エンリッチメント構成を **編集** します。
- 最新のデータで顧客プロファイルを更新するためのエンリッチメントを **実行** します。
- 既存のエンリッチメントを **非アクティブ化** して、スケジュールされた更新のたびに自動更新されないようにします。 最後に成功した更新のデータは引き続き使用できます。 非アクティブなエンリッチメントを **活性化** し、スケジュールされた更新ごとに自動更新を再開します。
- エンリッチメントを **削除** します。

リストで複数のエンリッチメントを選択して、一度に実行または非アクティブ化できます。 表示と編集のオプションは一括アクションとして使用できず、一度に 1 つのエンリッチメントに対してのみ機能します。


[!INCLUDE[footer-include](../includes/footer-banner.md)]