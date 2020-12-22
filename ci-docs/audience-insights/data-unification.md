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
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406157"
---
# <a name="data-unification"></a><span data-ttu-id="0dc4a-103">データ統合</span><span class="sxs-lookup"><span data-stu-id="0dc4a-103">Data unification</span></span>

<span data-ttu-id="0dc4a-104">[データ ソースの設定](data-sources.md) 後、データを統合できます。</span><span class="sxs-lookup"><span data-stu-id="0dc4a-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="0dc4a-105">データ統合には、**マップ**、**一致**、そして **結合** の 3 つのステップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0dc4a-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="0dc4a-106">データ統合プロセスにより、かつてはばらばらだったデータソースを単一のマスター データセットに統合し、顧客の統合ビューを提供できます。</span><span class="sxs-lookup"><span data-stu-id="0dc4a-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="0dc4a-107">統合段階は必須であり、次の順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="0dc4a-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="0dc4a-108">マップ</span><span class="sxs-lookup"><span data-stu-id="0dc4a-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="0dc4a-109">一致</span><span class="sxs-lookup"><span data-stu-id="0dc4a-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="0dc4a-110">統合</span><span class="sxs-lookup"><span data-stu-id="0dc4a-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="0dc4a-111">データの統合が完了したら、オプションで</span><span class="sxs-lookup"><span data-stu-id="0dc4a-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="0dc4a-112">[エンティティ間にリレーションシップを設定](relationships.md) して、高度なセグメントを作成できます</span><span class="sxs-lookup"><span data-stu-id="0dc4a-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="0dc4a-113">[データを強化](enrichment-hub.md) して、顧客に関する幅広いインサイトを獲得できます</span><span class="sxs-lookup"><span data-stu-id="0dc4a-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="0dc4a-114">取り込んだ属性の一部から [活動を定義](activities.md) できます</span><span class="sxs-lookup"><span data-stu-id="0dc4a-114">[define activities](activities.md) from some of the ingested attributes</span></span>
