---
title: セグメントの同意規則をアクティブ化する
description: Dynamics 365 Customer Insights で同意データを関連付けて、同意確認をアクティブ化するには、次の手順に従います。 管理者は同意確認を無効にすることもできます。
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755176"
---
# <a name="activate-consent-rules"></a>同意規則のアクティブ化

[同意センター (プレビュー)](consent-management/overview.md) は、さまざまなソースからの同意データを調和させるのに役立ちます。 統合された *同意* エンティティを使用し、既定の同意確認を適用します。 同意データをインポートし、マップ規則を構成した後、*同意* エンティティは自動的に Dynamics 365 Customer Insights に同期されます。

## <a name="enable-consent-checks"></a>同意確認を有効化する

同意データを同意センター (プレビュー) にインポートし、規則を設定すると、同意確認を有効にできます。 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="アクティブ化された同意データを使用した Customer Insights 設定の同意タブ。":::

1. Customer Insights で、**管理** > **システム** に移動します。

1. **同意 (プレビュー)** タブを選択します。

1. **同意確認を有効化する** セクションで、有効にする全てのエリアの切り替えを **オン** に設定します。

1. **既定の同意規則の上書きを許可する** チェックボックスをオンにし、特定のセグメントに適用されている既定の同意確認を削除します。 

1. ドロップダウン メニューで、上書きを許可する場所を選択します。     

1. **顧客プロファイルと同意をリンクする** のセクションで、同意データを顧客データにリンクするための識別子として使用される属性を選択します。 電話番号または電子メール アドレスである可能性があります。 

1. **保存** を選んで、設定を適用します。

## <a name="disable-consent-checks"></a>同意確認を無効化する

Customer Insights の同意データの使用を停止するには、管理者はそれに応じてシステム設定を更新する必要があります。

1. Customer Insights で、**管理** > **システム** に移動します。

1. **同意 (プレビュー)** タブを選択します。

1. **同意確認を有効化する** セクションで、切り替えを **オフ** に設定します。

> [!TIP]
> 同意管理機能の使用を停止するには、[同意センターのシステム設定 (プレビュー)](consent-management/system-settings.md)を参照してください。
