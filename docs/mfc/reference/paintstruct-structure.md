---
title: PAINTSTRUCT 構造体
ms.date: 11/04/2016
f1_keywords:
- PAINTSTRUCT
helpviewer_keywords:
- PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
ms.openlocfilehash: b5179a1bcba4a654ff235885ec2d0516e801fbb7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677124"
---
# <a name="paintstruct-structure"></a>PAINTSTRUCT 構造体

`PAINTSTRUCT`構造体には、ウィンドウのクライアント領域の描画に使用できる情報が含まれています。

## <a name="syntax"></a>構文

```
typedef struct tagPAINTSTRUCT {
    HDC hdc;
    BOOL fErase;
    RECT rcPaint;
    BOOL fRestore;
    BOOL fIncUpdate;
    BYTE rgbReserved[16];
} PAINTSTRUCT;
```

#### <a name="parameters"></a>パラメーター

*hdc*<br/>
描画に使用するディスプレイ コンテキストを識別します。

*fErase*<br/>
バック グラウンドが再描画する必要があるかどうかを指定します。 アプリケーションがバック グラウンドを再描画する場合は 0。 背景ブラシなし Windows ウィンドウ クラスを作成した場合、背景を描画するため、アプリケーションは、(の説明を参照して、`hbrBackground`のメンバー、 [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) Windows SDK の構造)。

*rcPaint*<br/>
左上隅を指定して、描画が要求された四角形の右下します。

*fRestore*<br/>
予約済みのメンバー。 Windows によって内部的に使用されます。

*fIncUpdate*<br/>
予約済みのメンバー。 Windows によって内部的に使用されます。

*rgbReserved [16]*<br/>
予約済みのメンバー。 Windows によって内部的に使用されるメモリの予約済みのブロック。

## <a name="requirements"></a>必要条件

**ヘッダー:** winuser.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CPaintDC::m_ps](../../mfc/reference/cpaintdc-class.md#m_ps)

