---
title: Common Data Model データを Azure Data Lake アカウントに接続する
description: Azure Data Lake Storage を使用して、Common Data Model データを操作します。
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643464"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Azure Data Lake アカウントを使用して Common Data Model のフォルダーに接続する

この記事では、Azure Data Lake Storage Gen2 アカウントを使用して、Common Data Model フォルダーからデータを取り込む方法について説明します。

## <a name="important-considerations"></a>重要な考慮事項

- Azure Data Lake のデータは、Common Data Model に準拠する必要があります。 他のフォーマットは現在のところ対応していません。

- データの取り込みは、Azure Data Lake *Gen2* ストレージ アカウントのみをサポートしています。 Azure Data Lake Gen1 ストレージ アカウントを使用してデータを取り込むことはできません。

- Azure サービス プリンシパルで認証するには、テナントで構成されていることを確認してください。 詳細については、[対象者に関するインサイトを Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。

- 接続してデータを取り込む Azure Data Lake は、Dynamics 365 Customer Insights 環境と同じ Azure リージョンに存在する必要があります。 別の Azure リージョンにあるデータ レイクから Common Data Model フォルダーへの接続はサポートされていません。 環境の Azure リージョンを確認するには、対象者に関するインサイトで **管理** > **システム** > **詳細** に移動します。

- オンライン サービスに保存されたデータは、Dynamics 365 Customer Insights でデータが処理または保存される場所とは別の場所に保存される場合があります。  オンライン サービスに保存されているデータをインポート、あるいは接続することで、 Dynamics 365 Customer Insights にデータの転送と保存がされることに同意するものとします。詳細については、 [Microsoft Trust Center](https://www.microsoft.com/trust-center) をご覧ください

## <a name="connect-to-a-common-data-model-folder"></a>Common Data Model フォルダーへの接続

1. 対象者に関するインサイトで、**データ** > **データ ソース** に移動します。

1. **データソースの追加** を選択します。

1. **Common Data Model フォルダーへの接続** を選択し、データ ソースの **名前** を入力して、**次へ** を選択します。

1. 認証にリソース ベースのオプションとサブスクリプション ベースのオプションのどちらを使用するかを選択できます。 詳細については、[対象者に関するインサイトを Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。 **コンテナー** 情報を入力し、**次へ** を選択します。
   > [!div class="mx-imgBorder"]
   > ![Azure Data Lake の接続の詳細を入力するダイアログボックス](media/enter-new-storage-details.png)

1. **Common Data Model フォルダーの選択** ダイアログで、データをインポートする model.json ファイルを選択し、**次へ** を選択します。
   > [!NOTE]
   > 環境内にある別のデータ ソースに関連付けられている model.json ファイルは一覧に表示されません。

1. 選択した model.json ファイルで利用可能なエンティティの一覧を取得します。 使用可能なエンティティのリストから、レビューと選択をし、**保存** を選択します。 選択したエンティティのすべてが新しいデータ ソースから取り込まれます。
   > [!div class="mx-imgBorder"]
   > ![ダイアログ ボックスに model.json ファイルのエンティティ リストが表示されます](media/review-entities.png)

8. データ プロファイルを有効にするデータ エンティティを指定し、**保存** を選択します。 データ プロファイルによって分析とその他の機能が有効になります。 エンティティ全体を選択して、エンティティからすべての属性を選択するか、選択した特定の属性を選択できます。 既定では、データ プロファイルが有効になっているエンティティはありません。
   > [!div class="mx-imgBorder"]
   > ![データ プロファイルを表示するダイアログ ボックス](media/dataprofiling-entities.png)

9. 選択内容を保存した後、**データ ソース** のページが開きます。 以上で、データ ソースとして Common Data Model フォルダーの接続が表示されます。

> [!NOTE]
> model.json ファイルは、同じ環境内の 1 つのデータ ソースにのみ関連付けることができます。 ただし、同じ model.json ファイルを複数の環境のデータ ソースに使用できます。

## <a name="edit-a-common-data-model-folder-data-source"></a>共通データモデルフォルダーのデータ ソースを編集する

Common Data Model フォルダーを含むストレージ アカウントのアクセス キーを更新できます。 model.json ファイルを変更することもできます。 ご利用のストレージ アカウントとは異なるコンテナーに接続をする場合や、アカウント名を変更する場合は、[新しいデータ ソースの接続を作成してください](#connect-to-a-common-data-model-folder)。

1. 対象者に関するインサイトで、**データ** > **データ ソース** に移動します。

2. 更新を行うデータ ソースの横にある省略記号を選択します。

3. リストから **編集** オプションを選択します。

4. 任意で、 **アクセス キー** を更新し、 **次へ** を選択します。

   ![既存のデータ ソースのアクセス キーを編集、更新するダイアログ](media/edit-access-key.png)

5. オプションで、アカウント キー接続からリソース ベースまたはサブスクリプション ベースの接続に更新できます。 詳細については、[対象者に関するインサイトを Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。 接続の更新時に、**コンテナー** 情報を変更することはできません。
   > [!div class="mx-imgBorder"]
   > ![Azure Data Lake の接続の詳細を入力するダイアログボックス](media/enter-existing-storage-details.png)

6. 必要に応じて、コンテナから異なるエンティティ セットを持つ別の model.json ファイルを選択します。

7. オプションで、取り込む追加のエンティティを選択できます。 依存関係がない場合は、選択済のエンティティを削除することもできます。

   > [!IMPORTANT]
   > 既存の model.json ファイルとエンティティのセットに依存関係がある場合は、エラーメッセージが表示され、別の model.json ファイルを選択することができません。 model.json ファイルを変更する前にこれらの依存関係を削除するか、または使用する model.json ファイルで新しいデータ ソースを作成すれば、依存関係の削除を回避することができます。

8. オプションで、追加の属性やエンティティを選択して、データ プロファイルを有効にしたり、すでに選択されているものを無効にしたりできます。   
