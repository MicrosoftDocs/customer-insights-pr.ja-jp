---
title: メジャーの理解と管理
description: メジャーをビジネスのパフォーマンスの分析と反映に役立てる方法について説明します。
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: ef10f480086ccac4fa5c6c58818e35ecae67532c
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529683"
---
# <a name="measures-overview"></a>メジャーの概要

メジャーは、顧客の行動とビジネス パフォーマンスをよりよく理解するのに役立ちます。 [統合されたプロファイル](data-unification.md) から関連する値を確認します。 たとえば、企業は、個々の顧客の購買履歴を把握するために *顧客ごとの合計支出* を確認したり、企業全体の集計レベルの収益を把握するために *会社の合計売上金額* を測定したいと考えています。  

メジャーは、さまざまな演算子と単純なマッピング オプションを備えたデータ クエリ プラットフォームである[メジャー ビルダーを使用して](measure-builder.md)作成されます。 データをフィルタリングし、結果をグループ化し、[エンティティ関連パス](relationships.md)を検出して、出力をプレビューします。 [定義済みのテンプレート](measure-templates.md)を使用して、一般的に使用されるメジャーを効率的に構成できます。

メジャー ビルダーを使用して、顧客データを照会し、インサイトを抽出することによりビジネス アクティビティを計画します。 たとえば、*顧客あたりの総支出* と *顧客あたりのトータル リターン* のメジャーを作成することにより、支出は多いが収益が高い顧客のグループを特定するのに役立ちます。 これらのメジャーに基づいて[セグメントを作成し](segments.md)、次に行う最善の行動を推進します。

## <a name="manage-your-measures"></a>メジャーの管理

メジャーのリストは、**メジャー** ページにあります。

メジャー タイプ、作成者、作成日、ステータス、および状態に関する情報が表示されます。 リストからメジャーを選択すると、出力をプレビューして CSV ファイルをダウンロードできます。

:::image type="content" source="media/measures-actions.png" alt-text="単一のメジャーを管理するためのアクション。"lightbox="media/measures-actions.png":::

メジャーを選択すると、次のアクションを使用できます。

- メジャーの構成を **編集** します。
- メジャーを **複製** します。 プロパティをすぐに編集するか、単に複製を保存するかを選択できます。
- 最新のデータに基づいて、メジャーを **更新** します。 すべてのメジャーを同時に更新するには、すべてのメジャーを選択してから **更新** を選択します。
- メジャーの **名前を変更** します。
- **アクティブ化** または **非アクティブ化** します。 非アクティブなメジャーは、[スケジュールされた更新](system.md#schedule-tab)中に更新されません。
- セグメントの [タグを管理する](work-with-tags-columns.md#manage-tags)ための **タグ** です。
- メジャーを **削除** します。

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>次のステップ

既存のメジャーを使用して、[顧客セグメント](segments.md)を作成できます。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
