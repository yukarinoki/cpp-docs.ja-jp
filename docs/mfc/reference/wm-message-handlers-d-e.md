---
description: '詳細については、「WM_ メッセージハンドラー: D-E」を参照してください。'
title: 'WM_ で始まるメッセージのハンドラー : D - E'
ms.date: 11/04/2016
f1_keywords:
- ON_WM_ERASEBKGND
- ON_WM_DEVICECHANGE
- ON_WM_ENTERIDLE
- ON_WM_DESTROYCLIPBOARD
- ON_WM_DESTROY
- ON_WM_DEADCHAR
- ON_WM_DELETEITEM
- ON_WM_DROPFILES
- ON_WM_DEVMODECHANGE
- ON_WM_ENDSESSION
- ON_WM_ENABLE
- ON_WM_DRAWITEM
- ON_WM_DRAWCLIPBOARD
helpviewer_keywords:
- ON_WM_ENTERIDLE [MFC]
- ON_WM_DESTROYCLIPBOARD [MFC]
- ON_WM_DEADCHAR [MFC]
- ON_WM_DEVMODECHANGE [MFC]
- ON_WM_ERASEBKGND [MFC]
- ON_WM_DESTROY [MFC]
- ON_WM_DRAWCLIPBOARD [MFC]
- ON_WM_ENDSESSION [MFC]
- ON_WM_DRAWITEM [MFC]
- ON_WM_ENABLE [MFC]
- ON_WM_DROPFILES [MFC]
- ON_WM_DELETEITEM [MFC]
- ON_WM_DEVICECHANGE [MFC]
- WM_ messages [MFC]
ms.assetid: 56fb89c8-68a8-4adf-883e-a9f63bf677e9
ms.openlocfilehash: fc9de81127e008eb69a57b39bd66907214b48f89
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218486"
---
# <a name="wm_-message-handlers-d---e"></a>WM_ で始まるメッセージのハンドラー : D - E

左側の次のマップエントリは、右側の関数プロトタイプに対応しています。

|マップエントリ|関数プロトタイプ|
|---------------|------------------------|
|ON_WM_DEADCHAR ()|afx_msg void [OnDeadChar](../../mfc/reference/cwnd-class.md#ondeadchar)(UINT, UINT, uint);|
|ON_WM_DELETEITEM ()|afx_msg void [OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)(INT, LPDELETEITEMSTRUCT);|
|ON_WM_DESTROY ()|afx_msg void [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy)();|
|ON_WM_DESTROYCLIPBOARD ()|void [Ondestroyclipboard](../../mfc/reference/cwnd-class.md#ondestroyclipboard)() を afx_msg します。|
|ON_WM_DEVICECHANGE ()|void [Ondevicechange](../../mfc/reference/cwnd-class.md#ondevicechange)(UINT, DWORD) を afx_msg します。|
|ON_WM_DEVMODECHANGE ()|void [Ondevmodechange](../../mfc/reference/cwnd-class.md#ondevmodechange)(LPSTR) を afx_msg します。|
|ON_WM_DRAWCLIPBOARD ()|afx_msg void [OnDrawClipboard](../../mfc/reference/cwnd-class.md#ondrawclipboard)();|
|ON_WM_DRAWITEM ()|afx_msg void [OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)(LPDRAWITEMSTRUCT);|
|ON_WM_DROPFILES ()|afx_msg void [OnDropFiles](../../mfc/reference/cwnd-class.md#ondropfiles)(HDROP);|
|ON_WM_DWMCOLORIZATIONCOLORCHANGED ()|afx_msg void [Oncolorizationcolorchanged](../../mfc/reference/cwnd-class.md#oncolorizationcolorchanged)(DWORD, BOOL);|
|ON_WM_DWMCOMPOSITIONCHANGED ()|afx_msg void [OnCompositionChanged](../../mfc/reference/cwnd-class.md#oncompositionchanged)();|
|ON_WM_DWMNCRENDERINGCHANGED ()|afx_msg void [OnNcRenderingChanged](../../mfc/reference/cwnd-class.md#onncrenderingchanged)(BOOL);|
|ON_WM_DWMWINDOWMAXIMIZEDCHANGE ()|afx_msg void [Onwindowが変更された](../../mfc/reference/cwnd-class.md#onwindowmaximizedchanged)(BOOL);|
|ON_WM_ENABLE ()|void [Onenable](../../mfc/reference/cwnd-class.md#onenable)(BOOL) を afx_msg します。|
|ON_WM_ENDSESSION ()|afx_msg void [OnEndSession](../../mfc/reference/cwnd-class.md#onendsession)(BOOL);|
|ON_WM_ENTERIDLE ()|void [Onenteridle](../../mfc/reference/cwnd-class.md#onenteridle)(UINT, CWnd *); を afx_msg します。|
|ON_WM_ENTERSIZEMOVE ()|void [Onentersizemove](../../mfc/reference/cwnd-class.md#onentersizemove)afx_msg を無効にします ()。|
|ON_WM_ERASEBKGND ()|afx_msg BOOL [OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd)(CDC *);|
|ON_WM_EXITSIZEMOVE ()|void [Onexitsizemove](../../mfc/reference/cwnd-class.md#onexitsizemove)afx_msg を無効にします ()。|

## <a name="see-also"></a>関連項目

[メッセージ マップ](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ メッセージのハンドラー](../../mfc/reference/handlers-for-wm-messages.md)
