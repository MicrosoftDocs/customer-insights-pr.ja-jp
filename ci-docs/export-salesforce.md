---
title: Salesforce Marketing Cloud にデータをエクスポートする (プレビュー)
description: 接続を構成して、Salesforce Marketing Cloud にエクスポートする方法を学びます。
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c3a6a40d9b9f08c8ebca8cb4a9196a1a79f03afa
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081462"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Salesforce Marketing Cloud にデータをエクスポートする (プレビュー)

セキュリティで保護されたファイル転送プロトコル (SFTP) の場所を介して顧客データをエクスポートすることにより、Salesforce Marketing Cloudで顧客データを使用します。

## <a name="prerequisites-for-connection"></a>接続の前提条件

- SFTP ホストと対応する管理者の資格情報が利用できること。 [Salesforce Marketing Cloud の SFTP ロケーションを設定する方法](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Salesforce Marketing Cloud への接続を設定する

1. **管理** > **接続** に移動します。

1. **接続の追加** を選択し、**Salesforce Marketing Cloud** を選んで、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. SFTP アカウントの **ユーザー名**、**パスワード**、**ホスト名**、および **エクスポート フォルダー** を入力します。

1. **検証する** を選択して接続をテストします。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、SFTP セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. データを **Gzip 形式** または **解凍済み** のどちらでエクスポートするか、およびエクスポートされたファイルの **フィールド区切り記号** を選択します。

1. エクスポートするエンティティ (セグメントなど) を選択します。

   > [!NOTE]
   > 選択した各エンティティは、エクスポート時に最大 5 つの出力ファイルに分割されます。 

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Customer Insights データを SFTP の場所から、Salesforce Marketing Cloud にインポートする

1. [Salesforce Marketing Cloud のデータ拡張](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) を作成して、SFTP の場所から Customer Insights データ ファイルをインポートします。

2. Salesforce Marketing Cloud データ拡張機能に [SFTP の場所からデータをインポートします](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5)。 

3. データをデータ拡張機能にインポートするようにオートメーションを設定します。 [ファイル ドロップのオートメーションとスケジュールされたオートメーション](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5) の詳細情報。

   [ファイル ドロップのオートメーション](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5)、または [スケジュールされたオートメーション](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5) を定義します。 

[SFTP によるオートメーション](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5) の例はこちらです。

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による SFTP 経由のデータ転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、エクスポート先がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエクスポート先はいつでも削除できます。

[!INCLUDE [footer-include](includes/footer-banner.md)]
