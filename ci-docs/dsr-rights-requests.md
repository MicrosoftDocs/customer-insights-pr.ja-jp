---
title: GDPR におけるデータ主体の権利 (DSR) | Microsoft Docs
description: Dynamics 365 Customer Insights のデータ主体の要求への応答。
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146701"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR におけるデータ主体の権利 (DSR)

欧州連合の一般データ保護規則 (GDPR) は、2018 年 5 月 25 日から施行されています。 これにより、個人にデータに関する重要な権利を与えています。 GDPR の目的は、各個人のプライバシーの権利を保護し、有効にすることです。 [Microsoft セキュリティ センター](https://www.microsoft.com/trust-center)では、Microsoft がセキュリティとコンプライアンスについてどのように約束しているかについての詳細を参照できます。

マイクロソフトは、お客様が GDPR の要件を満たせるように支援をしています。 これには、ユーザーID、電話番号、メール アドレスなどの個人情報を含むデータを削除し、エクスポートする権利が含まれます。 管理者は、個人データの削除やエクスポートに関するユーザーの要求を実行することができます。

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights のGDPR データ主体の削除要求へ応答する。

組織の顧客情報から個人データを削除する「削除する権利」は、一般データ保護規則 (GDPR) における主要な保護となっています。 個人データの削除では、監査ログ情報を除くすべての個人データとシステム生成ログが削除されます。

#### <a name="manage-data-subject-delete-requests"></a>データ主体の削除要求の管理

Customer Insights は、特定の顧客またはユーザーの個人データを削除するために次の製品内エクスペリエンスを提供します。

- **顧客データの削除要求を管理する** : Customer Insights の顧客データは、Customer Insights 外部の元のデータ ソースから取り込まれます。 GDPR 削除要求は、まず元のデータ ソースで実行します。
- **Customer Insights ユーザー データの削除要求の管理**: ユーザーのデータは Customer Insights によって作成されます。 すべての GDPR 削除要求は、Customer Insights で実行する必要があります。

##### <a name="manage-requests-to-delete-customer-data"></a>顧客データの削除要求を管理する

Customer Insights の管理者は、次の手順に従って、データ ソースで削除された顧客データを取り除くことができます。 以下の手順に進む前に、データ ソースで削除リクエストが実行されたことを確認してください。 

1. Dynamics 365 Customer Insights にサインインします。
1. **データ** > **データ ソース** に移動します
1. 削除された顧客データを含むリスト内の各データ ソースについて :
   1. 垂直の省略記号 (&vellip;) を選択し、**更新** を選択します。
   1. **状態** 下のデータ ソースの状態を確認します。 チェックマークが付いていると、更新が成功したことを意味します。 警告の三角形は、何かがうまくいかなかったことを意味します。 警告の三角形が表示された場合は、D365CI@microsoft.com にお問い合わせください。
1. データ ソースの更新が成功したら、ダウンストリームの更新も実行します。 特に、Customer Insights の定期的な完全更新がスケジュールされていない場合です。 

> [!IMPORTANT]
> 静的セグメントは、完全更新や、削除要求後のダウンストリーム更新の実行には含まれていません。 顧客データが静的セグメントからも確実に削除されるようにするには、更新されたソース データを使用して静的セグメントを再作成します。

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

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights でのデータ削除処理

1. データ パーティションとデータ スナップショットが 30 日を超えて非アクティブである場合、データは削除されます (データ パーティションとデータ スナップショット)。つまり、データ ソースの更新を通じて、新しいデータ パーティションとスナップショットに置き換えられます。
2. すべてのデータとスナップショットが削除されるわけではありません。 最新のデータ パーティションとデータ スナップショットは、Customer Insightsで使用されているため、定義上アクティブです。 最新のデータの場合、過去 30 日以内にデータ ソースが更新されなかったかどうかは関係ありません。

[!INCLUDE [footer-include](includes/footer-banner.md)]
