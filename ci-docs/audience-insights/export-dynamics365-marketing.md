---
title: Customer Insights のデータを Dynamics 365 Marketing にエクスポートする
description: Dynamics 365 Marketing への接続とエクスポートを構成する方法を説明します。
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976806"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Dynamics 365 Marketing でセグメントを使用する (プレビュー)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[セグメント](segments.md) を使用してキャンペーンを生成し、Dynamics 365 Marketing を使用して特定の顧客グループに連絡します。 詳しくは、[Dynamics 365 Marketing で Dynamics 365 Customer Insights のセグメントを使用する](/dynamics365/marketing/customer-insights-segments)を参照してください。

## <a name="prerequisite-for-a-connection"></a>接続の前提条件

- Customer Insights から Marketing にセグメントをエクスポートする前に、取引先担当者レコードが Dynamics 365 Marketing に存在している必要があります。 取引先担当者を取り込む方法の詳細については、[Common Data Services を使った Dynamics 365 Marketing](connect-power-query.md) を読んでください。

  > [!NOTE]
  > 対象者インサイトから Marketing にセグメントをエクスポートしても、Marketing インスタンスに新しい取引先担当者レコードは作成されません。 Marketing からの取引先担当者レコードは、対象者インサイトに取り込まれ、データ ソースとして使用される必要があります。 また、セグメントをエクスポートする前に、顧客 ID を取引先担当者 ID にマッピングするために、統合された顧客エンティティに含める必要があります。

## <a name="set-up-connection-to-marketing"></a>Marketing への接続を設定する

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**Dynamics 365 Marketing** を選択して、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. **サーバー アドレス** フィールドに組織の Marketing URL を入力します。

1. **サーバー管理者アカウント** セクションで、**サインイン** を選択し、Dynamics 365 Marketing アカウントを選択します。

1. 顧客 ID フィールドを Dynamics 365 取引先担当者 ID にマップします。

1. **保存** を選択して、接続を完了します。 

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポートの接続** フィールドで、Dynamics 365 Marketing セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. 1つ、または複数のセグメントを選択します。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
