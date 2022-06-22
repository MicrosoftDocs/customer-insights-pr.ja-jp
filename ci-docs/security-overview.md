---
title: Customer Insights におけるセキュリティ設定
description: Dynamics 365 Customer Insights のセキュリティ設定について説明します。
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947421"
---
# <a name="security-settings-in-customer-insights"></a>Customer Insights におけるセキュリティ設定

**セキュリティ** ページには、ユーザーのアクセス許可を構成するためのオプションと、Dynamics 365 Customer Insights をより安全にするための機能が一覧表示されます。 管理者のみがこのページにアクセスできます。

**管理者** > **安全** に移動して、設定を構成します。

**セキュリティ** ページには、次のタブが含まれています。

- [ユーザー](#users-tab)
- [API](#apis-tab)
- [非公開リンク](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [カスタマー ロックボックスを使用して顧客データに安全にアクセスする (プレビュー)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>ユーザー タブ

Customer Insights へのアクセスは、管理者によってアプリケーションに追加された組織内のユーザーに制限されています。**ユーザー** タブを使用すると、ユーザー アクセスとその権限を管理できます。 詳細については、[ユーザーのアクセス許可](permissions.md) を参照してください。

## <a name="apis-tab"></a>API タブ

キーを表示および管理して、[Customer Insights API](apis.md) をあなたの環境のデータと使用します。

**プライマリを再生成** または **セカンダリを再生成** を選択すると、新しいプライマリ キーとセカンダリ キーを作成できます。 

環境への API アクセスをブロックするには、**無効にする** を選択します。 API が無効になっている場合は、**有効にする** を選択して再度アクセスを許可します。

## <a name="private-links-tab"></a>非公開リンク タブ

[Azure Private Link](/azure/private-link/private-link-overview) により、Customer Insightsは、仮想ネットワーク内のプライベート エンドポイントを介して、Azure Data Lake Storageアカウントに接続します。 パブリック インターネットに公開されていないストレージ アカウント内のデータに対して、プライベート リンクはその制限されたネットワークへの接続を可能にします。

> [!IMPORTANT]
> プライベート リンク接続を設定するための最小の役割要件:
>
> - Customer Insights: 管理者
> - Azure の組み込みロール: [ストレージ アカウント共同作成者](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Azure のカスタム ロールのアクセス許可: [Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Customer Insights でプライベート リンクを設定するには、2 段階のプロセスがあります。 まず、Customer Insights の **管理者** > **セキュリティ** > **Private Links** から Private Link の作成を開始します。 **Private Link の追加** ペインには、表示権限があるテナントのストレージ アカウントが一覧表示されます。 ストレージ アカウントを選択し、Private Link の作成に同意します。

続いてに、Data Lake Storage のアカウント側で Private Link を承認する必要があります。 画面に表示されるリンクを開いて、新しい Private Link を承認してください。

## <a name="key-vault-tab"></a>Key Vault タブ

**Key Vault** タブを使用すると、自身の [Azure Key Vault](/azure/key-vault/general/basic-concepts) を環境にリンクおよび管理します。
専用の Key Vault を使用して、組織のコンプライアンス境界でシークレットをステージングおよび使用できます。 Customer Insights では、Azure Key Vault のシークレットを使用して、サードパーティ システムに [接続を設定する](connections.md) ことができます。

詳細については、[独自の Azure Key Vault を導入する](use-azure-key-vault.md) を参照してください。

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>カスタマー ロックボックスを使用して顧客データに安全にアクセスする (プレビュー)

Customer Insights は、Power Platform カスタマー ロックボックス機能を使用しています。 カスタマー ロックボックスは、データ アクセス要求を確認し、承認 (または拒否) するためのインターフェイスを提供します。 このリクエストは、サポート案件を解決するために顧客データへのデータアクセスが必要な場合に発生します。 この機能を利用するには、Customer Insights がテナント内の Microsoft Dataverse 環境と既存の接続を持つ必要があります。

Customer Lockbox の詳細については、Power Platform Customer Lockbox の [まとめ](/power-platform/admin/about-lockbox#summary) を参照してください。 また、Customer Lockbox を有効にするための[ワークフロー](/power-platform/admin/about-lockbox#workflow)と必要な[設定](/power-platform/admin/about-lockbox#enable-the-lockbox-policy)についても説明されています。

> [!IMPORTANT]
> Power Platform または Power Platform のグローバル管理者は、Customer Insights 対して発行された Customer Lockbox のリクエストを承認することができます。

[!INCLUDE [footer-include](includes/footer-banner.md)]
