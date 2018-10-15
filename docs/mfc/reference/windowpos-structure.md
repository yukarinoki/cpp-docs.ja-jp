---
title: WINDOWPOS 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WINDOWPOS
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPOS structure [MFC]
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 36e640187a87f3776a67a072e2fe77c141ed23f0
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2018
ms.locfileid: "49334578"
---
# <a name="windowpos-structure"></a>WINDOWPOS 構造体

`WINDOWPOS`構造体には、ウィンドウの位置とサイズに関する情報が含まれています。

## <a name="syntax"></a>構文

```
typedef struct tagWINDOWPOS { /* wp */
    HWND hwnd;
    HWND hwndInsertAfter;
    int x;
    int y;
    int cx;
    int cy;
    UINT flags;
} WINDOWPOS;
```

#### <a name="parameters"></a>パラメーター

*hwnd*<br/>
ウィンドウを識別します。

*オーダーで*<br/>
このウィンドウを配置するの背後にあるウィンドウを識別します。

*x*<br/>
ウィンドウの左端の位置を指定します。

*y*<br/>
ウィンドウの右端の位置を指定します。

*cx*<br/>
ウィンドウの幅をピクセル単位で指定します。

*cy*<br/>
ウィンドウの高さをピクセル単位で指定します。

*flags*<br/>
ウィンドウの位置決めオプションを指定します。 このメンバーには、次の値のいずれかを指定できます。

- SWP_DRAWFRAME を (ウィンドウのクラスの説明で定義されている) のフレーム ウィンドウの周囲に描画します。 ウィンドウは、WM_NCCALCSIZE メッセージを受け取ります。

- WM_NCCALCSIZE は SWP_FRAMECHANGED 送信、ウィンドウのサイズが変更されない場合でもにウィンドウに表示するメッセージします。 このフラグが指定されていない場合、ウィンドウのサイズが変更される場合にのみに WM_NCCALCSIZE が送信されます。

- SWP_HIDEWINDOW には、ウィンドウが非表示にします。

- ウィンドウをアクティブに SWP_NOACTIVATE しません。

- SWP_NOCOPYBITS では、クライアント領域の内容全体を破棄します。 このフラグが指定されていない場合、クライアント領域の有効な内容が保存され、ウィンドウのサイズまたは位置を変更した後、クライアント領域にコピーします。

- 現在の位置を SWP_NOMOVE が保持されます (は無視されます、`x`と`y`メンバー)。

- Z オーダーでのオーナー ウィンドウの位置を変更 SWP_NOOWNERZORDER しません。

- 現在のサイズを SWP_NOSIZE が保持されます (は無視されます、`cx`と`cy`メンバー)。

- 変更を再描画されない SWP_NOREDRAW しません。

- SWP_NOREPOSITION SWP_NOOWNERZORDER と同じです。

- SWP_NOSENDCHANGING では、ウィンドウが WM_WINDOWPOSCHANGING メッセージを受信できなくなります。

- 現在の注文を SWP_NOZORDER が保持されます (は無視されます、`hwndInsertAfter`メンバー)。

- SWP_SHOWWINDOW ウィンドウを表示します。

## <a name="requirements"></a>要件

**ヘッダー:** winuser.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)

