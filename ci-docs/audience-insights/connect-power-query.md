---
title: Power Query コネクタを使用してデータを取り込む
description: Power Queryに基づくデータソース用のコネクタです。
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305897"
---
# <a name="connect-to-a-power-query-data-source"></a>Power Query データソースに接続する

Power Query では一連の広範なコネクターを搭載しており、データを取り込むことができます。 これらコネクターの多くが Dynamics 365 Customer Insights でサポートされています。 Power Query コネクタに基づくデータ ソースの追加方法については、次のセクションで説明する手順を参照してください。 ただし、使用するコネクタによっては、異なる情報が必要になります。 それぞれのコネクタに関する詳細情報については、[Power Query コネクタについての参考資料](/power-query/connectors/) を参照してください。

## <a name="create-a-new-data-source"></a>新しいデータ ソースの作成

1. 対象者に関するインサイトで、**データ** > **データ ソース** に移動します。

1. **データソースの追加** を選択します。

1. **データをインポート** する方法を選択し、**次へ** を選択します。

1. データ ソースの **名前** を入力し、**次へ** を選択してデータ ソースを作成します。 名前のガイドライン: 
   - 文字で始まる必要があります。
   - 文字と数字のみを使用してください。 特殊文字とスペースは使用できません。
   - 3〜64 文字を使用します。

1. [使用可能なコネクタ](#available-power-query-data-sources) のいずれかを選択します。 この例では、**Text/CSV** コネクタを選択しています。

1. 選択したコネクタの **接続設定** で必要な詳細を入力し、**次へ** を選択するとデータのプレビューが表示されます。

1. **データの変換** を選択します。 この手順では、データ ソースにエンティティを追加します。 エンティティとはデータセットを意味します。 複数のデータセットを含むデータベースがある場合、各データセットは独自のエンティティです。

1. **Power Query - クエリの編集** ダイアログでは、データを確認したり、詳細化したりすることができます。 選択したデータ ソースで識別されたシステムが左側のペインに表示されます。

   > [!div class="mx-imgBorder"]
   > ![クエリの編集ダイアログ](media/data-manager-configure-edit-queries.png "クエリの編集ダイアログ")

1. また、データをエクスポートすることもできます。 編集または変換するエンティティを選択します。 変換を適用するには、Power Query ウィンドウのオプションを使用します。 それぞれの変換は、**適用された手順** 配下に表示されます。 Power Query には、事前に構築された変換オプションが多数用意されています。 詳細については、[Power Query の変換](/power-query/power-query-what-is-power-query#transformations) を参照してください。

1. **クエリの編集** ダイアログで **データの取得** を選択することで、その他のエンティティをデータ ソースに追加できます。

   次の変換を強くお勧めします。

   - CSV ファイルからデータを取り込む場合、多くの場合、最初の行にヘッダーが含まれています。 **テーブルの変換** に移動し、**最初の行をヘッダーとして使用する** を選択します。
   - データ型が適切に設定されていることを確認してください。

1. Power Query ウィンドウの下部にある **保存** を選択して変換を保存します。 保存をすると、**データ** > **データ ソース** にデータソースが表示されます。

1. **データ ソース** ページに、新しいデータ ソースが **更新中** の状態で表示されます。

## <a name="available-power-query-data-sources"></a>利用可能な Power Query のデータソース

Customer Insights にデータをインポートするために選択できるコネクタの最新のリストについては、[Power Query コネクタの参考資料](/power-query/connectors/)を参照してください。 

**Customer Insights (Dataflows)** 列にチェック マークが付いているコネクタは、Power Query に基づいた新しいデータ ソースを作成することができます。 特定のコネクタのドキュメントを確認し、その前提条件、制限、およびその他の詳細を確認します。

## <a name="edit-power-query-data-sources"></a>Power Query データソースの編集

> [!NOTE]
> アプリのプロセスの 1 つで (たとえば、*セグメント化*、*一致*、または *マージ*)、現在使用されているデータソースに変更を加えることができない場合があります。 
>
> **設定** ページを使用して、有効な各プロセスの進行状況を追跡できます。 プロセスが完了すると、**データ ソース** ページに戻り、変更を加えることができます。

1. 対象者に関するインサイトで、**データ** > **データ ソース** に移動します。

2. 変更するデータ ソースの横にある縦の省略記号を選択し、ドロップダウン メニューから **編集** を選択します。

   > [!div class="mx-imgBorder"]
   > ![オプションの編集](media/edit-option-data-sources.png "オプションの編集")

3. **Power Query - キューの編集** ダイアログで、[新しいデータソースの作成](#create-a-new-data-source)に記載されているように、変更と変換を適用します。

4. 編集の完了後は、Power Query で **保存** を選択して変更を保存します。


[!INCLUDE[footer-include](../includes/footer-banner.md)]