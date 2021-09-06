---
title: Customer Insights の有料ライセンスを作成して構成します
description: Dynamics 365 Customer Insights のライセンス サブスクリプションを取得し、設定する手順。
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034458"
---
# <a name="get-started-with-a-paid-subscription"></a>有料サブスクリプションの基本

この記事では、組織が Dynamics 365 Customer Insights サブスクリプションを購入後に、新しい環境を作成する方法について説明します。 Customer Insights の購入をご希望の場合、当社の連絡先は [Dynamics 365 Customer Insights のウェブサイト](https://dynamics.microsoft.com/ai/customer-insights/)に掲載されています。 

サービスと機能をお試しになりたい場合は、[トライアル環境をセットアップする](get-started-trial.md)を参照してください。

## <a name="create-an-environment-in-an-existing-organization"></a>既存の組織で環境を作成する

Customer Insights のサブスクリプションライセンスを購入すると、Microsoft 365 テナントのグローバル管理者に、環境の作成を促すメールが届きます。 [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) にアクセスし、使用を開始します。 

Customer Insights はユーザーごとのライセンスではないため、ライセンス エリアには表示されません。 Microsoft 365 管理センターでライセンスを探している場合は、**ご利用の製品** に進みます。 

> [!NOTE]
> 組織では、Customer Insights ライセンスごとに *2* つの環境を作成できます。 組織が複数のライセンスを購入する場合は、[サポート チームに連絡](https://go.microsoft.com/fwlink/?linkid=2079641) して利用可能な環境の数を増やしてください。 キャパシティとアドオン キャパシティの詳細については、 [Dynamics 365 ライセンスガイド](https://go.microsoft.com/fwlink/?LinkId=866544)をダウンロードしてください。

環境の作成方法 :

1. **環境を作成する** ダイアログで、**新しい環境** を選択します。

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="新しい Customer Insights 環境を作成するダイアログ。":::

   最初から環境のセットアップを開始することをお勧めします。 しかし、試用版環境の管理者やメンバーであれば、**既存の環境からコピー** を選択することで、[他の環境からデータをコピー](manage-environments.md#copy-the-environment-configuration)することができます。 データのコピー元となる組織の、利用可能なすべての環境のリストが表示されます。

1. 次の詳細を入力します:
   - **名前**: この環境の名前。 既存の環境からコピーする場合は、このフィールドには既にに入力されていますが、変更することもできます。
   - **リージョン** : サービスが展開、ホストされるリージョンを示します。
   - **タイプ**: 実稼働環境、またはサンドボックス環境のどちらを作成するかを選択します。 サンドボックス環境では、スケジュールされたデータの更新は許可されておらず、事前の実装とテストを目的としています。
   
1. オプションで、**詳細設定** を選択できます:

   - **すべてのデータを保存する** : Customer Insights から生成された出力データを保存する場所を指定します。 **Customer Insights ストレージ** (Customer Insights チームによって管理される Azure Data Lake) および **Azure Data Lake Storage** (独自の Azure Data Lake Storage) の 2 つのオプションがあります。 既定では、Customer Insights のストレージが選択されています。

     > [!NOTE]
     > Azure Data Lake Storage にデータを保存することで、その Azure Storage のアカウントに対して適切な地理的位置にデータが転送され、保存されることに同意したことになります。これは、 Dynamics 365 Customer Insights におけるデータの保存場所とは異なる場合があります。 [Microsoft Trust Center を詳しく知る。](https://www.microsoft.com/trust-center)
     >
     > 現在、Power BI データフローから取り込まれたエンティティは、Microsoft Dataverse のマネージド Data Lake に格納されます。 
     > 
     > 環境の作成時に選択したのと同じ Azure リージョンの Azure Data Lake Storage アカウントのみをサポートしています。 
     > 
     > 階層名前空間が有効になっている Azure Data Lake Storage アカウントのみをサポートしています。


   - Azure Data Lake Storage オプションでは、認証用にリソース ベース オプションとサブスクリプション ベース オプションのどちらかを選択できます。 詳細については、[対象者に関するインサイトを Azure サービス プリンシパルで Azure Data Lake Storage Gen2 アカウントに接続する](connect-service-principal.md) を参照してください。 **コンテナー** 名は変更できず、`customerinsights` になります。
   
   - [既成のモデル](predictions-overview.md#out-of-box-models)を使用したり、Microsoft Dataverse とのデータ共有を構成したり、オンプレミスのデータソースからのデータ取り込みを可能にしたい場合は、**Microsoft Dataverseとのデータ共有を構成し、追加機能を有効にする** の下に Microsoft Dataverse の環境 URL を入力してください。 **データ共有を有効にする** を選択して、Customer Insights 出力データを Microsoft Dataverse マネージド Data Lake と共有します。

     > [!NOTE]
     > - Microsoft Dataverse マネージド Data Lake とのデータ共有は、すべてのデータを自分の Azure Data Lake Storage に保存する場合、現在サポートされていません。
     > - Microsoft Dataverse Managed Data Lake を使用したデータ共有を有効にした場合、[エンティティでの不足値の予測](predictions.md) は、現在サポートされていません。

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Microsoft Dataverse とのデータ共有を有効にする構成オプション。":::

   データの取り込みなどのシステム処理が完了すると、指定したストレージ アカウントに対応するフォルダが作成されます。 データファイルと model.json ファイルが作成され、プロセス名に基づいたフォルダに追加されます。

   Customer Insights の複数の環境を作成し、それらの環境からの出力エンティティをストレージ アカウントに保存することを選択した場合、コンテナーに ci_<environmentid> が含まれる環境ごとに個別のフォルダーが作成されます。

1. **作成** を選択して環境を設定します。 

## <a name="configure-an-environment"></a>環境を構成する

Customer Insights の構成を始める際には、以下の記事を参考にしてください。 

- [ユーザーを追加し、権限を割り当てる](permissions.md)。
- [データソースを取り込み](data-sources.md)、[データ統合プロセス](data-unification.md)を通してそれらを実行し、[統一された顧客プロファイル](customer-profiles.md)を取得する。
- [統一された顧客プロファイルを充実させる](enrichment-hub.md)または [予測モデルを実行する](predictions-overview.md)。
- [セグメント](segments.md)を作成して顧客をグループ化し、KPI [対策](measures.md)を確認します。
- [接続](connections.md)と[エクスポート](export-destinations.md)を設定し、他のアプリケーションでデータのサブセットを処理します。
