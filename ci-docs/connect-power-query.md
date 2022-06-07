---
title: Power Query コネクタを介してデータを取り込む (ビデオを含む)
description: Power Query に基づくデータ ソース用のコネクタ。
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4db97ec02eb96662d30a8536ea42372f81f318d2
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800157"
---
# <a name="connect-to-a-power-query-data-source"></a>Power Query データ ソースに接続する

Power Query はデータを取り込むための幅広いコネクタ セットを提供します。 これらコネクターの多くが Dynamics 365 Customer Insights でサポートされています。 

Power Query コネクタに基づくデータ ソースの追加は、通常、このセクションで概説されている手順に従います。 ただし、使用するコネクタによっては、異なる情報が必要になります。 詳細については、[Power Query コネクタ リファレンス](/power-query/connectors/) で個々のコネクタに関するドキュメントを参照してください。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>新しいデータ ソースの作成

1. **データ** > **データ ソース** にアクセスします。

1. **データソースの追加** を選択します。

1. **Microsoft Power Query** を選択します。

1. データ ソースの **名前** を入力し、**次へ** を選択してデータ ソースを作成します。

1. [使用可能なコネクタ](#available-power-query-data-sources) のいずれかを選択します。 この例では、**テキスト/CSV** コネクタを選択します。

1. 選択したコネクタの **接続設定** で必要な詳細を入力し、**次へ** を選択するとデータのプレビューが表示されます。

1. **データの変換** を選択します。 この手順では、データ ソースにエンティティを追加します。 エンティティとはデータセットを意味します。 複数のデータセットを含むデータベースがある場合、各データセットは独自のエンティティです。

1. **Power Query - クエリの編集** ダイアログでデータの確認と調整を実行できます。 選択したデータ ソースで識別されたシステムが左側のペインに表示されます。

   > [!div class="mx-imgBorder"]
   > ![クエリの編集ダイアログ。](media/data-manager-configure-edit-queries.png "クエリの編集ダイアログ")

1. また、データをエクスポートすることもできます。 編集または変換するエンティティを選択します。 Power Query ウィンドウでオプションを使用し、変換を適用します。 それぞれの変換は、**適用された手順** 配下に表示されます。 Power Query は多数の構築済み変換オプションを提供します。 詳細については、[Power Query の変換](/power-query/power-query-what-is-power-query#transformations) を参照してください。

   次の変換を使用することを強くお勧めします。

   - CSV ファイルからデータを取り込む場合、多くの場合、最初の行にヘッダーが含まれています。 **変換** に移動して **1 行目をヘッダーとして使用** を選択します。
   - データ型が適切に設定されていることを確認してください。 たとえば日付フィールドの場合、日付タイプを選択します。

1. **クエリの編集** ダイアログでデータ ソースにエンティティを追加する場合は、**ホーム** に移動して **データの取得** を選択します。

1. Power Query ウィンドウの下部にある **保存** を選択して、変換を保存します。 保存をすると、**データ** > **データ ソース** にデータソースが表示されます。

1. **データ ソース** ページに、新しいデータ ソースが **更新中** の状態で表示されます。

## <a name="available-power-query-data-sources"></a>利用できる Power Query データソース

Customer Insights にデータをインポートするために使用できるコネクタのリストについては、[Power Query コネクタ リファレンス](/power-query/connectors/) を参照してください。 

**Customer Insights (データフロー)** 列にチェックマークが付いているコネクタを使用して、Power Query に基づく新しいデータ ソースを作成できます。 特定のコネクタのドキュメントを確認し、その前提条件、制限、およびその他の詳細を確認します。

## <a name="edit-power-query-data-sources"></a>Power Query データ ソースを編集する

> [!NOTE]
> アプリのプロセスの 1 つで (たとえば、*セグメント化*、*一致*、または *マージ*)、現在使用されているデータソースに変更を加えることができない場合があります。 
>
> **設定** ページで、有効な各プロセスの進行状況を追跡できます。 プロセスが完了すると、**データ ソース** ページに戻り、変更を加えることができます。

1. **データ** > **データ ソース** にアクセスします。

2. 変更するデータ ソースの横にある垂直の省略記号 (&vellip;) を選択し、ドロップダウン メニューから **編集** を選択します。

   > [!div class="mx-imgBorder"]
   > ![オプションの編集。](media/edit-option-data-sources.png "オプションの編集")

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]
   
3. [新しいデータ ソースの作成](#create-a-new-data-source) セクションの説明に従って、**Power Query - クエリの編集** ダイアログで変更と変換を適用します。

4. 編集を完了したら Power Query で **保存** を選択し、変更を保存します。


[!INCLUDE [footer-include](includes/footer-banner.md)]
