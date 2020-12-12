---
description: 詳細については、「CFrameWnd から派生していない Windows のツールヒント」を参照してください。
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
ms.openlocfilehash: 1d5d2ba744800424a9dce325f9d4341956bc22ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264428"
---
# <a name="tool-tips-in-windows-not-derived-from-cframewnd"></a>CFrameWnd から派生していないウィンドウのツール ヒント

この記事ファミリでは、 [CFrameWnd](../mfc/reference/cframewnd-class.md)から派生していないウィンドウに含まれるコントロールのツールヒントを有効にする方法について説明します。 記事ツール [バーのツールヒント](../mfc/toolbar-tool-tips.md) には、のコントロールのツールヒントに関する情報が記載されて `CFrameWnd` います。

この記事ファミリで取り上げるトピックは次のとおりです。

- [有効化 (ツールヒントを)](../mfc/enabling-tool-tips.md)

- [ツールヒントの TTN_NEEDTEXT 通知の処理](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)

- [TOOLTIPTEXT 構造体](../mfc/tooltiptext-structure.md)

ツールヒントは、から派生した親ウィンドウに含まれるボタンおよびその他のコントロールに対して自動的に表示され `CFrameWnd` ます。 これは、 `CFrameWnd` には、コントロールに関連付けられているツールヒントコントロールからの **TTN_NEEDTEXT** 通知を処理する [TTN_GETDISPINFO](/windows/win32/Controls/ttn-getdispinfo)通知の既定のハンドラーがあるためです。

ただし、  `CFrameWnd` ダイアログボックスやフォームビューのコントロールなど、ではないウィンドウ内のコントロールに関連付けられているツールヒントコントロールから TTN_NEEDTEXT 通知が送信された場合、この既定のハンドラーは呼び出されません。 したがって、子コントロールのツールヒントを表示するには、 **TTN_NEEDTEXT** 通知メッセージにハンドラー関数を指定する必要があります。

[CWnd:: EnableToolTips ヒント](../mfc/reference/cwnd-class.md#enabletooltips)によってウィンドウに提供される既定のツールヒントには、テキストが関連付けられていません。 表示するツールヒントのテキストを取得するために、ツールヒントウィンドウが表示される直前に、 **TTN_NEEDTEXT** 通知がツールヒントコントロールの親ウィンドウに送信されます。 このメッセージに対して、 **TOOLTIPTEXT** 構造体の *psztext* メンバーになんらかの値を割り当てるためのハンドラーがない場合、ツールヒントのテキストは表示されません。

## <a name="see-also"></a>関連項目

[ツールヒント](../mfc/tool-tips.md)
