---
title: Dynamics 365 Customer Insights の新機能
description: 新機能、改善、およびバグ修正に関する情報。
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: dcee60a73e0c32278553253040478c31e45237ae
ms.sourcegitcommit: 618ef15b434de0a68213383b6521ce2a60753afb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2022
ms.locfileid: "9638357"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights の新機能

最新の更新プログラムについてお知らせします ! この記事は、パブリック プレビュー機能、全般的な可用性の強化、毎月の更新プログラム、機能の更新をまとめたものです。 長期的な機能計画を確認するには、[Dynamics 365 と Power Platform のリリース計画](/dynamics365/release-plans/) をご覧ください。

更新プログラムは地域ベースで配信されます。 そのため、特定の地域では、他の地域より先に機能が表示される場合があります。 特に指定がない限り、何もする必要はなく、アプリはダウンタイムなしで自動的に更新されます。

> [!TIP]
> 機能要求と製品に関する提案を送信して投票するには、[Dynamics 365 アプリケーションのアイデア ポータル](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights) に移動してください。

## <a name="september-2022-updates"></a>2022 年 9 月の更新プログラム

2022 年 9 月の更新には、新機能、パフォーマンス アップグレード、およびバグ修正が含まれています。

### <a name="export-data-to-hubspot"></a>HubSpot にデータをエクスポートする

統合顧客プロファイルのセグメントを HubSpot にエクスポートして、メール マーケティングに使用します。

詳細については、[セグメントの HubSpot へのエクスポート](export-hubspot.md) を参照してください。

### <a name="remove-a-unified-field-or-entity-from-data-unification"></a>統合されたフィールドまたはエンティティをデータ統合から削除する

データ統合プロセスからフィールドとエンティティを削除できます。

詳細については、 [統合フィールドを削除する](data-unification-update.md#remove-a-unified-field)を参照してください。

### <a name="manage-unknown-customer-profiles"></a>不明な顧客プロファイルを管理する

記憶に残るパーソナライゼーションは、顧客データの豊富さと完全性にかかっており、Customer Insights はこれらの目標を達成するのに役立ちます。 ID 以外の情報を持っていないユーザーの顧客プロファイルを管理できます。

詳細については、[Customer Insights で不明なプロファイルを管理する](manage-unknown-profiles.md) を参照してください。

## <a name="august-2022-updates"></a>2022 年 8 月の更新プログラム

2022 年 8 月の更新プログラムには、新機能、パフォーマンスのアップグレード、バグ修正が含まれます。

### <a name="contact-unification-in-b-to-b-environments"></a>B-to-B 環境の連絡先の統一

Customer Insights の B-to-B 環境では、強化されたデータ統合体験をサポートするようになりました。

アカウントに加えて連絡先を統合して、ビジネス連絡先を完全に把握できるようになりました。 統合された連絡先は統合されたアカウントに関連付けられ、顧客カードに表示されるようになりました。 

詳細については、[モバイル オフライン プロファイルを作成する](data-unification-contacts.md) を参照してください。

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>統合された連絡先に基づくセグメントの作成とエクスポート

この新しい連絡先統合のおかげで、連絡先、アカウント、またはその両方の基準を使用して、連絡先のセグメントを作成できます。 これらのセグメントは、他のサービスでアクティブ化するためにエクスポートできます。

詳細については、[エクスポートの概要](export-destinations.md) を参照してください。

### <a name="deployment-regions-aligned-with-microsoft-dataverse"></a>Microsoft Dataverse に合わせて調整された展開地域

新しい Customer Insights 環境を作成する際、サービスを展開してホストする地域を選択できます。 Microsoft Dataverse と Power Platform に合わせて地域の選択を更新しました。

既存の Microsoft Dataverse 環境または Azure Data Lake Storage アカウント (そのオプションを選択した場合) と同じ地域を簡単に選択できるようになりましたが、これはその地域での Customer Insights の可用性に応じて異なります。

詳細については、[新しい環境を作成する](create-environment.md)および[地域別の製品の入手可能性](https://dynamics.microsoft.com/availability-reports/)を参照してください。

## <a name="july-2022-updates"></a>2022 年 7 月の更新プログラム

2022 年 7 月の更新プログラムには、新機能、パフォーマンス アップグレード、およびバグ修正が含まれています。

### <a name="export-to-moengage"></a>MoEngage にエクスポート

統合された顧客プロファイルのセグメントを MoEngage にエクスポートし、MoEngage での E メール マーケティングに使用します。

詳細については、[セグメントの MoEngage へのエクスポート](export-moengage.md) を参照してください。

### <a name="ssh-support-for-sftp-based-exports"></a>SFTP ベースのエクスポートの SSH サポート

SFTP エクスポート先への接続で、SSH またはユーザー名/パスワードのどちらを使用して認証するかを選択します。

詳細については [データを SFTP ホストにエクスポートする](export-sftp.md) を参照してください。

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>既知と未知のユーザーに関するデータでエクスペリエンスをパーソナライズする

顧客データの管理は新しい課題ではありませんが、ブランドが提供するさまざまなデジタルチャネルをユーザーがナビゲートするにつれて、ますます困難になっています。 あるチャネルで認識されている (認証されている) ユーザーは、ログインしていない場合、別のチャネルでは不明 (認証されていない) になります。 多くの場合、認証されていない (不明な) ユーザーが共通の ID を持っていないことが問題になります。 意味のあるプロファイル属性を関連付け、統一された顧客プロファイルを生成するために使用できます。 Customer Insights は、ソース システムの追跡方法からデータを取り込むことにより、この問題を解決できます。

詳細については [既知と未知のユーザーに関するデータでエクスペリエンスをパーソナライズする](unknown-to-known.md) を参照してください。

## <a name="june-2022-updates"></a>2022 年 6 月の更新プログラム

2022 年 6 月の更新プログラムには、新機能、パフォーマンス アップグレード、およびバグ修正が含まれています。

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>データ ソースとデータ インジェストのユーザーエクスペリエンスを更新

さまざまなデータ ソースからデータをインポートすることは、Dynamics 365 Customer Insights で顧客データを統合するための基盤です。 データ ソースのインポートと接続のユーザー エクスペリエンスを再検討しました。 この更新は、Customer Insights へのデータの取り込みを容易にすることを目的としています。

詳細については、[データ ソースの概要](data-sources.md) を参照してください。

### <a name="export-to-inmobi"></a>InMobi にエクスポート

InMobi は、ブランドが消費者を理解し、特定し、関与し、獲得するのに役立ちます。 Azure Blob Storage アカウントを介して、セグメントやその他のデータを InMobi サービスにエクスポートできます。

詳細については、[InMobi にエクスポートする (プレビュー)](export-inmobi.md)を参照してください。

### <a name="lockbox-support-in-customer-insights"></a>Customer Insights でのロックボックスのサポート

カスタマー ロックボックスは、データ アクセス要求を確認し、承認 (または拒否) するためのインターフェイスを提供します。 このリクエストは、サポート案件を解決するために顧客データへのデータアクセスが必要な場合に発生します。

詳細については、[カスタマー ロックボックスを使用して顧客データに安全にアクセスする (プレビュー)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview) を参照してください。

### <a name="connect-to-your-data-using-azure-private-link"></a>Azure Private Link を使用してデータに接続する

Azure Private Link により、Customer Insightsは、仮想ネットワーク内のプライベート エンドポイントを介して、Azure Data Lake Storage アカウントに接続します。 パブリック インターネットに公開されていないストレージ アカウント内のデータに対して、プライベート リンクはその制限されたネットワークへの接続を可能にします。

詳細については、[Customer Insights での Private Link の使用](security-overview.md#set-up-an-azure-private-link) を参照してください。

## <a name="may-2022-updates"></a>2022 年 5 月の更新

2022 年 5 月の更新プログラムには、新機能、パフォーマンス アップグレード、およびバグ修正が含まれています。

### <a name="updated-data-unification-experience"></a>更新されたデータ統合エクスペリエンス

 データ統合により、かつては異なっていたデータソースを単一のマスター データセットに統合して、そのデータの統合ビューを提供できます。 データは、単一のエンティティまたは複数のエンティティに統合できます。 まず、[エンティティやソースフィールドの選択](map-entities.md)、[重複レコードの削除](remove-duplicates.md)、[マッチング条件](match-entities.md)のルール指定、[Unified customer profile に含めるフィールド](merge-entities.md)の定義などを行います。

詳細については、[データ統合の概要](data-unification.md) を参照してください。

### <a name="refreshed-home-page-in-customer-insights"></a>Customer Insights のホームページを更新しました

**ホーム** では、主要な機能の構成プロセスを示し、セグメント、メジャー、エンリッチメント データの概要を提供します。 エクスペリエンスを一新し、より関連性の高い情報を一目で確認できるようにしました。

詳細については、[Customer Insights について](home.md)を参照してください。

### <a name="track-usage-of-a-segment"></a>セグメントの使用状況を追跡する

Customer Insights と連携している Dataverse 組織をベースにしたアプリで、[セグメントの利用状況を追跡](segments.md#track-usage-of-a-segment)できるようになりました。 [Dynamics 365 Marketing の顧客体験で使用する Customer Insights セグメント](/dynamics365/marketing/real-time-marketing-ci-profile) の場合、システムが、そのセグメントの使用状況について通知します。

### <a name="export-to-criteo"></a>Criteo へのエクスポート

Criteo は、ユーザーがデジタル広告を管理するのに役立つオンライン プラットフォームです。 Unified customer profile のセグメントをエクスポートして、キャンペーンを生成してメール マーケティングを提供し、Criteo の特定の顧客グループを使用できます。

詳細については、[Criteo にセグメントをエクスポートする (プレビュー)](export-criteo.md)を参照してください。

### <a name="refined-documentation-structure-for-environment-creation"></a>環境作成のための洗練されたドキュメント構造

Customer Insights の環境の作成と管理に関連するヘルプ ドキュメントを再検討しました。 これで、記事は目次の環境ノードの下にグループ化されます。 再構築された記事は、環境のさまざまな設定方法に対するガイダンスを提供し、より明確な構成になっています。 共有するフィードバックがある場合は、ヘルプ記事の最後にあるコントロールを介してお伝えください。

詳しくは、[新しい環境を作成する方法](create-environment.md)をご覧ください。

## <a name="april-2022-updates"></a>2022 年 4 月の更新プログラム

2022 年 4 月の更新プログラムには、新機能、パフォーマンス アップグレード、およびバグ修正が含まれています。

### <a name="dun--bradstreet-enrichment-preview"></a>Dun & Bradstreet のエンリッチメント (プレビュー)

Dun ＆ Bradstreet は、企業向けの商用データ、分析、およびインサイトを提供します。 これを使用することで、企業の顧客プロファイルが統一された顧客は、データを充実させることができます。 エンリッチメントには、DUNS 番号、会社の規模、業界などの属性が含まれます。

詳細については、[Dun＆Bradstreet (プレビュー) による企業プロファイルのエンリッチメント](enrichment-dnb.md) を参照してください。

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>新しいメジャーを作成するときにメジャー タイプを定義する

これで、個々のプロファイルのメジャーとビジネス全体のメジャーを区別できます。 ビジネス メジャーは Customer Insights のホーム ページに表示されますが、顧客メジャーは詳細な顧客ビューに公開されます。

詳細については、[メジャー ビルダーを使用して最初からメジャーを作成する](measure-builder.md) を参照してください。

### <a name="consolidation-of-customer-insights-documentation"></a>Customer Insights のドキュメントの連結

ドキュメントの記事を再検討し、エンゲージメント分析情報と対象者分析情報機能についての言及を削除しました。 今後、アプリケーションのコア機能について説明するときは、一貫して製品名 Customer Insights を参照します。 この変更により、目次、URL 構造、および基になるドキュメント リポジトリ内のファイル パスが大幅に再構築されます。 すべてのブックマークまたは既存のリンクは引き続き機能し、更新された URL にリダイレクトされます。

その変化をどのように認識しているか、または期待どおりに機能していないものを見つけたい場合は、[このページのフィードバックを送信](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**) してください。

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

詳細については、[独自の Azure Data Lake Storage から Dataverse とのデータ共有を有効にする (プレビュー)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview) を参照してください。

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

詳細については、[破損したデータ ソース](data-sources.md#corrupt-data-sources) を参照してください。

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>エンゲージメント インサイト機能におけるレポート機能のプレビューの終了

Dynamics 365 Customer Insights エンゲージメント分析機能のプレビューは 2022 年 2 月 15 日に終了しました。  
この変更は、Customer Insights の試用版エクスペリエンスに、ファネルの作成機能も他のレポート機能も含まれなくなることを意味します。

Microsoft の顧客データ プラットフォーム (CDP)、[Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) の他の多くの機能を調べて評価することをお勧めします。    
 
移行期間中、既存のプレビュー参加者は引き続き一部のプレビュー機能にアクセスできます。

- Web サイトやモバイル アプリをインストルメント化するためのコードを取得する 
- イベントとイベント プロパティを表示する 
- 取り込まれたイベントと絞り込まれたイベントで統合プロファイルを強化して、顧客データの価値を最大限に活用します
  
移行期間中も、キャプチャされたイベントは接続された Data Lake にストリーミングされます。 この機能をオフにすると、データ共有が停止し、接続されたストレージに新しいイベントが送信されなくなります。
機能のプレビューの終了に関するご質問は、Microsoft アカウント チームに直接お問い合わせください。 アカウント チームは、今後のリリースについて最新の情報を提供します。 

## <a name="january-2022-updates"></a>2022 年 1 月の更新

2022 年 1 月の更新プログラムには、新機能、パフォーマンス アップグレード、およびバグ修正が含まれています。

### <a name="sentiment-analysis-of-your-customers-feedback"></a>顧客フィードバックの感情分析

Customer Insights は、顧客の感情を統合して的を絞った改善のチャンスとして特定のビジネス要因を特定する、AI を活用した新機能を提供します。 顧客が書いた文字によるフィードバックを分析して、低コストで正確なインサイトを獲得できます。 自然言語処理 (NLP) モデルを利用した感情分析は、顧客 ID ごとに 2 つの派生したインサイトを生成します。 感情スコア (of –5 to 5) と適用できるビジネス要因のリスト。 

詳細については [顧客フィードバックで感情を分析する (プレビュー)](sentiment-analysis.md) を参照してください。


[!INCLUDE [footer-include](includes/footer-banner.md)]