---
title: 顧客体験の統一ビューを作成する
description: データを使用してデータ統合プロセスを実行し、顧客プロファイルの単一のマスター データセットを作成します。
ms.date: 10/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-unify
ms.openlocfilehash: c5422c9b60c21923caf4d9dc9baeec575cba093f
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977465"
---
# <a name="data-unification-overview"></a>データの統合の概要

[データ ソースの設定](data-sources.md) 後、データを統合できます。 データ統合には、**マップ**、**一致**、そして **結合** の 3 つのステップが含まれます。

データ統合プロセスにより、かつてはばらばらだったデータソースを単一のマスター データセットに統合し、顧客の統合ビューを提供できます。 統合段階は必須であり、次の順序で実行されます。

1. [マップ](map-entities.md)
2. [一致](match-entities.md)
3. [統合](merge-entities.md)

データの統合が完了したら、オプションで

- [エンティティ間にリレーションシップを設定](relationships.md) して、高度なセグメントを作成できます
- [データを強化](enrichment-hub.md) して、顧客に関する幅広いインサイトを獲得できます
- 取り込んだ属性の一部から [活動を定義](activities.md) できます


[!INCLUDE[footer-include](../includes/footer-banner.md)]