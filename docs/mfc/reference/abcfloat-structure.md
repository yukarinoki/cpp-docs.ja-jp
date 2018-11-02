---
title: ABCFLOAT 構造体
ms.date: 11/04/2016
f1_keywords:
- ABCFLOAT
helpviewer_keywords:
- ABCFLOAT structure [MFC]
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
ms.openlocfilehash: b9e3923e8c70e38fe5efe959db8da43118cc6445
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443662"
---
# <a name="abcfloat-structure"></a>ABCFLOAT 構造体

`ABCFLOAT`フォント文字の A、B、および C の幅が構造に含まれています。

## <a name="syntax"></a>構文

```
typedef struct _ABCFLOAT { /* abcf */
    FLOAT abcfA;
    FLOAT abcfB;
    FLOAT abcfC;
} ABCFLOAT;
```

#### <a name="parameters"></a>パラメーター

*abcfA*<br/>
文字の A の間隔を指定します。 A の間隔は、文字のグリフを描画する前に、現在の位置に追加する距離です。

*abcfB*<br/>
文字の B の間隔を指定します。 B の間隔は、文字のグリフの描画の部分の幅です。

*abcfC*<br/>
C の文字の間隔を指定します。 C の間隔は、文字のグリフの右側に空白文字を提供する現在の位置に追加する距離です。

## <a name="remarks"></a>Remarks

A、B、および C の幅は、フォントのベース ラインに沿って測定されます。 文字の文字のインクリメント (幅の合計) は、A、B、および C のスペースの合計です。 A または C 領域のいずれかをスペーシングまたはオーバー ハングを示す負にすることができます。

## <a name="requirements"></a>必要条件

**ヘッダー:** wingdi.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

