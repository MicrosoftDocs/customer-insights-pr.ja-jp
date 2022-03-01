---
title: サポートされている予測シナリオの概要
description: Dynamics 365 Customer Insights アプリケーションで対応する予測シナリオとオプション。
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 57c61895d636273fc90a0ac5a942fd0c9abf583c687ae20621949554e581cdf8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036015"
---
# <a name="predictions-overview"></a>予測の概要

Dynamics 365 Customer Insights には、AI や機械学習を活用してデータを予測するさまざまなオプションが用意されています。 

## <a name="out-of-box-models"></a>標準モデル

データの予測を開始する最も簡単な方法は、事前定義されたモデルであり、多くの場合、標準モデルと呼ばれます。 特定のデータと構造があれば、インサイトをすばやく生成することができます。 現在、以下のモデルが使用可能です: 
- [顧客の生涯価値](predict-customer-lifetime-value.md): ビジネスとのやり取り全体を通じて、顧客の潜在的な売上を予測します。 
- [製品推奨](predict-product-recommendation.md): 購入行動や類似の購入パターンを持つ顧客に基づいて、予測製品推奨セットを提案します。
- [サブスクリプション離反](predict-subscription-churn.md): 顧客が自社のサブスクリプション製品やサービスを使用しなくなるリスクがあるかどうかを予測します。
- [トランザクション離反](predict-transactional-churn.md): 顧客が一定期間内に製品やサービスを購入しなくなるかどうかを予測します。

## <a name="azure-machine-learning-integration"></a>Azure Machine Learning 統合

組織が既に Azure Machine Learning の実験に基づく機械学習シナリオを使用している場合、Customer Insights のカスタム モデル機能はドットを関連付けるのに役立ちます。 インサイトを生成するデータの選択に役立つワークフローを作成し、結果を統合された顧客プロファイルにマップします。 詳細については、[カスタム機械学習モデル](custom-models.md) を参照してください。

## <a name="ai-builder-prediction"></a>AI Builder の予測

データ セットが不完全で、一部の値が欠落している場合があります。 Customer Insights は、顧客エンティティとセグメントの不足している値を予測するのに役立ちます。 詳細については、[予測を使用した部分データの完成](predictions.md) を参照してください。
