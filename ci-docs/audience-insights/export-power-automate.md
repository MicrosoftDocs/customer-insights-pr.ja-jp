---
title: Power Automate コネクタ | Microsoft Docs
description: Dynamics 365 Customer Insights から Microsoft Power Automate でフローを作成します。
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406149"
---
# <a name="power-automate-connector-preview"></a>Power Automateコネクタ (プレビュー)

データが変更されたときに特定のイベントを自動的にトリガーし、[Power Automate](https://flow.microsoft.com/) でより複雑なフローを直接管理します。

## <a name="power-automate-triggers"></a>Power Automate のトリガー

さまざまなトリガーを使用して、通知やその他の高度なアクションなどの反復タスクを自動化するフローを作成できます。 

- データ ソースの更新が失敗したときにトリガーされます。 
- データ ソースの更新が成功したときにトリガーされます。
- セグメントのしきい値を超えたときにトリガーされます。 トリガーは、しきい値を超えると制限されます。
- 業務の計測値のしきい値を超えたときにトリガーされます。 トリガーは、しきい値を超えると制限されます。
- (データソース、セグメント、メジャーなど) の完全更新が完了したときに、トリガーします。
- 統合プロセス (マップ、照合、結合) の更新が完了したときにトリガーします。

[Power Automateでトリガーを構成する](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)。

## <a name="power-automate-actions"></a>Power Automate  のアクション
Power Automate のコネクタは、利用可能なトリガー以外のアクションを提供します。 詳細については、『[Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/)』を参照してください。

## <a name="create-a-power-automate-flow-in-audience-insights"></a>対象者に関するインサイトで Power Automate フローを作成する

1. 対象者に関するインサイトで、**管理** > **システム** に移動します。

1. **システム** ページで、**状態** タブを選択します。

1. **データソース** セクションの中に、**フロー** を選択し、ドロップダウンリストから **フローの作成** を選択します。
   > [!div class="mx-imgBorder"]
   > ![フローアクションの作成を示す Power Automate コネクタ](media/power-automate-connector-create-flow.png "フロー アクションの作成を示す Power Automate コネクタ")

1. Power Automate で、使用可能なトリガーの 1 つを選択して、優先フローを作成します。 最初のフローを作成する場合は、最初に Power Automate コネクタで認証する必要があります。
