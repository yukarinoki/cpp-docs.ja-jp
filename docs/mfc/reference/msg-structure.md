---
title: MSG 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MSG
dev_langs:
- C++
helpviewer_keywords:
- MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b2f58af3bcf3eef524b95d25579e5bc233f9108
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2018
ms.locfileid: "49334567"
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

## <a name="requirements"></a>要件

**ヘッダー:** winuser.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

