---
title: Customer Insights データを SFTP ホストにエクスポートする (ビデオを含む)
description: SFTP ロケーションへの接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5170ec4ca35ad2a94f02e9d696c44a32da888120
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646757"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>セグメントとその他のデータを SFTP にエクスポート (プレビュー)

顧客データをセキュリティで保護されたファイル転送プロトコル (SFTP) ロケーションにエクスポートし、サード パーティ アプリケーションで使用します。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>接続の前提条件

- SFTP ホストと対応する資格情報が必要です。

## <a name="known-limitations"></a>既知の制限

- ファイアウォールの SFTP デスティネーションは現在サポートされていません。 
- エクスポートの実行時間は、システムのパフォーマンスによって異なります。 サーバーの最小構成としては、2 つの CPU コアと 1Gb のメモリをお勧めします。 
- 2 つの CPU コアと 1Gb のメモリの推奨される最小構成を使用する場合、最大 1 億件の顧客プロファイルを持つエンティティのエクスポートには 90 分かかる場合があります。 

## <a name="set-up-connection-to-sftp"></a>SFTP への接続を設定する

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**SFTP** を選択して、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. SFTP アカウントの **ユーザー名**、**パスワード**、**ホスト名**、および **エクスポート フォルダー** を入力します。

1. **検証する** を選択して接続をテストします。

1. データを **Gzip 形式** または **解凍済み** のどちらでエクスポートするか、およびエクスポートされたファイルの **フィールド区切り記号** を選択します。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、SFTP セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. エクスポートするエンティティ (セグメントなど) を選択します。

   > [!NOTE]
   > 選択した各エンティティは、エクスポート時に最大 5 つの出力ファイルに分割されます。 

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による SFTP 経由のデータ転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、エクスポート先がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。

[!INCLUDE [footer-include](includes/footer-banner.md)]
