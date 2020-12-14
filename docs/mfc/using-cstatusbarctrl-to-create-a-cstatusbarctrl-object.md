---
description: 詳細については、CStatusBarCtrl を使用した CStatusBarCtrl オブジェクトの作成に関するページを参照してください。
title: CStatusBarCtrl を使用して CStatusBarCtrl オブジェクトを作成する方法
ms.date: 11/04/2016
helpviewer_keywords:
- status bar controls [MFC], creating
- CStatusBarCtrl class [MFC], creating
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
ms.openlocfilehash: 0b76065ce4e90600bdec7e4f4a89ee2c5bb14085
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202380"
---
# <a name="using-cstatusbarctrl-to-create-a-cstatusbarctrl-object"></a>CStatusBarCtrl を使用して CStatusBarCtrl オブジェクトを作成する方法

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)の一般的な使用例を次に示します。

### <a name="to-use-a-status-bar-control-with-parts"></a>パーツでステータスバーコントロールを使用するには

1. オブジェクトを構築 `CStatusBarCtrl` します。

1. ステータスバーコントロールの描画領域の最小の高さを設定する場合は、 [Setminheight](../mfc/reference/cstatusbarctrl-class.md#setminheight) を呼び出します。

1. [SetBkColor](../mfc/reference/cstatusbarctrl-class.md#setbkcolor)を呼び出して、ステータスバーコントロールの背景色を設定します。

1. [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts)を呼び出して、ステータスバーコントロール内のパーツの数と各部分の右端の座標を設定します。

1. [SetText](../mfc/reference/cstatusbarctrl-class.md#settext)を呼び出して、ステータスバーコントロールの特定の部分のテキストを設定します。 このメッセージは、変更されたコントロールの一部を無効にし、コントロールが次に WM_PAINT メッセージを受信したときに新しいテキストを表示します。

場合によっては、ステータスバーがテキスト行を表示するだけで済みます。 この場合は、 [Setsimple](../mfc/reference/cstatusbarctrl-class.md#setsimple)を呼び出します。 これにより、ステータスバーコントロールが "simple" モードになり、1行のテキストが表示されます。

## <a name="see-also"></a>関連項目

[CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
