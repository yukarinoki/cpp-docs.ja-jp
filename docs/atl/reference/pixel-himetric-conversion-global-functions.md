---
title: ピクセル-HIMETRIC 変換のグローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
ms.openlocfilehash: 43a12985f259603a9b67f22f7a7891bf847c0b0f
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423016"
---
# <a name="pixelhimetric-conversion-global-functions"></a>Pixel/HIMETRIC 変換のグローバル関数

これらの関数は、ピクセルおよび HIMETRIC 単位との間の変換をサポートします。

> [!IMPORTANT]
>  次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。

|||
|-|-|
|[AtlHiMetricToPixel](#atlhimetrictopixel)|HIMETRIC 単位 (各単位は0.01 ミリメートル) をピクセルに変換します。|
|[Atlピクセル Tohimetric](#atlpixeltohimetric)|ピクセルを HIMETRIC 単位 (各単位は0.01 ミリメートル) に変換します。|

##  <a name="atlhimetrictopixel"></a>AtlHiMetricToPixel

HIMETRIC 単位 (各単位は 0.01 mm) のオブジェクトのサイズを画面デバイス上のピクセル単位のサイズに変換します。

```
extern void AtlHiMetricToPixel(
    const SIZEL* lpSizeInHiMetric,
    LPSIZEL lpSizeInPix);
```

### <a name="parameters"></a>パラメーター

*lpSizeInHiMetric*<br/>
からHIMETRIC 単位のオブジェクトのサイズへのポインター。

*lpSizeInPix*<br/>
入出力オブジェクトのサイズ (ピクセル単位) が返される位置へのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#49](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin. h

##  <a name="atlpixeltohimetric"></a>Atlピクセル Tohimetric

画面デバイス上のピクセル単位のオブジェクトのサイズを HIMETRIC 単位 (各単位は 0.01 mm) のサイズに変換します。

```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix,
    LPSIZEL lpSizeInHiMetric);
```

### <a name="parameters"></a>パラメーター

*lpSizeInPix*<br/>
からオブジェクトのサイズ (ピクセル単位) へのポインター。

*lpSizeInHiMetric*<br/>
入出力HIMETRIC 単位のオブジェクトのサイズが返される位置へのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin. h

## <a name="see-also"></a>参照

[関数](../../atl/reference/atl-functions.md)
