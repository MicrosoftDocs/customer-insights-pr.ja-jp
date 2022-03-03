---
title: メジャーの理解と管理
description: メジャーをビジネスのパフォーマンスの分析と反映に役立てる方法について説明します。
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359784"
---
# <a name="measures-overview"></a>メジャーの概要

メジャーは、顧客の行動とビジネス パフォーマンスをよりよく理解するのに役立ちます。 [統合されたプロファイル](data-unification.md) から関連する値を確認します。 たとえば、企業は、個々の顧客の購買履歴を把握するために *顧客ごとの合計支出* を確認したり、企業全体の集計レベルの収益を把握するために *会社の合計売上金額* を測定したいと考えています。  

メジャーは、さまざまな演算子と単純なマッピング オプションを備えたデータ クエリ プラットフォームである[メジャー ビルダーを使用して](measure-builder.md)作成されます。 データをフィルタリングし、結果をグループ化し、[エンティティ関連パス](relationships.md)を検出して、出力をプレビューします。 [定義済みのテンプレート](measure-templates.md)を使用して、一般的に使用されるメジャーを効率的に構成できます。

メジャー ビルダーを使用して、顧客データを照会し、インサイトを抽出することによりビジネス アクティビティを計画します。 たとえば、*顧客あたりの総支出* と *顧客あたりのトータル リターン* のメジャーを作成することにより、支出は多いが収益が高い顧客のグループを特定するのに役立ちます。 これらのメジャーに基づいて[セグメントを作成し](segments.md)、次に行う最善の行動を推進します。 

## <a name="manage-your-measures"></a>メジャーの管理

メジャーのリストは、**メジャー** ページにあります。

メジャー タイプ、作成者、作成日、ステータス、および状態に関する情報が表示されます。 リストからメジャーを選択すると、出力をプレビューして CSV ファイルをダウンロードできます。

すべてのメジャーを同時に更新するには、特定のメジャーを選択せずに **すべて更新** を選択します。

:::image type="content" source="media/measure-actions.png" alt-text="単一のメジャーを管理するためのアクション。":::

次のオプションのリストからメジャーを選択します。

- メジャー名を選択して詳細を表示します。
- メジャーの構成を **編集** します。
- 最新のデータに基づいて、メジャーを **更新** します。
- メジャーの **名前を変更** します。
- メジャーを **削除** します。
- **アクティブ化** または **非アクティブ化** します。 非アクティブなメジャーは、[スケジュールされた更新](system.md#schedule-tab)中に更新されません。

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>次のステップ

既存のメジャーを使用して、[顧客セグメント](segments.md)を作成できます。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
