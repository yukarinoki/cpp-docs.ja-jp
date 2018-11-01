---
title: RECT 構造体
ms.date: 11/04/2016
f1_keywords:
- LPRECT
- RECT
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
ms.openlocfilehash: 1cb997fc0f1ec89eabf5e4d2c2c5ccb15e3bafec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549014"
---
# <a name="rect-structure"></a>RECT 構造体

`RECT` 構造体は、四角形の左上隅および右下隅の座標を定義します。

## <a name="syntax"></a>構文

```
typedef struct tagRECT {
    LONG left;
    LONG top;
    LONG right;
    LONG bottom;
} RECT;
```

## <a name="members"></a>メンバー

`left`<br/>
四角形の左上隅の X 座標を指定します。

`top`<br/>
四角形の左上隅の Y 座標を指定します。

`right`<br/>
四角形の右下隅の X 座標を指定します。

`bottom`<br/>
四角形の右下隅の Y 座標を指定します。

## <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** windef.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CRect クラス](../../atl-mfc-shared/reference/crect-class.md)
