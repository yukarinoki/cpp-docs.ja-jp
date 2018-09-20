---
title: WINDOWPLACEMENT 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WINDOWPLACEMENT
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPLACEMENT structure [MFC]
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b163d93de22d313d72ca5dbfd384788077ae1b01
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447278"
---
# <a name="windowplacement-structure"></a>WINDOWPLACEMENT 構造体

`WINDOWPLACEMENT`構造体には、画面上のウィンドウの配置に関する情報が含まれています。

## <a name="syntax"></a>構文

```
typedef struct tagWINDOWPLACEMENT {     /* wndpl */
    UINT length;
    UINT flags;
    UINT showCmd;
    POINT ptMinPosition;
    POINT ptMaxPosition;
    RECT rcNormalPosition;
} WINDOWPLACEMENT;
```

#### <a name="parameters"></a>パラメーター

*length*<br/>
構造体のバイト単位の長さを指定します。

*flags*<br/>
最小化されたウィンドウと、ウィンドウを復元する方法の位置を制御するフラグを指定します。 このメンバーには、次のフラグの一方または両方を指定できます。

- WPF_SETMINPOSITION では、最小化されたウィンドウの x 位置と y 位置を指定できることを指定します。 このフラグである必要があります指定座標を設定するかどうか、`ptMinPosition`メンバー。

- WPF_RESTORETOMAXIMIZED では、復元されたウィンドウが最大化される、最小化する前に、最大化されていたかどうかに関係なくを指定します。 この設定は次に、ウィンドウの復元時にのみ有効です。 既定の復元動作は変わりません。 このフラグが有効ではこのメンバーは値が指定されている場合にのみ、`showCmd`メンバー。

*showCmd*<br/>
ウィンドウの現在の表示状態を指定します。 このメンバーには、次の値のいずれかを指定できます。

- SW_HIDE では、ウィンドウを非表示にし、別のウィンドウをアクティブ化を渡します。

- SW_MINIMIZE では、指定したウィンドウを最小化し、システムの一覧にあるトップレベル ウィンドウをアクティブにします。

- SW_RESTORE をアクティブにし、ウィンドウを表示します。 ウィンドウが最小化または最大化されている場合、Windows を元のサイズと位置 (SW_SHOWNORMAL と同じ) に復元します。

- SW_SHOW はウィンドウをアクティブにし、現在のサイズと位置に表示されます。

- SW_SHOWMAXIMIZED はウィンドウをアクティブにし、最大化されたウィンドウとして表示されます。

- このメンバーはでは、ウィンドウをアクティブにし、アイコンとして表示されます。

- SW_SHOWMINNOACTIVE ウィンドウをアイコンとして表示します。 現在アクティブなウィンドウは、アクティブなままです。

- SW_SHOWNA では、現在の状態でウィンドウが表示されます。 現在アクティブなウィンドウは、アクティブなままです。

- SW_SHOWNOACTIVATE では、最新のサイズと位置で、ウィンドウが表示されます。 現在アクティブなウィンドウは、アクティブなままです。

- SW_SHOWNORMAL をアクティブにし、ウィンドウを表示します。 ウィンドウが最小化または最大化されている場合、Windows を元のサイズと位置 (SW_RESTORE と同じ) に復元します。

*ptMinPosition*<br/>
ウィンドウが最小化するときは、ウィンドウの左上隅の位置を指定します。

*ptMaxPosition*<br/>
ウィンドウを最大化するときは、ウィンドウの左上隅の位置を指定します。

*rcNormalPosition*<br/>
ウィンドウが通常の (復元) の位置にあるときは、ウィンドウの座標を指定します。

## <a name="requirements"></a>要件

**ヘッダー:** winuser.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::SetWindowPlacement](../../mfc/reference/cwnd-class.md#setwindowplacement)

