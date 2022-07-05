---
title: Dynamics 365 アプリの顧客カード アドイン (プレビュー) (ビデオを含む)
description: このアドインを使用して、Dynamics 365 アプリの Customer Insights からの顧客プロファイル データを表示します。
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: ead18963959f94fd07912384cf61802f83523e2f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081255"
---
# <a name="customer-card-add-in-for-dynamics-365-apps-preview"></a>Dynamics 365 アプリの顧客カード アドイン (プレビュー)

Dynamics 365 アプリで直接、顧客を全方位から確認します。 サポートされている Dynamics 365 アプリにカスタマー カード アドインをインストールすると、カスタマー プロファイル フィールド、インサイト、およびアクティビティのタイムラインを表示するように選択できます。 アドインは、接続されている Dynamics 365 アプリのデータに影響を与えることなく、Customer Insights からデータを取得します。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>前提条件

- アドインは、Sales や Customer Service など、Dynamics 365 モデル駆動型アプリ 9.0 以降でのみ機能します。
- Dynamics 365 データを Customer Insights の顧客プロファイルにマップするには、[Microsoft Dataverse コネクタを使用して Dynamics 365 アプリから取り込む](connect-power-query.md)  ことをお勧めします。 別の方法で Dynamics 365 取引先担当者 (または取引先企業) を取り込む場合は、`contactid` (または `accountid`) フィールドが [データ統合プロセスのマップ ステップでのデータ ソースの主キー](map-entities.md#select-primary-key-and-semantic-type-for-attributes) として設定されていることを確認する必要があります。
- カスタマー カード アドインのすべての Dynamics 365 ユーザーは、データを見るには、Customer Insights で [ユーザーとして追加](permissions.md) する必要があります。
- Customer Insights の [構成された検索およびフィルター機能](search-filter-index.md) は、作業するデータの検索に必要です。
- 各アドイン コントロールは、Customer Insights の特定のデータに依存します。 一部のデータとコントロールは、特定のタイプの環境でのみ使用できます。 アドイン構成は、選択した環境タイプが原因でコントロールが使用できない場合に通知します。 [環境ユース ケース](work-with-business-accounts.md)に関する詳細を参照してください。
  - **メジャー制御**: タイプ顧客属性の[構成されたメジャー](measures.md)が必要です。
  - **インテリジェンス制御**: [予測またはカスタム モデル](predictions-overview.md) を使用して生成されたデータが必要です。
  - **顧客詳細制御**: プロファイルのすべてのフィールドは、統合された顧客プロファイルで使用できます。
  - **エンリッチメント制御**: 顧客プロファイルに適用されるアクティブな[エンリッチメント](enrichment-hub.md)が必要です。 カード アドインは、次の機能強化をサポートしています。Microsoft 提供の[ブランド](enrichment-microsoft.md)、Microsoft 提供の[興味](enrichment-microsoft.md)、Microsoft が提供の[Office エンゲージメント データ](enrichment-office.md)。
  - **連絡先制御**: 連絡先タイプのセマンティック エンティティの定義が必要です。
  - **タイムライン コントロール**: [構成済みアクティビティ](activities.md)が必要です。

## <a name="install-the-customer-card-add-in"></a> 顧客カード アドイン のインストール

カスタマー カード アドインは、Dynamics 365 の Customer Engagement アプリのソリューションです。 ソリューションをインストールするには、AppSource に移動し、**Dynamics 顧客カード** を検索します。 [AppSource で顧客カードアドイン](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) を選択して、**今すぐ入手** を選択します。

ソリューションをインストールするには、Dynamics 365 アプリの管理者の資格情報でログインする必要があります。 ソリューションが環境にインストールされるまでに時間がかかる場合があります。

## <a name="configure-the-customer-card-add-in"></a>顧客カードアドインの構成

1. 管理者は、 Dynamics 365の **設定** セクションに移動し、**ソリューション** を選択してください。

1. **Dynamics 365 Customer Insights 顧客カード アドイン (プレビュー)** ソリューションの **表示名** を選択します。

   > [!div class="mx-imgBorder"]
   > ![表示名の選択。](media/select-display-name.png "表示名を選択します。")

1. **サインイン** を選択し、Customer Insights の構成に使用する管理者アカウントの資格情報を入力します。

   > [!NOTE]
   > **サインイン** ボタンを選択する場合に、ブラウザのポップアップ ブロッカーが認証ウィンドウをブロックしないことを確認します。

1. データを取得する Customer Insights 環境を選択します。

1. Dynamics 365 アプリでレコードへのフィールド マッピングを定義します。 Customer Insights のデータに応じて、次のオプションのマップを選択できます:
   - 取引先担当者とマップするには、取引先担当者エンティティの ID と一致する顧客エンティティのフィールドを選択します。
   - 取引先企業とマップするには、取引先企業エンティティの ID と一致する顧客エンティティのフィールドを選択します。

   > [!div class="mx-imgBorder"]
   > ![取引先担当者 ID フィールド。](media/contact-id-field.png "取引先担当者 ID フィールド。")

1. 設定を保存するには、**構成を保存** を選択します。

1. 次に、Dynamics 365 でセキュリティ ロールを割り当てて、ユーザーが顧客カードをカスタマイズして表示できるようにする必要があります。 Dynamics 365 で、**設定** > **セキュリティ** > **ユーザー** に移動します。 ユーザー ロールを編集するユーザーを選択し、**役割を管理する** を選択します。

1. 組織全体で使用するカードに表示されているコンテンツをカスタマイズするユーザーに **Customer Insights カード カスタマイザ** のロールを割り当てます。

## <a name="add-customer-card-controls-to-forms"></a>フォームに顧客カード コントロールを追加する

シナリオに応じて、**取引先担当者** フォームまたは **取引先企業** フォームのいずれかにコントロールを追加するよう選択できます。 Customer Insights 環境がビジネス アカウント用である場合は、取引先企業フォームにコントロールを追加することをお勧めします。 その場合、以下の手順の「取引先担当者」を「取引先企業」に置き換えてください。

1. 顧客カードコントロールを連絡先フォームに追加するには、**設定** > **カスタマイズ** Dynamics 365 の順に移動します。

1. **システムのカスタマイズ** を選択。

1. **取引先担当者** エンティティを参照し、メニューを展開して、**フォーム** を選択します。

1. 顧客カード コントロールを追加する先の取引先担当者フォームを選択します。

    > [!div class="mx-imgBorder"]
    > ![取引先担当者フォームを選択する。](media/contact-active-forms.png "取引先担当者フォームを選択します。")

1. 人口統計コントロールを追加するには、フォーム エディターで、任意のフィールドを **フィールド エクスプローラー** から人口統計コントロールを配置する場所にドラッグします。

1. 今追加したフォームのフィールドを選択し、**プロパティの変更** を選択します。

1. **コントロール** タブに移動し、**コントロールの追加** を選択します。 利用可能なカスタム コントロールの 1 つを選択し、**追加** を選択します。

1. **フィールドのプロパティ** ダイアログで、**フォームにラベルを表示する** チェックボックスをオフにします。

1. **Web** オプションをコントロールに選択します。 エンリッチメント制御で、**enrichmentType** フィールドを設定して、表示するエンリッチメントのタイプを選択します。 エンリッチメントのタイプごとに個別のエンリッチメント コントロールを追加します。

1. **保存** そして **公開** を選択して、更新された問い合わせフォームを公開します。

1. 公開されている取引先担当者フォームに移動します。 新しく追加されたコントロールが表示されます。 初めて使用するときはサインインする必要がある場合があります。

1. カスタム コントロールで表示したいものをカスタマイズするには、右上隅の編集ボタンを選択します。

## <a name="upgrade-customer-card-add-in"></a>顧客カード アドインのアップグレード

顧客カード アドインは自動的にアップグレードされません。 最新バージョンにアップグレードするには、アドインがインストールされている Dynamics 365 アプリで次のステップを実行します。

1. Dynamics 365 アプリで、**設定** > **カスタマイズ**、そして **ソリューション** を選択します。

1. アドインの表で、**CustomerInsightsCustomerCard** を探して、行を選択します。

1. アクションバーで **ソリューションのアップグレードを適用する** を選択します。

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Dynamics 365 アプリのカスタマイズ領域でソリューションをアップグレードする。":::

1. アップグレード プロセスを開始すると、アップグレードが完了するまで読み込みインジケータが表示されます。 新しいバージョンがない場合、アップグレードでエラーメッセージが表示されます。

## <a name="troubleshooting"></a>トラブルシューティング​​

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>顧客カード アドインによるコントロールがデータを検出しません

**問題:**

ID フィールドを正しく構成した場合も、コントロールが顧客のデータを検出できません。  

**解決方法:**

1. この手順に従ってカード アドインの構成を確認してください: [顧客カード アドインの構成](#configure-the-customer-card-add-in)

1. データ取り込み構成を確認します。 取引先担当者 ID GUID を含む Dynamics 365 システムのデータ ソースを編集します。 Power Query エディタで取引先担当者 ID GUID が大文字で表示される場合は、次の手順を実行してください。
    1. データ ソースを編集して Power Query エディタでデータ ソースを開きます。
    1. 取引先担当者 ID 列を選択します。
    1. ヘッダー バーの **変換** を選択して、使用できるアクションを確認します。
    1. **小文字** を選択します。 テーブルが含む GUID が小文字になったことを確認します。
    1. データ ソースを保存します。
    1. データの取り込み、統合、下流プロセスを実行して、変更を GUID に伝播します。

完全にシステムの更新が完了すると、顧客カード アドイン コントロールに必要なデータが表示されます。

[!INCLUDE [footer-include](includes/footer-banner.md)]
