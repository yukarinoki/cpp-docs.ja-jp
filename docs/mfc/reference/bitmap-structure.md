---
title: BITMAP 構造体
ms.date: 11/04/2016
f1_keywords:
- BITMAP
helpviewer_keywords:
- BITMAP structure [MFC]
ms.assetid: 05d33b4d-7232-4643-a108-87dda8ff5f22
ms.openlocfilehash: 1a1079ea0b032f5d28995dc0e3b15b5ba6d16376
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50576086"
---
# <a name="bitmap-structure"></a>BITMAP 構造体

**ビットマップ**構造体は、高さ、幅、色の書式、および論理ビットマップのビット値を定義します。**します。**

## <a name="syntax"></a>構文

```
typedef struct tagBITMAP {  /* bm */
    int bmType;
    int bmWidth;
    int bmHeight;
    int bmWidthBytes;
    BYTE bmPlanes;
    BYTE bmBitsPixel;
    LPVOID bmBits;
} BITMAP;
```

#### <a name="parameters"></a>パラメーター

*bmType*<br/>
ビットマップの種類を指定します。 論理ビットマップの場合、このメンバーは 0 であることが必要です。

*bmWidth*<br/>
ビットマップの幅 (ピクセル単位) を指定します。 幅は 0 より大きい値でなければなりません。

*bmHeight*<br/>
ラスター行数を使用してビットマップの高さを指定します。 高さは 0 より大きい値でなければなりません。

*bmWidthBytes*<br/>
各ラスター行に含まれるバイト数を指定します。 グラフィック デバイス インターフェイス (GDI) は、ビットマップ形式のビット値が整数値 (2 バイト) の配列を形成することを想定するため、この値は偶数であることが必要です。 つまり、 *bmWidthBytes* \* 8 は、ときに取得した値以上の 16 の倍数である必要があります、 *bmWidth*メンバーを乗算して、 *bmBitsPixel*メンバー。

*bmPlanes*<br/>
ビットマップ内でのカラー プレーンの数を指定します。

*bmBitsPixel*<br/>
ピクセルを定義するために必要とされる各プレーンで、隣接するカラー ビット数を指定します。

*bmBits*<br/>
ビットマップのビット値が配置されている位置へのポインター。 *BmBits*メンバーは 1 バイト値の配列への long ポインターである必要があります。

## <a name="remarks"></a>Remarks

現在使用されているビットマップ形式は、モノクロおよびカラーです。 モノクロ ビットマップは、1 ビット、1 プレーンのファイル形式を使用します。 各スキャンは 16 ビットの倍数です。

モノクロ ビットマップの高さのスキャンが次のように編成された*n*:

```
Scan 0
Scan 1
.
.
.
Scan n-2
Scan n-1
```

モノクロ デバイス上のピクセルは黒と白のどちらかです。 ビットマップ内で対応するビットが 1 の場合、そのピクセルはオン (白) になります。 ビットマップ内で対応するビットが 0 の場合、そのピクセルはオフ (黒) になります。

すべてのデバイスの RASTERCAPS インデックスのビット RC_BITBLT セット ビットマップをサポートする、[は](../../mfc/reference/cdc-class.md#getdevicecaps)メンバー関数。

各デバイスには、独自のカラー形式があります。 別に 1 つのデバイスからビットマップを転送するために使用して、 [GetDIBits](/windows/desktop/api/wingdi/nf-wingdi-getdibits)と[SetDIBits](/windows/desktop/api/wingdi/nf-wingdi-setdibits) Windows 関数。

## <a name="requirements"></a>必要条件

**ヘッダー:** wingdi.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Cbitmap::createbitmapindirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)
