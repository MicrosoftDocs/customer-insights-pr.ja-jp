---
title: サービス制限
description: 制限と制約について理解します。
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 81253332cbea3110c0b3804db3a4d03b514f92d4
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604375"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights 対象者に関するインサイト機能のサービス制限

この記事では、 Customer Insights サービスの組み込み制限について説明します。これはサービスの信頼性と安定性を確保する目的で設計されています。 変更に対する要求はすべて、 [アイデアフォーラム](https://go.microsoft.com/fwlink/?linkid=2074172) を通しておこなうことができます。 
 
| 面グラフ  | 制限  | メモ  |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| セグメントとメジャー | 100 セグメントまたはメジャー。 | アクティブな [セグメント](segments.md) と [メジャー](measures.md) の総数の合計は 100 を超えることはできません。  |
| 関係 | エンティティ パスの関係性には、20 段階の深さがあります。 | ビルダーのインターフェイスを使用して[セグメント](segments.md)または[メジャー](measures.md)を作成する場合、エンティティ パスでは、開始エンティ ティとターゲット・エンティティの間に最大 20 のリレーションシップ・ホップを設定できます。  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]