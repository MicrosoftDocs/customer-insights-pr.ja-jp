---
title: 新しい機能および今後の機能
description: 新機能、改善、およびバグ修正に関する情報。
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547678"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights の対象者に関するインサイト機能の新機能

最新の更新プログラムについてお知らせします ! この記事は、パブリック プレビュー機能、全般的な可用性の強化、毎月の更新プログラム、機能の更新をまとめたものです。 長期的な機能計画を確認するには、[Dynamics 365 と Power Platform のリリース計画](/dynamics365/release-plans/) をご覧ください。

更新プログラムは地域ベースで配信されます。 そのため、特定の地域では、他の地域より先に機能が表示される場合があります。 特に指定がない限り、何もする必要はなく、アプリはダウンタイムなしで自動的に更新されます。

> [!TIP]
> 機能要求と製品に関する提案を送信して投票するには、[Dynamics 365 アプリケーションのアイデア ポータル](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights) に移動してください。


## <a name="march-2022-updates"></a>2022 年 3 月の更新プログラム

2022 年 3 月の更新プログラムには、新機能、パフォーマンス アップグレード、およびバグ修正が含まれています。

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec のエンリッチメント (プレビュー)

LiveRamp は、ID の解決と顧客データの統合を提供します。 顧客データの個人 ID を AbiliTec ID グラフにマッピングし、AbiliTec ID を受け取ることができます。 その後、これらの ID を使用して、顧客データをより適切に統合できます。

詳細については、[LiveRamp からの ID データで顧客プロファイルをエンリッチする (プレビュー)](enrichment-liveramp.md) を参照してください。

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>タグとフィルターを使用してセグメントとメジャーを整理します
組織が多くのセグメントまたはメジャーを管理している場合、適切なものを見つけるのは難しいと感じることがあります。 この新機能を使用すると、タグと列を使用してリストを整理できます。 データをすばやく簡単に検索し、ビューをカスタマイズするのに役立ちます。

詳細については、[タグと列の使用](work-with-tags-columns.md)を参照してください。

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>独自にのストレージ アカウントを使用する場合に Dataverse とのデータ共有を有効にする

Azure Data Lake Storage 環境を使用して Customer Insights データを格納するように場合、Microsoft Dataverse とのデータ共有は、追加の構成がいくつか必要です。
以前は、データが管理対象データ レイクに保存されている場合しか、Dataverse とのデータ共有を有効にできませんでした。 

詳細については、[独自の Azure Data Lake Storage から Dataverse とのデータ共有を有効にする (プレビュー)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview) を参照してください。

### <a name="new-export-destinations-iterable-and-braze"></a>新しいエクスポート先: Iterable と Braze

私たちは、新しいつながりでエクスポート先のエコシステムを拡大し続けています。 セグメントを Iterable と Braze にエクスポートして、それらのアクティベーション サービスを使用できるようになりました。

詳細については、[セグメントを Iterable にエクスポートする (プレビュー)](export-iterable.md)と[セグメントをBrazeにエクスポート（プレビュー）](export-braze.md)を参照してください。

### <a name="improvements-to-marketo-and-google-ads-export"></a>Marketo と Google Ads エクスポートの改善

接続されたサービスの API を変更することで、更新プログラムによってコネクタが確実かつスムーズに実行できます。 Marketo および Google Ads サービスへのエクスポートに関するいくつかの更新プログラムをリリースしました。

- Google Ads: 新しいバージョンの Google Ads エクスポート コネクタでは、認証エクスペリエンスが簡素化され、新しい Google Ads 対象者を自動的に作成できます。 
- Marketo: 新しいバージョンの Marketo エクスポート コネクタでは、Marketo ID のサポートを提供し、データの重複を回避し、既存のレコードを更新し、Marketo で新しいレコードを作成できます。 


## <a name="february-2022-updates"></a>2022 年 2 月の更新プログラム

2022 年 2 月の更新プログラムには、新機能、パフォーマンス アップグレード、およびバグ修正が含まれています。

### <a name="general-availability-for-prediction-models"></a>予測モデルの一般提供

**サブスクリプション解約**、**トランザクション解約**、**顧客生涯価値 (CLV)** を含む、すぐに使用できる予測モデルが Customer Insights の一部として一般提供になります。 

詳細については、[予測の概要](predictions-overview.md) を参照してください。

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>新しいデータ ソース: Azure Synapse Analytics との統合 (プレビュー)

Azure Synapse Analytics は、データ ウェアハウスとビッグ データ システム全体の分析情報までの時間を短縮するエンタープライズ分析サービスです。

Azure Synapse Analytics をすでに使用している組織は、そのデータを Customer Insights に取り込むことができます。 

詳細については、[Azure Synapse データ ソースを接続する (プレビュー)](connect-synapse.md) を参照してください。

### <a name="liveramp-enrichment-preview"></a>LiveRamp のエンリッチメント (プレビュー)

LiveRamp は、ID の解決と顧客データの統合を提供します。 顧客データの個人 ID を AbiliTec ID グラフにマッピングし、AbiliTec ID を受け取ることができます。 その後、これらの ID を使用して、顧客データをより適切に統合できます。

詳細については、[LiveRamp からの ID データで顧客プロファイルをエンリッチする (プレビュー)](enrichment-liveramp.md) を参照してください。

### <a name="enrichment-for-data-sources-preview"></a>データ ソースのエンリッチメント (プレビュー)

Microsoft や他のパートナーなどのソースからのデータを使用して、データ統合前に顧客データをエンリッチします。 データ ソース エンリッチメントは、データを統合するとより良い結果を達成するのに役立つ、より高いデータの完全性と品質を生み出すのに役立ちます。

詳細については、[データ ソースのエンリッチメント (プレビュー)](data-sources-enrichment.md) を参照してください。

### <a name="change-owner-of-environment"></a>環境の所有者を変更する

Customer Insights では複数のユーザーが管理者権限を持つことができますが、環境の所有者は 1 人のユーザーのみです。 改善したエクスペリエンスにより、環境の所有者を変更し、前の所有者が組織を離れた場合に所有権を要求できます。 

詳細については、[環境の所有者を変更する](manage-environments.md#change-the-owner-of-an-environment) を参照してください。

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>データ準備プロセスにより、破損したレコードの破損理由が一覧表示される

データ準備で、データが破損しているすべてのフィールドの破損の理由が表示されるようになりました。 情報が個々のレコードレベルで提供されれるため、簡単に識別できます。 

詳細については、[破損したデータ ソース](entities.md#corrupted-data-sources) を参照してください。

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>エンゲージメント インサイト機能におけるレポート機能のプレビューの終了

Dynamics 365 Customer Insights エンゲージメント分析機能のプレビューは 2022 年 2 月 15 日に終了しました。  
この変更は、Customer Insights の試用版エクスペリエンスに、ファネルの作成機能も他のレポート機能も含まれなくなることを意味します。

Microsoft の顧客データ プラットフォーム (CDP)、[Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) の他の多くの機能を調べて評価することをお勧めします。    
 
移行期間中、既存のプレビュー参加者は引き続き一部のプレビュー機能にアクセスできます。

- Web サイトやモバイル アプリをインストルメント化するためのコードを取得する 
- イベントとイベント プロパティを表示する 
- 取り込まれたイベントと絞り込まれたイベントで統合プロファイルを強化して、顧客データの価値を最大限に活用します
  
移行期間中も、キャプチャされたイベントは接続された Data Lake にストリーミングされます。 この機能をオフにすると、エンゲージメント分析情報と対象者分析情報間のデータ共有が停止し、接続されたストレージに新しいイベントが送信されなくなります。
機能のプレビューの終了に関するご質問は、Microsoft アカウント チームに直接お問い合わせください。 アカウント チームは、今後のリリースについて最新の情報を提供します。 

## <a name="january-2022-updates"></a>2022 年 1 月の更新

2022 年 1 月の更新プログラムには、新機能、パフォーマンス アップグレード、およびバグ修正が含まれています。

### <a name="sentiment-analysis-of-your-customers-feedback"></a>顧客フィードバックの感情分析

Customer Insights は、顧客の感情を統合して的を絞った改善のチャンスとして特定のビジネス要因を特定する、AI を活用した新機能を提供します。 顧客が書いた文字によるフィードバックを分析して、低コストで正確なインサイトを獲得できます。 自然言語処理 (NLP) モデルを利用した感情分析は、顧客 ID ごとに 2 つの派生したインサイトを生成します。 感情スコア (of –5 to 5) と適用できるビジネス要因のリスト。 

詳細については [顧客フィードバックで感情を分析する (プレビュー)](sentiment-analysis.md) を参照してください。


[!INCLUDE[footer-include](../includes/footer-banner.md)]