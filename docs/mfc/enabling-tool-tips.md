---
title: ツール ヒントを有効にする方法
ms.date: 11/04/2016
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
ms.openlocfilehash: 270eb8bad03679cd6e605e3279c0e4ffc499a765
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571149"
---
# <a name="enabling-tool-tips"></a>ツール ヒントを有効にする方法

フォーム ビューまたはダイアログ ボックス コントロール) などのウィンドウの子コントロールのツール ヒントのサポートを有効にすることができます。

### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>ウィンドウの子コントロールのツール ヒントを有効にするには

1. 呼び出す`EnableToolTips`ツール ヒントを提供するウィンドウ。

1. 内の各コントロールの文字列を指定して[TTN_NEEDTEXT 通知の](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)ハンドラー。 ハンドラーは、子コントロール (フォーム ビュー クラスなど) を含むウィンドウのメッセージ マップでは。 このハンドラーは関数を呼び出すコントロールを識別し、設定**pszText**ツール ヒント コントロールで使用されるテキストを指定します。

## <a name="see-also"></a>関連項目

[CFrameWnd から派生していないウィンドウのツール ヒント](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

