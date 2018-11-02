---
title: RGNDATA 構造体
ms.date: 11/04/2016
f1_keywords:
- RGNDATA
helpviewer_keywords:
- RGNDATA structure [MFC]
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
ms.openlocfilehash: d6ee25b490aa5c7055b4e8ccf63939fbdd8dd4ac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638140"
---
# <a name="rgndata-structure"></a>RGNDATA 構造体

`RGNDATA`構造には、ヘッダーとリージョンを構成する四角形の配列が含まれています。 これらの四角形、並べ替えられた上部から下、左から右は重複しません。

## <a name="syntax"></a>構文

```
typedef struct _RGNDATA { /* rgnd */
    RGNDATAHEADER rdh;
    char Buffer[1];
} RGNDATA;
```

#### <a name="parameters"></a>パラメーター

*rdh*<br/>
指定します、 [RGNDATAHEADER](/windows/desktop/api/wingdi/ns-wingdi-_rgndataheader)構造体。 (この構造体の詳細については、Windows SDK を参照してください)。この構造体のメンバーでは、リージョン (かどうかは四角形または台形)、領域、四角形構造体を格納しているバッファーのサイズを構成する四角形の数の種類を指定しにします。

*Buffer*<br/>
含む、任意のサイズのバッファーを指定します、 [RECT](../../mfc/reference/rect-structure1.md)リージョンを構成します。

## <a name="requirements"></a>必要条件

**ヘッダー:** wingdi.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)<br/>
[CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)

