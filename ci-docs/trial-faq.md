---
title: Dynamics 365 Customer Insights 試用版に関するよくあるご質問
description: Customer Insights 試用版の設定と管理に関連するよくある質問への解決策。 プラットフォームとアプリ固有の問題を解決する方法について説明します。
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 41f112466d54c9923d0daf7c55d343f9b5c81d98
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051505"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Dynamics 365 Customer Insights 試用版に関するよくあるご質問

## <a name="sign-up"></a>サインアップ

### <a name="what-are-the-system-requirements-for-the-trial"></a>試用版のシステム要件は何ですか。

このアプリはクラウド ベースのサービスであり、最新の Web ブラウザー以外に特別なソフトウェアは必要ありませんが、いくつかの制約があります。 最高の試用版体験を得るには、シークレット モードで試用版サイトにアクセスすることを避け、最も近い試用版の場所を選択してください。 [Web アプリケーションの要件についての詳細情報。](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Microsoft 365 テナントがない状態で試用版にサインアップする方法は?

仕事用以外のメール アドレスを入力すると、アカウントとテナントが作成されます。

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Sales、Marketing、Customer Service など、複数の Dynamics 365 アプリにサインアップできますか。

はい。 利用可能な試用版をすべて表示するには、[試用版ハブのページにアクセスしてください](https://dynamics.microsoft.com/dynamics-365-free-trial)。 同じメール アカウントを使用して、さまざまな試用版にサインアップできます。 ただし、同じ試用版サイトに複数のアプリを配置することはできません。 それぞれの試用版は、異なる組織と URL で実行されます。 試用データはアプリ間では共有されません。

## <a name="trial-app"></a>試用版アプリ

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>サインアップした後、試用版の詳細メールが届きませんでした。どうすればよいですか。

試用版にサインアップすると、試用版の詳細が記載されたメールが届きます。 受信トレイにメールが見当たらない場合は、スパム フォルダーを確認してください。 または、次の手順でアプリにアクセスします:

1. 試用版サイトに移動し、**無料で試す** を選択します。
1. 試用版のサインアップに使用したメール ID を入力します。 試用版アプリにリダイレクトされます。

### <a name="how-do-i-add-more-users-to-a-trial"></a>試用版にユーザーをさらに追加するにはどうすればよいですか。

ユーザーを追加する際は、試用版の管理者アカウントを使用して [Microsoft 365 管理センター](https://admin.microsoft.com) に移動します。 [管理センターのガイダンス](/microsoft-365/admin/add-users/add-users) に従って、試用版ライセンスの上限までユーザーを追加します。 追加するユーザーが既に Microsoft 365 アカウントを持っている場合は、試用する組織で適切なセキュリティ ロールを割り当てます。詳細は [セキュリティ ロールをユーザーに割り当てる](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user) を参照してください。

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>試用版環境には何人のユーザーを追加できますか？

試用版環境に追加できるユーザーの数に制限はありません。

### <a name="how-do-i-reset-the-trial-environment"></a>試用版の環境をリセットするにはどうすればよいですか。

試用版の環境はリセットできません。 ただし、試用期間の終了後に、新たに試用版を申し込むことも可能です。

## <a name="trial-expiration-and-extension"></a>試用版の有効期限と延長

### <a name="how-do-i-extend-the-trial"></a>試用版を延長するにはどうすればよいですか。

アプリで直接試用期間を延長できます。 試用版の期間は 1 回延長できます。

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>試用版を有料ライセンスに切り替えることはできますか?

一般的に、Customer Insights の有料版にアップグレードする際には、独自のデータで新しく始めることをお勧めします。 

オプションで、Customer Insights のみを使用する場合、Customer Insights を購入すると、試用版環境からデータをコピーできます。 試用版環境から有料環境に設定を移行する場合は、Customer Insights 試用版の管理者および Microsoft 365 テナントのグローバル管理者、または組織の Dynamics 365 管理者である必要があります。

Customer Insights の有料インスタンスに初めてサインインすると、新しい環境を作成するよう求められます。 このプロセスでは、既存の環境から構成をコピーし、ほとんどの設定を移行することを選択できます。 上記の権限がある場合、このリストに試用環境が表示されます。 詳細については、[環境の構成をコピーする](create-environment.md#copy-the-environment-configuration)を参照してください。

### <a name="what-are-the-trial-limits-and-quotas"></a>試用版の制限とクォータはどれくらいですか?

- Customer Insights の試用版では、独自の Azure Data Lake Storage アカウントを使用して出力データを保存することはできません。 ただし、Data Lake ストレージ アカウントからデータを取り込むことができます。
- Customer Insights 試用版を開始すると自動的にプロビジョニングされる Dataverse 環境には、最大 3GB までデータを保存できます。

## <a name="customer-insights-specific-questions"></a>Customer Insights 固有の質問

### <a name="how-do-i-start-using-the-trial"></a>試用版を開始するにはどうすればよいですか?

試用版にサインアップすると、アプリのメイン画面が表示されます。 メイン画面には、ユーザー ガイドとチュートリアルへのリンクがあります。 詳細については、試用版の新規登録ページにある [追加リソース](trial-signup.md#additional-resources) のリンクを参照してください。

### <a name="what-features-are-available-in-the-trial"></a>試用版で利用できる機能を確認する

Customer Insights 機能のほとんどの機能は、試用版で利用できます。

次の機能は **利用できません**。

- 独自の Azure Data Lake Storage アカウントを使用する新しい環境を作成することはできません。
- 試用版環境は削除できません。

### <a name="how-long-does-the-trial-last"></a>試用版の期間はどのくらいですか?

Customer Insights の試用期間は 30 日間です。 試用版環境にログインすると、23 日後に 1 回試用期間を延長できます。

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>試用版からサンプル データを削除するにはどうすればよいですか?

試用版からサンプル データを削除することはできません。
