---
description: '詳細については、「WM_ メッセージハンドラー: L-M」を参照してください。'
title: 'WM_ で始まるメッセージのハンドラー : L - M'
ms.date: 11/04/2016
f1_keywords:
- ON_WM_MENUSELECT
- ON_WM_MBUTTONDBLCLK
- ON_WM_MOUSEACTIVATE
- ON_WM_MOUSEMOVE
- ON_WM_MOVING
- ON_WM_LBUTTONUP
- ON_WM_LBUTTONDBLCLK
- ON_WM_MEASUREITEM
- ON_WM_MDIACTIVATE
- ON_WM_MOVE
- ON_WM_LBUTTONDOWN
- ON_WM_MBUTTONDOWN
- ON_WM_MENUCHAR
- ON_WM_MBUTTONUP
helpviewer_keywords:
- ON_WM_MENUSELECT [MFC]
- ON_WM_MBUTTONDBLCLK [MFC]
- ON_WM_MOVE [MFC]
- ON_WM_MOUSEACTIVATE [MFC]
- ON_WM_MBUTTONUP [MFC]
- ON_WM_MOUSEMOVE [MFC]
- ON_WM_MENUCHAR [MFC]
- ON_WM_MBUTTONDOWN [MFC]
- ON_WM_MEASUREITEM [MFC]
- ON_WM_MOVING [MFC]
- ON_WM_LBUTTONDOWN [MFC]
- ON_WM_MDIACTIVATE [MFC]
- ON_WM_LBUTTONDBLCLK [MFC]
- ON_WM_LBUTTONUP [MFC]
- WM_ messages
ms.assetid: 96ecaaf1-6d13-4e12-a454-535635967489
ms.openlocfilehash: 2044f8eeb74c75f92f42c6e0199820528f7c10c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218330"
---
# <a name="wm_-message-handlers-l---m"></a>WM_ で始まるメッセージのハンドラー : L - M

左側の次のマップエントリは、右側の関数プロトタイプに対応しています。

|マップエントリ|関数プロトタイプ|
|---------------|------------------------|
|ON_WM_LBUTTONDBLCLK ()|afx_msg void [OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk)(UINT, CPoint);|
|ON_WM_LBUTTONDOWN ()|afx_msg void [OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown)(UINT, CPoint);|
|ON_WM_LBUTTONUP ()|afx_msg void [OnLButtonUp](../../mfc/reference/cwnd-class.md#onlbuttonup)(UINT, CPoint);|
|ON_WM_MBUTTONDBLCLK ()|afx_msg void [OnMButtonDblClk](../../mfc/reference/cwnd-class.md#onmbuttondblclk)(UINT, CPoint);|
|ON_WM_MBUTTONDOWN ()|void [Onmbuttondown](../../mfc/reference/cwnd-class.md#onmbuttondown)(UINT, CPoint) を afx_msg します。|
|ON_WM_MBUTTONUP ()|void [Onmbuttonup](../../mfc/reference/cwnd-class.md#onmbuttonup)(UINT, CPoint) を afx_msg します。|
|ON_WM_MDIACTIVATE ()|void [Onmdiactivate](../../mfc/reference/cwnd-class.md#onmdiactivate)(BOOL, cwnd \* , cwnd) を afx_msg し \* ます。|
|ON_WM_MEASUREITEM ()|afx_msg void [OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)(LPMEASUREITEMSTRUCT);|
|ON_WM_MENUCHAR ()|afx_msg LONG [Onmenuchar](../../mfc/reference/cwnd-class.md#onmenuchar)(UINT, Uint, CMenu \* );|
|ON_WM_MENUDRAG ()|afx_msg UINT [Onmenudrag](../../mfc/reference/cwnd-class.md#onmenudrag)(Uint, CMenu \* );|
|ON_WM_MENUGETOBJECT ()|afx_msg UINT [Onmenugetobject](../../mfc/reference/cwnd-class.md#onmenugetobject)(menugetobjectinfo \* );|
|ON_WM_MENURBUTTONUP ()|void [Onmenurbuttonup](../../mfc/reference/cwnd-class.md#onmenurbuttonup)(UINT, CMenu); を afx_msg し \* ます。|
|ON_WM_MENUSELECT ()|afx_msg void [OnMenuSelect](../../mfc/reference/cwnd-class.md#onmenuselect)(UINT, UINT, HMENU);|
|ON_WM_MOUSEACTIVATE ()|afx_msg int [Onmouseactivate](../../mfc/reference/cwnd-class.md#onmouseactivate)(CWnd \* , uint, uint);|
|ON_WM_MOUSEHOVER ()|void [Onmousehover](../../mfc/reference/cwnd-class.md#onmousehover)(UINT, CPoint) を afx_msg します。|
|ON_WM_MOUSEHWHEEL ()|void [Onmousehwheel](../../mfc/reference/cwnd-class.md#onmousehwheel)(UINT、Short、CPoint) を afx_msg します。|
|ON_WM_MOUSELEAVE ()|afx_msg void [OnMouseLeave](../../mfc/reference/cwnd-class.md#onmouseleave)();|
|ON_WM_MOUSEMOVE ()|afx_msg void [OnMouseMove](../../mfc/reference/cwnd-class.md#onmousemove)(UINT, CPoint);|
|ON_WM_MOUSEWHEEL ()|afx_msg BOOL [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel)(UINT, Short, CPoint);|
|ON_WM_MOVE ()|afx_msg void [OnMove](../../mfc/reference/cwnd-class.md#onmove)(int, int);|
|ON_WM_MOVING ()|void [onmoving](../../mfc/reference/cwnd-class.md#onmoving)(UINT, LPRECT) を afx_msg します。|

## <a name="see-also"></a>関連項目

[メッセージ マップ](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ メッセージのハンドラー](../../mfc/reference/handlers-for-wm-messages.md)
