---
title: Customer Insights のデータを Dynamics 365 Sales にエクスポートする
description: Dynamics 365 Sales への接続を構成する方法について説明します。
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643824"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Dynamics 365 Sales のコネクタ (プレビュー)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Sales で顧客データを使用して、マーケティング リストの作成、ワークフローのフォローアップ、プロモーションの送信を行います。

## <a name="prerequisite"></a>前提条件

[Common Data Service を使用して取り込んだ Dynamics 365 Sales](connect-power-query.md) の取引先担当者レコード。

## <a name="configure-the-connector-for-sales"></a>Sales 用のコネクタを構成する

1. 対象者に関するインサイトで、**管理** > **エクスポート先** に移動します。

1. **Dynamics 365 Sales** で **設定** を選択します。

1. **表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。

1. **サーバー アドレス** フィールドに組織の Sales URL を入力します。

1. **サーバー管理者アカウント** セクションで、**サインイン** を選択し、Dynamics 365 Sales アカウントを選択します。

1. 顧客 ID フィールドを Dynamics 365 取引先担当者 ID にマップします。

1. **次へ** を選択します。

1. 1つ、または複数のセグメントを選択します。

1. **保存** を選択します。

## <a name="export-the-data"></a>データをエクスポートする

[オンデマンドでデータをエクスポート](export-destinations.md) できます。 エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。
