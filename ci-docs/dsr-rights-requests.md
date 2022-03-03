---
title: GDPR におけるデータ主体の権利 (DSR) | Microsoft Docs
description: Dynamics 365 Customer Insights の対象者に関するインサイト機能についてデータ主体の要求に対応します。
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350275"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR におけるデータ主体の権利 (DSR)

欧州連合の一般データ保護規則 (GDPR) は、2018 年 5 月 25 日から施行されています。 これにより、個人にデータに関する重要な権利を与えています。 GDPR の目的は、各個人のプライバシーの権利を保護し、有効にすることです。 [Microsoft セキュリティ センター](https://www.microsoft.com/trust-center)では、Microsoft がセキュリティとコンプライアンスについてどのように約束しているかについての詳細を参照できます。

マイクロソフトは、お客様が GDPR の要件を満たせるように支援をしています。 これには、ユーザーID、電話番号、メール アドレスなどの個人情報を含むデータを削除し、エクスポートする権利が含まれます。 管理者は、個人データの削除やエクスポートに関するユーザーの要求を実行することができます。

## <a name="audience-insights"></a>対象者分析情報

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights の対象者に関するインサイト機能に対する GDPR データ主体の削除要求への対応

組織の顧客情報から個人データを削除する「削除する権利」は、一般データ保護規則 (GDPR) における主要な保護となっています。 個人データの削除では、監査ログ情報を除くすべての個人データとシステム生成ログが削除されます。

#### <a name="manage-data-subject-delete-requests"></a>データ主体の削除要求の管理

対象者に関するインサイトは、特定の顧客またはユーザーの個人データを削除するために、次の製品内エクスペリエンスを提供します。

- **顧客データの削除要求を管理する** : Customer Insights の顧客データは、Customer Insights 外部の元のデータ ソースから取り込まれます。 すべての GDPR 削除要求は、元のデータ ソースで実行しなければなりません。
- **Customer Insights ユーザー データの削除要求の管理**: ユーザーのデータは Customer Insights によって作成されます。 すべての GDPR 削除要求は、Customer Insights で実行する必要があります。

##### <a name="manage-requests-to-delete-customer-data"></a>顧客データの削除要求を管理する

Customer Insights の管理者は、次の手順に従って、データ ソースで削除された顧客データを 取り除くことができます。

1. Dynamics 365 Customer Insights にサインインします。
2. 対象者に関するインサイトで、**データ** > **データ ソース** に移動します
3. 削除された顧客データを含むリスト内の各データ ソースについて :
   1. (...) を選択し、続いて **更新** を選択します。
   2. **状態** 下のデータ ソースの状態を確認します。 チェックマークが付いていると、更新が成功したことを意味します。 警告の三角形は、何かがうまくいかなかったことを意味します。 警告の三角形が表示された場合は、D365CI@microsoft.com にお問い合わせください。

> [!div class="mx-imgBorder"]
> ![顧客データの GDPR 削除要求の処理。](audience-insights/media/gdpr-data-sources.png "顧客データの GDPR 削除要求の処理")

##### <a name="manage-delete-requests-for-user-data"></a>ユーザー データの削除要求の管理

Customer Insights 管理者は、次の手順に従って Customer Insights ユーザー データを削除できます。

1. Dynamics 365 Customer Insights にサインインします。
2. 対象者に関するインサイトで、**管理** > **アクセス許可** に移動します。
3. 削除するユーザーのチェック ボックスを選択します。
4. **Remove** を選択します。

### <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR データ主体のエクスポート要求に対応する

一般データ保護規則 (GDPR) への道のりであなたのパートナーとなるという当社のコミットメントの一環として、準備に役立つドキュメントを開発しました。 このドキュメントでは、対象者に関するインサイトを使用するときに GDPR 準拠をサポートするために、現時点で実行可能な手順について説明します。

#### <a name="manage-export-and-view-requests"></a>要求のエクスポートおよび表示の管理

データ可搬性の権限では、データ サブジェクトが、他のデータコントローラに送信ができる個人データを電子フォーマット (「構造化され、一般的に使用され、機械可読で、相互運用可能なフォーマット」) で要求することができます。

##### <a name="export-customer-data-tenant-admin"></a>顧客データのエクスポート (テナント管理者)

テナント管理者は、これらの手順に従ってデータをエクスポートします :

1. 要求で顧客のメールアドレスを指定して、D365CI@microsoft.com にメールを送ります。 Customer Insights チームは、登録されたテナント管理者のメール アドレスにメールを送信し、データのエクスポートの確認を求めます。
2. 要求された顧客のデータをエクスポートするにあたっての確認をします。
3. テナント管理者のメールアドレスからエクスポートされたデータを受け取ります。

##### <a name="export-user-data-tenant-admin"></a>ユーザー データのエクスポート (テナント管理者)

1. 要求でユーザーのメールアドレスを指定して、D365CI@microsoft.com にメールを送ります。 Customer Insights チームは、登録されたテナント管理者のメール アドレスにメールを送信し、データのエクスポートの確認を求めます。
2. 要求されたユーザーのデータをエクスポートするにあたっての確認をします。
3. テナント管理者のメールアドレスからエクスポートされたデータを受け取ります。

## <a name="consent-management-preview"></a>同意の管理 (プレビュー)

同意管理機能は、ユーザー データを直接収集しません。 他のアプリケーションのユーザーから提供された同意データのみをインポートして処理します。

特定のユーザーに関する同意データを削除するには、同意管理機能に取り込まれたデータ ソースで削除します。 データ ソースを更新すると、削除されたデータは同意センターでも削除されます。 同意エンティティを使用するアプリケーションは、[更新](audience-insights/system.md#refresh-processes) 後にソースで削除されたデータも削除します。 他のすべてのプロセスおよびアプリケーションからユーザーのデータを削除するために、データ主体の要求に応答した後、データ ソースをすばやく更新することをお勧めします。


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]