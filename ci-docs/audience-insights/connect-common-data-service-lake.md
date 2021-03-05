---
title: Common Data Service が管理するレイク内のエンティティへの接続
description: Common Data Service が管理する  Data Lake からデータをインポートする。
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267820"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Common Data Service の管理された Data Lake に接続する

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

この記事では、既存の Dynamics 365 のお客様が Common Data Service マネージド レイクの分析エンティティに素早く接続する方法をご紹介します。 これを進めるには、 Common Data Service 組織の管理者で、マネージド レイクで利用可能なエンティティのリストを見る還元が付与されている必要があります。

## <a name="important-considerations"></a>重要な考慮事項

Azure Data Lake Storage などのオンライン サービスに保存されるデータは、Dynamics 365 Customer Insights で処理や保存される場所とは異なる場所に保存される場合があります。  オンライン サービスに保存されているデータをインポート、あるいは接続することで、 Dynamics 365 Customer Insights にデータの転送と保存がされることに同意するものとします。詳細については、 [Microsoft Trust Center](https://www.microsoft.com/trust-center) をご覧ください

## <a name="connect-to-a-common-data-service-managed-lake"></a>Common Data Service マネージド レイクに接続する

1. 対象者に関するインサイトで、**データ** > **データ ソース** に移動します。

2. **データソースの追加** を選択します。

3. **Common Data Serviceに接続する** を選択し、**次へ** を選択します。

4. データソースの **名前** を入力し、 **次へ** を選択します。 名前のガイドライン: 
   - 文字で始まる必要があります。
   - 文字と数字のみを使用してください。 特殊文字とスペースは使用できません。
   - 3〜64 文字を使用します。

5. Common Data Service 組織の **サーバーアドレス** を入力し、**サイン イン** を選択します。

   > [!div class="mx-imgBorder"]
   > ![Common Data Service のサーバーアドレスを入力するダイアログ ボックス](media/enter-CDS-org-details.png)

6. 使用可能な一覧から取り込むエンティティを選択します。    

   > [!NOTE]
   > 一部のエンティティが既に選択されている場合、それらは他の Dynamics 365 アプリケーション（Dynamics 365 Sales Insights や Customer Service Insights など）によって使用されている可能性があります。 この選択を変更することはできません。 これらのエンティティは、データ ソースが作成されると利用可能になります。

   > [!div class="mx-imgBorder"]
   > ![組織のエンティティ リストを表示するダイアログ ボックスCommon Data Service](media/select-analytical-entities.png)

7. 選択を保存して、選択したエンティティを Common Data Service マネージド レイクへの同期を開始します。 新しく追加された接続は、**データソース** ページで確認することができます。 すべてのエンティティが同期されるまでは、更新のキューに入れられ、エンティティの件数が 0 と表示されます。

環境のデータ ソース は 1 つだけで、同じ Common Data Service が管理するレイクを同時に使用できます。

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Common Data Service マネージド レイク データ ソースを編集する

データ ソースを作成した後に、エンティティの選択を編集します。 例えば、Common Data Service に追加のエンティティが追加されており、これらもインポートしたいとします。    
異なる Common Data Service に接続するには、[新規データ ソースを作成します](#connect-to-a-common-data-service-managed-lake)。

1. 対象者に関するインサイトで、**データ** > **データ ソース** に移動します。

2. 更新を行うデータ ソースの横にある省略記号を選択します。

3. リストから **編集** オプションを選択します。

4. 使用可能なエンティティのリストから追加するエンティティを選択し、**保存** を選択します。


[!INCLUDE[footer-include](../includes/footer-banner.md)]