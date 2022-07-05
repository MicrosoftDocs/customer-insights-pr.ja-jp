---
title: Microsoft Dataverse の管理された Data Lake に接続する
description: Microsoft Dataverse が管理する  Data Lake からデータをインポートする。
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 9ae0b964d8d39835715b7ddadc712e2338b855af
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081262"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Microsoft Dataverse の管理された Data Lake に接続する

Microsoft Dataverse ユーザーは、Microsoft Dataverse マネージド レイクにある分析エンティティに素早く接続することができます。

> [!NOTE]
> 進んで、管理レイクで使用できるエンティティのリストを表示するには、Dataverse 組織の管理者である必要があります。

## <a name="important-considerations"></a>重要な考慮事項

1. Azure Data Lake Storage などのオンライン サービスに保存されるデータは、Dynamics 365 Customer Insights で処理や保存される場所とは異なる場所に保存される場合があります。  オンライン サービスに保存されているデータをインポート、あるいは接続することで、 Dynamics 365 Customer Insights にデータの転送と保存がされることに同意するものとします。詳細については、 [Microsoft Trust Center](https://www.microsoft.com/trust-center) をご覧ください。
2. [変更の追跡](/power-platform/admin/enable-change-tracking-control-data-synchronization)が有効な Dataverse エンティティのみ表示されます。 これらのエンティティは、Dataverse マネージド データ レイクにエクスポートして、Customer Insights で使用できます。 すぐに使える Dataverse テーブルは、デフォルトで変更の追跡が有効になっています。 カスタム テーブルの変更の追跡を有効にする必要があります。 Dataverse テーブルで変更の追跡が有効になっているか確認するには、[Power Apps](https://make.powerapps.com) > **データ** > **テーブル** に移動します。 目的のテーブルを見つけて選択します。 **設定** > **詳細オプション** に移動して **変更の追跡** の設定を確認します。

## <a name="connect-to-a-dataverse-managed-lake"></a>Dataverse マネージド レイクに接続する

1. **データ** > **データ ソース** にアクセスします。

1. **データソースの追加** を選択します。

1. **Microsoft Dataverse** を選択します。

1. データソースの **名前** とオプションの **説明** を入力します。

1. Dataverse の組織で使用する **サーバーアドレス** を入力し、**サインイン** を選択します。

1. 使用可能なリストから、エンティティとして Customer Insights に取り込むテーブルを選択します。

   > [!NOTE]
   > 既に選択されているテーブルは、他の Dynamics 365 アプリケーション (例: Dynamics 365 Sales Insights や Customer Service Insights) で使用されている可能性があります。 この選択を変更することはできません。 これらのテーブルは、データソースが作成されると、エンティティとして利用できるようになります。

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dataverse 環境内のエンティティのリストを表示するダイアログ ボックス。":::

1. 選択した内容を保存すると、Dataverse から選択したテーブルの同期が始まります。 新しく追加された接続は、**データソース** ページで確認することができます。 選択されたすべてのテーブルが同期されるまで、更新のキューに入り、エンティティ数が 0 と表示されます。

環境のデータ ソース は 1 つだけで、同じ Dataverse が管理するレイクを同時に使用できます。

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataverse マネージド レイク データ ソースを編集する

データ ソースを作成した後に、エンティティの選択を編集します。 例えば、Dataverse に追加のエンティティが追加されており、これらもインポートしたいとします。
別の Dataverse Data Lakeに接続するには、[新しいデータ ソースを作成します](#connect-to-a-dataverse-managed-lake)。

1. **データ** > **データ ソース** にアクセスします。

1. 更新するデータ ソースの横にある、**編集** を選択します。

1. 使用可能なエンティティのリストから追加するエンティティを選択し、**保存** を選択します。
