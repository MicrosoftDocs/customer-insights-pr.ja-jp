---
title: メジャーの概要
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
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245379"
---
# <a name="measures-overview"></a>メジャーの概要

メジャーは、顧客の行動とビジネス パフォーマンスをよりよく理解するのに役立ちます。 [統合されたプロファイル](data-unification.md) から関連する値を確認します。 たとえば、企業は、個々の顧客の購買履歴を把握するために *顧客ごとの合計支出* を確認したり、企業全体の集計レベルの収益を把握するために *会社の合計売上金額* を測定したいと考えています。

メジャーを作成して、顧客データを照会し、インサイトを抽出することによりビジネス アクティビティを計画します。 たとえば、*顧客あたりの総支出* と *顧客あたりのトータル リターン* のメジャーを作成することにより、支出は多いが収益が高い顧客のグループを特定できます。 次に、これらのメジャーに基づいて[セグメントを作成し](segments.md)、次に行う最善の行動を推進します。

## <a name="create-a-measure"></a>メジャーを作成する

ターゲット対象ユーザーに基づいてメジャーを作成する方法を選択します。

# <a name="individual-consumers-b-to-c"></a>[個人消費者 (B2C)](#tab/b2c)

- メジャー ビルダーでゼロから[独自のメジャーを作成](measure-builder.md)します。
- 一般的に使用されるメジャーから、[定義済みテンプレートを使用します](measure-templates.md)。

# <a name="business-accounts-b-to-b"></a>[事業取引先企業 (B2B)](#tab/b2b)

メジャー ビルダーでゼロから[独自のメジャーを作成](measure-builder.md)します。

---

## <a name="manage-existing-measures"></a>既存のメジャーを管理する

**メジャー** に移動して作成したメジャー、そのステータス、メジャーの種類、およびデータが最後に更新された時刻を表示します。 メジャーのリストを任意の列で並べ替えたり、検索ボックスを使用して管理するメジャーを検索したりできます。

メジャーの横を選択して、使用可能なアクションを表示します。 メジャー名を選択し、出力をプレビューして CSV ファイルをダウンロードします。

:::image type="content" source="media/measures-actions.png" alt-text="単一のメジャーを管理するためのアクション。"lightbox="media/measures-actions.png":::

- プロパティを変更するメジャーを **編集** します。
- 最新のデータを含めるメジャーを **最新の情報に更新します**。
- メジャーの **名前を変更** します。
- メジャーを **アクティブ化** または **非アクティブ化** します。 [スケジュールされた更新](schedule-refresh.md)中は非アクティブなメジャーが更新されず、**状態** が **スキップされた** としてリストされ、更新も試行されなかったことが示されます。
- メジャーの [タグを管理する](work-with-tags-columns.md#manage-tags)ための **タグ** です。
- メジャーを **削除** します。
- 表示する [列をカスタマイズする](work-with-tags-columns.md#customize-columns)ための **列** です。
- [タグをフィルターする](work-with-tags-columns.md#filter-on-tags)ための **フィルター** です。
- メジャー名で検索するための **検索名** です。

## <a name="refresh-measures"></a>メジャーを更新する

メジャーは、自動スケジュールで更新することも、オンデマンドで手動で更新することもできます。 1 つ以上のメジャーを手動で更新するには、それらを選択して **更新** を選択します。 [自動更新をスケジュールする](schedule-refresh.md)には、**管理者** > **システム** > **スケジュール** に移動します。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
