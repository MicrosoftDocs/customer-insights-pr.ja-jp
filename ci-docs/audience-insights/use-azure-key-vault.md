---
title: シークレットを管理するために独自の Azure Key Vault を持参する
description: 独自の Azure Key Vault を使用するように Customer Insights を構成する方法を学習します。
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 418575f724090628da8bd01e2569a4cb9e646337
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376514"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>独自の Azure Key Vault を持ち込む (プレビュー)

専用の [Azure key vault](/azure/key-vault/general/basic-concepts)を対象者分析情報環境にリンクすると組織がコンプライアンス要件を満たすのに役立ちます。
専用の Key Vault を使用して、組織のコンプライアンス境界でシークレットをステージングおよび使用できます。 対象者分析情報では、Azure Key Vault のシークレットを使用してサードパーティ システムに[接続を設定する](connections.md)ことができます。

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Key Vault を対象者分析情報環境にリンクする

### <a name="prerequisites"></a>前提条件

対象者分析情報で Key Vault を構成するには、次の前提条件が満たされている必要があります。

- 有効な Azure サブスクリプションがある。

- 対象者に関するインサイトで [管理者](permissions.md#admin) ロールを持っていること。 [対象者分析情報のユーザー権限](permissions.md#assign-roles-and-permissions)の詳細を参照してください。

- Key Vault または Key Vault が属するリソース グループでは、[共同作成者](/azure/role-based-access-control/built-in-roles#contributor)と[ユーザー アクセス管理者](/azure/role-based-access-control/built-in-roles#user-access-administrator)の役割があります。 詳細については、[Azure ポータルを使用して Azure 役割の割り当てを追加または削除する](/azure/role-based-access-control/role-assignments-portal)にアクセスしてください。 Key Vault にユーザー アクセス管理者役割がない場合は、Dynamics 365 Customer Insights の Azure サービス プリンシパルの役割ベースのアクセス制御権限を別々に設定する必要があります。 リンクする必要のある Key Vault に [Azure サービス プリンシパルを使用する](connect-service-principal.md)ステップに従います。

- Key Vault では Key Vault ファイアウォールを **無効** にしておく必要があります。

- Key Vault は、対象者分析情報環境と同じ [Azure 場所](https://azure.microsoft.com/global-infrastructure/geographies/#overview)にあります。 対象者分析情報の環境のリージョンは、**管理者** > **システム** > **会社情報** > **リージョン** に表示されています。

### <a name="link-a-key-vault-to-the-environment"></a>Key Vault を環境にリンクする

1. **管理者** > **システム** に移動して、**セキュリティ** タブを選択します。
1. **Key Vault** タイルで、**設定** を選択します。
1. **サブスクリプション** を選択します。
1. **Key Vault** ドロップダウン リストから Key Vault を選択します。 表示される Key Vault が多すぎる場合は、リソース グループを選択して、検索結果を絞り込みます。
1. **データのプライバシーとコンプライアンス** に関する声明を受諾します。
1. **保存** を選択します。

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="対象者分析情報でリンクされた Key Vault を設定するステップ。":::

**Key Vault** タイルに、リンクされた Key Vault 名、リソース グループ、およびサブスクリプションが表示されるようになりました。 接続設定で使用する準備ができています。
Key Vault のどのアクセス許可が対象者分析情報に付与されるかについての詳細は、この記事の後半にある[対象者分析情報の Key Vault に付与されたアクセス許可](#permissions-granted-on-the-key-vault-to-audience-insights)を参照してください。

## <a name="use-the-key-vault-in-the-connection-setup"></a>接続設定で Key Vault を使用する

サードパーティ システムに[接続を設定](connections.md)する際、リンクされた Key Vault からのシークレットを使用して接続を構成できます。

1. **管理** > **接続** に移動します。
1. **接続の追加** を選択します。
1. サポートされている接続タイプの場合、Key Vault をリンクすると **Key Vault を使用する** トグルが表示されます。
1. シークレットを手動で入力する代わりに、Key Vault のシークレット値を指すシークレット名を選択できます。

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Key Vault シークレットを使用する SFTP 接続のある接続ペイン。":::

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Key Vault で対象者分析情報に付与されたアクセス許可

[Key Vault アクセス ポリシー](/azure/key-vault/general/assign-access-policy?tabs=azure-portal)または [Azure ロールベースのアクセス制御](/azure/key-vault/general/rbac-guide?tabs=azure-cli)のいずれかが有効な場合、リンクされた Key Vault の対象者分析情報に次のアクセス許可が付与されます。

### <a name="key-vault-access-policy"></a>Key Vault アクセス ポリシー

| タイプ        | 権限          |
| ----------- | -------------------- |
| キー         | [キーを取得する](/rest/api/keyvault/get-keys)、[キーを取得する](/rest/api/keyvault/get-key)                                 |
| 機密      | [シークレットを取得する](/rest/api/keyvault/get-secrets)、[シークレットを取得する](/rest/api/keyvault/get-secret)                     |
| 証明書 | [証明書を取得する](/rest/api/keyvault/get-certificates)、[証明書を取得する](/rest/api/keyvault/get-certificate) |

上記の値は、実行中にリストして読み取るための最小値です。

### <a name="azure-role-based-access-control"></a>Azure ロールベースのアクセス制御

Key Vault Reader および Key Vault Secrets User ロールが、対象者分析情報に追加されます。 これらの役割の詳細については、[Key Vault データ プレーン操作用の Azure 組み込みロール](/azure/key-vault/general/rbac-guide?tabs=azure-cli)にアクセスしてください。

## <a name="recommendations"></a>レコメンデーション

- 対象者分析情報に必要なシークレットのみを含む個別または専用の Key Valut を使用します。 [個別の Key Vault が推奨される](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults)理由について詳しくご覧ください。

- コントロール アクセス、バックアップ、監査、およびリカバリのオプションについては、[Key Vault を使用するためのベストプラクティス](/azure/key-vault/general/best-practices#turn-on-logging)に従います。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>対象者分析情報はシークレットを書き込んだり、Key Vault にシークレットを上書きしたりできますか?

番号 この記事の前半にある[付与されたアクセス許可](#permissions-granted-on-the-key-vault-to-audience-insights)セクションで概説されている読み取りおよびリストのアクセス許可のみが、対象者分析情報に付与されています。 システムは、Key Vault のシークレットを追加、削除、または上書きすることはできません。 これは、接続で Key Vault を使用しているときに資格情報を入力できない理由でもあります。

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>接続を Key Vault シークレットの使用から既定の認証に変更できますか?

番号 リンクされた Key Vault のシークレットを使用して構成した後は、既定の接続に戻すことはできません。 別の接続を作成し、不要になった場合は古い接続を削除します。

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>対象者分析情報の Key Vault へのアクセスを取り消すにはどうすればよいですか?

[Key Vault アクセスポリシー](/azure/key-vault/general/assign-access-policy?tabs=azure-portal)または [Azure ロールベースのアクセス制御](/azure/key-vault/general/rbac-guide?tabs=azure-cli)が有効になっているかどうかによって、`Dynamics 365 AI for Customer Insights` という名前でサービス プリンシパル `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` のアクセス許可を削除する必要があります。 Key Vault を使用するすべての接続が機能しなくなります。

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>接続で使用されているシークレットが Key Vault から削除されました。 対処法は何か。

Key Vault から構成されたシークレットにアクセスできなくなると、対象者分析情報に通知が表示されます。 Key Vault で[ソフト削除](/azure/key-vault/general/soft-delete-overview)を有効にして、誤って削除された場合にシークレットを復元できるようにします。

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>接続は機能しませんが、シークレットは Key Vault にあります。 原因は何でしょうか?

Key Vault にアクセスできない場合、対象者分析情報に通知が表示されます。 考えられる原因:

- 対象者分析情報サービス プリンシパルのアクセス許可が削除された。 手動で復元する必要があります。

- Key Vault のファイアウォールが有効になっている。 対象者分析情報で Key Vault に再度アクセスできるようにするには、ファイアウォールを無効にする必要があります。
