---
title: エンゲージメント インサイト機能の用語集
description: 用語と概念について収録した用語集です。
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: fd6513f66777f8be312c8b594d52836ac325f2825e9d019d2ba0f49c587cf8ca
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035742"
---
# <a name="engagement-insights-capability-glossary"></a>エンゲージメント インサイト機能の用語集

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

このリストでは、Dynamics 365 Customer Insights のエンゲージメント インサイト機能とその付属文書に登場する特定の用語を定義しています。

## <a name="base-event"></a>基本イベント

基本イベントは、ページ ビューやクリックなど、Web サイトでのアクティビティを表すデータのセットです。 

## <a name="dimensions"></a>ディメンション

分析コードとは、データを記述、フィルタリング、グループ化するためのイベントの属性です。 たとえば、レポートの分析コードには、*オペレーティングシステム (OS)*、*ブラウザ*、*ページ名* を選択できます。

## <a name="event"></a>イベント

デジタル分析では、イベントはユーザーの行動を表します。 イベントは、ユーザーがページを表示したとき (イベントの表示)、またはコンテンツとやり取りしたとき (アクション イベント) に記録します。 Webサイトからの活動データは、*基本イベント* として取得されます。 レポートの場合、表示するデータのプロパティを決定できます。 このデータの仮想ビューは、*改良されたイベント* と呼ばれます。 

## <a name="environment"></a>環境

 環境とは、1つまたは複数のワークスペースを含むことができるスペースを意味します。 環境を使用して、ワークスペースとCustomer Insights の対象ユーザーのインサイト機能への接続を管理できます。

## <a name="member"></a>メンバー

ワークスペースのメンバーとは、ワークスペースにアクセスできるユーザーを意味します。 メンバーには、ワークスペースやそのデータの管理、レポートの閲覧などを行うロールを付与できます。 現在、*オーナー* は、エンゲージメント インサイトの機能で利用できる唯一のロールです。

## <a name="metric"></a>指標

メトリックとは、プロセスを追跡または評価するために使用されるデータの定量化可能な測定値を意味します。 ページビューや平均滞在時間は、関連する指標の一例です。

## <a name="refined-event"></a>改良されたイベント

改良されたイベントとは、基本となるイベントをデータの特定のプロパティでフィルター処理して仮想的に表示したものです。 改良されたイベントを使用して、エクスポート用の基本イベントを簡素化したり、公開やエクスポートに必要のないプロパティをイベントから削除したりすることができます。

## <a name="report"></a>レポート 

レポートとは、ユーザーの行動を測定、理解するためのデータビジュアライゼーションの集合体を意味します。 エンゲージメントのインサイト機能には、Web プロジェクトの事前定義されたレポートがいくつか含まれています。 また、カスタム レポートを作成することもできます。 

## <a name="workspace"></a>ワークスペース

ワークスペースは、イベントとレポートを保存および管理する方法です。 ここでは、ユーザーのアクティビティをリアルタイムで表示できます。 ワークスペースを作成する際には、ワークスペースに送信するデータの種類を選択します。


[!INCLUDE[footer-include](../includes/footer-banner.md)]