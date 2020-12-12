---
description: '詳細情報: WM_ メッセージ: P-R'
title: 'WM_ で始まるメッセージのハンドラー : P - R'
ms.date: 11/04/2016
f1_keywords:
- ON_WM_RBUTTONUP
- ON_WM_PALETTECHANGED
- ON_WM_RBUTTONDBLCLK
- ON_WM_QUERYENDSESSION
- ON_WM_PARENTNOTIFY
- ON_WM_PALETTEISCHANGING
- ON_WM_QUERYOPEN
- ON_WM_PAINT
- ON_WM_QUERYNEWPALETTE
- ON_WM_RBUTTONDOWN
- ON_WM_RENDERALLFORMATS
- ON_WM_PAINTCLIPBOARD
- ON_WM_RENDERFORMAT
- ON_WM_QUERYDRAGICON
helpviewer_keywords:
- ON_WM_RENDERFORMAT [MFC]
- ON_WM_QUERYOPEN [MFC]
- ON_WM_RBUTTONDOWN [MFC]
- ON_WM_PAINTCLIPBOARD [MFC]
- ON_WM_QUERYNEWPALETTE [MFC]
- ON_WM_RBUTTONUP [MFC]
- ON_WM_PARENTNOTIFY [MFC]
- ON_WM_RBUTTONDBLCLK [MFC]
- ON_WM_PALETTECHANGED [MFC]
- ON_WM_PALETTEISCHANGING [MFC]
- ON_WM_QUERYDRAGICON [MFC]
- ON_WM_PAINT [MFC]
- ON_WM_RENDERALLFORMATS [MFC]
- ON_WM_QUERYENDSESSION [MFC]
- WM_ messages
ms.assetid: f46962e5-8329-4f1f-9b4d-fdad2a5ce1f8
ms.openlocfilehash: d1e3ad4ca65bcf9f4b1b0901a6fe1dbf441595e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218304"
---
# <a name="wm_-messages-p---r"></a>WM_ で始まるメッセージのハンドラー : P - R

次のマップエントリは、関数プロトタイプに対応しています。

|マップエントリ|関数プロトタイプ|
|---------------|------------------------|
|ON_WM_PAINT ()|void [OnPaint](../../mfc/reference/cwnd-class.md#onpaint)() を afx_msg します。|
|ON_WM_PAINTCLIPBOARD ()|afx_msg void [OnPaintClipboard](../../mfc/reference/cwnd-class.md#onpaintclipboard)(CWnd *, HANDLE);|
|ON_WM_PALETTECHANGED ()|afx_msg void [OnPaletteChanged](../../mfc/reference/cwnd-class.md#onpalettechanged)(CWnd *);|
|ON_WM_PALETTEISCHANGING ()|afx_msg void [Onパレット Ischanging](../../mfc/reference/cwnd-class.md#onpaletteischanging)(CWnd *);|
|ON_WM_PARENTNOTIFY ()|afx_msg void [OnParentNotify](../../mfc/reference/cwnd-class.md#onparentnotify)(UINT, LONG);|
|ON_WM_POWERBROADCAST ()|afx_msg UINT [Onpowerbroadcast](../../mfc/reference/cwnd-class.md#onpowerbroadcast)(UINT, uint);|
|ON_WM_QUERYDRAGICON ()|afx_msg HCURSOR [Onquerydragicon](../../mfc/reference/cwnd-class.md#onquerydragicon)();|
|ON_WM_QUERYENDSESSION ()|afx_msg BOOL [Onqueryendsession](../../mfc/reference/cwnd-class.md#onqueryendsession)() () です。|
|ON_WM_QUERYNEWPALETTE ()|afx_msg BOOL [Onquerynewpalette](../../mfc/reference/cwnd-class.md#onquerynewpalette)() () です。|
|ON_WM_QUERYOPEN ()|afx_msg BOOL [Onqueryopen](../../mfc/reference/cwnd-class.md#onqueryopen)() ();|
|ON_WM_RBUTTONDBLCLK ()|afx_msg void [OnRButtonDblClk](../../mfc/reference/cwnd-class.md#onrbuttondblclk)(UINT, CPoint);|
|ON_WM_RBUTTONDOWN ()|void [Onrbuttondown](../../mfc/reference/cwnd-class.md#onrbuttondown)(UINT, CPoint) を afx_msg します。|
|ON_WM_RBUTTONUP ()|void [Onrbuttonup](../../mfc/reference/cwnd-class.md#onrbuttonup)(UINT, CPoint) を afx_msg します。|
|ON_WM_RENDERALLFORMATS ()|afx_msg void [OnRenderAllFormats](../../mfc/reference/cwnd-class.md#onrenderallformats)();|
|ON_WM_RENDERFORMAT ()|afx_msg void [OnRenderFormat](../../mfc/reference/cwnd-class.md#onrenderformat)(UINT);|

## <a name="see-also"></a>関連項目

[メッセージ マップ](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ メッセージのハンドラー](../../mfc/reference/handlers-for-wm-messages.md)
