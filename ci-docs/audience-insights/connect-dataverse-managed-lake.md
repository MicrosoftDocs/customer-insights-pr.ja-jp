---
title: Microsoft Dataverse のテーブルへの接続
description: Microsoft Dataverse が管理する  Data Lake からデータをインポートする。
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 81412ea8259e690eb839676d82ab31847854a97e
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464072"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Microsoft Dataverse の管理された Data Lake に接続する

この記事では、Dataverseユーザーが Microsoft Dataverse 管理レイクの分析エンティティにすばやく接続する方法について説明しています。 

> [!NOTE]
> 進んで、管理レイクで使用できるエンティティのリストを表示するには、Dataverse 組織の管理者である必要があります。

## <a name="important-considerations"></a>重要な考慮事項

1. Azure Data Lake Storage などのオンライン サービスに保存されるデータは、Dynamics 365 Customer Insights で処理や保存される場所とは異なる場所に保存される場合があります。  オンライン サービスに保存されているデータをインポート、あるいは接続することで、 Dynamics 365 Customer Insights にデータの転送と保存がされることに同意するものとします。詳細については、 [Microsoft Trust Center](https://www.microsoft.com/trust-center) をご覧ください。
2. [変更の追跡](/power-platform/admin/enable-change-tracking-control-data-synchronization)が有効な Dataverse エンティティのみ表示されます。 これらのエンティティは、Dataverse マネージド データ レイクにエクスポートして、Customer Insights で使用できます。 すぐに使える Dataverse テーブルは、デフォルトで変更の追跡が有効になっています。 カスタム テーブルの変更の追跡を有効にする必要があります。 Dataverse テーブルで変更の追跡が有効になっているか確認するには、[Power Apps](https://make.powerapps.com) > **データ** > **テーブル** に移動します。 目的のテーブルを見つけて選択します。 **設定** > **詳細オプション** に移動して **変更の追跡** の設定を確認します。

## <a name="connect-to-a-dataverse-managed-lake"></a>Dataverse マネージド レイクに接続する

1. 対象者に関するインサイトで、**データ** > **データ ソース** に移動します。

2. **データソースの追加** を選択します。

3. **Microsoft Dataverse** を選び、**次へ** を選択します。

4. データソースの **名前** を入力し、 **次へ** を選択します。 

5. Dataverse の組織で使用する **サーバーアドレス** を入力し、**サインイン** を選択します。

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="データ取り込みの手順で、ユーザーが Dataverse 環境の URL を入力する画面。":::

6. 対象ユーザーインサイトのエンティティとして取り込むテーブルを、利用可能なリストから選択します。    

   > [!NOTE]
   > 既に選択されているテーブルは、他の Dynamics 365 アプリケーション (例: Dynamics 365 Sales Insights や Customer Service Insights) で使用されている可能性があります。 この選択を変更することはできません。 これらのテーブルは、データソースが作成されると、エンティティとして利用できるようになります。

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dataverse 環境内のエンティティのリストを表示するダイアログ ボックス。":::

7. 選択した内容を保存すると、Dataverse から選択したテーブルの同期が始まります。 新しく追加された接続は、**データソース** ページで確認することができます。 選択されたすべてのテーブルが同期されるまで、更新のキューに入り、エンティティ数が 0 と表示されます。

環境のデータ ソース は 1 つだけで、同じ Dataverse が管理するレイクを同時に使用できます。

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataverse マネージド レイク データ ソースを編集する

データ ソースを作成した後に、エンティティの選択を編集します。 例えば、Dataverse に追加のエンティティが追加されており、これらもインポートしたいとします。    
別の Dataverse Data Lakeに接続するには、[新しいデータ ソースを作成します](#connect-to-a-dataverse-managed-lake)。

1. 対象者に関するインサイトで、**データ** > **データ ソース** に移動します。

2. 更新を行うデータ ソースの横にある省略記号を選択します。

3. リストから **編集** オプションを選択します。

4. 使用可能なエンティティのリストから追加するエンティティを選択し、**保存** を選択します。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
