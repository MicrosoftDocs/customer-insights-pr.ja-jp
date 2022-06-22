---
title: Customer Insights におけるサービス制限
description: Customer Insights SaaS サービスにおける制限や制約を理解していること。
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940674"
---
# <a name="service-limits-in-customer-insights"></a>Customer Insights におけるサービス制限

この記事では、 Customer Insights サービスの組み込み制限について説明します。これはサービスの信頼性と安定性を確保する目的で設計されています。 変更に対する要求はすべて、 [アイデアフォーラム](https://go.microsoft.com/fwlink/?linkid=2074172) を通しておこなうことができます。

## <a name="customer-insights"></a>Customer Insights

| 領域  | 制限  | メモ  |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| セグメント、メジャー、および予測 | 300  | [セグメント](segments.md)、[メジャー](measures.md)、および[予測](predictions.md)の合計は、300 を超えることはできません。  |
| 顧客間関係 | エンティティ パスの関係性には、20 段階の深さがあります。 | ビルダーのインターフェイスを使用して[セグメント](segments.md)または[メジャー](measures.md)を作成する場合、エンティティ パスでは、開始エンティ ティとターゲット・エンティティの間に最大 20 のリレーションシップ・ホップを設定できます。  |

## <a name="fair-scheduling-of-jobs"></a>ジョブの公平なスケジューリング

Customer Insights は、Azure の共有リソースを利用する SaaS サービスです。 顧客は、さまざまなスケジュールで、さまざまな強度の業務を抱えている傾向があります。 また、システム プロセスが公正な順序で実行されるよう、基盤となるリソースへの公正なアクセスを保証しています。 システム プロセスの例としては、データの統一、セグメントの更新、メジャーの計算などに関連するジョブがあります。 公平なスケジューリングにより、要求されたジョブが急増した場合に、リソースをキューに入れることができなくなります。 同時に、Customer Insights は、キューに入れたすべてのジョブが並列処理されることを保証するものではありません。

[!INCLUDE [footer-include](includes/footer-banner.md)]
