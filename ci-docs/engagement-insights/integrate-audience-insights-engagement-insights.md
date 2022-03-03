---
title: 対象ユーザー インサイトとエンゲージメント インサイトの間にリンクを作成する
description: 対象者インサイトとエンゲージメント インサイトの間にアクティブなリンクを作成して、データの双方向共有を可能にします。
ms.date: 09/08/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56adc206d83bc6e34a55f11383393b5ac66da531
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229878"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>対象ユーザー インサイトとエンゲージメント インサイトの間にリンクを作成する

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

エンゲージメント インサイトと対象ユーザーインサイトの統合により、両方の機能から環境がリンクされ、データをそれらの間で双方向に共有できるようになります。

エンゲージメント インサイトの分析オプションを増やすには、対象者インサイトの統合プロファイルとセグメントを使用してください。 エンゲージメント インサイトからビジネス価値の高いイベントをエクスポートします。 これらのイベントを使用して、対象ユーザーインサイトの統合プロファイルにデータを追加します。

## <a name="prerequisites"></a>前提条件

- 対象ユーザー インサイトのプロファイルは、ご利用の Azure Data Lake Storage アカウント、または [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash; のマネージド データレイクに保存する必要があります。 
- ご利用の対象ユーザー インサイト環境には、関連する Dataverse 環境が必要です。 また、その環境でもデータの保存に Dataverse を使用している場合は、対象ユーザー インサイトの **データ共有を有効にする** にチェックを入れてください。 詳細については、[対象ユーザー インサイトで環境を作成および構成する](../audience-insights/create-environment.md)を参照してください。
- エンゲージメント インサイトと対象ユーザーインサイト環境の両方に管理者権限が必要です。
- リンク先の環境は同一の地域である必要があります。

> [!NOTE]
> - 対象ユーザー インサイトのサブスクリプションが、対象ユーザー インサイトが社内で管理している Data Lake を使用した試用版の場合は、[pirequest@microsoft.com](mailto:pirequest@microsoft.com) までお問い合わせください。 
> - 対象ユーザー インサイト環境で独自の Azure Data Lake Storage を使用してデータを保存する場合は、ストレージ アカウントにエンゲージメント インサイトの Azure サービス プリンシパルを追加する必要があります。 詳しくは、[対象ユーザー インサイトの Azure サービス プリンシパルで Azure Data Lake Storage アカウントに接続する](../audience-insights/connect-service-principal.md) を参照してください。 


## <a name="create-an-environment-link"></a>環境のリンクを作成する

エンゲージメント インサイトの **管理** > **環境** の設定を更新することで、環境リンクを作成することができます。

**対象ユーザー インサイトとエンゲージメント インサイトの間にリンクを作成する**

1. **環境管理者** ページで、**リンク環境** タブを選択します。

    :::image type="content" source="media/integrate1.png" alt-text="環境を設定します。":::

1. 画面の左上または下部にある、**環境の設定** を選択します。

     :::image type="content" source="media/integrate2.png" alt-text="対象者分析情報環境を選択する。":::

1. 対象者インサイトの環境を選択し、**次へ** を選択して終了します。 以上で、リンクされた環境のオプション機能を選択できます。
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>対象ユーザー インサイトの統合プロファイルの属性とセグメントを有効にする

環境をリンクした後、リンクした環境のオプション機能を選択することができます。 これらの機能により、対象ユーザー インサイトからの統合されたプロファイル属性とセグメントが可能になり、顧客データをインタラクティブに分析できます。

> [!IMPORTANT]
> 対象ユーザー インサイトのセグメントがエンゲージメント インサイトに表示するには、まず[マージとダウンストリームのプロセスを実行する](../audience-insights/merge-entities.md)必要があります。 ダウンストリームのプロセスでは、対象ユーザー インサイトのセグメントをエンゲージメント インサイトと共有するための固有のテーブルを生成することが重要です。 (システムの更新がスケジュールされている場合、自動的にダウンストリームのプロセスが含まれます。)

**エンゲージメント インサイトでWebデータを分析する**

1. **環境管理者** ページで、**対象者インサイトからのデータをエンゲージメント インサイトと共有する** に切り替えて、**次へ** を選択します。

    :::image type="content" source="media/integrate4.png" alt-text="機能を選択する。":::

1. エンゲージメント インサイトのディメンションとなる統合プロファイルの属性を選択します。 (すべての属性が有用なディメンションであるとは限りません。 たとえば、Web サイトのイベントを分析する際に、**名** や **姓** を属性として必要とする可能性は低いでしょう。)

    :::image type="content" source="media/integrate5.png" alt-text="ディメンションをキュレーションする。":::

   >[!NOTE]
   > 識別子 (**ID** や **代替 ID** など) を表す対象ユーザー インサイトのプロファイル属性はすべて、利用可能な属性からフィルタリングされ、エンゲージメント インサイトのディメンションとなります。

1. 属性の選択をした後は、**次へ** を選択します。
1. エンゲージメント インサイトで対象ユーザーインサイト プロファイルのディメンションとセグメントを表示できるユーザーを追加します。

    :::image type="content" source="media/integrate6.png" alt-text="顧客データへのアクセスを管理する 。":::

   > [!IMPORTANT]
   > このステップでユーザーを明示的に追加しない場合、データはエンゲージメント インサイトでユーザーから非表示になります。
   > 対象ユーザー インサイトのセグメントがエンゲージメント インサイトに表示するには、まず[マージとダウンストリームのプロセスを実行する](../audience-insights/merge-entities.md)必要があります。 ダウンストリームのプロセスでは、対象ユーザー インサイトのセグメントをエンゲージメント インサイトと共有するための固有のテーブルを生成することが重要です。 (システムの更新がスケジュールされている場合、自動的にダウンストリームのプロセスが含まれます。)

1. 選択項目を確認し、**完了** を選択します。

    :::image type="content" source="media/integrate7.png" alt-text="顧客データ設定の確認。":::

## <a name="export-refined-events-to-audience-insights"></a>絞り込んだイベントを対象ユーザー インサイトにエクスポートする

環境間のリンクを作成した後、エンゲージメント インサイトから対象ユーザー インサイトに絞り込まれたイベントをエクスポートして、新しいデータソースとして取り込むことができます。 

詳細については、[エンゲージメント インサイトからのウェブデータを対象ユーザー インサイトと統合する](../audience-insights/integrate-engagement-insights.md)にアクセスしてください。

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
