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
# <a name="data-unification-overview"></a><span data-ttu-id="33907-103">データの統合の概要</span><span class="sxs-lookup"><span data-stu-id="33907-103">Data unification overview</span></span>

<span data-ttu-id="33907-104">[データ ソースの設定](data-sources.md) 後、データを統合できます。</span><span class="sxs-lookup"><span data-stu-id="33907-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="33907-105">データ統合には、**マップ**、**一致**、そして **結合** の 3 つのステップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="33907-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="33907-106">データ統合プロセスにより、かつてはばらばらだったデータソースを単一のマスター データセットに統合し、顧客の統合ビューを提供できます。</span><span class="sxs-lookup"><span data-stu-id="33907-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="33907-107">統合段階は必須であり、次の順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="33907-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="33907-108">マップ</span><span class="sxs-lookup"><span data-stu-id="33907-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="33907-109">一致</span><span class="sxs-lookup"><span data-stu-id="33907-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="33907-110">統合</span><span class="sxs-lookup"><span data-stu-id="33907-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="33907-111">データの統合が完了したら、オプションで</span><span class="sxs-lookup"><span data-stu-id="33907-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="33907-112">[エンティティ間にリレーションシップを設定](relationships.md) して、高度なセグメントを作成できます</span><span class="sxs-lookup"><span data-stu-id="33907-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="33907-113">[データを強化](enrichment-hub.md) して、顧客に関する幅広いインサイトを獲得できます</span><span class="sxs-lookup"><span data-stu-id="33907-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="33907-114">取り込んだ属性の一部から [活動を定義](activities.md) できます</span><span class="sxs-lookup"><span data-stu-id="33907-114">[define activities](activities.md) from some of the ingested attributes</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]