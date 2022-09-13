---
title: システム更新のスケジューリング
description: システムを更新する時間をスケジュールする
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 949ea071ca41127b0c45488d5d7af3f6aa4e1c35
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395962"
---
# <a name="schedule-system-refresh"></a>システム更新のスケジューリング

すべての [取り込んだデータ ソース](data-sources.md) の自動更新をスケジュールします。 自動更新により、データソースの更新が統一された顧客プロファイルに確実に反映されます。

> [!NOTE]
> ユーザーが管理する Power Query データ ソースは、独自のスケジュールで更新されます。 Power Query データ ソースの更新をスケジュールするには、**データ ソース** ページでその特定のデータ ソースの更新設定を構成します。
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform データフローの更新設定。":::

## <a name="set-system-refresh-schedule"></a>システムの更新スケジュールを設定する

1. **管理者** > **システム** に移動して、**スケジュール** タブを選択します。

   :::image type="content" source="media/schedule_refresh.png" alt-text="[システム] ページの [スケジュール更新] タブ。":::

1. スケジュールされた更新の規定の状態は **オフ** です。 スケジュールされた更新を有効にするには、画面上部のトグルを **ON** に変更します。

1. **毎週** の更新(デフォルト) か **毎日** の更新を選択します。 毎週更新をスケジュールする場合は、更新を実行する日を 1 日以上選択します。

1. **タイム ゾーン** を設定し、続いて **時間** ドロップダウンで更新のタイミングを設定します。 1 日に複数の更新をスケジュールする場合は、**別の時間を追加** を選択します。 最大 4 つリフレッシュを追加できます。

1. **保存** を選択して変更を適用します。

[!INCLUDE [footer-include](includes/footer-banner.md)]
