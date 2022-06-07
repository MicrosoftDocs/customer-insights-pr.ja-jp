---
title: Dynamics 365 Marketing で統一されたプロファイルを使用する
description: Dynamics 365 Marketing と統合プロファイル、またはセグメントを統合する方法について説明します。
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4cc3cbde97d0f9da198652e86c0843476393b646
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833314"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Dynamics 365 Marketing で統一された顧客プロファイルを操作する

[Dynamics 365 Marketing](/dynamics365/marketing/overview) は、顧客エクスペリエンスを向上させ、すべてのタッチポイントでパーソナライズされた体験を調整し、関係を強化してロイヤルティを獲得できます。 Dynamics 365 Marketing アプリは、Dynamics 365 Sales、Dynamics 365 Customer Insights、Microsoft Teams などの製品とシームレスに連携し、データや AI の力を使用してより迅速に、より適切な意思決定を行うことができます。

Customer Insights データを Marketing と連携させることで、以下のことが可能になります。

- Unified customer profile とセグメントをターゲットにします。 これにより、顧客のデータの所在にかかわらず、すべての顧客をエンゲージすることができます。
- メール、SMS、プッシュ通知の動的コンテンツ (パーソナライズされたトークンなど) は、ロイヤルティの状態、定期購入の更新日、親アカウントなど、統合された Customer Insights のプロファイルで把握した指標に基づいて作成されます。
- Marketing から Customer Insights にデータを読み込み、他のソースからの顧客データと組み合わせることができます。
- Customer Insights のデータ クリーニング、強化、ファジーマッチングなどのツールを適用します。

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>豊富な顧客プロファイルをリアルタイム マーケティングに活用する

リアルタイム マーケティングでは、顧客のあらゆる行動に基づいて顧客体験を起動する [カスタム トリガー](/dynamics365/marketing/real-time-marketing-custom-triggers) を作成することができます。 データをパーソナライズすればするほど、より適切でパーソナライズされた体験を実現することができます。 これが、Marketing と Customer Insights の組み合わせを非常に強力なものにしている理由です。 あらゆるソースからの[データを統合](data-unification.md) でき、パーソナライズされた顧客体験を促進できます。

[リアルタイム マーケティングで Customer Insights のプロファイルとセグメントを使用する方法](/dynamics365/marketing/real-time-marketing-ci-profile) について説明します

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>発信の顧客体験で統合されたセグメントを使用する

Customer Insights では、多くのソースからのデータを絞り込み、集計された顧客セグメントに組み合わせることができます。 [Customer Insights とアウトバウンド マーケティングを連携させる](export-dynamics365-marketing.md) ことで、これらのセグメントは顧客体験デザイナーに自動的に表示され、*かつ* 自動的に更新します。

詳細: [Dynamics 365 Marketing で Dynamics 365 Customer Insights のセグメントを利用する](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>自身の Azure Data Lake Storage からデータを引き出す

Customer Insights データを Marketing に活用する場合、クラウド ストレージに限定されません。 すでに自分の Azure Data Lake Storage 設定を持っている場合は、Customer Insights と連携し、クラウドベースの設定と同様にマーケティング アプリとデータを共有することが可能です。

詳細: [Azure Data Lake Storage から Dataverse とデータ共有ができるようにする](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
