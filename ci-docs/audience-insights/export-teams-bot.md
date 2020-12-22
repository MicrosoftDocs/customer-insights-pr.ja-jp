---
title: Microsoft Teams 用ボット
description: ボットのヘルプを使用して、Microsoft Teams で統合顧客プロファイルを検索します。
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406182"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Dynamics 365 Customer Insights 用 Teams ボット (プレビュー)

Microsoft Teams に接続して、ボットが Teams チャネルで統合顧客プロファイルを検索できるようにします。

> [!div class="mx-imgBorder"]
> ![顧客レコードを表示する Teams ボット](media/teams-bot.png "顧客レコードを表示する Teams ボット")

## <a name="prerequisites"></a>前提条件

ボットを設定して構成するには、次の前提条件を満たす必要があります:

- 少なくとも 1 つの [追加されたデータ ソース](data-sources.md) があります。
- [統合プロセス](data-unification.md) が完了しました。
- フィールドが [検索とフィルター インデックス](search-filter-index.md) に追加されます。
- Customer Insights と Teams は同じ組織内にあります。

## <a name="configure-the-bot"></a>ボットの構成

1. 対象者に関するインサイトで、**管理** > **エクスポート先** に移動します。
1. Microsoft Teams タイルで、**設定** を選択します。
1. Teams の **アプリ** 領域にリダイレクトされます。 Teams を開いて、左下隅にある **アプリ** を選択するか、直接 [AppSource から取得](https://go.microsoft.com/fwlink/?linkid=2124104) することもできます。
1. **Customer Insights** を検索して、アプリを選択します。
1. **追加** を選択します。
1. Teams で Customer Insights にサインインすると、ウェルカム メッセージが表示され、開始できます。

## <a name="things-you-can-do-with-the-bot"></a>ボットでできること

ボットは、統合された顧客プロファイルの検索機能を提供します。

- 検索とフィルターのインデックスに追加された統合された顧客プロファイルで、**検索** に続けて名前、メール アドレス、またはその他のフィールドを入力します。

  得られた顧客プロファイルから、最大 15 フィールドを持つカードを取得します。 複数の一致は、プロファイルを選択できる結果の一覧を返します。 検索語句を二重引用符で囲んで、完全一致を検索できます。

- 組織が同じ組織内に複数の Customer Insights 環境を維持している場合は、**switchinstance** を入力し、ボットを接続する環境を選択できます。

- **ヘルプ** と入力して、ボットで使用できるコマンドのリストを表示します。  
