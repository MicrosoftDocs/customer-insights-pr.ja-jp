---
title: Customer Insights のデータを Facebook 広告マネージャーにエクスポートする
description: Facebook 広告マネージャへの接続とエクスポートを構成する方法を説明します。
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 34dc753aa9d2420ef8780d436e14c3c27377e4779eda0f83ca6b5424f2328f22
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031434"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>セグメント リストを Facebook 広告マネージャにエクスポート (プレビュー)

統合された顧客プロファイルのセグメントを Facebook 広告マネージャにエクスポートして Facebook と Instagram でキャンペーンを作成する。

## <a name="prerequisites-for-connection"></a>接続の前提条件

- [**Facebook ビジネス アカウント**](https://business.facebook.com/) を含む、[**Facebook 広告アカウント**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) が必要です。
- [**Facebook 広告アカウント**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) の管理者である必要があります。

## <a name="known-limitations"></a>既知の制限

- Facebook 広告マネージャーへのエクスポートごとに最大 1,000 万の顧客プロファイル。
- Facebook 広告マネージャへのエクスポートはセグメントに限定されます。
- Facebook でカスタム対象者を作成または更新する場合は、*顧客リスト* の種類のみです。
- 合計 1,000 万件のプロファイルを持つセグメントのエクスポートには、完了までに最大 90 分間かかります。

## <a name="set-up-connection-to-facebook-ads-manager"></a>Facebook 広告マネージャへの接続を設定する

ユーザーがエクスポートを作成する前に、管理者はサービスへの接続を構成し、共同作成者が接続を使用できるようにする必要があります。

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択し、**Facebook 広告マネージャ** を選択して、接続を構成します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. この接続を使用できるユーザーを選択します。 アクションを実行しない場合、既定は管理者になります。 詳細については、[共同作成者がエクスポートに接続を使用できるようにする](connections.md#allow-contributors-to-use-a-connection-for-exports) を参照してください。

1. Facebook Ads による認証: 

   1. **Facebook で続行** を選択して、Facebook 広告アカウントにサインインします。

   1. Facebook で認証した後、**ads_management** アクセス許可を付与します。

   1. 作業する **Facebook 広告アカウント** を選択します。

   1. ドロップダウン リストから **既存のカスタム対象ユーザー** を選択するか、または **新しいカスタム対象ユーザー** を作成します。 詳細については、[**Facebook 広告マネージャの対象ユーザー**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)を参照してください。
      > [!NOTE]
      > このエクスポートでは、Facebook で *顧客リスト* の種類のカスタム対象者のみを作成または更新できます。 場合によっては、ドロップダウン リストにさまざまな種類のカスタム対象ユーザーが表示されます。 *顧客リスト* とは異なる種類を選択すると、エクスポートに失敗します。 

1. **データのプライバシーとコンプライアンス** を確認し、**同意する** を選択します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

この種類の接続にアクセスできる場合は、このエクスポートを構成できます。 詳細については、[エクスポートの構成に必要なアクセス許可](export-destinations.md#set-up-a-new-export) を参照してください。

1. **データ** > **エクスポート** に移動します。

1. 新しいエクスポートを作成するには、**エクスポート先の追加** を選択します。 

1. **エクスポートの接続** で、**Facebook 広告マネージャ** セクションから接続を選択します。 このセクション名が表示されない場合、この種類の接続は利用できません。

1. **キー識別子のフィールドを選択する** にて、**E メール**、**名前と住所**、または **電話** を選択して、Facebook 広告マネージャに送信します。 

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。

1. 選択したキー識別子に対応する統合顧客エンティティの対応する属性をマッピングします。
   > [!TIP]
   > キー識別子に **E メール** を選択すると、一致する可能性が最も高くなります。 識別子を追加すると、マッチングが向上する場合があります。

1. **属性の追加** を選択し、送信する属性をさらに Facebook 広告マネージャにマップします。 Facebook 広告マネージャの属性は、以下のユーザー フレンドリ名にマッピングされます: **FN** = **名**、**LN** = **姓**、**FI** = **最初の頭文字**、**PHONE** = **電話**、**GEN** = **性別**、**DOB** = **生年月日**、**ST** = **都道府県**、**CT** = **市**、**ZIP** = **郵便番号**、**COUNTRY** = **国 / 地域**

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

エクスポートを保存しても、エクスポートはすぐには実行されません。

エクスポートは、すべての [スケジュール更新](system.md#schedule-tab) で実行されます。 

[オンデマンドでデータをエクスポート](export-destinations.md#run-exports-on-demand) することもできます。 

## <a name="data-privacy-and-compliance"></a>データのプライバシーとコンプライアンス

Dynamics 365 Customer Insights による Facebook 広告マネージャーへのデータの転送を有効化すると、Dynamics 365 Customer Insights のコンプライアンス境界線の外部へ、個人データなどの機密データを含む可能性のあるデータの転送を許可したことになります。 Microsoft ではこのようなデータをお客様の指示により転送しますが、Facebook 広告がプライバシーまたはセキュリティの義務を満たしていることを確認するのはお客様の責任になります。 詳細については、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=396732) を参照してください。
Dynamics 365 Customer Insights 管理者は、この機能の使用を中止するために、このエクスポート先はいつでも削除できます。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
