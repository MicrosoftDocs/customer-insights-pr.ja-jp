---
title: Power Query コネクタを介してデータを取り込む (ビデオを含む)
description: Power Query に基づくデータ ソース用のコネクタ。
ms.date: 05/09/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: b99c3b446e580f455f9678d54d9db414aea9b331
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011663"
---
# <a name="connect-to-a-power-query-data-source"></a>Power Query データ ソースに接続する

Power Query はデータを取り込むための幅広いコネクタ セットを提供します。 これらコネクターの多くが Dynamics 365 Customer Insights でサポートされています。

Power Query コネクタに基づくデータ ソースの追加は、通常、このセクションで概説されている手順に従います。 ただし、使用するコネクタによっては、異なる情報が必要になります。 詳細については、[Power Query コネクタ リファレンス](/power-query/connectors/) で個々のコネクタに関するドキュメントを参照してください。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>新しいデータ ソースの作成

1. **データ** > **データ ソース** にアクセスします。

1. **データソースの追加** を選択します。

1. **Microsoft Power Query** を選択します。

1. データソースの **名前** とオプションの **説明** を入力し、**次へ** を選択します。

1. [使用可能なコネクタ](#available-power-query-data-sources) のいずれかを選択します。 この例では、**テキスト/CSV** コネクタを選択します。

1. 選択したコネクタの **接続設定** で必要な詳細を入力し、**次へ** を選択するとデータのプレビューが表示されます。

1. **データの変換** を選択します。 この手順では、データ ソースにエンティティを追加します。 エンティティとはデータセットを意味します。 複数のデータセットを含むデータベースがある場合、各データセットは独自のエンティティです。

1. **Power Query - クエリの編集** ダイアログでデータの確認と調整を実行できます。 選択したデータ ソースで識別されたシステムが左側のペインに表示されます。

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="クエリの編集ダイアログ":::

1. また、データをエクスポートすることもできます。 編集または変換するエンティティを選択します。 Power Query ウィンドウでオプションを使用し、変換を適用します。 各変換は **適用された手順** 以下にリストされています。 Power Query は多数の構築済み変換オプションを提供します。 詳細については、[Power Query の変換](/power-query/power-query-what-is-power-query#transformations) を参照してください。

   次の変換を使用することを強くお勧めします。

   - CSV ファイルからデータを取り込む場合、多くの場合、最初の行にヘッダーが含まれています。 **変換** に移動して **1 行目をヘッダーとして使用** を選択します。
   - データ型が適切に設定されていることを確認してください。 たとえば日付フィールドの場合、日付タイプを選択します。

1. **クエリの編集** ダイアログでデータ ソースにエンティティを追加する場合は、**ホーム** に移動して **データの取得** を選択します。 このデータ ソースのすべてのエンティティを追加するまで、手順 6〜10 を繰り返します。

1. **保存** を選択します。 **データソース** ページが開き、新しいデータソースが **更新** された状態で表示されます。

### <a name="available-power-query-data-sources"></a>利用できる Power Query データソース

Customer Insights にデータをインポートするために使用できるコネクタのリストについては、[Power Query コネクタ リファレンス](/power-query/connectors/) を参照してください。

**Customer Insights (データフロー)** 列にチェックマークが付いているコネクタを使用して、Power Query に基づく新しいデータ ソースを作成できます。 特定のコネクタの前提条件、[クエリの制限](/power-query/power-query-online-limits),、およびその他の詳細については、そのコネクタのドキュメントを参照してください。

## <a name="add-data-from-on-premises-data-sources"></a>オンプレミスのデータ ソースからデータを追加する

オンプレミスのデータ ソースからのデータの取り込みは、Microsoft Power Platform データフロー (PPDFs) に基づいてサポートされています。 Customer Insights でデータフローを有効にするには、環境を設定するときに[Microsoft Dataverse 環境 URL の提供](create-environment.md)を参照してください。

Dataverse 環境を Customer Insights に関連付けた後に作成されるデータ ソースは、既定で[Power Platform データフロー](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365)を使用します。 データフローは、データ ゲートウェイを使用したオンプレミス接続をサポートします。 [オンプレミスのデータ ゲートウェイを使用して](/data-integration/gateway/service-gateway-app)、Dataverse 環境が関連付けられる前に存在するデータソースを削除して再作成できます。

既存の Power BI または Power Apps 環境からのデータ ゲートウェイが表示され、Customer Insights で再利用できます。 データ ソース ページには、Microsoft Power Platform 環境に移動するためのリンクが表示され、オンプレミスのデータ ゲートウェイを表示および構成することができます。

> [!IMPORTANT]
> ゲートウェイが最新バージョンに更新されていることを確認してください。 更新プログラムをインストールして、ゲートウェイ画面に表示されるプロンプトから直接ゲートウェイを再構成するか、[最新バージョンをダウンロードする](https://powerapps.microsoft.com/downloads/)ことができます。 最新のゲートウェイ バージョンを使用しない場合、データフローの更新は失敗し、**キーワードはサポートされていません: 構成プロパティ。パラメータ名: キーワード** のようなエラーメッセージが表示されます。。

## <a name="edit-power-query-data-sources"></a>Power Query データ ソースを編集する

> [!NOTE]
> アプリのプロセスの 1 つで (たとえば、*セグメント化*、*一致*、または *マージ*)、現在使用されているデータソースに変更を加えることができない場合があります。
>
> **設定** ページで、有効な各プロセスの進行状況を追跡できます。 プロセスが完了すると、**データ ソース** ページに戻り、変更を加えることができます。

1. **データ** > **データ ソース** にアクセスします。

1. 更新するデータ ソースの横にある、**編集** を選択します。

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. [新しいデータ ソースの作成](#create-a-new-data-source) セクションの説明に従って、**Power Query - クエリの編集** ダイアログで変更と変換を適用します。

1. 編集を完了したら Power Query で **保存** を選択し、変更を保存します。
