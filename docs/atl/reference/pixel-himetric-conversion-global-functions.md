---
title: ピクセル HIMETRIC 変換に関するグローバル関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
dev_langs:
- C++
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b5ab980813eec09fe0eef35f54280444d8c08b80
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105389"
---
# <a name="pixelhimetric-conversion-global-functions"></a>ピクセル/HIMETRIC 変換に関するグローバル関数

これらの関数は、ピクセルと HIMETRIC 単位から変換するためのサポートを提供します。

> [!IMPORTANT]
>  Windows ランタイムで実行するアプリケーションでは、次の表に示す関数を使用できません。

|||
|-|-|
|[AtlHiMetricToPixel](#atlhimetrictopixel)|(各単位は 0.01 ミリメートル) HIMETRIC 単位をピクセルに変換します。|
|[AtlPixelToHiMetric](#atlpixeltohimetric)|ピクセル HIMETRIC 単位に変換 (各単位は 0.01 ミリメートル)。|

##  <a name="atlhimetrictopixel"></a>  AtlHiMetricToPixel

HIMETRIC 単位 (各単位は 0.01 mm) のオブジェクトのサイズを画面デバイス上のピクセル単位のサイズに変換します。

```
extern void AtlHiMetricToPixel(
    const SIZEL* lpSizeInHiMetric, 
    LPSIZEL lpSizeInPix);
```

### <a name="parameters"></a>パラメーター

*lpSizeInHiMetric*<br/>
[in]HIMETRIC 単位内のオブジェクトのサイズへのポインター。

*lpSizeInPix*<br/>
[out]オブジェクトのサイズ (ピクセル単位) が返されるへのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#49](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]  

### <a name="requirements"></a>要件

**ヘッダー:** atlwin.h

##  <a name="atlpixeltohimetric"></a>  AtlPixelToHiMetric

画面デバイス上のピクセル単位のオブジェクトのサイズを HIMETRIC 単位 (各単位は 0.01 mm) のサイズに変換します。

```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix, 
    LPSIZEL lpSizeInHiMetric);
```

### <a name="parameters"></a>パラメーター

*lpSizeInPix*<br/>
[in]オブジェクトのサイズ (ピクセル単位) へのポインター。

*lpSizeInHiMetric*<br/>
[out]HIMETRIC 単位オブジェクトのサイズが返されるへのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]  

### <a name="requirements"></a>要件

**ヘッダー:** atlwin.h  

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
