---
title: 統合顧客プロファイルを強化する
description: 機能を使用して、顧客データを強化します。
ms.date: 07/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: a64bbd754d4013d0a6243074ac9f55991547be82b269047a9937b583baf98697
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032534"
---
# <a name="enrichment-for-customer-profiles-preview"></a>顧客プロファイルを拡充させる (プレビュー版)

Microsoft やその他のパートナーなどのソースからのデータを使用して、顧客データを拡充させます。

:::image type="content" source="media/enrichment-hub-page.png" alt-text="エンリッチメント ハブ ページ。":::

対象者に関するインサイトで、**データ** > **エンリッチメント** に移動し、エンリッチメント オプションを使用します。  

エンリッチメントを作成、編集するには、コントリビューターまたは管理者権限が必要です。 詳細については、[権限](permissions.md)を参照してください。

**検出** タブでは、次のような拡充機能があります :

- Microsoft が提供する [ブランド](enrichment-microsoft.md)
- Microsoft が提供する [関心](enrichment-microsoft.md)
- Microsoft が提供する [拡張住所](enrichment-enhanced-addresses.md)
- Leadspace が提供する [会社データ](enrichment-leadspace.md)
- Experian が提供する [人口統計情報](enrichment-experian.md)
- HERE Technologies が提供する [位置データ](enrichment-here.md)
- セキュリティで保護されたファイル転送プロトコル (SFTP) による [カスタム データ](enrichment-SFTP-custom-import.md)

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

サード パーティのエンリッチメントは、管理者が資格情報を使用して設定し、データ転送の同意を提供する [接続](connections.md) を使用して構成されます。 管理者と共同作成者は接続を使用して、エンリッチメントを構成できます。  

## <a name="multiple-enrichments-of-the-same-type"></a>同じ種類の複数のエンリッチメント

強化されるエンティティは、エンリッチメントの構成中に指定され、プロファイルのサブセットのみを強化できます。 たとえば、特定のセグメントのデータのみをエンリッチします。 同じ種類の複数のエンリッチメントを構成し、同じ接続を再利用できます。 一部のエンリッチメントには、作成できる同じ種類のエンリッチメントの数に制限があります。 制限と現在の使用状況は **エンリッチメント** ページで確認できます。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
