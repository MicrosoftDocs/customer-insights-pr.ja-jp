---
title: Power Automate コネクタ (プレビュー) | Microsoft Docs
description: Dynamics 365 Customer Insights から Microsoft Power Automate のフローを作成します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196124"
---
# <a name="power-automate-connector-preview"></a>Power Automateコネクタ (プレビュー)

データが変更されたときに特定のイベントを自動的にトリガーし、[Microsoft Power Automate](https://flow.microsoft.com/) でより複雑なフローを直接管理します。

## <a name="known-limitations"></a>既知の制限

- 60 秒あたり最大 100 回の呼び出し。 [$skip パラメーター](/connectors/customerinsights/#get-items-from-an-entity) を使用して、API エンドポイントを複数回呼び出します。

## <a name="power-automate-triggers"></a>Power Automate のトリガー

トリガーを使用してクラウド フローを作成し、通知やより高度なアクションなどの反復的なタスクを自動化します。 次の場合にトリガーを使用します。

- データ ソースの更新に失敗した。
- データ ソースの更新に成功した。
- セグメントのしきい値を超えた。 トリガーは、しきい値を超えると制限されます。
- 業務の計測値のしきい値を超えた。 ディメンションのないビジネス メジャーのみがサポートされます。 トリガーは、しきい値を超えると制限されます。
- フル スケジュール更新が完了した。 このトリガーは、手動で開始された更新では機能しません。
- 統合プロセスの更新が完了した。

[Power Automate でトリガーを構成する。](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate  のアクション

Power Automate のコネクタは、利用可能なトリガー以外のアクションを提供します。 詳細については、『[Dynamics 365 Customer Insights Connector](/connectors/customerinsights/)』を参照してください。

## <a name="create-a-power-automate-flow"></a>Power Automate フローを作成する

1. **管理** > **接続** に移動します。

1. **Power Automate** タイルで、**設定** を選択します。

1. Power Automate で Customer Insights コネクタ (プレビュー) が開きます。 Power Automate に **サインイン** します。

1. 使用可能なトリガーの 1 つを選択し、新しいフローにステップを追加します。 詳細については、[Power Automateでクラウド フローを作成する](/power-automate/get-started-logic-flow)を参照してください。

フローの使用方法の例: 
- データ ソースの更新が失敗した場合、Microsoft Teams チャネルにメッセージを投稿します。 
- セグメントのしきい値を超えたときに、データ所有者に E メールを送信します。

[!INCLUDE [footer-include](includes/footer-banner.md)]
