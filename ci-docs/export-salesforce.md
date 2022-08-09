---
title: Salesforce Marketing Cloud にデータをエクスポートする (プレビュー)
description: 接続を構成して、Salesforce Marketing Cloud にエクスポートする方法を学びます。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197044"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Salesforce Marketing Cloud にデータをエクスポートする (プレビュー)

セキュリティで保護されたファイル転送プロトコル (SFTP) の場所を介して顧客データをエクスポートすることにより、Salesforce Marketing Cloudで顧客データを使用します。

## <a name="prerequisites"></a>前提条件

- [Salesforce Marketing Cloud の SFTP ホスト](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) および対応する管理者の資格情報。

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Salesforce Marketing Cloud への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **接続の追加** を選択し、**Salesforce Marketing Cloud** を選びます。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. SFTP アカウントの **ユーザー名**、**パスワード**、**ホスト名**、および **エクスポート フォルダー** を入力します。

1. **検証する** を選択して接続をテストします。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、SFTP セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. データを **Gzip 形式** または **解凍済み** のどちらでエクスポートするか、およびエクスポートされたファイルの **フィールド区切り記号** を選択します。

1. エクスポートするエンティティ (セグメントなど) を選択します。

   > [!NOTE]
   > 選択した各エンティティは、エクスポート時に最大 5 つの出力ファイルに分割されます。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Customer Insights データを SFTP の場所から、Salesforce Marketing Cloud にインポートする

1. [Salesforce Marketing Cloud のデータ拡張](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) を作成して、SFTP の場所から Customer Insights データ ファイルをインポートします。

2. Salesforce Marketing Cloud データ拡張機能に [SFTP の場所からデータをインポートします](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5)。

3. データをデータ拡張機能にインポートするようにオートメーションを設定します。 [ファイル ドロップのオートメーションとスケジュールされたオートメーション](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5) の詳細情報。

   [ファイル ドロップのオートメーション](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5)、または [スケジュールされたオートメーション](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5) を定義します。

[SFTP によるオートメーション](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5) の例はこちらです。

[!INCLUDE [footer-include](includes/footer-banner.md)]
