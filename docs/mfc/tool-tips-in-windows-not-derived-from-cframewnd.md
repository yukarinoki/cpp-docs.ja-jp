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
ms.openlocfilehash: 2545bda725428835c256ad81edc9070bd004d474
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620299"
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

