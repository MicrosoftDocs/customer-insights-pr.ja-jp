---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755550"
---
データを取り込んだ後、データ統合プロセスを開始して、統合された顧客プロファイルを作成します。 詳細については、[データの統合](../data-unification.md) を参照してください。

### <a name="select-source-fields"></a>ソース フィールドを選択する

1. データを取り込んだ後、連絡先を eコマースおよびロイヤルティ データから共通のデータ型にマップします。 **データ** > **統合** に移動します。

1. 顧客プロファイルを表すエンティティ - **eCommerceContacts** および **loyCustomers** を選択します。

   ![eコマースとロイヤルティ データソースを統合します。](../media/unify-ecommerce-loyalty.png)

1. **eCommerceContacts** の主キーとして **ContactId**、**loyCustomers** の主キーとして **LoyaltyID** を選択します。

1. **次へ** を選択します。 重複するレコードをスキップして、**次** を選択します。

### <a name="match-conditions"></a>一致条件

1. 主エンティティとして **eCommerceContacts : eCommerce** を選択し、すべてのレコードを含めます。

1. **loyCustomers : LoyaltyScheme** を選択し、すべてのレコードを含めます。

1. ルールを追加します。
   - eCommerceContacts と loyCustomers の両方に **FullName** を選択します。
   - **正規化** に対して **種類 (電話、名前、住所、...)** を選択します。
   - **精度レベル** の設定: **基本** と **値**: **高い**。
   - 名前に **FullName、Email** と入力します。

1. メール アドレスの 2 番目の条件を追加します。
   - eCommerceContacts と loyCustomers の両方に **Email** を選択します。
   - 正規化を空白のままにします。
   - **精度レベル** の設定: **基本** と **値**: **高い**。

   ![名前とメールの照合ルールを統一します。](../media/unify-match-rule.png)

1. **完了** を選択します。

1. **次へ** を選択します。

### <a name="unify-fields"></a>統合フィールド

1. **loyCustomers** エンティティの **ContactId** の名前を **ContactIdLOYALTY** に変更して、取り込まれた他の ID と区別します。

1. **次へ** を選択して確認し、**顧客プロファイルの作成** を選択します。
