---
title: テンプレートからメジャーを作成する
description: 一般的な使用事例にのテンプレートを使用してメジャーを定義します。
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: eeabd889f7b694f8d809894169a3cdc068acc340
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646656"
---
# <a name="use-a-template-to-build-a-measure"></a>テンプレートを使用してメジャーを作成する

一般的に使用される[メジャー](measures.md)の定義済みテンプレートを使用して、それらを作成できます。 テンプレートの詳細な説明とガイド付きのエクスペリエンスは、効率的なメジャーの作成に役立ちます。 テンプレートは、*Unified Activity* エンティティからマップされたデータに基づいて構築されます。 したがって、テンプレートからメジャーを作成する前に、[顧客活動](activities.md) を構成していることを確認します。

カスタム メジャーを作成するには、[メジャー ビルダーを使用して最初からメジャーを作成する](measure-builder.md)を参照してください。

# <a name="individual-consumers-b-to-c"></a>[個人消費者 (B2C)](#tab/b2c)

使用できるメジャー テンプレート: 
- 平均取引値 (ATV)
- 合計取引値
- 日別平均売上
- 年別平均売上
- 取引回数
- 獲得したロイヤルティ ポイント
- 引き換え済みのロイヤルティ ポイント
- ロイヤルティ ポイントの残高
- アクティブな顧客ライフスパン
- ロイヤルティ メンバーシップの期間
- 最後の購入以降の時間

## <a name="build-a-new-measure-using-a-template"></a>テンプレートを使用して新しいメジャーを作成する

1. **メジャー** に移動します。

1. **新規** を選択し、**テンプレートを選択** を選択します。

   :::image type="content" source="media/measure-use-template.png" alt-text="テンプレートを強調表示して新しいメジャーを作成する際のドロップダウン メニューのスクリーンショット。":::

1. ニーズに最適なテンプレートを検索し、**テンプレートを選択** を選択します。

1. すべてのデータが揃っている場合、必要なデータを確認して、**開始する** を選択します。

1. メジャー名の横にある **詳細の編集** を選択します。 メジャーの名前を入力します。 オプションで、[タグ](work-with-tags-columns.md#manage-tags)をメジャーに追加します。

   :::image type="content" source="media/measures_edit_details.png" alt-text="[詳細の編集] ダイアログ ボックス。":::

1. **完了** を選択します。

1. **期間の設定** セクションで、使用するデータの概算時間を定義します。 **すべての時間** を選択して新しいメジャーをデータセット全体に適用するか、メジャーを **特定の期間** にフォーカスするかどうかを選択します。

   :::image type="content" source="media/measure-set-time-period.png" alt-text="テンプレートからメジャーを構成するときの期間セクションを示すスクリーンショット。":::

1. 次のセクションで、**データの追加** を選択し、活動を選択して、*Unified Activity* エンティティから対応するデータをマップします。

    1. ステップ 1/2: **活動の種類** の下にある、使用するエンティティの種類を選択します。 **活動** でマップするエンティティを選択します。
    1. ステップ 2/2: 計算式に必要なコンポーネントの *Unified Activity* エンティティから属性を選択します。 たとえば、平均取引値の場合は、取引値を表す属性です。 **活動のタイムスタンプ** で、活動の日時を表す属性を Unified Activity エンティティから選択します。
   
1. データ マッピングが成功すると、状態が **完了** と表示され、マップされた活動と属性の名前が表示されます。

1. **実行** を選択してメジャーの結果を計算できるようになりました。 後で調整するには、**下書きの保存** を選択します。

# <a name="business-accounts-b-to-b"></a>[事業取引先企業 (B2B)](#tab/b2b)

この機能は、個々の顧客がプライマリ ターゲット対象ユーザーである環境で作成されたメジャーでのみ使用できます。

---
