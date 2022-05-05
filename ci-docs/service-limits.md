---
title: Dynamics 365 Customer Insights のサービス制限
description: 制限と制約について理解します。
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641768"
---
# <a name="service-limits-in-customer-insights"></a>Customer Insights におけるサービス制限

この記事では、 Customer Insights サービスの組み込み制限について説明します。これはサービスの信頼性と安定性を確保する目的で設計されています。 変更に対する要求はすべて、 [アイデアフォーラム](https://go.microsoft.com/fwlink/?linkid=2074172) を通しておこなうことができます。 

## <a name="customer-insights"></a>Customer Insights

| 領域  | 制限  | メモ  |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| セグメント、メジャー、および予測 | 300  | [セグメント](segments.md)、[メジャー](measures.md)、および[予測](predictions.md)の合計は、300 を超えることはできません。  |
| 顧客間関係 | エンティティ パスの関係性には、20 段階の深さがあります。 | ビルダーのインターフェイスを使用して[セグメント](segments.md)または[メジャー](measures.md)を作成する場合、エンティティ パスでは、開始エンティ ティとターゲット・エンティティの間に最大 20 のリレーションシップ・ホップを設定できます。  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
