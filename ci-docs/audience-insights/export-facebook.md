---
title: Customer Insights のデータを Facebook 広告マネージャーにエクスポートする
description: Facebook 広告マネージャへの接続の構成方法を説明します。
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643689"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Facebook 広告マネージャ向けコネクタ (プレビュー版)

統合された顧客プロファイルのセグメントを Facebook 広告マネージャにエクスポートして Facebook と Instagram でキャンペーンを作成する。

## <a name="prerequisites"></a>前提条件

- [**Facebook ビジネス アカウント**](https://business.facebook.com/) を含む [**Facebook 広告アカウント**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) が必要です。
- [**Facebook 広告アカウント**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) の管理者である必要があります。

## <a name="connect-to-facebook-ads-manager"></a>Facebook 広告マネージャに接続する

1. **管理** > **エクスポート先** へと移動します。

1. **Facebook 広告マネージャ** 配下で、**設定** を選択します。

1. **表示名** フィールドで、エクスポート先にわかりやすい名前を付けます。

1. **Facebook で続ける** を選択して、Facebook 広告アカウントにサインインします。

1. Facebook で認証した後、**ads_management** アクセス許可を付与します。

1. 作業する **Facebook 広告アカウント** を選択します。

1. **既存のカスタム対象ユーザー** ドロップダウン リストから選択するか、または **新しいカスタム対象ユーザー** を作成します。 詳細については、[**Facebook 広告マネージャの対象ユーザー**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)を参照してください。

1. **同意する** を選択して **データのプライバシーとコンプライアンス** を確認してください。

1. **次へ** を選択してエクスポートを構成します。

## <a name="configure-the-connector"></a>コネクタの構成

1. **キー識別子のフィールドを選択する** にて、**E メール**、**名前と住所**、または **電話** を選択して、Facebook 広告マネージャに送信します。

1. 選択したキー識別子に対応する統合顧客エンティティの対応する属性をマッピングします。
   > [ヒント] キー識別子に **E メール** を選択すると、一致する可能性が最も高くなります。 識別子を追加すると、マッチングが向上する場合があります。

1. **属性の追加** を選択して、追加の属性をマッピングして、Facebook 広告マネージャに送信します。 Facebook 広告マネージャは、次のようなわかりやすい名前にマッピングされています : **FN** = **名**、**LN** = **姓**、**FI** = **最初の頭文字**、**PHONE** = **電話**、**GEN** = **性別**、**DOB** = **生年月日**、**ST** = **状態**、**CT** = **市**、**ZIP** = **郵便番号**、**COUNTRY** = **国/地域**

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

## <a name="export-the-data"></a>データをエクスポートする

[オンデマンドでデータをエクスポート](export-destinations.md) できます。 エクスポートは、[スケジュールされた更新](system.md#schedule-tab) ごとに実行されます。

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Facebook 広告マネージャーへのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Facebook 広告がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、エクスポート先はいつでも削除できます。
