---
title: CREATESTRUCT 構造体
ms.date: 11/04/2016
f1_keywords:
- CREATESTRUCT
helpviewer_keywords:
- CREATESTRUCT structure [MFC]
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
ms.openlocfilehash: 13f715dc914ccc052945790aeaff9c47bd34ed46
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619649"
---
# <a name="createstruct-structure"></a>CREATESTRUCT 構造体

`CREATESTRUCT`構造体は、アプリケーションのウィンドウ プロシージャに渡される初期化パラメーターを定義します。

## <a name="syntax"></a>構文

```
typedef struct tagCREATESTRUCT {
    LPVOID lpCreateParams;
    HANDLE hInstance;
    HMENU hMenu;
    HWND hwndParent;
    int cy;
    int cx;
    int y;
    int x;
    LONG style;
    LPCSTR lpszName;
    LPCSTR lpszClass;
    DWORD dwExStyle;
} CREATESTRUCT;
```

#### <a name="parameters"></a>パラメーター

*lpCreateParams*<br/>
ウィンドウを作成するためのデータへのポインター。

*hInstance*<br/>
新しいウィンドウを所有しているモジュールのモジュール インスタンス ハンドルを識別します。

*hMenu*<br/>
新しいウィンドウで使用するメニューを識別します。 子ウィンドウの場合は、整数の ID が含まれています

*hwndParent*<br/>
新しいウィンドウを所有しているウィンドウを識別します。 新しいウィンドウが最上位ウィンドウの場合、このメンバーは NULL です。

*cy*<br/>
新しいウィンドウの高さを指定します。

*cx*<br/>
新しいウィンドウの幅を指定します。

*y*<br/>
新しいウィンドウの左上隅の y 座標を指定します。 新しいウィンドウが子ウィンドウの場合に、親ウィンドウとの相対座標はそれ以外の場合、座標は画面の原点は。

*x*<br/>
新しいウィンドウの左上隅の x 座標を指定します。 新しいウィンドウが子ウィンドウの場合に、親ウィンドウとの相対座標はそれ以外の場合、座標は画面の原点は。

*style*<br/>
新しいウィンドウの指定[スタイル](../../mfc/reference/styles-used-by-mfc.md)します。

*lpszName*<br/>
新しいウィンドウの名前を指定する null で終わる文字列へのポインター。

*lpszClass*<br/>
新しいウィンドウの Windows クラス名を指定する null で終わる文字列の指す (、 [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576)構造体は、詳細については、Windows SDK を参照してください)。

*dwExStyle*<br/>
指定します、[拡張スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)新しいウィンドウの。

## <a name="requirements"></a>必要条件

**ヘッダー:** winuser.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)

