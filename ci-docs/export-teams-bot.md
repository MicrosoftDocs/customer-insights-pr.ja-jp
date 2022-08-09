---
title: Dynamics 365 Customer Insights 用 Teams ボット (プレビュー)
description: ボットのヘルプを使用して、Microsoft Teams で統合顧客プロファイルを検索します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195848"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Dynamics 365 Customer Insights 用 Teams ボット (プレビュー)

Microsoft Teams に接続して、ボットが Teams チャネルで統合顧客プロファイルを検索できるようにします。

:::image type="content" source="media/teams-bot.png" alt-text="顧客レコードを表示する Teams ボット":::

## <a name="prerequisites"></a>前提条件

- 少なくとも 1 つの [追加されたデータ ソース](data-sources.md)。
- [統合プロセス](data-unification.md) が完了しました。
- フィールドが [検索とフィルター インデックス](search-filter-index.md) に追加されます。
- Customer Insights と Teams は同じ組織内にあります。
- ご使用の環境では、プライマリ ターゲット対象者が個人顧客に設定されています。 ビジネス アカウントはサポートされていません。


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>ボットの構成

1. **管理** > **接続** に移動します。
1. Microsoft Teams タイルで、**設定** を選択します。
1. Teams の **アプリ** 領域にリダイレクトされます。 Teams を開いて、左下隅にある **アプリ** を選択するか、直接 [AppSource から取得](https://go.microsoft.com/fwlink/?linkid=2124104) することもできます。
1. **Customer Insights** を検索して、アプリを選択します。
1. **追加** を選択します。
1. Teams で Customer Insights に サインイン します。 ウェルカム メッセージが表示されます。

## <a name="things-you-can-do-with-the-bot"></a>ボットでできること

ボットは、統合された顧客プロファイルの検索機能を提供します。

- 検索とフィルターのインデックスに追加された統合された顧客プロファイルで、**検索** に続けて名前、メール アドレス、またはその他のフィールドを入力します。

  得られた顧客プロファイルから、最大 15 フィールドを持つカードを取得します。 複数の一致は、プロファイルを選択できる結果の一覧を返します。 完全一致を検索するには、検索語句を二重引用符で囲みます。

- 組織が同じ組織内に複数の Customer Insights 環境を維持している場合は、**switchinstance** を入力し、ボットを接続する環境を選択します。

- **ヘルプ** と入力して、ボットで使用できるコマンドのリストを表示します。  

[!INCLUDE [footer-include](includes/footer-banner.md)]