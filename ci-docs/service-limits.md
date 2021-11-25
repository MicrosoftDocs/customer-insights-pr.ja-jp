---
title: Dynamics 365 Customer Insights のサービス制限
description: 制限と制約について理解します。
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791987"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Customer Insights の機能におけるサービス制限

この記事では、 Customer Insights サービスの組み込み制限について説明します。これはサービスの信頼性と安定性を確保する目的で設計されています。 変更に対する要求はすべて、 [アイデアフォーラム](https://go.microsoft.com/fwlink/?linkid=2074172) を通しておこなうことができます。 

## <a name="audience-insights"></a>対象者分析情報

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights 対象者に関するインサイト機能のサービス制限

| 面グラフ  | 制限  | メモ  |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| セグメント、メジャー、および予測 | 300  | [セグメント](audience-insights/segments.md)、[メジャー](audience-insights/measures.md)、および[予測](audience-insights/predictions.md)の合計は、300 を超えることはできません。  |
| 顧客間関係 | エンティティ パスの関係性には、20 段階の深さがあります。 | ビルダーのインターフェイスを使用して[セグメント](audience-insights/segments.md)または[メジャー](audience-insights/measures.md)を作成する場合、エンティティ パスでは、開始エンティ ティとターゲット・エンティティの間に最大 20 のリレーションシップ・ホップを設定できます。  |


## <a name="engagement-insights"></a>エンゲージメント分析情報

### <a name="workspace-and-event-quotas"></a>ワークスペースとイベントの割り当て

エンゲージメント インサイトは、毎秒数百万のイベントをサポートできる非常にスケーラブルなアプリケーションです。 パブリック プレビュー中、イベントにはボリュームのしきい値があります。 組織内のワークスペースの数にも制限があります。

### <a name="engagement-insights-limits"></a>エンゲージメント インサイトの制限

- ワークスペースあたりの最大イベント数 = 毎秒 100 イベント

- 組織あたりの最大ワークスペース数 = 100

イベントがしきい値を超えると、それらのイベントに基づくレポートのデータが失われる可能性があります。 制限を超過する前に、[サポートに連絡](https://go.microsoft.com/fwlink/?linkid=2145734) することでボリュームの増加をリクエストできます。 Microsoft は顧客と協力して、ボリューム増加の必要性を判断し、リクエストをサポートします。


[!INCLUDE[footer-include](includes/footer-banner.md)]
