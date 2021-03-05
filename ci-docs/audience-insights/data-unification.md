---
title: データ統合
description: 取り込んだデータを統合する方法について説明します。
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 44f97696ec91dc488dd6a7528e186abb99c8288b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269658"
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