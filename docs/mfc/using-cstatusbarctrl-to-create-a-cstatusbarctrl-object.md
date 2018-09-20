---
title: CStatusBarCtrl を使用して CStatusBarCtrl オブジェクトを作成する |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- status bar controls [MFC], creating
- CStatusBarCtrl class [MFC], creating
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c68603eff0393d76af4e0617548e5bf1dd4aa63
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413693"
---
# <a name="using-cstatusbarctrl-to-create-a-cstatusbarctrl-object"></a>CStatusBarCtrl を使用して CStatusBarCtrl オブジェクトを作成する方法

一般的な用途の例を次に示します[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md):

### <a name="to-use-a-status-bar-control-with-parts"></a>パーツでステータス バー コントロールを使用するには

1. 構築、`CStatusBarCtrl`オブジェクト。

1. 呼び出す[SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight)ステータス バー コントロールの高さの最小値を設定する場合の領域を描画します。

1. 呼び出す[SetBkColor](../mfc/reference/cstatusbarctrl-class.md#setbkcolor)ステータス バー コントロールの背景色を設定します。

1. 呼び出す[呼び出した](../mfc/reference/cstatusbarctrl-class.md#setparts)ステータス バーのコントロールと各部分の右端の座標で部分の数を設定します。

1. 呼び出す[SetText](../mfc/reference/cstatusbarctrl-class.md#settext)ステータス バー コントロールの特定の部分でテキストを設定します。 メッセージは、原因で、コントロールが次に WM_PAINT メッセージを受信すると、新しいテキストを表示するように、変更されたコントロールの部分を無効にします。

場合によっては、ステータス バーは、行のテキストを表示するだけ済みます。 この場合、呼び出しを行う[SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple)します。 これにより、ステータス バー コントロールが 1 行のテキストが表示されます「簡単」モードには。

## <a name="see-also"></a>関連項目

[CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

