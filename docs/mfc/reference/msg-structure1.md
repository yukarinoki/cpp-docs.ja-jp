---
title: MSG Structure1 |Microsoft Docs
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
ms.openlocfilehash: 2819faa25e2dbd41d6578d60780d13011bb645c0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388395"
---
# <a name="msg-structure1"></a>MSG Structure1

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

