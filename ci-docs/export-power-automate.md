---
title: Power Automate コネクタ (プレビュー) | Microsoft Docs
description: Dynamics 365 Customer Insights から Microsoft Power Automate のフローを作成します。
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29a861dad926072f6f849d738d868f0f3b9306be
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081388"
---
# <a name="power-automate-connector-preview"></a>Power Automateコネクタ (プレビュー)

データが変更されたときに特定のイベントを自動的にトリガーし、[Microsoft Power Automate](https://flow.microsoft.com/) でより複雑なフローを直接管理します。

## <a name="known-limitations"></a>既知の制限

- 60 秒あたり最大 100 回の呼び出しを実行できます。 $skip パラメーターを使用して、API エンドポイントを複数回呼び出すことができます。 [$skip パラメーターの詳細](/connectors/customerinsights/#get-items-from-an-entity)。

## <a name="power-automate-triggers"></a>Power Automate のトリガー

トリガーを使用してクラウド フローを作成し、通知やより高度なアクションなどの反復的なタスクを自動化します。

- データ ソースの更新が失敗したときにトリガーされます。
- データ ソースの更新が成功したときにトリガーされます。
- セグメントのしきい値を超えたときにトリガーされます。 トリガーは、しきい値を超えると制限されます。
- 業務の計測値のしきい値を超えたときにトリガーされます。 ディメンションのないビジネス メジャーのみがサポートされます。 トリガーは、しきい値を超えると制限されます。
- (データソース、セグメント、メジャーなど) の更新がすべて完了したときに、トリガーします。
- 統合プロセスの更新が完了した場合のトリガー。

[Power Automate でトリガーを構成する。](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate  のアクション

Power Automate のコネクタは、利用可能なトリガー以外のアクションを提供します。 詳細については、『[Dynamics 365 Customer Insights Connector](/connectors/customerinsights/)』を参照してください。

## <a name="create-a-power-automate-flow"></a>Power Automate フローを作成する

1. **管理** > **エクスポート先** へと移動します。

1. **Power Automate** タイルで、**設定** を選択します。

1. Power Automate で Customer Insights コネクタ (プレビュー) が開きます。 Power Automate に **サインイン** します。

1. 使用可能なトリガーの 1 つを選択し、新しいフローにステップを追加します。 詳細については、[Power Automateでクラウド フローを作成する](/power-automate/get-started-logic-flow)を参照してください。

フローの使用方法の例: 
- データ ソースの更新が失敗した場合、Microsoft Teams チャネルにメッセージを投稿します。 
- セグメントのしきい値を超えたときに、データ所有者に E メールを送信します。



[!INCLUDE [footer-include](includes/footer-banner.md)]
