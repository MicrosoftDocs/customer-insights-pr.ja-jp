---
title: 顧客カード アドインのインストールと構成
description: Dynamics 365 Customer Insights の顧客カード アドインのインストールと構成
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268050"
---
# <a name="customer-card-add-in-preview"></a>顧客カード アドイン (プレビュー)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 アプリで直接、顧客を全方位から確認します。 顧客カード アドインを使用して、人口統計、インサイト、および活動のタイムラインを表示します。

## <a name="prerequisites"></a>前提条件

- Dynamics 365アプリ (営業ハブまたは顧客サービス ハブなど)、バージョン9.0以降、統一インターフェイスが有効化されていること。
- [Common Data Service を使用して Dynamics 365 アプリから取り込んだ](connect-power-query.md) 顧客プロファイル。
- 顧客カード アドインのユーザーは、対象者に関するインサイトに [ユーザーとして追加](permissions.md) する必要があります。
- [構成された検索およびフィルター機能](search-filter-index.md)。
- 人口統計コントロール: 人口統計フィールド (年齢や性別など) は、統合顧客プロファイルで利用できます。
- エンリッチメント制御 : 顧客プロファイルに適用されるアクティブな[エンリッチメント](enrichment-hub.md)が必要です。
- インテリジェンス制御: Azure Machine Learning ([予測](predictions.md) または [カスタム モデル](custom-models.md)) を使用して生成されたデータが必要です
- メジャー制御: [構成済みメジャー](measures.md) が必要です。
- タイムライン コントロール: [構成済みアクティビティ](activities.md) が必要です。

## <a name="install-the-customer-card-add-in"></a> 顧客カード アドイン のインストール

カスタマー カード アドインは、Dynamics 365 の Customer Engagement アプリのソリューションです。 ソリューションをインストールするには、AppSource に移動し、**Dynamics 顧客カード** を検索します。 [AppSource で顧客カードアドイン](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) を選択して、**今すぐ入手** を選択します。

ソリューションをインストールするには、Dynamics 365 アプリの管理者の資格情報でログインする必要があります。

ソリューションが環境にインストールされるまでに時間がかかる場合があります。

## <a name="configure-the-customer-card-add-in"></a>顧客カードアドインの構成

1. 管理者は、 Dynamics 365の **設定** セクションに移動し、**ソリューション** を選択してください。

1. **Dynamics 365 Customer Insights 顧客カード アドイン (プレビュー)** ソリューションの **表示名** を選択します。

   > [!div class="mx-imgBorder"]
   > ![表示名の選択](media/select-display-name.png "表示名の選択")

1. **サインイン** を選択し、Customer Insights の構成に使用する管理者アカウントの資格情報を入力します。

   > [!NOTE]
   > **サインイン** ボタンを選択する場合に、ブラウザのポップアップ ブロッカーが認証ウィンドウをブロックしないことを確認します。

1. データを取り込む環境を選択します。

1. Dynamics 365 アプリのレコードにマッピングするフィールドを定義します。
   - 取引先担当者とマップするには、取引先担当者エンティティの ID と一致する顧客エンティティのフィールドを選択します。
   - 取引先企業とマップするには、取引先企業エンティティの ID と一致する顧客エンティティのフィールドを選択します。

   > [!div class="mx-imgBorder"]
   > ![取引先担当者 ID フィールド](media/contact-id-field.png "取引先担当者 ID フィールド")

1. 設定を保存するには、**構成を保存** を選択します。

1. 次に、Dynamics 365 でセキュリティ ロールを割り当てて、ユーザーが顧客カードをカスタマイズして表示できるようにする必要があります。 Dynamics 365 で、**設定** > **セキュリティ** > **ユーザー** に移動します。 ユーザー ロールを編集するユーザーを選択し、**役割を管理する** を選択します。

1. 組織全体で使用するカードに表示されているコンテンツをカスタマイズするユーザーに **Customer Insights カード カスタマイザ** のロールを割り当てます。

## <a name="add-customer-card-controls-to-forms"></a>フォームに顧客カード コントロールを追加する
  
1. 顧客カードコントロールを連絡先フォームに追加するには、**設定** > **カスタマイズ** Dynamics 365 の順に移動します。

1. **システムのカスタマイズ** を選択。

1. **取引先担当者** エンティティを参照し、メニューを展開して、**フォーム** を選択します。

1. 顧客カード管理を追加したい取引先担当者フォームを選択します。

    > [!div class="mx-imgBorder"]
    > ![取引先担当者フォームを選択する](media/contact-active-forms.png "取引先担当者フォームを選択する")

1. 人口統計コントロールを追加するには、フォーム エディターで、任意のフィールドを **フィールド エクスプローラー** から人口統計コントロールを配置する場所にドラッグします。

1. 今追加したフォームのフィールドを選択し、**プロパティの変更** を選択します。

1. **コントロール** タブに移動し、**コントロールの追加** を選択します。 利用可能なカスタム コントロールの 1 つを選択し、**追加** を選択します。

1. **フィールドのプロパティ** ダイアログで、**フォームにラベルを表示する** チェックボックスをオフにします。

1. **Web** オプションをコントロールに選択します。 エンリッチメント制御で、**enrichmentType** フィールドを設定して、表示するエンリッチメントのタイプを選択します。 エンリッチメントのタイプごとに個別のエンリッチメント コントロールを追加します。

1. **保存** そして **公開** を選択して、更新された問い合わせフォームを公開します。

1. 公開されている取引先担当者フォームに移動します。 新しく追加されたコントロールが表示されます。 初めて使用するときはサインインする必要がある場合があります。

1. カスタム コントロールで表示したいものをカスタマイズするには、右上隅の編集ボタンを選択します。

## <a name="upgrade-customer-card-add-in"></a>顧客カード アドインのアップグレード
顧客カード アドインは自動的にアップグレードされません。 最新バージョンにアップグレードするには、アドインがインストールされている Dynamics 365 アプリでこの手順に従います。

1. Dynamics 365 アプリで、**設定** > **カスタマイズ**、そして **ソリューション** を選択します。

1. アドインの表で、**CustomerInsightsCustomerCard** を探して、行を選択します。

1. アクションバーで **ソリューションのアップグレードを適用する** を選択します。

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Dynamics 365 アプリのカスタマイズ領域でソリューションをアップグレードする":::

1. アップグレード プロセスを開始すると、アップグレードが完了するまで読み込みインジケータが表示されます。 新しいバージョンがない場合、アップグレードでエラーメッセージが表示されます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]