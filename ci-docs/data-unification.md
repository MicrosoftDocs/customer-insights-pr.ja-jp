---
title: 顧客体験の統一ビューを作成する
description: データを使用してデータ統合プロセスを実行し、統合された顧客プロファイルの単一のデータセットを作成します。
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: bb8da6f4b9f92f2b265ff9807e04638edae4f814
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755740"
---
# <a name="data-unification-overview"></a>データの統合の概要

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

[データ ソースの設定](data-sources.md) 後、データを統合できます。 データ統合により、かつては異なっていたデータソースを単一のマスター データセットに統合して、そのデータの統合ビューを提供できます。 データが個人を中心とする個人消費者 (B-to-C) の場合、統合により顧客の統合されたビューが提供されます。 データが取引先企業を中心とするビジネス アカウント (B-to-B) の場合、統合により顧客の統合されたビューが提供されます。

データは、単一のエンティティまたは複数のエンティティに統合できます。 統合は次の順序で実行されます。

1. [ソース フィールド](map-entities.md) (以前はマップと呼ばれていた): ソースフィールドのステップで、統合プロセスに含めるエンティティとフィールドを選択します。 フィールドを、フィールドの目的を説明する一般的なセマンティック タイプにマッピングします。

1. [重複レコード](remove-duplicates.md) (以前は一致の一部): レコードの重複ステップで、オプションとして、各エンティティ内から重複する顧客レコードを削除するルールを定義します。

1. [一致の条件](match-entities.md) (以前は一致と呼ばれていた): 一致条件のステップで、エンティティ間で顧客レコードを一致させるルールを定義します。 顧客が 2 つ以上のエンティティで見つかった場合、各エンティティのすべての列とデータを含む単一の統合レコードが作成されます。

1. [統合された顧客フィールド](merge-entities.md) (以前はマージと呼ばれていた): 統合顧客フィールドのステップで、統合された顧客プロファイルに含める、除外する、またはマージする必要があるソース フィールドを決定します。  

1. [確認](review-unification.md)して、統合プロファイルを作成します。

データの統合が完了したら、オプションで:

- [エンティティ間にリレーションシップを設定](relationships.md)して、洗練されたセグメントを作成します。
- [データを強化](enrichment-hub.md)し、顧客に関する幅広いインサイトを獲得します。
- 取り込んだ属性の一部から [活動を定義](activities.md)できます。
- [対策を構築](measures.md)して、顧客の行動と業績をよりよく理解できます。

[!INCLUDE [footer-include](includes/footer-banner.md)]
