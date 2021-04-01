---
title: データ統合
description: 取り込んだデータを統合する方法について説明します。
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 73d8006c670268420f8cd6a2b37cb214ba1bbd6c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597885"
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