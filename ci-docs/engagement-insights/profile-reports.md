---
title: すぐに使用できるプロファイル レポートを有効にする
description: 性別、年齢、出身市区郡または出身地域ごとにグループ化された、すぐに使用できるプロファイル レポートを作成する方法について説明します。
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033958"
---
# <a name="out-of-box-profile-reports"></a>すぐに使用できるプロファイル レポート

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

レポートは、ユーザーの行動を理解するのに役立つデータのビジュアル化のコレクションです。 Customer Insights の対象者に関するインサイトに接続することで、エンゲージメント インサイトは統合顧客プロファイルに関する情報を含むレポートを表示できます。 このレポートには、性別、年齢、地理的な場所ごとにグループ化された、所有するプロファイルの数が含まれます。

## <a name="prerequisites"></a>前提条件

対象者に関するインサイトの環境では、顧客が管理する Azure Data Lake Storage アカウントにデータを保存する必要があります。

対象者に関するインサイト機能の試用版または Customer Insights が管理するデータ レイク内の環境を使用している場合は、[当社までお問い合わせください](https://go.microsoft.com/fwlink/?linkid=2145734)。  


## <a name="enable-the-customer-profile-report"></a>顧客プロファイル レポートを有効にする

環境管理者は、[対象者に関するインサイトへの接続を作成](configure-connections.md) する必要があります。

接続の詳細を指定した後、管理者は組織内の他のユーザーにレポートを表示するためのアクセスを許可できます。 接続を設定する環境管理者は、レポートに自動的にアクセスできます。 

接続が完了すると、**プロファイル** 機能は左側のナビゲーション ウィンドウで使用できるようになります。 

- **検出** > **プロファイル** に移動し、レポートを表示します。

**プロファイル** レポートには、接続している顧客プロファイルの性別、年齢、地理的な場所に関するビジュアル化が含まれています。

:::image type="content" source="media/customer-profiles.png" alt-text="顧客プロファイル レポート。":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]