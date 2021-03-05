---
title: GDPR におけるデータ主体の権利 (DSR) | Microsoft Docs
description: Dynamics 365 Customer Insights の対象者に関するインサイト機能についてデータ主体の要求に対応します。
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268692"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR におけるデータ主体の権利 (DSR)

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights の対象者に関するインサイト機能に対する GDPR データ主体の削除要求への対応

組織の顧客情報から個人データを削除する「削除する権利」は、一般データ保護規則 (GDPR) における主要な保護となっています。 個人データの削除では、監査ログ情報を除くすべての個人データとシステム生成ログが削除されます。

### <a name="manage-data-subject-delete-requests"></a>データ主体の削除要求の管理

対象者に関するインサイトは、特定の顧客またはユーザーの個人データを削除するために、次の製品内エクスペリエンスを提供します。

- **顧客データの削除要求を管理する** : Customer Insights の顧客データは、Customer Insights 外部の元のデータ ソースから取り込まれます。 すべての GDPR 削除要求は、元のデータ ソースで実行しなければなりません。
- **Customer Insights ユーザー データの削除要求の管理**: ユーザーのデータは Customer Insights によって作成されます。 すべての GDPR 削除要求は、Customer Insights で実行する必要があります。

#### <a name="manage-delete-requests-for-customer-data"></a>顧客データの削除要求の管理

Customer Insights の管理者は、次の手順に従って、データ ソースで削除された顧客データを 取り除くことができます。

1. Dynamics 365 Customer Insights にサインインします。
2. 対象者に関するインサイトで、**データ** > **データ ソース** に移動します
3. 削除された顧客データを含むリスト内の各データ ソースについて :
   1. (...) を選択し、続いて **更新** を選択します。
   2. **状態** 下のデータ ソースの状態を確認します。 チェックマークが付いていると、更新が成功したことを意味します。 警告の三角形は、何かがうまくいかなかったことを意味します。 警告の三角形が表示された場合は、D365CI@microsoft.com にお問い合わせください。

> [!div class="mx-imgBorder"]
> ![顧客データのGDPR 削除要求の処理](media/gdpr-data-sources.png "顧客データの GDPR 削除要求の処理")

#### <a name="manage-delete-requests-for-user-data"></a>ユーザー データの削除要求の管理

Customer Insights 管理者は、次の手順に従って Customer Insights ユーザー データを削除できます。

1. Dynamics 365 Customer Insights にサインインします。
2. 対象者に関するインサイトで、**管理** > **アクセス許可** に移動します。
3. 削除するユーザーのチェック ボックスを選択します。
4. **Remove** を選択します。

> [!div class="mx-imgBorder"]
> ![ユーザー データの GDPR 削除要求の処理](media/gdpr-permissions.png "ユーザー データの GDPR 削除要求の処理")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR データ主体のエクスポート要求に対応する

一般データ保護規則 (GDPR) への道のりであなたのパートナーとなるという当社のコミットメントの一環として、準備に役立つドキュメントを開発しました。 このドキュメントでは、対象者に関するインサイトを使用するときに GDPR 準拠をサポートするために、現時点で実行可能な手順について説明します。

### <a name="manage-export-and-view-requests"></a>要求のエクスポートおよび表示の管理

データ可搬性の権限では、データ サブジェクトが、他のデータコントローラに送信ができる個人データを電子フォーマット (「構造化され、一般的に使用され、機械可読で、相互運用可能なフォーマット」) で要求することができます。

#### <a name="export-customer-data-tenant-admin"></a>顧客データのエクスポート (テナント管理者)

テナント管理者は、これらの手順に従ってデータをエクスポートします :

1. 要求で顧客のメールアドレスを指定して、D365CI@microsoft.com にメールを送ります。 Customer Insights チームは、登録されたテナント管理者のメール アドレスにメールを送信し、データのエクスポートの確認を求めます。
2. 要求された顧客のデータをエクスポートするにあたっての確認をします。
3. テナント管理者のメールアドレスからエクスポートされたデータを受け取ります。

#### <a name="export-user-data-tenant-admin"></a>ユーザー データのエクスポート (テナント管理者)

1. 要求でユーザーのメールアドレスを指定して、D365CI@microsoft.com にメールを送ります。 Customer Insights チームは、登録されたテナント管理者のメール アドレスにメールを送信し、データのエクスポートの確認を求めます。
2. 要求されたユーザーのデータをエクスポートするにあたっての確認をします。
3. テナント管理者のメールアドレスからエクスポートされたデータを受け取ります。


[!INCLUDE[footer-include](../includes/footer-banner.md)]