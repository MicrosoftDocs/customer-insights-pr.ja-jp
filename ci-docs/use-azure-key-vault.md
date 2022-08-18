---
title: 独自の Azure Key Vault を持ち込む (プレビュー)
description: 独自の Azure Key Vault を使用してシークレットを管理するために Customer Insights を構成する方法を学習します。
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246161"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>独自の Azure Key Vault を持ち込む (プレビュー)

専用の [Azure key vault](/azure/key-vault/general/basic-concepts) を Customer Insights 環境にリンクすると組織がコンプライアンス要件を満たすのに役立ちます。

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Key Vault を  Customer Insights 環境にリンクする

専用の Key Vault を設定して、組織のコンプライアンス境界でシークレットをステージングおよび使用できます。

### <a name="prerequisites"></a>前提条件

- 有効な Azure サブスクリプション。

- Customer Insights で [割り当てられた](permissions.md#add-users) [管理者](permissions.md#admin) ロール。

- Key Vault または Key Vault が属するリソース グループの、[共同作成者](/azure/role-based-access-control/built-in-roles#contributor) と [ユーザー アクセス管理者](/azure/role-based-access-control/built-in-roles#user-access-administrator)のロール。 詳細については、[Azure ポータルを使用して Azure 役割の割り当てを追加または削除する](/azure/role-based-access-control/role-assignments-portal)にアクセスしてください。 Key Vault にユーザー アクセス管理者役割がない場合は、Dynamics 365 Customer Insights の Azure サービス プリンシパルのロール ベースのアクセス制御アクセス許可を別々に設定します。 リンクする必要のある Key Vault に [Azure サービス プリンシパルを使用する](connect-service-principal.md)ステップに従います。

- Key Vault では Key Vault ファイアウォールを **無効** にしておく必要があります。

- Key Vault は、Customer Insights 環境と同じ [Azure 場所](https://azure.microsoft.com/global-infrastructure/geographies/#overview) にあります。 Customer Insights で **管理者** > **システム** の **詳細** タブに移動して、環境のリージョンを表示します。

### <a name="recommendations"></a>レコメンデーション

- Customer Insights に必要なシークレットのみを含む [個別または専用の Key Valut を使用します](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults)。

- コントロール アクセス、バックアップ、監査、およびリカバリのオプションについては、[Key Vault を使用するためのベストプラクティス](/azure/key-vault/general/best-practices#turn-on-logging)に従います。

### <a name="link-a-key-vault-to-the-environment"></a>Key Vault を環境にリンクする

1. **管理者** > **セキュリティ** に移動して、**Key Vault** タブを選択します。
1. **Key Vault** タイルで、**設定** を選択します。
1. **サブスクリプション** を選択します。
1. **Key Vault** ドロップダウン リストから Key Vault を選択します。 利用できる Key Vault が多すぎる場合は、リソース グループを選択して、検索結果を絞り込みます。
1. [データのプライバシーとコンプライアンス](connections.md#data-privacy-and-compliance) を確認し、**同意する** を選択します。
1. **保存** を選択します。

**Key Vault** タイルには、リンクされた Key Vault 名、サブスクリプション、リソース グループが表示されます。 接続設定で使用する準備ができています。
Key Vault のどのアクセス許可が Customer Insights に付与されるかについての詳細は、[Key Vault に付与されたアクセス許可](#permissions-granted-on-the-key-vault) を参照してください。

## <a name="use-the-key-vault-in-the-connection-setup"></a>接続設定で Key Vault を使用する

[対応するサードパーティ システム](#supported-connection-types) への [接続を設定する](connections.md) 際は、リンクした Key Vault のシークレットを使用して接続を構成します。

1. **管理** > **接続** に移動します。
1. **接続の追加** を選択します。
1. サポートされている接続タイプの場合、Key Vault をリンクすると **Key Vault を使用する** トグルが表示されます。
1. シークレットを手動で入力する代わりに、Key Vault のシークレット値を指すシークレット名を選択します。

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Key Vault シークレットを使用する SFTP 接続のある接続ペイン。":::

1. **保存** を選択し、接続を作成します。

## <a name="supported-connection-types"></a>サポートされている接続タイプ

次の[エクスポート](export-destinations.md)接続がサポートされています。

* [ActiveCampaign](export-active-campaign.md)
* [AutoPilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google 広告](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Key Vault に付与されたアクセス許可

[Key Vault アクセス ポリシー](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) または [Azure ロールベースのアクセス制御](/azure/key-vault/general/rbac-guide?tabs=azure-cli) のいずれかが有効な場合、リンクされた Key Vault の Customer Insights に次のアクセス許可が付与されます。

### <a name="key-vault-access-policy"></a>Key Vault アクセス ポリシー

| タイプ        | 権限          |
| ----------- | -------------------- |
| キー         | [キーを取得する](/rest/api/keyvault/keys/get-keys/get-keys)、[キーを取得する](/rest/api/keyvault/keys/get-key/get-key)                                 |
| 機密      | [シークレットを取得する](/rest/api/keyvault/secrets/get-secrets/get-secrets)、[シークレットを取得する](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| 証明書 | [証明書を取得する](/rest/api/keyvault/certificates/get-certificates/get-certificates)、[証明書を取得する](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

上記の値は、実行中にリストして読み取るための最小値です。

### <a name="azure-role-based-access-control"></a>Azure ロールベースのアクセス制御

[Key Vault リーダーおよび Key Vault シークレット ユーザー ロール](/azure/key-vault/general/rbac-guide?tabs=azure-cli) が、Customer Insights に追加されます。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Customer Insights はシークレットを書き込んだり、Key Vault にシークレットを上書きしたりできますか?

いいえ。 [付与されたアクセス許可](#permissions-granted-on-the-key-vault) セクションで概説されている読み取りおよびリストのアクセス許可のみが、Customer Insights に付与されています。 システムは、Key Vault のシークレットを追加、削除、または上書きすることはできません。 これは、接続で Key Vault を使用しているときに資格情報を入力できない理由でもあります。

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>接続を Key Vault シークレットの使用から既定の認証に変更できますか?

番号 リンクされた Key Vault のシークレットを使用して構成した後は、既定の接続に戻すことはできません。 別の接続を作成し、不要になった場合は古い接続を削除します。

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Customer Insights の Key Vault へのアクセスを取り消すにはどうすればよいですか?

[Key Vault アクセスポリシー](/azure/key-vault/general/assign-access-policy?tabs=azure-portal)または [Azure ロールベースのアクセス制御](/azure/key-vault/general/rbac-guide?tabs=azure-cli)が有効な場合は、`Dynamics 365 AI for Customer Insights` という名前でサービス プリンシパル `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` のアクセス許可を削除する必要があります。 Key Vault を使用するすべての接続が機能しなくなります。

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>接続で使用されているシークレットが Key Vault から削除されました。 どうすれば良いですか?

Key Vault から構成されたシークレットにアクセスできなくなると、Customer Insights に通知が表示されます。 Key Vault で[ソフト削除](/azure/key-vault/general/soft-delete-overview)を有効にして、誤って削除された場合にシークレットを復元できるようにします。

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>接続は機能しませんが、シークレットは Key Vault にあります。 原因は何でしょうか?

Key Vault にアクセスできない場合、Customer Insights に通知が表示されます。 考えられる原因:

- Customer Insights サービス プリンシパルのアクセス許可が削除された。 手動で復元する必要があります。

- Key Vault のファイアウォールが有効になっている。 Customer Insights で Key Vault に再度アクセスできるようにするには、ファイアウォールを無効にする必要があります。
