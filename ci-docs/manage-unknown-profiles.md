---
title: Customer Insights で不明なプロファイルを管理する
description: 'Dynamics 365 Customer Insights で作成および管理されている不明な顧客プロファイルを操作する '
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776827"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Customer Insights で不明なプロファイルを管理する

多くの場合、インターネット ユーザーは身元不明か匿名のオンラインです。 最も忠実な顧客であっても、別のデバイスでログインしていなければ、"不明" に見えることがあります。 多くのブランドにとって、パーソナライゼーションに対する顧客の期待が高まっているにもかかわらず、既知または認証済みのユーザーは少数派です。 当該のサードパーティの Cookie の未来を以て、パーソナライズされたエクスペリエンスを実現するには、ファーストパーティ データに基づいてユーザー設定を管理することが不可欠です。

記憶に残るカスタマイズは、顧客をどれだけよく知っているかにかかっています。Customer Insights は、すべての顧客を追跡することでそれを実現するのに役立ちます。  顧客体験の開始時に収集されたデータの使用を制限または停止する必要はありません。 Customer Insights を使用すると、独自のデータを使用して、不明なユーザーの顧客プロファイルを作成できます。 連絡先情報がなくても、そのプロファイルを使用して以降のアクションを実行できます。 Web、モバイル、CRM システムなどのソースからファーストパーティ データを Customer Insights にインポートして、顧客プロファイルを継続的に充実させます。 より多くの相互作用を統合して、[*不明な* 顧客を *既知の* 顧客に変更します](unknown-to-known.md)。

## <a name="sample-scenario"></a>サンプル シナリオ

ユーザーがモバイル デバイスを使用してeコマース サイトを閲覧すると仮定します。 Web サイトは訪問者「mobile_guest123」を一意の識別子として割り当て、オンライン アクティビティに基づいて行動アクティビティの収集を開始します。 たとえば、訪問したページ、それらのページで費やした時間、またはクリックしたリンクなどです。 名前や電子メール アドレスはわかりませんが、このデータは、この特定のユーザーについて意義のある分析情報をブランドに提供するのに役立ちます。 次に、そのユーザーが次にサイトにアクセスしたときに、それらの分析情報を機能させることができます。 Customer Insights に「mobile_guest123」をクエリして、「organic」、「mobile pre-order customers」、「high-value customers」などのユーザーのセグメント リストを取得するか、プロファイルを取得してパーソナライズされた Web エクスペリエンスを作成します。 データを任意のアクティベーション システムにエクスポートして、同じことを行うこともできます。

## <a name="prerequisites"></a>前提条件

- ファーストパーティ データを Customer Insights に取り込む
- 各エンティティには、主キーとして設定された一意の ID がある
- パーソナライゼーションの主キーを持つ各エンティティが統合される
- Web サイトのコンテンツ管理システムは API を使用できます (Customer Insights との直接通信に基づく Web パーソナライゼーション用)

次の表は、価値の高い Web イベントをキャプチャする方法の簡単な例を示しています。

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|6|2022/09/15 9:00:00|abc123|CookieID1|製品ビュー|
|2|2022/09/18 10:05:00|abc123|CookieID1|製品ビュー|
|3|2022/09/18 10:10:00|abc123|CookieID1|カートに追加|
|4|2022/09/21 09:05:00|abc123|CookieID1|製品ビュー|

## <a name="data-ingestion"></a>データ インジェスト

データ インジェストの使用可能なオプションに関する詳細情報は、[データ ソースの概要](data-sources.md) を参照してください。

## <a name="data-unification"></a>データ統合

顧客プロファイルの統合の詳細については、[データ統合の概要](data-unification.md) を参照してください。

## <a name="get-insights"></a>インサイトの取得

データを[エンリッチ](enrichment-hub.md) して、[対策](measures.md) を構築し、さらなる活性化のために[セグメント](segments.md) を作成します。

たとえば、同じ製品ページを閲覧したもののチェックアウトを完了しなかった不明なユーザーのセグメントを作成できます。

## <a name="activation"></a>アクティブ化

Customer Insights のデータと分析情報をすぐに使用できるようになったら、Customer Insights を使用してパーソナライズを行うことができます。

1. [OData API](apis.md) を使用してセグメント メンバーシップまたは顧客プロファイルを取得しますが、その他の例については、[Customer Insights API の OData クエリの例](odata-examples.md) を参照してください。

1. データをアクティベーション システムに[エクスポートします](export-destinations.md)。

例: 不明なユーザーが Web サイトに複数回アクセスし、さまざまなモデルの革靴の製品ページにアクセスします。 そのデータを Customer Insights で利用できるようにすることで、不明なユーザーを革靴に関心のある人々のセグメントに含めることができます。 このセグメントを使用して、リピーター向けの Web サイト構築のパーソナライゼーションを通知します。 次回の訪問時に、サイトは見知らぬユーザーを認識し、革靴の 10% クーポンを提供できます。

[!INCLUDE [footer-include](includes/footer-banner.md)]
