---
title: CFrameWnd から派生していないウィンドウのツール ヒント |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enabling tool tips [MFC]
- TOOLTIPTEXT structure [MFC]
- Help [MFC], tool tips for controls
- TTN_NEEDTEXT message [MFC]
- controls [MFC], tool tips
- handler functions [MFC], tool tips
ms.assetid: cad5ef0f-02e3-4151-ad0d-3d42e6932b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34eb8f0b7394828782a3d0f9ed1ca44fb5731af6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382087"
---
# <a name="tool-tips-in-windows-not-derived-from-cframewnd"></a>CFrameWnd から派生していないウィンドウのツール ヒント
ここから派生していない、ウィンドウに含まれているコントロールの有効化のツール ヒントを説明する[CFrameWnd](../mfc/reference/cframewnd-class.md)です。 アーティクル[ツールバーのツール ヒント](../mfc/toolbar-tool-tips.md)でのコントロールのツール ヒントに関する情報を提供する`CFrameWnd`です。  
  
 ここで説明されているトピックは次のとおりです。  
  
-   [有効化 (ツール ヒントを)](../mfc/enabling-tool-tips.md)  
  
-   [ツール ヒント用 TTN_NEEDTEXT 通知の処理](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)  
  
-   [TOOLTIPTEXT 構造体](../mfc/tooltiptext-structure.md)  
  
 ツール ヒントが自動的にボタンの表示し、親ウィンドウに含まれているその他のコントロールから派生した`CFrameWnd`です。 これは、ため`CFrameWnd`の既定のハンドラーを持つ、 [TTN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760269)通知を処理する**TTN_NEEDTEXT**ツールからの通知はコントロールに関連付けられたコントロールのヒントします。  
  
 ただし、この既定のハンドラーがないときに呼び出されます、 **TTN_NEEDTEXT**はウィンドウ内のコントロールに関連付けられている、ツール ヒント コントロールから通知が送信された、 `CFrameWnd`、ダイアログまたはフォーム ビューのコントロールなどです。 そのため、必要があるためのハンドラー関数を提供するための**TTN_NEEDTEXT**子コントロールのツール ヒントを表示するために通知メッセージです。  
  
 によって、windows の既定ツール ヒント[CWnd::EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips)それらに関連付けられたテキストはありません。 テキストを表示するツールヒントを取得する、 **TTN_NEEDTEXT**ツール ヒントのウィンドウが表示される直前に、ツール ヒント コントロールの親ウィンドウに通知が送信されます。 いくつかの値を割り当てるには、このメッセージのハンドラーがないかどうか、 **pszText**のメンバー、 **TOOLTIPTEXT**構造体にはないツール ヒントに表示されるテキストです。  
  
## <a name="see-also"></a>関連項目  
 [ツール ヒント](../mfc/tool-tips.md)

