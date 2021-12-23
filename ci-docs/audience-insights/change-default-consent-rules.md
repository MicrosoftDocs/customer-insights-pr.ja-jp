---
title: セグメントの既定の同意規則を管理する
description: 同意管理機能を使用すると、上書きが有効になっている場合、既定の同意規則を無効化または変更できます。
ms.date: 12/01/2021
ms.service: customer-insights
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28c9ea49b1f3aebd3abd7d4de58fe61e6474158b
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884176"
---
# <a name="disable-or-change-default-consent-rules"></a>既定の同意規則を無効にするか変更する

組織が[同意管理機能](../consent-management/overview.md)を対象者分析情報と組み合わせて使用する場合、セグメントに対して[管理者は同意規則を強制できます](activate-consent.md)。 

セグメント領域に強制された同意規則により、すべてのセグメントが同意確認と規則の状態について通知します。 上書きが許可されている場合、特定のセグメントに対して既定の同意規則がオフになります。 セグメントのすべての作成者は、セグメントの既定の規則の上にさらに追加できます。 

## <a name="for-administrators"></a>管理者向け

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="同意規則オプションを備えたセグメント ビルダー。":::

**既定の同意規則を無効にするには:**

1. **同意規則** 通知で、**詳細を表示** を選択します。 

1. **既定の同意規則** 切り替えを **オフ** に設定します。

**同意規則を追加するには:**

1. **同意規則** 通知で、**詳細を表示** を選択します。 

1. **同意規則を追加する** を選択し、**同意データの種類** ドロップダウンから同意規則を選択します。

1. **保存** を選択し、セグメントに新しい規則を適用します。

## <a name="for-contributors"></a>共同作成者の場合

強制された同意規則なしでセグメントを作成するには、管理者と協力して、セグメントでそれらを無効にする必要があります。 ただし、所有および管理するセグメントに独自の同意規則を追加できます。

これは 3 つのステップのプロセスです。 
1. 対象者インサイトで、[セグメントを作成し](segments.md)、それを保存します。 

1. セグメント名を管理者と共有し、[セグメントのオーバーライドを有効にする](activate-consent.md)よう管理者に依頼してください。 

1. セグメントをもう一度開きます。 **同意規則** 通知で、**詳細を見る** を選択して、適用する同意規則を追加します。 次に、セグメントを **保存** して、**実行** します。



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
