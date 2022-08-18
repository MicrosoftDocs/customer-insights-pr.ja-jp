---
title: セキュリティ設定を構成する
description: Dynamics 365 Customer Insights のセキュリティ設定について説明します。
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246068"
---
# <a name="configure-security-settings"></a>セキュリティ設定を構成する

API キーを管理して顧客データにアクセスし、Azure 非公開リンクを設定します。

## <a name="manage-api-keys"></a>API キーの管理

キーを表示および管理して、[Customer Insights API](apis.md) をあなたの環境のデータと使用します。

1. **システム** > **セキュリティ** に移動して、**API** タブを選択します。

1. 環境への API アクセスを設定していない場合は、**有効化** を選択します。 または、環境への API アクセスをブロックする場合は、**無効化** を選択して確認します。

1. プライマリ API キーとセカンダリ API キーを管理します。

   1. プライマリやセカンダリの API キーを表示する際は、**表示** 記号を選択します。

   1. プライマリやセカンダリの API キーをコピーする際は、**コピー** 記号を選択します。

   1. 新しいプライマリやセカンダリの API キーを作成する際は、**プライマリを再生成** または **セカンダリを再生成** を選択します。

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>カスタマー ロックボックスを使用して顧客データに安全にアクセスする (プレビュー)

Customer Insights は、Power Platform カスタマー ロックボックス機能を使用します。 カスタマー ロックボックスは、データ アクセス要求を確認し、承認 (または拒否) するためのインターフェイスを提供します。 このリクエストは、サポート案件を解決するために顧客データへのデータアクセスが必要な場合に発生します。 この機能を利用するには、Customer Insights がテナント内の Microsoft Dataverse 環境と既存の接続を持つ必要があります。

Customer Lockbox の詳細については、Power Platform Customer Lockbox の [まとめ](/power-platform/admin/about-lockbox#summary) を参照してください。 また、Customer Lockbox を有効にするための[ワークフロー](/power-platform/admin/about-lockbox#workflow)と必要な[設定](/power-platform/admin/about-lockbox#enable-the-lockbox-policy)についても説明されています。

> [!IMPORTANT]
> Power Platform または Power Platform のグローバル管理者は、Customer Insights 対して発行された Customer Lockbox のリクエストを承認することができます。

## <a name="set-up-an-azure-private-link"></a>Azure 非公開リンクを設定する

[Azure Private Link](/azure/private-link/private-link-overview) により、Customer Insightsは、仮想ネットワーク内のプライベート エンドポイントを介して、Azure Data Lake Storageアカウントに接続します。 パブリック インターネットに公開されていないストレージ アカウント内のデータに対して、プライベート リンクはその制限されたネットワークへの接続を可能にします。

> [!IMPORTANT]
> プライベート リンク接続を設定するための最小の役割要件:
>
> - Customer Insights: 管理者
> - Azure の組み込みロール: [ストレージ アカウント共同作成者](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Azure のカスタム ロールのアクセス許可: [Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Customer Insights で、**管理者** > **セキュリティ** に移動して **非公開リンク** タブを選択します。

1. **非公開リンクの追加** を選択します。

   **Private Link の追加** ペインには、表示権限があるテナントのストレージ アカウントが一覧表示されます。

1. サブスクリプション、リソース グループ、ストレージ アカウントを選択します。

1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。

1. **保存** を選択します。

1. Data Lake Storage アカウントに移動して、画面に表示されたリンクを開きます。

1. 非公開リンクを承認します。


[!INCLUDE [footer-include](includes/footer-banner.md)]
