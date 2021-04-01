---
title: Customer Insights のデータを Dynamics 365 Marketing にエクスポートする
description: Dynamics 365 Marketing への接続を構成する方法について説明します。
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597609"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Dynamics 365 Marketing のコネクタ (プレビュー)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[セグメント](segments.md) を使用してキャンペーンを生成し、Dynamics 365 Marketing を使用して特定の顧客グループに連絡します。 詳しくは、[Dynamics 365 Marketing で Dynamics 365 Customer Insights のセグメントを使用する](/dynamics365/marketing/customer-insights-segments)を参照してください。

## <a name="prerequisite"></a>前提条件

- Customer Insights から Marketing にセグメントをエクスポートする前に、取引先担当者レコードが Dynamics 365 Marketing に存在している必要があります。 取引先担当者を取り込む方法の詳細については、[Common Data Services を使った Dynamics 365 Marketing](connect-power-query.md) を読んでください。

  > [!NOTE]
  > 対象者インサイトから Marketing にセグメントをエクスポートしても、Marketing インスタンスに新しい取引先担当者レコードは作成されません。 Marketing からの取引先担当者レコードは、対象者インサイトに取り込まれ、データ ソースとして使用される必要があります。 また、セグメントをエクスポートする前に、顧客 ID を取引先担当者 ID にマッピングするために、統合された顧客エンティティに含める必要があります。

## <a name="configure-the-connector-for-marketing"></a>Marketing 用のコネクタを構成する

1. 対象者に関するインサイトで、**管理** > **エクスポート先** に移動します。

1. **Dynamics 365 Marketing** で **設定** を選択します。

1. **表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。

1. **サーバー アドレス** フィールドに組織の Marketing URL を入力します。

1. **サーバー管理者アカウント** セクションで、**サインイン** を選択し、Dynamics 365 Marketing アカウントを選択します。

1. 顧客 ID フィールドを Dynamics 365 取引先担当者 ID にマップします。

1. **次へ** を選択します。

1. 1つ、または複数のセグメントを選択します。

1. **保存** を選択します。

## <a name="export-the-data"></a>データをエクスポートする

[オンデマンドでデータをエクスポート](export-destinations.md) できます。 エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]