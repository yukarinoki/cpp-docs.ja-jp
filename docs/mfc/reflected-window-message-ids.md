---
title: 返送されたウィンドウ メッセージの ID
ms.date: 11/04/2016
f1_keywords:
- OCM_CTLCOLORBTN
- OCM_PARENTNOTIFY
- OCM_VKEYTOITEM
- OCM_CTLCOLORSTATIC
- OCM_HSCROLL
- OCM_CHARTOITEM
- OCM_DRAWITEM
- OCM_MEASUREITEM
- OCM_COMPAREITEM
- OCM_COMMAND
- OCM_NOTIFY
- OCM_CTLCOLORMSGBOX
- OCM_DELETEITEM
- OCM_CTLCOLORLISTBOX
- OCM_CTLCOLORDLG
- OCM_CTLCOLOREDIT
- OCM_CTLCOLORSCROLLBAR
- OCM_VSCROLL
- OCM_CTLCOLOR
helpviewer_keywords:
- OCM_HSCROLL message [MFC]
- OCM_PARENTNOTIFY message [MFC]
- messages, reflected
- reflected messages, window message Ids
- OCM_CTLCOLORDLG message [MFC]
- OCM_COMMAND message [MFC]
- OCM_CTLCOLORMSGBOX message [MFC]
- OCM_COMPAREITEM message [MFC]
- OCM_DRAWITEM message [MFC]
- OCM_VSCROLL message [MFC]
- OCM_CTLCOLOREDIT message [MFC]
- OCM_VKEYTOITEM message [MFC]
- OCM_CHARTOITEM message [MFC]
- OCM_CTLCOLORBTN message [MFC]
- OCM_CTLCOLORSTATIC message [MFC]
- OCM_MEASUREITEM message [MFC]
- OCM_CTLCOLOR message [MFC]
- OCM_CTLCOLORSCROLLBAR message [MFC]
- OCM_ messages
- OCM_DELETEITEM message [MFC]
- OCM_CTLCOLORLISTBOX message [MFC]
- OCM_NOTIFY message [MFC]
- reflected messages
ms.assetid: 3417ff51-ff9f-458c-bff4-17c200f00d96
ms.openlocfilehash: 5b44a1b4e96d92d9ddd150a5b5f68cf83863f8db
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372852"
---
# <a name="reflected-window-message-ids"></a>返送されたウィンドウ メッセージの ID

ActiveX コントロールやその他の特殊なコントロールを簡単に作成するには、ウィンドウをサブクラス化します。 詳細については、「 [MFC ActiveX コントロール : Windows コントロールのサブクラス化](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)」を参照してください。

コントロールのコンテナーがサブクラス化された Windows コントロールから送信されたウィンドウ メッセージを受信しないように[、COleControl](../mfc/reference/colecontrol-class.md)は、特定のウィンドウ メッセージをインターセプトし、コントロールに返す"リフレクタ" ウィンドウを作成します。 そのウィンドウ プロシージャ内のコントロールは、ActiveX コントロールに適したアクションを実行することによって、これらの反映されたメッセージを処理できます。

次の表は、インターセプトされるメッセージと、リフレクタ ウィンドウが送信する対応するメッセージを示しています。

|コントロールによって送信されたメッセージ|コントロールに反映されるメッセージ|
|---------------------------------|--------------------------------------|
|[WM_COMMAND](/windows/win32/menurc/wm-command)|OCM_COMMAND|
|[WM_CTLCOLORBTN](/windows/win32/Controls/wm-ctlcolorbtn)|OCM_CTLCOLORBTN|
|[WM_CTLCOLOREDIT](/windows/win32/Controls/wm-ctlcoloredit)|OCM_CTLCOLOREDIT|
|[WM_CTLCOLORDLG](/windows/win32/dlgbox/wm-ctlcolordlg)|OCM_CTLCOLORDLG|
|[WM_CTLCOLORLISTBOX](/windows/win32/Controls/wm-ctlcolorlistbox)|OCM_CTLCOLORLISTBOX|
|[WM_CTLCOLORSCROLLBAR](/windows/win32/Controls/wm-ctlcolorscrollbar)|OCM_CTLCOLORSCROLLBAR|
|[WM_CTLCOLORSTATIC](/windows/win32/Controls/wm-ctlcolorstatic)|OCM_CTLCOLORSTATIC|
|[Wm_drawitem](/windows/win32/Controls/wm-drawitem)|OCM_DRAWITEM|
|[WM_MEASUREITEM](/windows/win32/Controls/wm-measureitem)|OCM_MEASUREITEM|
|[WM_DELETEITEM](/windows/win32/Controls/wm-deleteitem)|OCM_DELETEITEM|
|[WM_VKEYTOITEM](/windows/win32/Controls/wm-vkeytoitem)|OCM_VKEYTOITEM|
|[WM_CHARTOITEM](/windows/win32/Controls/wm-chartoitem)|OCM_CHARTOITEM|
|[WM_COMPAREITEM](/windows/win32/Controls/wm-compareitem)|OCM_COMPAREITEM|
|[WM_HSCROLL](/windows/win32/Controls/wm-hscroll)|OCM_HSCROLL|
|[WM_VSCROLL](/windows/win32/Controls/wm-vscroll)|OCM_VSCROLL|
|[WM_PARENTNOTIFY](/previous-versions/windows/desktop/inputmsg/wm-parentnotify)|OCM_PARENTNOTIFY|
|[Wm_notify](/windows/win32/controls/wm-notify)|OCM_NOTIFY|

> [!NOTE]
> コントロールが Win32 システムで実行されている場合、受信する可能性のある\*WM_CTLCOLOR メッセージには複数の種類があります。 詳細については、「WM_CTLCOLORBTN、WM_CTLCOLORDLG、WM_CTLCOLOREDIT、WM_CTLCOLORLISTBOX、WM_CTLCOLORMSGBOX、WM_CTLCOLORSCROLLBAR、WM_CTLCOLORSTATIC」を参照してください。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール: Windows コントロールのサブクラス化](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)<br/>
[テクニカル ノート 62: Windows コントロールへのメッセージ リフレクション (メッセージ返送)](../mfc/tn062-message-reflection-for-windows-controls.md)
