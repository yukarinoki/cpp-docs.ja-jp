---
title: ツリー コントロールの項目の選択
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
ms.openlocfilehash: a88a2c8ea5b935bbcb1f40b705337ff676d8b8a5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264119"
---
# <a name="tree-control-item-selection"></a>ツリー コントロールの項目の選択

選択範囲が変更されたとき 1 つの項目からを別のツリー コントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 送信[TVN_SELCHANGING](/windows/desktop/Controls/tvn-selchanging)と[TVN_SELCHANGED](/windows/desktop/Controls/tvn-selchanged)通知メッセージ。 両方の通知には、変更がマウス クリックやキー入力の結果であるかどうかを指定する値が含まれます。 通知には、項目選択が解除されると、選択される項目に関する情報も含まれます。 項目の選択状態に依存する項目の属性を設定するのには、この情報を使用できます。 返す**TRUE**への応答で`TVN_SELCHANGING`返す選択項目を変更することを防止**FALSE**の変更は可能です。

アプリケーションは呼び出すことで、選択を変更することができます、 [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem)メンバー関数。

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](../mfc/using-ctreectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
