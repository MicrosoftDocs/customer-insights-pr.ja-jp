---
title: PowerQuery ベースのデータ ソースの増分更新
description: Power Query に基づいて、大規模なデータ ソースの新規および更新されたデータを更新します。
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: f614d701aeb06720a60b14549a7fe666f8fe0617
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900274"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Power Query ベースのデータ ソースの増分更新

この記事では、Power Query に基づいてデータ ソースの増分更新を構成する方法について説明します。

データ ソースの増分更新には、次の利点があります:

- **更新速度の増強** - 変更のあったデータのみが更新されます。 例えば、履歴データセットの過去 5 日間だけを更新することができます。
- **安定性の増加** - 更新の規模を縮小化することで、揮発性のソース システムへの接続を長期間維持する必要がなくなり、接続の問題が発生するリスクが軽減されます。
- **リソース消費の軽減** - データ全体の一部のみを更新することで、コンピューター上のリソース使用効率が向上し、環境への負荷が軽減します。

## <a name="configure-incremental-refresh"></a>増分更新を構成する

対象者に関するインサイトでは、増分取り込みをサポートする Power Query でインポートしたデータ ソースの増分更新が可能です。 たとえば、データ レコードが最後に更新された日付と時刻のフィールドを持つ Azure SQL データベースなどです。

1. [Power Query に基づいて新しいデータ ソースを作成します](connect-power-query.md)。

1. データ ソースの **名前** を入力してください。

1. [Azure SQL データベース](/power-query/connectors/azuresqldatabase)などの、増分更新に対応するデータ ソースを選択します。

1. 取り込むエンティティまたはテーブルを選択します。

1. この変換の手順を完了し、**保存** を選択します。

1. **増分更新を設定する** ダイアログ ボックスで、**設定** を選択して、**増分更新の設定** を開きます。 **スキップ** を選択すると、データソースがデータセット全体を更新します。
   > [!TIP]
   > 既存のデータ ソースを編集することで、増分更新を後から適用することも可能です。

1. **増分更新の設定** にて、データ ソースの作成時に選択したすべてのエンティティーの増分更新を構成します。

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="データソースのエンティティの増分更新を設定する。":::

1. エンティティを選択し、次の詳細を指定します：

   - **主キーの設定**：エンティティまたはテーブルの主キーを選択します。
   - **最終更新フィールドの設定**：このフィールドには、日付または時刻タイプの属性のみが表示されます。 レコードが最後に更新された日時を示す属性を選択します。 これは、増分更新概算時間枠内にあるレコードを識別するために使用されます。
   - **すべての更新を確認する**：増分更新の時間枠の長さを指定します。

1. **保存** を選択して、データ ソースの作成を完了します。 最初のデータ更新は全体の更新になります。 その後の更新からは、上記手順で設定したように増分の更新が行われます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
