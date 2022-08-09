---
title: Dynamics 365 Sales にセグメントをエクスポートする (プレビュー)
description: Dynamics 365 Sales への接続とエクスポートを構成する方法を説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195987"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Dynamics 365 Sales にセグメントをエクスポートする (プレビュー)

Dynamics 365 Sales で顧客データを使用して、マーケティング リストの作成、ワークフローのフォローアップ、プロモーションの送信を行います。

## <a name="prerequisites"></a>前提条件

Customer Insights から Sales にセグメントをエクスポートする前に、取引先担当者レコードが Dynamics 365 Sales に存在している必要があります。 [Microsoft Dataverse を使用した Dynamics 365 Sales](connect-dataverse-managed-lake.md) から連絡先を取り込む方法の詳細を参照します。

   > [!NOTE]
   > Customer Insights から Sales にセグメントをエクスポートしても、Sales インスタンスに新しい連絡先レコードは作成されません。 Sales からの取引先担当者レコードは、Customer Insights に取り込まれ、データ ソースとして使用される必要があります。 また、セグメントをエクスポートする前に、顧客 ID を取引先担当者 ID にマッピングするために、統合された顧客エンティティに含める必要があります。

## <a name="known-limitations"></a>既知の制限

Dynamics 365 Sales へのエクスポートは、セグメントあたり 10 万件に制限されます。完了するまでに最大 3 時間かかります。

## <a name="set-up-connection-to-sales"></a>Sales への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**Dynamics 365 Sales** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **サーバー アドレス** フィールドに組織の Sales URL を入力します。

1. **サーバー管理者アカウント** セクションで、**サインイン** を選択し、Dynamics 365 Sales アカウントを選択します。

1. 顧客 ID フィールドを Dynamics 365 取引先担当者 ID にマップします。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、Dynamics 365 Sales セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. Dynamics 365 の取引先担当者 ID に一致する顧客エンティティの [取引先担当者 ID] フィールドを選択します。

1. エクスポートするセグメントを選択します。

1. **保存** を選択します

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
