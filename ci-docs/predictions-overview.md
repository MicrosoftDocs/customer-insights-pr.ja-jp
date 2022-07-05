---
title: 予測の概要
description: Dynamics 365 Customer Insights アプリケーションで対応する予測シナリオとオプション。
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: a87af80fa713a1ac70493345c0c920e416692b0f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081695"
---
# <a name="predictions-overview"></a>予測の概要

Dynamics 365 Customer Insights には、AI や機械学習を活用してデータを予測するさまざまなオプションが用意されています。 

## <a name="out-of-box-models"></a>標準モデル

データの予測を開始する最も簡単な方法は、事前定義されたモデルであり、多くの場合、標準モデルと呼ばれます。 特定のデータと構造があれば、インサイトをすばやく生成することができます。 現在、以下のモデルが使用可能です: 

# <a name="individual-consumers-b-to-c"></a>[個人消費者 (B2C)](#tab/b2c)

- [顧客の生涯価値](predict-customer-lifetime-value.md): ビジネスとのやり取り全体を通じて、顧客の潜在的な売上を予測します。
- [製品推奨](predict-product-recommendation.md): 購入行動や類似の購入パターンを持つ顧客に基づいて、予測製品推奨セットを提案します。
- [サブスクリプション離反](predict-subscription-churn.md): 顧客が自社のサブスクリプション製品やサービスを使用しなくなるリスクがあるかどうかを予測します。
- [トランザクション離反](predict-transactional-churn.md): 顧客が一定期間内に製品やサービスを購入しなくなるかどうかを予測します。
- [感情分析](sentiment-analysis.md): 顧客のフィードバックの感情を分析し、頻繁に言及されるビジネスに関する意見を特定します。

# <a name="business-accounts-b-to-b"></a>[事業取引先企業 (B2B)](#tab/b2b)

- [トランザクション離反](predict-transactional-churn.md): 顧客が一定期間内に製品やサービスを購入しなくなるかどうかを予測します。

---

> [!TIP]
> 更新されたデータを使用してすぐに使用できるモデルを定期的に更新し、ビジネスのユース ケースを正確に通知することをお勧めします。 システムが新しいデータ ソースや更新されたデータ ソースを取り込むと、データはアドホックに更新されます。 ただし、モデルはこの場合にのみ再スコアリングし、既存のトレーニング データを引き続き使用します。
> 
> **更新スケジュール** を構成するには、構成エクスペリエンスでモデルの再トレーニング スケジュールを設定します。 モデルはこのスケジュールで再トレーニングと再スコアリングを行います。このスケジュールはいつでも変更できます。


## <a name="azure-machine-learning-integration"></a>Azure Machine Learning 統合

組織が既に Azure Machine Learning の実験に基づく機械学習シナリオを使用している場合、Customer Insights のカスタム モデル機能はドットを関連付けるのに役立ちます。 インサイトを生成するデータの選択に役立つワークフローを作成し、結果を統合された顧客プロファイルにマップします。 詳細については、[カスタム機械学習モデル](custom-models.md) を参照してください。

## <a name="ai-builder-prediction"></a>AI Builder の予測

データ セットが不完全で、一部の値が欠落している場合があります。 Customer Insights は、顧客エンティティとセグメントの不足している値を予測するのに役立ちます。 詳細については、[予測を使用した部分データの完成](predictions.md) を参照してください。
