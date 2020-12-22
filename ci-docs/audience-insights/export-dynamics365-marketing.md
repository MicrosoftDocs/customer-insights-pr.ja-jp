---
title: Customer Insights のデータを Dynamics 365 Marketing にエクスポートする
description: Dynamics 365 Marketing への接続を構成する方法について説明します。
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643779"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Dynamics 365 Marketing のコネクタ (プレビュー)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[セグメント](segments.md) を使用してキャンペーンを生成し、Dynamics 365 Marketing を使用して特定の顧客グループに連絡します。 詳しくは、[Dynamics 365 Marketing で Dynamics 365 Customer Insights のセグメントを使用する](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)を参照してください。

## <a name="prerequisite"></a>前提条件

[Dynamics 365 Marketing が取り込んだ Common Data Service](connect-power-query.md) の取引先担当者レコード。

## <a name="configure-the-connector-for-marketing"></a>Marketing 用のコネクタを構成する

1. 対象者に関するインサイトで、**管理** > **エクスポート先** に移動します。

1. **Dynamics 365 Marketing** で **設定** を選択します。

1. **表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。

1. **サーバー アドレス** フィールドに組織の Marketing URL を入力します。

1. **サーバー管理者アカウント** セクションで、**サインイン** を選択し、Dynamics 365 Marketing アカウントを選択します。

1. 顧客 ID フィールドを Dynamics 365 取引先担当者 ID にマップします。

1. **次へ** を選択します。

1. 1つ、または複数のセグメントを選択します。

1. **保存** を選択します。

## <a name="export-the-data"></a>データをエクスポートする

[オンデマンドでデータをエクスポート](export-destinations.md) できます。 エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。
