---
title: セグメントを Facebook 広告マネージャーにエクスポートする (プレビュー) (ビデオを含む)
description: Facebook 広告マネージャへの接続とエクスポートを構成する方法を説明します。
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195020"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>セグメントを Facebook 広告マネージャーにエクスポートする (プレビュー)

統合された顧客プロファイルのセグメントを Facebook 広告マネージャにエクスポートして Facebook と Instagram でキャンペーンを作成する。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>前提条件

- [Facebook ビジネス アカウント](https://business.facebook.com/) を含む、[Facebook 広告アカウント](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) が必要です。
- [Facebook 広告アカウント](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) における管理者権限。

## <a name="known-limitations"></a>既知の制限

- Facebook 広告マネージャーへのエクスポートあたり最大 100 万の顧客プロファイル。最大 90 分かかる場合があります。
- セグメントのみ。
- [カスタム対象者](https://www.facebook.com/business/help/744354708981227?id=2469097953376494)における Facebook *顧客リスト* の種類のみ。
  > [!NOTE]
  > 場合によっては、ドロップダウン リストにさまざまな種類のカスタム対象ユーザーが表示されることがあります。 *顧客リスト* とは異なる種類を選択した場合、エクスポートに失敗します。

## <a name="set-up-connection-to-facebook-ads-manager"></a>Facebook 広告マネージャへの接続を設定する

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **管理** > **接続** に移動します。

1. **つながりの追加** を選択して、**Facebook 広告マネージャー** を選択します。

1. 接続にわかりやすい名前を **表示名** フィールドに付けます。 接続の表示名と種類は、この接続を説明します。 接続の目的とターゲットを説明する名前を選択することをお勧めします。

1. [共同作成者がエクスポートに接続を使用できるようにします](connections.md#allow-contributors-to-use-a-connection-for-exports)。

1. Facebook Ads による認証:

   1. **Facebook で続行** を選択して、Facebook 広告アカウントにサインインします。

   1. Facebook で認証した後、**ads_management** アクセス許可を付与します。

   1. 作業する **Facebook 広告アカウント** を選択します。

   1. ドロップダウン リストから **既存のカスタム対象ユーザー** を選択するか、または **新しいカスタム対象ユーザー** を作成します。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **保存** を選択して、接続を完了します。

## <a name="configure-an-export"></a>エクスポートの構成

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **データ** > **エクスポート** に移動します。

1. **エクスポートの追加** を選択します。

1. **エクスポートの接続** フィールドで、Facebook 広告マネージャー セクションから接続を選択します。 接続できない場合は、管理者に連絡してください。

1. エクスポートの名前を入力します。

1. **データの接続** フィールドで、**E メール**、**名前と住所**、または **電話** を選択して、Facebook 広告マネージャに送信します。

1. 選択したキー識別子に対応する統合顧客エンティティの対応する属性をマッピングします。
   > [!TIP]
   > キー識別子に **E メール** を選択すると、一致する可能性が最も高くなります。 識別子を追加すると、マッチングが向上する場合があります。

1. **属性の追加** を選択し、送信する属性をさらに Facebook 広告マネージャにマップします。 Facebook 広告マネージャの属性は、以下のユーザー フレンドリ名にマッピングされます: **FN** = **名**、**LN** = **姓**、**FI** = **最初の頭文字**、**PHONE** = **電話**、**GEN** = **性別**、**DOB** = **生年月日**、**ST** = **都道府県**、**CT** = **市**、**ZIP** = **郵便番号**、**COUNTRY** = **国 / 地域**

1. エクスポートするセグメントを選択します。

1. **保存** を選択します。

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
