---
title: Dynamics 365 Marketing にセグメントをエクスポートする (プレビュー)
description: Dynamics 365 Marketing への接続とエクスポートを構成する方法を説明します。
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
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196630"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Dynamics 365 Marketing にセグメントをエクスポートする (プレビュー)

[セグメント](segments.md) を使用してキャンペーンを生成し、[Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments) を使用して特定の顧客グループに連絡します。

Dynamics 365 Marketing の新機能を使って、Dataverse 組織でリアルタイムに顧客体験をオーケストレーションする場合は、Dynamics 365 Marketing への標準的なエクスポートを作成する必要はありません。 Customer Insights の連絡先とセグメントは、マーケティングと Customer Insights を接続した後、Dynamics 365 Marketing で直接利用できます。 既存のエクスポートを削除する前に、[Customer Insights と Dynamics 365 Marketing 顧客体験オーケストレーションを接続する方法](/dynamics365/marketing/real-time-marketing-ci-profile) 上のドキュメントをレビューします。

## <a name="prerequisite"></a>前提条件

Customer Insights から Marketing にセグメントをエクスポートする前に、取引先担当者レコードが Dynamics 365 Marketing に存在している必要があります。 取引先担当者を取り込む方法の詳細については、[Microsoft Dataverse を使った Dynamics 365 Marketing](connect-dataverse-managed-lake.md) を読んでください。

> [!NOTE]
> Customer Insights から Marketing にセグメントをエクスポートしても、Marketing インスタンスに新しい連絡先レコードは作成されません。 Marketing からの取引先担当者レコードは、Customer Insights に取り込まれ、データ ソースとして使用される必要があります。 また、セグメントをエクスポートする前に、顧客 ID を取引先担当者 ID にマッピングするために、統合された顧客エンティティに含める必要があります。

## <a name="set-up-connection-to-marketing"></a>Marketing への接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**Dynamics 365 Marketing** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **サーバー アドレス** フィールドに組織の Marketing URL を入力します。

1. **サーバー管理者アカウント** セクションで、**サインイン** を選択し、Dynamics 365 Marketing アカウントを選択します。

1. 顧客エンティティの [取引先担当者 ID] フィールドを Dynamics 365 の取引先担当者 ID にマップします。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、Dynamics 365 Marketing セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. Dynamics 365 の取引先担当者 ID に一致する顧客エンティティの [取引先担当者 ID] フィールドを選択します。

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
