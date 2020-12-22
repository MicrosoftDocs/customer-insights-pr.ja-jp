---
title: エクスポート先
description: データをエクスポートし、エクスポート先を管理します。
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643869"
---
# <a name="export-destinations-preview"></a>エクスポート先 (プレビュー)

**エクスポート先** ページには、データのエクスポート先として設定したすべての場所が表示されます。 エクスポートには新しい宛先を追加することもできます。 さらに、現在利用可能なエクスポート オプションが表示されます。 概要や説明を参照し、各拡張オプションでできることを確認してください。 統一されたプロファイル、メジャーおよびセグメントを業務に関連するサポート対象のアプリケーションにエクスポートします。

**管理者** > **エクスポート先** へと移動し、次の拡張オプションを見つけます。

- [Dynamics 365 顧客カードのアドイン](customer-card-add-in.md)
- [Facebook 広告マネージャ コネクタ](export-facebook.md)
- [Power Automate コネクタ](export-power-automate.md)
- [Power Apps コネクタ](export-power-apps.md)
- [Power BI コネクタ](export-power-bi.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 の販売](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Azure Blob Storage](export-azure-blob-storage.md)
- [LiveRamp&reg; コネクタ](export-liveramp.md)
- [Microsoft Teams 用ボット](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [Customer Insights API](apis.md)

## <a name="add-a-new-export-destination"></a>新しいエクスポート先を追加する

エクスポート先を追加するするために、[管理者のアクセス許可](permissions.md) があります。 Microsoft サービスにエクスポートする場合、両方のサービスが同じ組織にあると見なされます。

1. **管理** > **エクスポート先** へと移動します。

1. **自分のエクスポート先** タブに切り替えます。

1. **エクスポート先の追加** を選択して、新しいエクスポート先を作成します。

1. **エクスポート先の追加** ウィンドウで、ドロップダウンでエクスポート先の **種別** を選択します。

1. 必要な詳細を入力し、**次へ** て選択してエクスポート先を作成します。

**検出** タブのタイルで、**設定** を選択することもできます。

## <a name="view-export-destinations"></a>エクスポート先を表示する

エクスポート先を作成すると、**自分のエクスポート先** タブのテーブルに表示されます。このテーブルには 3 つの列があります:

- **表示名**：エクスポートの出力先を作成した時に入力した名前。
- **種別**: エクスポートの出力先を作成した時に設定した出力先の種別。
- **作成日**: エクスポートの出力先が作成された日付。

## <a name="edit-an-export-destination"></a>エクスポート先を編集する

1. 編集するエクスポート先の垂直方向の省略記号を選択します。

   > [!div class="mx-imgBorder"]
   > ![垂直方向の省略記号](media/export-destinations-page-ellipsis.png "垂直方向の省略記号")

1. ドロップダウン メニューから **編集** を選択します。

1. 更新が必要な値を変更して、**保存** を選択します。

## <a name="export-data-on-demand"></a>オンデマンドでデータをエクスポートする

エクスポート先のコネクタを構成すると、[スケジュールされた更新](system.md#schedule-tab) ごとにエクスポートが実行されます。

スケジュールされた更新を待たずにデータをエクスポートするには、**管理** > **エクスポート先** の **自分のエクスポート先** タブに移動します。

> [!div class="mx-imgBorder"]
> ![垂直方向の省略記号](media/export-destinations-page-ellipsis.png "垂直方向の省略記号")

- リストの上にある **エクスポート** を選択して、すべてのエクスポート先へのエクスポートを同時に実行します。
- リスト項目の後の省略記号 (...) を選択し、**エクスポート** オプションを選択して、単一のエクスポート先に対してエクスポートを実行します。

## <a name="remove-an-export-destination"></a>エクスポート先を削除する

エクスポート先を削除するには、メインの **エクスポート先** ページから開始します。

1. 削除するエクスポート先の垂直方向の省略記号を選択します。

   > [!div class="mx-imgBorder"]
   > ![垂直方向の省略記号](media/export-destinations-page-ellipsis.png "垂直方向の省略記号")

2. ドロップダウン メニューで **削除** を選択します。

3. 確認画面で **削除** を選択して削除を確認します。
