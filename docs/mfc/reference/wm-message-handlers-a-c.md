---
description: '詳細情報: WM_ メッセージハンドラー: A-C'
title: 'WM_ で始まるメッセージのハンドラー : A - C'
ms.date: 11/04/2016
f1_keywords:
- ON_WM_CREATE
- ON_WM_COMPACTING
- ON_WM_CHARTOITEM
- ON_WM_ASKCBFORMATNAME
- ON_WM_CTLCOLOR
- ON_WM_COMPAREITEM
- ON_WM_CHILDACTIVATE
- ON_WM_CONTEXTMENU
- ON_WM_ACTIVATE
- ON_WM_CANCELMODE
- ON_WM_CLOSE
- ON_WM_CAPTURECHANGED
- ON_WM_ACTIVATEAPP
- ON_WM_CHAR
- ON_WM_CHANGECBCHAIN
helpviewer_keywords:
- ON_WM_COMPACTING [MFC]
- ON_WM_COMPAREITEM [MFC]
- ON_WM_CLOSE [MFC]
- ON_WM_CTLCOLOR [MFC]
- ON_WM_CHAR [MFC]
- ON_WM_CAPTURECHANGED [MFC]
- ON_WM_CHARTOITEM [MFC]
- ON_WM_CREATE [MFC]
- ON_WM_ACTIVATE [MFC]
- ON_WM_CONTEXTMENU [MFC]
- ON_WM_CANCELMODE [MFC]
- ON_WM_ASKCBFORMATNAME [MFC]
- ON_WM_CHILDACTIVATE [MFC]
- WM_ messages [MFC]
- ON_WM_ACTIVATEAPP [MFC]
- ON_WM_CHANGECBCHAIN
ms.assetid: 4e315896-d646-4b87-b0ab-41a4a753b045
ms.openlocfilehash: 898635961e3fc1ad3df571e813bcfef629318446
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218447"
---
# <a name="wm_-message-handlers-a---c"></a>WM_ で始まるメッセージのハンドラー : A - C

左側の次のマップエントリは、右側の関数プロトタイプに対応しています。

|マップエントリ|関数プロトタイプ|
|---------------|------------------------|
|ON_WM_ACTIVATE ()|afx_msg void [OnActivate](../../mfc/reference/cwnd-class.md#onactivate)(UINT, CWnd \* , BOOL);|
|ON_WM_ACTIVATEAPP ()|void [Onアクティブアプリ](../../mfc/reference/cwnd-class.md#onactivateapp)(BOOL、DWORD) を afx_msg します。|
|ON_WM_APPCOMMAND ()|void [Onappcommand](../../mfc/reference/cwnd-class.md#onappcommand)(CWnd \* , uint, uint, uint) を afx_msg します。|
|ON_WM_ASKCBFORMATNAME ()|afx_msg void [OnAskCbFormatName](../../mfc/reference/cwnd-class.md#onaskcbformatname)(UINT, LPSTR);|
|ON_WM_CANCELMODE ()|void [Oncancelmode](../../mfc/reference/cwnd-class.md#oncancelmode)() を afx_msg します。|
|ON_WM_CAPTURECHANGED ()|afx_msg void [OnCaptureChanged](../../mfc/reference/cwnd-class.md#oncapturechanged)(CWnd \* );|
|ON_WM_CHANGECBCHAIN ()|void [Onchangecbchain](../../mfc/reference/cwnd-class.md#onchangecbchain)を afx_msg します (HWND、hwnd)。|
|ON_WM_CHAR ()|afx_msg void [OnChar](../../mfc/reference/cwnd-class.md#onchar)(UINT, UINT, uint);|
|ON_WM_CHARTOITEM ()|afx_msg int [Onchartoitem](../../mfc/reference/cwnd-class.md#onchartoitem)(Uint, CWnd \* , uint);|
|ON_WM_CHILDACTIVATE ()|afx_msg void [OnChildActivate](../../mfc/reference/cwnd-class.md#onchildactivate)();|
|ON_WM_CLIPBOARDUPDATE ()|afx_msg void [OnClipboardUpdate](../../mfc/reference/cwnd-class.md#onclipboardupdate)();|
|ON_WM_CLOSE ()|void [OnClose](../../mfc/reference/cwnd-class.md#onclose)() を afx_msg|
|ON_WM_COMPACTING ()|void [Oncompacting](../../mfc/reference/cwnd-class.md#oncompacting)(UINT) を afx_msg します。|
|ON_WM_COMPAREITEM ()|afx_msg int [Oncompareitem](../../mfc/reference/cwnd-class.md#oncompareitem)(LPCOMPAREITEMSTRUCT);|
|ON_WM_CONTEXTMENU ()|void [Oncontextmenu](../../mfc/reference/cwnd-class.md#oncontextmenu)(CWnd \* , CPoint); を afx_msg します。|
|ON_WM_COPYDATA ()|afx_msg BOOL [OnCopyData](../../mfc/reference/cwnd-class.md#oncopydata)(CWnd \* PWND, copydatastruct \* pcopydatastruct);|
|ON_WM_CREATE ()|afx_msg int [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)(LPCREATESTRUCT);|
|ON_WM_CTLCOLOR ()|afx_msg HBRUSH [OnCtlColor](../../mfc/reference/cwnd-class.md#onctlcolor)(CDC \* , CWnd \* , UINT);|

## <a name="see-also"></a>関連項目

[メッセージ マップ](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ メッセージのハンドラー](../../mfc/reference/handlers-for-wm-messages.md)
