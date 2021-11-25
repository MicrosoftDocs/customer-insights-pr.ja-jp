---
title: セグメントの同意規則をアクティブ化する
description: 対象者分析情報で同意データを関連付けて、同意確認をアクティブ化するには、次の手順に従います。 管理者は同意確認を無効にすることもできます。
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 45899738d39bd5caa433e123f9fe59020e831998
ms.sourcegitcommit: 79b09498d1328e5551fb8684c44af1fb149f9881
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790782"
---
# <a name="activate-consent-rules"></a>同意規則のアクティブ化

[同意センター (プレビュー)](../consent-management/overview.md) は、さまざまなソースからの同意データを調和させるのに役立ちます。 統合された *同意* エンティティを使用し、既定の同意確認を適用します。 同意センターに同意データをインポートし、インポートされた同意データの規則を構成した後、*同意* エンティティは自動的に対象者分析情報に同期されます。

## <a name="enable-consent-checks"></a>同意確認を有効化する

同意データを同意センター (プレビュー) にインポートし、規則を設定すると、同意確認を有効にできます。 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="アクティブ化された同意データを使用した対象者分析情報設定の同意タブ。":::

1. 対象者に関するインサイトで、**管理** > **システム** に移動します。

1. **同意 (プレビュー)** タブを選択します。

1. **同意確認を有効化する** セクションで、有効にする全てのエリアの切り替えを **オン** に設定します。

1. **既定の同意規則の上書きを許可する** チェックボックスをオンにし、特定のセグメントに適用されている既定の同意確認を削除します。 

1. ドロップダウン メニューで、上書きを許可する場所を選択します。     

1. **顧客プロファイルと同意をリンクする** のセクションで、同意データを顧客データにリンクするための識別子として使用される属性を選択します。 電話番号または電子メール アドレスである可能性があります。 

1. **保存** を選んで、設定を適用します。

## <a name="disable-consent-checks"></a>同意確認を無効化する

対象者分析情報の同意データの使用を停止するには、管理者はそれに応じてシステム設定を更新する必要があります。

1. 対象者に関するインサイトで、**管理** > **システム** に移動します。

1. **同意 (プレビュー)** タブを選択します。

1. **同意確認を有効化する** セクションで、切り替えを **オフ** に設定します。
