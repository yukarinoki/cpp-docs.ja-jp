---
title: CFrameWnd から派生していないウィンドウのツール ヒント
ms.date: 11/04/2016
helpviewer_keywords:
- enabling tool tips [MFC]
- TOOLTIPTEXT structure [MFC]
- Help [MFC], tool tips for controls
- TTN_NEEDTEXT message [MFC]
- controls [MFC], tool tips
- handler functions [MFC], tool tips
ms.assetid: cad5ef0f-02e3-4151-ad0d-3d42e6932b0e
ms.openlocfilehash: 3d44f2c503b689360f040e6804d319c331d5c0ca
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260661"
---
# <a name="tool-tips-in-windows-not-derived-from-cframewnd"></a>CFrameWnd から派生していないウィンドウのツール ヒント

ここから派生していないウィンドウに含まれるコントロールに対して有効にするツール ヒントをカバーする[CFrameWnd](../mfc/reference/cframewnd-class.md)します。 この記事[ツールバーのツール ヒント](../mfc/toolbar-tool-tips.md)でのコントロールのヒントに関する情報を提供、 `CFrameWnd`。

ここで説明したトピックは次のとおりです。

- [有効化 (ツール ヒントを)](../mfc/enabling-tool-tips.md)

- [ツール ヒント用 TTN_NEEDTEXT 通知の処理](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)

- [TOOLTIPTEXT 構造体](../mfc/tooltiptext-structure.md)

ツール ヒントがボタンに自動的に表示されから派生したその他のコントロールの親ウィンドウに含まれている`CFrameWnd`します。 これは、ため`CFrameWnd`の既定のハンドラーを持つ、 [TTN_GETDISPINFO](/windows/desktop/Controls/ttn-getdispinfo) 、通知を処理する**TTN_NEEDTEXT**ツールからの通知コントロールに関連付けられたコントロールのヒントします。

ただし、この既定のハンドラーを呼び出さない場合に、 **TTN_NEEDTEXT**でないウィンドウのコントロールに関連付けられたツール ヒント コントロールから通知が送信された、 `CFrameWnd`、ダイアログ ボックスまたはフォーム ビューのコントロールなど。 したがってのハンドラー関数を提供する必要があります、 **TTN_NEEDTEXT**の子コントロールのツールヒントを表示するためにメッセージを通知します。

Windows によって提供される既定のツール ヒント[CWnd::EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips)それらに関連付けられたテキストはありません。 表示するにはツール ヒントのテキストを取得する、 **TTN_NEEDTEXT**ツール ヒントのウィンドウが表示される直前に、ツール ヒント コントロールの親ウィンドウに通知が送信されます。 何らかの値を割り当てるには、このメッセージのハンドラーがないかどうか、 *pszText*のメンバー、 **TOOLTIPTEXT**構造体、ツール ヒントに表示されるテキストことはありません。

## <a name="see-also"></a>関連項目

[ツール ヒント](../mfc/tool-tips.md)
