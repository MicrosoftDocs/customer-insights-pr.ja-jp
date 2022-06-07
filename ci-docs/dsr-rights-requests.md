---
title: GDPR におけるデータ主体の権利 (DSR) | Microsoft Docs
description: Dynamics 365 Customer Insights のデータ主体の要求への応答。
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: af2583295627f98e980adbca4f216b9c34c3cad8
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808567"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR におけるデータ主体の権利 (DSR)

欧州連合の一般データ保護規則 (GDPR) は、2018 年 5 月 25 日から施行されています。 これにより、個人にデータに関する重要な権利を与えています。 GDPR の目的は、各個人のプライバシーの権利を保護し、有効にすることです。 [Microsoft セキュリティ センター](https://www.microsoft.com/trust-center)では、Microsoft がセキュリティとコンプライアンスについてどのように約束しているかについての詳細を参照できます。

マイクロソフトは、お客様が GDPR の要件を満たせるように支援をしています。 これには、ユーザーID、電話番号、メール アドレスなどの個人情報を含むデータを削除し、エクスポートする権利が含まれます。 管理者は、個人データの削除やエクスポートに関するユーザーの要求を実行することができます。

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights のGDPR データ主体の削除要求へ応答する。

組織の顧客情報から個人データを削除する「削除する権利」は、一般データ保護規則 (GDPR) における主要な保護となっています。 個人データの削除では、監査ログ情報を除くすべての個人データとシステム生成ログが削除されます。

#### <a name="manage-data-subject-delete-requests"></a>データ主体の削除要求の管理

Customer Insights は、特定の顧客またはユーザーの個人データを削除するために次の製品内エクスペリエンスを提供します。

- **顧客データの削除要求を管理する** : Customer Insights の顧客データは、Customer Insights 外部の元のデータ ソースから取り込まれます。 すべての GDPR 削除要求は、元のデータ ソースで実行しなければなりません。
- **Customer Insights ユーザー データの削除要求の管理**: ユーザーのデータは Customer Insights によって作成されます。 すべての GDPR 削除要求は、Customer Insights で実行する必要があります。

##### <a name="manage-requests-to-delete-customer-data"></a>顧客データの削除要求を管理する

Customer Insights の管理者は、次の手順に従って、データ ソースで削除された顧客データを 取り除くことができます。

1. Dynamics 365 Customer Insights にサインインします。
2. **データ** > **データ ソース** に移動します
3. 削除された顧客データを含むリスト内の各データ ソースについて :
   1. 垂直の省略記号 (&vellip;) を選択し、**更新** を選択します。
   2. **状態** 下のデータ ソースの状態を確認します。 チェックマークが付いていると、更新が成功したことを意味します。 警告の三角形は、何かがうまくいかなかったことを意味します。 警告の三角形が表示された場合は、D365CI@microsoft.com にお問い合わせください。

> [!div class="mx-imgBorder"]
> ![顧客データの GDPR 削除要求の処理。](media/gdpr-data-sources.png "顧客データの GDPR 削除要求の処理")

##### <a name="manage-delete-requests-for-user-data"></a>ユーザー データの削除要求の管理

Customer Insights 管理者は、次の手順に従って Customer Insights ユーザー データを削除できます。

1. Dynamics 365 Customer Insights にサインインします。
2. **管理者** > **セキュリティ** > **アクセス許可** の順に移動します。
3. 削除するユーザーのチェック ボックスを選択します。
4. **Remove** を選択します。

### <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR データ主体のエクスポート要求に対応する

一般データ保護規則 (GDPR) への道のりであなたのパートナーとなるという当社のコミットメントの一環として、データ サブジェクトからのリクエストするための応答を支援するドキュメントを開発しました。

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

特定のユーザーに関する同意データを削除するには、同意管理機能に取り込まれたデータ ソースで削除します。 データ ソースを更新すると、削除されたデータは同意センターでも削除されます。 同意エンティティを使用するアプリケーションは、[更新](system.md#refresh-processes) 後にソースで削除されたデータも削除します。 他のすべてのプロセスおよびアプリケーションからユーザーのデータを削除するために、データ主体の要求に応答した後、データ ソースをすばやく更新することをお勧めします。

[!INCLUDE [footer-include](includes/footer-banner.md)]