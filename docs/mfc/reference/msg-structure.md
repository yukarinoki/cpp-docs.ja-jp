---
title: MSG 構造体
ms.date: 11/04/2016
f1_keywords:
- MSG
helpviewer_keywords:
- MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
ms.openlocfilehash: 1a953f8d0d685e25beedd2d401e227c934414208
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499814"
---
# <a name="msg-structure"></a>MSG 構造体

`MSG`構造体には、スレッドのメッセージ キューからメッセージの情報が含まれています。

## <a name="syntax"></a>構文

```
typedef struct tagMSG {     // msg
    HWND hwnd;
    UINT message;
    WPARAM wParam;
    LPARAM lParam;
    DWORD time;
    POINT pt;
} MSG;
```

#### <a name="parameters"></a>パラメーター

*hwnd*<br/>
ウィンドウ プロシージャがメッセージを受け取るウィンドウを識別します。

*message*<br/>
メッセージの数を指定します。

*wParam*<br/>
メッセージに関する追加情報を指定します。 厳密な意味は、の値によって異なります、`message`メンバー。

*lParam*<br/>
メッセージに関する追加情報を指定します。 厳密な意味は、の値によって異なります、`message`メンバー。

*time*<br/>
メッセージが投稿された時刻を指定します。

*pt*<br/>
カーソルの位置を画面座標では、メッセージがポストされたときに指定します。

## <a name="requirements"></a>必要条件

**ヘッダー:** winuser.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

