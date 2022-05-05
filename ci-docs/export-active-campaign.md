---
title: Customer Insights データを ActiveCampaign にエクスポートする
description: 接続を構成して、ActiveCampaign にエクスポートする方法を学びます。
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d15b9bf7383d06070ac92d7a729fc6e6e00c9d7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646937"
---
# <a name="export-segments-to-activecampaign-preview"></a>セグメントを ActiveCampaign にエクスポートする (プレビュー)

統合された顧客プロファイルのセグメントを ActiveCampaign にエクスポートし、マーケティング活動に使用します。

## <a name="prerequisites"></a>前提条件

-   [ActiveCampaign アカウント](https://www.activecampaign.com/) および対応する管理者資格情報を所有していること。
-   Customer Insights で [セグメントを構成](segments.md) しました。
-   エクスポートされたセグメントの統合された顧客プロファイルには、メール アドレスのあるフィールドが含まれていること。

## <a name="known-limitations"></a>既知の制限

- ActiveCampaign へのエクスポートごとに最大 100 万の顧客プロファイルをエクスポートでき、完了するまでに最大 90 分間かかる場合があります。
- ActiveCampaign へのエクスポートはセグメントに制限されています。
- ActiveCampaign にエクスポートできる顧客プロファイルの数は、ActiveCampaign との契約によって異なります。

## <a name="set-up-connection-to-activecampaign"></a>ActiveCampaign への接続を設定する

1. **管理** > **接続** に移動します。

1. **接続の追加** を選択し、**ActiveCampaign** を選んで、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 既定では、管理者のみです。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. [ActiveCampaign API キーおよび REST エンドポイント ホスト名](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) を入力してください。 REST エンドポイントのホスト名はホスト名のみで、https:// は含まれません。 

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. ActiveCampaign への接続を開始するには、**接続** を選択します。

1. **エクスポート ユーザーとして自分自身を追加する** を選択して、Customer Insights の資格情報を入力します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、エクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。

1. **エクスポート用の接続** フィールドで、ActiveCampaign セクションから、接続を選択します。 このセクション名が表示されない場合、この種類の接続は使用できません。

1. [**ActiveCampaign リスト ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign) を入力します。    

1. **データ マッチング** セクションの **メール** フィールドで、顧客のメール アドレスを表すフィールドを選択します。 ActiveCampaign へは、セグメントをエクスポートする必要があります。 オプションで、姓、名、および電話番号をエクスポートして、よりパーソナライズされた電子メールを作成できます。 属性の追加 を選択し、これらのフィールドをマップします。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 [オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 


## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights から ActiveCampaign へのデータ送信を可能にすると、Dynamics 365 Customer Insights のコンプライアンスの範囲を越えて、個人情報などの機密性の高い情報が潜在的に含まれるデータの転送を許可することになります。 Microsoft はお客様の指示でそのようなデータを送信することがありますが、ActiveCampaign が関係するプライバシーまたはセキュリティのすべての義務を満たすよう見届ける責任はお客様にあります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。

Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエクスポート先はいつでも削除できます。
