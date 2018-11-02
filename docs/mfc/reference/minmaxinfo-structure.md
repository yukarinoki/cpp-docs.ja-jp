---
title: MINMAXINFO 構造体
ms.date: 11/04/2016
f1_keywords:
- MINMAXINFO
helpviewer_keywords:
- MINMAXINFO structure [MFC]
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
ms.openlocfilehash: 11f55b1756623626769e21c006543b6993607b08
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517846"
---
# <a name="minmaxinfo-structure"></a>MINMAXINFO 構造体

`MINMAXINFO`構造体には、ウィンドウの最大サイズと位置、および追跡の最小値と最大サイズに関する情報が含まれています。

## <a name="syntax"></a>構文

```
typedef struct tagMINMAXINFO {
    POINT ptReserved;
    POINT ptMaxSize;
    POINT ptMaxPosition;
    POINT ptMinTrackSize;
    POINT ptMaxTrackSize;
} MINMAXINFO;
```

#### <a name="parameters"></a>パラメーター

*ptReserved*<br/>
内部使用のために予約されています。

*ptMaxSize*<br/>
最大の幅 (point.x) と、ウィンドウの最大の高さ (point.y) を指定します。

*ptMaxPosition*<br/>
最大表示されたウィンドウ (point.x) の左側の位置と最大化ウィンドウ (point.y) の上端の位置を指定します。

*ptMinTrackSize*<br/>
最小のトラッキングの幅 (point.x) と、ウィンドウの高さ (point.y) の追跡の最小値を指定します。

*ptMaxTrackSize*<br/>
トラッキングの幅 (point.x) の最大値、およびウィンドウの高さ (point.y) を追跡する最大値を指定します。

## <a name="requirements"></a>必要条件

**ヘッダー:** winuser.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)

