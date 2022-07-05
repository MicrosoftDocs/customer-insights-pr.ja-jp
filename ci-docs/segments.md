---
title: すべてのセグメントの概要
description: セグメントの概要と、セグメントの作成および管理方法。
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 8b2c2f9b84bf8b7f37d1468b871946ecb3e6aa98
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050953"
---
# <a name="segments-overview"></a>すべてのセグメントの概要

セグメントでは、統計、トランザクション、または行動の属性に基づいて、顧客をグループ化できます。 セグメントを使用すると、プロモーション キャンペーン、営業活動、顧客サポート アクションを対象にして、ビジネス目標を達成することができます。

セグメント定義のフィルターに一致する顧客プロファイルは、セグメントの *メンバー* として参照されます。 一部の [サービス制限](/dynamics365/customer-insights/service-limits) が適用されます。

## <a name="create-a-new-segment"></a>新しいセグメントの作成

新しいセグメントを作成するには、複数の方法があります: 

# <a name="individual-consumers-b-to-c"></a>[個人消費者 (B2C)](#tab/b2c)

- セグメント ビルダーを使用した複雑なセグメント: [独自に構築する](segment-builder.md#create-a-new-segment) 
- 1 つの演算子の単純なセグメント: [クイック セグメント](segment-builder.md#quick-segments) 
- AI を活用した類似顧客の検索方法: [類似顧客](find-similar-customer-segments.md) 
- メジャーまたは属性に基づく AI を活用した提案: [メジャーを改善するための提案されたセグメント](suggested-segments.md) 
- 活動に基づく提案: [顧客活動に基づく提案されたセグメント](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[事業取引先企業 (B2B)](#tab/b2b)

- セグメント ビルダーを使用した複雑なセグメント: [独自に構築する](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>既存のセグメントを管理する

**セグメント** ページに移動し、保存したすべてのセグメントを表示して管理します。

各セグメントは、セグメントに関する追加情報を含む行で表されます。

:::image type="content" source="media/segments-selected-segment.png" alt-text="オプション ドロップダウン リストと使用可能なオプションを含む選択されたセグメント。" lightbox="media/segments-selected-segment.png":::

セグメントを選択すると、次のアクションを使用できます。

- セグメント メンバーのプレビューなどメンバー数の傾向など、セグメントの詳細を **表示** します。
- メンバーのリストを、CSV ファイル形式で **ダウンロード** します。
- プロパティを変更するセグメントを **編集** します。
- セグメントの **複製を作成** します。 プロパティをすぐに編集するか、または複製の保存を選択できます。
- 最新のデータを含めるセグメントを **最新の情報に更新します**。
- セグメントを **アクティブ化** または **非アクティブ化** します。 非アクティブなセグメントの場合、セグメント定義は存在しますが、まだ顧客は含まれていません。 アクティブなセグメントは、セグメント定義に一致する顧客を探します。 [スケジュールされた更新](system.md#schedule-tab) が構成されている場合、非アクティブなセグメントには **状態** が **スキップされた** としてリストされ、更新も試行されなかったことを示しています。 非アクティブなセグメントがアクティブ化されると、これによって最新の情報に更新され、これはスケジュールされた更新に含まれます。
  または、**アクティブ化/非アクティブ化** ドロップダウンで **後でスケジュール** 機能を使用して、特定のセグメントをアクティブ化および非アクティブ化する未来の日時を指定します。
- **セグメントから[類似の顧客を探します](find-similar-customer-segments.md)**。
- セグメントの **名前を変更します**。
- セグメントの [タグを管理する](work-with-tags-columns.md#manage-tags)ための **タグ** です。
- メンバーのリストを、CSV ファイル形式で **ダウンロード** します。
- **エクスポートを管理** して、エクスポートに関連するセグメントを表示および管理します。 [エクスポートについて詳細を確認します。](export-destinations.md)
- セグメントを **削除** します。
- 表示する [列をカスタマイズする](work-with-tags-columns.md#customize-columns)ための **列** です。
- [タグをフィルターする](work-with-tags-columns.md#filter-on-tags)ための **フィルター** です。
- 検索名で検索するための **検索名** です。

## <a name="refresh-segments"></a>セグメントを最新の情報に更新する

**セグメント** pページで **すべて更新** を選択すると、すべてのセグメントを一度に更新することができ、1つまたは複数のセグメントを選択してオプションから **更新** を選択すると、該当するセグメントを更新することができます。 または、**管理者** > **システム** > **スケジュール** で定期的な更新を構成できます。 定期的な更新が構成されている場合、次のルールが適用されます。

- **動的** または **拡張** タイプのすべてのセグメントは、設定されたケイデンスで自動的に更新されます。 更新が完了すると、**状態** にセグメントの更新に問題がないかどうかを示します。 **最終更新日** には、最後に成功した更新のタイムスタンプが表示されます。 エラーが発生した場合は、エラーを選択して詳細を確認してください。
- **静的** タイプのセグメントは自動的に *更新されません*。 **最終更新日** には、静的セグメントが最後に手動で実行または更新されたときのタイムスタンプが表示されます。

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>セグメントのエクスポート

セグメント ページまたは [エクスポート ページ](export-destinations.md) からセグメントをエクスポートできます。 

1. **セグメント** ページを表示します。

1. エクスポートするセグメントの垂直省略記号 (&vellip;) を選択します。

1. アクション ドロップダウン リストから **エクスポートの管理** を選択します。

1. ページ **セグメントのエクスポート (プレビュー)** を開きます。 現在のセグメントが含まれているかどうかによってグループ化された、構成済みのすべてのエクスポートを確認できます。

   1. 選択したセグメントをエクスポートに追加するには、それぞれのエクスポートを **編集** し、対応するセグメントを選択して、保存します。 個人の顧客向けの環境では、リストからエクスポートを選択し、**セグメントを追加** を選択しても同じ結果を達成できます。

   1. 選択したセグメントで新しいエクスポートを作成するには、**エクスポートの追加** を選択します。 エクスポートの作成の詳細については、[新しいエクスポートの設定](export-destinations.md#set-up-a-new-export) を参照してください。

1. **戻る** を選択して、セグメントのメイン ページに戻ります。

## <a name="track-usage-of-a-segment"></a>セグメントの使用状況を追跡する

アプリでセグメントを使用し、それが Customer Insights に接続しているのと同じ Microsoft Dataverse 組織に基づく場合、セグメントの使用状況を追跡できます。 [Dynamics 365 Marketing の顧客体験で使用する Customer Insights セグメント](/dynamics365/marketing/real-time-marketing-ci-profile) の場合、システムが、そのセグメントの使用状況について通知します。

Customer Insights 環境、または Marketing の顧客体験で使用しているセグメントを編集する場合、[セグメント ビルダー](segment-builder.md) のバナーに依存関係の情報が表示されます。 このバナーから直接調査するか、またはセグメント ビルダーで **使用状況** を選択することで依存関係の詳細を調査できます。

**セグメントの使用状況** ペインには、このセグメントの Dataverse に基づくアプリでの使用状況について、詳細が示されます。 顧客体験で使用するセグメントの場合、このセグメントを使用している Marketing の体験を調査するためのリンクが表示されます。 Marketing アプリにアクセスするアクセス許可がある場合は、そこから詳細にアクセスできます。

:::image type="content" source="media/segment-usage-pane.png" alt-text="セグメント使用状況の詳細が表示されたセグメント ビルダーのサイド ペイン。":::

追跡対象のセグメントを削除しようとすると、その使用状況をシステムが通知します。 削除対象のセグメントを Marketing の顧客体験で使用している場合、セグメントが含むすべてのユーザーに対して、その体験が停止します。 その体験がマーケティング キャンペーンの一部である場合、削除はそのキャンペーン自体に影響します。 ただし、警告が表示されてもセグメントを削除できます。

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dataverse アプリケーションでセグメントを使用している場合に、セグメントの削除を確認するダイアログ ボックス。":::

### <a name="supported-apps"></a>対応しているアプリ

現在、次に示す Dataverse に基づくアプリで、使用状況を追跡できます。

- [Dynamics 365 Marketing の顧客体験](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="view-processing-history-and-segment-members"></a>処理履歴とセグメント メンバーの表示

セグメントの詳細を確認すると、セグメントに関する統合データを表示できます。

**セグメント** ページで、レビューするセグメントを選択します。

ページの上部には、メンバー数の変化を視覚化する傾向グラフが含まれています。 データ ポイントにカーソルを合わせると、特定の日付のメンバー数が表示されます。

視覚化の概算時間を更新できます。

> [!div class="mx-imgBorder"]
> ![時間の範囲のセグメント化。](media/segment-time-range.png "時間の範囲のセグメント化")

下部には、セグメント メンバーのリストが含まれています。

> [!NOTE]
> このリストに表示されるフィールドは、セグメントのエンティティの属性に基づいています。
>
>このリストは、一致するセグメント メンバーのプレビューであり、セグメントの最初の 100 レコードが表示されるため、必要に応じてセグメントをすばやく評価し、定義をレビューできます。 一致するすべてのレコードを表示するには、[セグメントをエクスポートする](export-destinations.md) 必要があります。

[!INCLUDE [footer-include](includes/footer-banner.md)]
