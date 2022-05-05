---
title: Dynamics 365 Customer Insights のセキュリティ設定
description: Dynamics 365 Customer Insights のセキュリティ設定について説明します。
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653739"
---
# <a name="security-overview-page"></a>セキュリティの概要ページ

**セキュリティ** ページには、ユーザーのアクセス許可を構成するためのオプションと、Dynamics 365 Customer Insights をより安全にするための機能が一覧表示されます。 管理者のみがこのページにアクセスできます。 

**管理者** > **安全** に移動して、設定を構成します。

**セキュリティ** ページには、次のタブが含まれています。
- [ユーザー](#users-tab)
- [API](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>ユーザー タブ

Customer Insights へのアクセスは、管理者によってアプリケーションに追加された組織内のユーザーに制限されています。**ユーザー** タブを使用すると、ユーザー アクセスとその権限を管理できます。 詳細については、[ユーザーのアクセス許可](permissions.md) を参照してください。

## <a name="apis-tab"></a>API タブ

キーを表示および管理して、[Customer Insights API](apis.md) をあなたの環境のデータと使用します。

**プライマリを再生成** または **セカンダリを再生成** を選択すると、新しいプライマリ キーとセカンダリ キーを作成できます。 

環境への API アクセスをブロックするには、**無効にする** を選択します。 API が無効になっている場合は、**有効にする** を選択して再度アクセスを許可します。

## <a name="key-vault-tab"></a>Key Vault タブ

**Key Vault** タブを使用すると、自身の [Azure Key Vault](/azure/key-vault/general/basic-concepts) を環境にリンクおよび管理します。
専用の Key Vault を使用して、組織のコンプライアンス境界でシークレットをステージングおよび使用できます。 Customer Insights では、Azure Key Vault のシークレットを使用して、サードパーティ システムに [接続を設定する](connections.md) ことができます。

詳細については、[独自の Azure Key Vault を導入する](use-azure-key-vault.md) を参照してください。


[!INCLUDE [footer-include](includes/footer-banner.md)]
