---
title: Customer Insights の試用版を作成して構成します
description: Dynamics 365 Customer Insights の試用版サブスクリプションを取得し、設定する手順。
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3a235e924395a606b9332de3d205289288a597a9
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558829"
---
# <a name="set-up-a-trial-environment"></a>試用版環境の設定 

Dynamics 365 Customer Insights の試用版では、さまざまな機能の主要な機能を確認し、詳しく知ることができます。 試用版のサブスクリプションは、有効期限が切れると削除されます。 試用版環境は、個々のユーザーが作成し、それぞれの試用版環境の管理者となります。 より多くのユーザーを試用版に招待し、さまざまな機能を構成できます。

## <a name="create-a-trial-environment"></a>試用版環境の作成

[試用版サインアップ ページ](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights) で試用版にサインアップできます。 

1. **無料試用版へのサインアップ** オプションを選択し、**今すぐサインアップ** を選択します。

1. 職場または学校のメールアドレスとユーザーの情報を入力し、**開始する** を選択してください。

   :::image type="content" source="media/trial-signup-dialog.png" alt-text=" 無料の試用版にサインアップするためのダイアログ":::

1. 利用条件を確認し、**続ける** を選択します。

1. 新しい環境の **名前** を入力します。 

1. 環境の **タイプ** に **試用版** を設定します。

1. **業種別のデモを選択する** フィールドでは、オプションで業種固有のデータセットを選択できます。 後から[業種別デモを変更し](#use-industry-specific-demo-data-sets-in-audience-insights)、既定のデータセットから始めることもできます。

1. 環境に応じた **リージョン** を選択します。

1. また、Dynamics 365 組織の管理者である場合: **高度な設定** を選択し、顧客の解約予測などの予測機能を使用する組織の URL を入力します。 

1. **作成** を選択します。 

環境の設定は数分で終了します。 完了すると、デモ環境または上のステップで選択した業種のデモにリダイレクトされます。 以上で、読み取り専用のデモデータでアプリを探索できるようになりました。 独自のデータを環境に追加するには、[独自の環境でシナリオ固有のデモデータを作成する](#create-scenario-specific-demo-data-in-your-own-environment)を参照してください。

:::image type="content" source="media/trial-environment.png" alt-text="新たに作成された試用版環境のスクリーンショット。":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>対象ユーザーインサイトで業種固有のデモデータセットを使用する

実際のデータソースに接続することは、Customer Insights の力を活用する重要なステップの一つです。 独自のデータに影響を与えずに機能を試すために、オプションで業種別のデモデータを使用することができます。 次の業種で利用できるデモデータセットがいくつか用意しています: 

-   自動車産業
-   銀行業
-   消費財
-   政府機関
-   ヘルスケア
-   ホスピタリティ
-   保険
-   製造業
-   専門サービス
-   小売業

### <a name="see-industry-specific-demo-data-in-trials"></a>試用版で業種固有のデモデータを見る

特定の業種やシナリオに合わせてカスタマイズされた Customer Insights の読取り専用版は、デモ環境で開始してください。 
 
1.  対象ユーザーインサイトの、環境ピッカーで **デモ** 環境を選択します。

2.  **ホーム** で、[業種のデモを選択する] ドロップダウン メニューからオプションを選択します。

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="試用環境の業種を選択してください。":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>独自の環境でシナリオ固有のデモデータを作成する

管理者で、アプリのヘッダーにある環境ピッカーを選択して、新しい環境を作成します。 新しい環境では、独自のデータソースを設定し、要件に応じてアプリを設定することができます。 

1.  対象者に関するインサイトで、**データ** > **データ ソース** に移動します。

2.  独自のデータソースをインポートするには、[データ インジェストに関するガイド](data-sources.md)にアクセスしてください。     
   サンプルデータを使ってデータ インジェストを試してみる場合は、業種のデモデータをご利用の環境にインジェストできます。 **Datahub からインポート** オプションを選択し、以下の手順に従ってください。

3.  シナリオに合った業種カードを選択してください。 

4.  データ ソースの推奨名を確認し、オプションで更新します。 

5.  **次** を選択してサンプルデータを取り込みます。 

以上で、取り込んだデータを使用して、シナリオに合わせて Customer Insights を調整できます。 取り込んだデモデータに固有の環境を表示するには、環境ピッカーの **<Industry> デモ** オプションを選択してください。

## <a name="limitations-in-trials"></a>試用版の制限

- 試用版は既定でで30日間有効です。 ただし、試用版にログイン後、23日目以降は延長できます。
- 試用期間中、独自の Azure Data Lake Storage アカウントを使用して出力データを保存することはできません。 ただし、Data Lake storage アカウントからデータを取り込むことができます。
- Customer Insights 試用版を開始すると自動的にプロビジョニングされる Dataverse 環境には、最大 3GB までデータを保存できます。

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>試用版から有料サブスクリプションにデータをコピーする

一般的に、Customer Insights の有料版にアップグレードする際には、独自のデータで新しく始めることをお勧めします。 

オプションで、Customer Insights を購入した場合は、試用環境からデータをコピーできます。 試用環境から有料環境に設定を移行するには、Customer Insights の試用版の管理者と Microsoft 365 テナントのグローバル管理者、または組織内の Dynamics 365 管理者である必要があります。 

Customer Insights の有料インスタンスに初めてサインインすると、新しい環境を作成するよう求められます。 このプロセスでは、既存の環境から構成をコピーし、ほとんどの設定を移行することを選択できます。 上記の権限がある場合、このリストに試用環境が表示されます。 詳細については、[環境の構成をコピーする](manage-environments.md#copy-the-environment-configuration)を参照してください。

## <a name="next-steps"></a>次の手順

Customer Insights の構成を始める際には、以下の記事を参考にしてください。 

- [ユーザーを追加し、権限を割り当てる](permissions.md)。
- [データソースを取り込み](data-sources.md)、[データ統合プロセス](data-unification.md)を通してそれらを実行し、[統一された顧客プロファイル](customer-profiles.md)を取得する。
- [統一された顧客プロファイルを充実させる](enrichment-hub.md)または [予測モデルを実行する](predictions-overview.md)。
- [セグメント](segments.md)を作成して顧客をグループ化し、KPI [対策](measures.md)を確認します。
- [接続](connections.md)と[エクスポート](export-destinations.md)を設定し、他のアプリケーションでデータのサブセットを処理します。
