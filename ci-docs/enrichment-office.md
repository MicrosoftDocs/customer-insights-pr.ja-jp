---
title: Microsoft Office 365 からのデータで顧客プロファイルをエンリッチする
description: Microsoft Office からの専有データを使用して、エンゲージメント データで顧客プロファイルをエンリッチします。
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954139"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>エンゲージメント データで顧客プロファイルをエンリッチする (プレビュー)

Microsoft Office 365 からのデータを使用して、Office 365 アプリ経由でエンゲージメントに関するインサイトで顧客アカウント プロファイルをエンリッチします。 エンゲージメント データは、アカウント レベルで集計されたメールと会議の活動で構成されます。 たとえば、ビジネス アカウントからのメールの数、またはアカウントとの会議の数などです。 個々のユーザーに関するデータは利用できません。

## <a name="supported-countries-or-regions"></a>サポートされている国または地域

現時点では、英国、ヨーロッパ、北米地域でのみサポートしています。

## <a name="prerequisites"></a>前提条件

- アクティブな Office 365 クラウド ライセンス。
- [ビジネスのアカウント](work-with-business-accounts.md) に基づく.[Unified customer profile](customer-profiles.md)。
- Customer Insights 環境に、[Microsoft Dataverse 組織](create-environment.md#step-3-connect-to-microsoft-dataverse)が付属している必要があります。
- [管理者](permissions.md#admin) 権限。
- Office 365 データを使って Dynamics 365 アプリケーション内に **組織のためのインサイト** を提供するために、Office 365 テナント管理者から同意を得ている、または得ることができる。

## <a name="configure-the-enrichment"></a>エンリッチメントの構成

1. **データ** > **エンリッチメント** に移動し、**検出** タブを選択します。

1. **アカウント エンゲージメント** タイルで **データのエンリッチ** を選択します。

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="アカウント エンゲージメント タイル。":::

1. 概要を確認し、**次へ** を選択します。

1. Office データの集計対象となる組織のメールアドレスを入力します。 リストされたメール アドレスからのデータのみが、関連する通信のために処理されます。 ベスト プラクティスは、たとえば *米国の営業チーム* などのメール グループを使用することですが、これは Office 365 で管理できます。 グループ内のメール アドレスの数が解決され、表示されます。 メール アドレスの総数は 2 つ以上で、2,500 件を超えることはできません。

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text=" アカウント エンゲージメントのメール アドレス。":::

1. [Office 365テナント管理者の同意](#office-365-tenant-administrator-consent)を選択して **同意する** を選択します。

1. **次へ** を選択します。

1. **連絡先のデータセット** を選択し、エンリッチするプロファイルまたはセグメントを選択します。 **次へ** を選択します。

1. 連絡先のメール アドレス フィールドをマッピングし、**次へ** を選択します。

1. エンリッチメントと **出力エンティティ** の **名前** を指定します。

1. 選択内容を確認した後、**エンリッチメントの保存** を選択します。

1. **閉じる** を選択し、**エンリッチメント** エディターに戻ります。

### <a name="office-365-tenant-administrator-consent"></a>Office 365 テナント管理者の同意

エンリッチメントをアクティブ化するには、Office 365 テナント管理者からの同意が必要です。 エンリッチメントが保存されると、メールが Office 365 テナント管理者に送信されます。これでは、Dynamics 365 アプリケーションが企業の Office 365 使用して **組織のためのインサイト** を提供できるようにすることを確認して同意するように求められます。 Office 365 テナント管理者は、**組織のためのインサイト** を選択することにより、Office 365 管理コンソールで直接同意することもできます。

## <a name="running-the-enrichment-for-the-first-time"></a>初めてエンリッチメントを実行する

エンリッチメントが初めて開始されたとき、Office 365 テナント管理者が同意した後、Office 365 からのデータ ダウンロードが始まります。 このプロセスには少々時間がかかります。 最初のエンリッチメント実行は、6 時間の遅延で発生するようにスケジュールされます。 エンリッチメントが終了した後、アカウント エンゲージメントの概要ページでデータがカバーする日数を確認できます。 データ量が多い場合は、数日後にエンリッチメントを再度実行してください。 これにより、1 年間の時間枠全体のデータが完成します。

Office データのサイズによっては、エンリッチメントの実行が完了するまでに数時間かかる場合があります。

エンリッチメントを実行すると、Microsoft は Office 365 コンプライアンス境界内のデータを処理し、集約されたインサイトを作成します。これは、Customer Insights 環境に追加されます。 Customer Insights のユーザーは、個人レベルのデータ (たとえば、メールやカレンダーの招待状の本文) を利用できなくなります。

**実行** を選択して、エンリッチメント処理を開始します。

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>強化の結果

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] これは *Office* エンティティです。 *Office_UserEntity* には、エンリッチメント構成中に選択されたメール アドレスの Active Directory の ID が含まれています。

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="強化プロセスの実行結果プレビュー。":::

すべてのデータはアカウント レベルまで集計されます。 システムは、すべてのアカウントについて、0〜100 の範囲のエンゲージメント スコアを計算します。 エンゲージメント スコアは、他のアカウントと比較した、メールと会議全体のアカウント エンゲージメントの複合的な尺度を提供します。 次のリストには、アカウント エンゲージメント エンリッチメントが提供する集計データが含まれています。

| データ​​                                                                              | 列名                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| エンゲージメント スコア                                                                  |  EngagementScore                         |
| アカウントに送信するメールの数                                                       |  NoOfEmails_ToAccount                    |
| アカウントから送信するメールの数                                                     |  NoOfEmails_FromAccount                  |
| アカウントから開始された会議の数                                           |  NoOfMeetings_FromAccount                |
| 組織から開始された会議の数                                 |  NoOfMeetings_ToAccount                  |
| アカウントとの会議に参加している組織の人数                  |  NoOfContactsInvolved_Meetings           |
| アカウントとのメール会話に参加している組織の人数       |  NoOfContactsInvolved_Emails             |
| 組織との会議に参加しているアカウントの人数                  |  NoOfAccountContactsInvolved_Meetings    |
| 組織とのメール会話に参加しているアカウントの人数       |  NoOfAccountContactsInvolved_Emails      |
| エンゲージメント開始日 (データ内の最初のメールまたは会議)                        |  EngagementStartDate                     |
| 最終メールからの日数                                                             |  DaysSinceLastEmail                      |
| 最終会議からの日数                                                           |  DaysSinceLastMeeting                    |
| 会議の平均期間                                                      |  AverageDuration_Of_Meetings             |
| アカウントからのメール返信の平均期間                                    |  AverageDuration_Of_AccountEmailReplies  |
| 集計開始日                                                            |  AggregationStartDate                    |
| 集計レベル (年、月、または週)                                          |  AggregationLevel                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>顧客カードで強化されてデータを確認する

アカウントエンゲージメントは、個々の顧客カードでも表示できます。 **顧客** に移動し、顧客のプロフィールを選択します。 顧客カードには、アカウントのエンゲージメント スコア、メールの総数、および過去 1 年間に集計された会議の総数が表示されます。 また、メールと会議の履歴を示すグラフもあります。

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="データが強化された顧客カード。":::

## <a name="next-steps"></a>次の手順

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
たとえば、*最後のメールからの日数* と *前回の会議からの日数* の値が 60 を超えるすべての顧客を含むセグメント。 そのセグメントには、再アクティブ化を試みることができる古いアカウントが含まれています。

[!INCLUDE [footer-include](includes/footer-banner.md)]
