---
title: GDPR におけるデータ主体の権利 (DSR) | Microsoft Docs
description: Dynamics 365 Customer Insights のデータ主体の要求への応答。
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387117"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR におけるデータ主体の権利 (DSR)

欧州連合の一般データ保護規則 (GDPR) は、2018 年 5 月 25 日から施行されています。 これにより、個人にデータに関する重要な権利を与えています。 GDPR の目的は、各個人のプライバシーの権利を保護し、有効にすることです。 [Microsoft Trust Center](https://www.microsoft.com/trust-center) では、Microsoft がセキュリティとコンプライアンスについてどのように約束しているかについてお読みいただけます。

マイクロソフトは、お客様が GDPR の要件を満たせるように支援をしています。 これには、ユーザーID、電話番号、メール アドレスなどの個人情報を含むデータを削除し、エクスポートする権利が含まれます。 管理者は、個人データの削除やエクスポートに関するユーザーの要求を実行することができます。

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Customer Insights の対象者に関するインサイト機能に対する GDPR データ主体の削除要求への対応

組織の顧客情報から個人データを削除する「削除する権利」は、一般データ保護規則 (GDPR) における主要な保護となっています。 個人データの削除では、監査ログ情報を除くすべての個人データとシステム生成ログが削除されます。

### <a name="manage-data-subject-delete-requests"></a>データ主体の削除要求の管理

Customer Insights は、特定の顧客またはユーザーの個人データを削除するために次の製品内エクスペリエンスを提供します。

- **顧客データの削除要求を管理する** : Customer Insights の顧客データは、Customer Insights 外部の元のデータ ソースから取り込まれます。 GDPR 削除要求は、まず元のデータ ソースで実行します。
- **Customer Insights ユーザー データの削除要求の管理**: ユーザーのデータは Customer Insights によって作成されます。 すべての GDPR 削除要求は、Customer Insights で実行します。

#### <a name="manage-requests-to-delete-customer-data"></a>顧客データの削除要求を管理する

Customer Insights 管理者として、次の手順に従って、データ ソースで削除された Customer Insights の顧客データを取り除くことができます。 すべての GDPR 削除要求が、元のデータ ソースで実行されていたかどうかを検証します。

1. Dynamics 365 Customer Insights にサインインします。

1. **データ** > **データ ソース** にアクセスします。

1. 削除された顧客データを含むリスト内の各データ ソースについて :
   1. データ ソースを選択して、**更新** を選択します。
   1. **状態** 下のデータ ソースの状態を確認します。 チェックマークが付いていると、更新が成功したことを意味します。 警告の三角形は、何かがうまくいかなかったことを意味します。 警告の三角形が表示された場合は、D365CI@microsoft.com にお問い合わせください。

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="顧客データの GDPR 削除要求の処理。":::

1. データ ソースの更新が成功したら、ダウンストリームの更新も実行します。 特に、Customer Insights の定期的な完全更新がスケジュールされていない場合です。

   > [!IMPORTANT]
   > 静的セグメントは、完全更新や、削除要求後のダウンストリーム更新の実行には含まれていません。 顧客データが静的セグメントからも確実に削除されるようにするには、更新されたソース データを使用して静的セグメントを再作成します。

#### <a name="manage-delete-requests-for-user-data"></a>ユーザー データの削除要求の管理

Customer Insights 管理者として、Customer Insights ユーザー データを削除します。

1. Dynamics 365 Customer Insights にサインインします。

1. **管理者** > **セキュリティ** に移動して、**ユーザー** タブを選択します。

1. 削除するユーザーのチェック ボックスを選択します。

1. **Remove** を選択します。

1. 削除を確認します。

## <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR データ主体のエクスポート要求に対応する

データ可搬性の権限では、データ サブジェクトが、他のデータコントローラに送信ができる個人データを電子フォーマット (「構造化され、一般的に使用され、機械可読で、相互運用可能なフォーマット」) で要求することができます。

### <a name="manage-export-and-view-requests"></a>要求のエクスポートおよび表示の管理

顧客またはユーザー データのエクスポート要求を管理します。

#### <a name="export-customer-data-tenant-admin"></a>顧客データのエクスポート (テナント管理者)

テナント管理者として、顧客データをエクスポートします。

1. 要求で顧客のメールアドレスを指定して、D365CI@microsoft.com にメールを送ります。 Customer Insights チームは、登録されたテナント管理者のメール アドレスにメールを送信し、データのエクスポートの確認を求めます。
2. 要求された顧客のデータをエクスポートするにあたっての確認をします。
3. テナント管理者のメールアドレスからエクスポートされたデータを受け取ります。

#### <a name="export-user-data-tenant-admin"></a>ユーザー データのエクスポート (テナント管理者)

テナント管理者として、ユーザー データをエクスポートします。

1. 要求でユーザーのメールアドレスを指定して、D365CI@microsoft.com にメールを送ります。 Customer Insights チームは、登録されたテナント管理者のメール アドレスにメールを送信し、データのエクスポートの確認を求めます。
1. 要求されたユーザーのデータをエクスポートするにあたっての確認をします。
1. テナント管理者のメールアドレスからエクスポートされたデータを受け取ります。

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights でのデータ削除処理

データ パーティションとデータ スナップショットが 30 日以上非アクティブである場合、データは削除されます (データ パーティションとデータ スナップショット)。つまり、データ ソースの更新によって新しいデータ パーティションとスナップショットに置き換えられます。

すべてのデータとスナップショットが削除されるわけではありません。 最新のデータ パーティションとデータ スナップショットは、Customer Insights で使用されているためアクティブです。 最新のデータの場合、過去 30 日以内にデータ ソースが更新されなかったかどうかは関係ありません。

[!INCLUDE [footer-include](includes/footer-banner.md)]
