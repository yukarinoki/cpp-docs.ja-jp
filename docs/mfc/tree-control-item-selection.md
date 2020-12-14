---
description: 詳細については、「ツリーコントロール項目の選択」を参照してください。
title: ツリー コントロールの項目の選択
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
ms.openlocfilehash: 46e1256eea3e8175b996a1b6bdfdd7c1de2739d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264038"
---
# <a name="tree-control-item-selection"></a>ツリー コントロールの項目の選択

選択項目がある項目から別の項目に変更されると、ツリーコントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) は [TVN_SELCHANGING](/windows/win32/Controls/tvn-selchanging) および [TVN_SELCHANGED](/windows/win32/Controls/tvn-selchanged) 通知メッセージを送信します。 どちらの通知にも、変更がマウスクリックまたはキー入力の結果であるかどうかを指定する値が含まれます。 通知には、選択範囲を取得している項目と選択範囲を失う項目に関する情報も含まれます。 この情報を使用すると、項目の選択状態に依存する項目属性を設定できます。 への応答として **TRUE** を返すことによっ `TVN_SELCHANGING` て選択が変更されないようにします。 **FALSE** を返すと変更が許可されます。

アプリケーションでは、 [Selectitem](../mfc/reference/ctreectrl-class.md#selectitem) メンバー関数を呼び出すことによって、選択を変更できます。

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](../mfc/using-ctreectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
