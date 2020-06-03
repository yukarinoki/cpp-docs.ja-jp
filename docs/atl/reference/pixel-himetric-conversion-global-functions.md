---
title: ピクセル-HIMETRIC変換グローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
ms.openlocfilehash: 08c72c0d8f3d061950d6945d9fb412c0a16355da
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326145"
---
# <a name="pixelhimetric-conversion-global-functions"></a>ピクセル/HIMETRIC 変換グローバル関数

これらの関数は、ピクセル単位と HIMETRIC 単位との間の変換をサポートします。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

|||
|-|-|
|[AtlHiMetricToPixel](#atlhimetrictopixel)|HIMETRIC 単位 (各単位は 0.01 ミリメートル) をピクセルに変換します。|
|[AtlPixelToHiMetric](#atlpixeltohimetric)|ピクセルを HIMETRIC 単位に変換します(各単位は 0.01 ミリメートル)。|

## <a name="atlhimetrictopixel"></a><a name="atlhimetrictopixel"></a>アトリメトリックトピクセル

HIMETRIC 単位 (各単位は 0.01 mm) のオブジェクトのサイズを画面デバイス上のピクセル単位のサイズに変換します。

```
extern void AtlHiMetricToPixel(
    const SIZEL* lpSizeInHiMetric,
    LPSIZEL lpSizeInPix);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]HIMETRIC 単位でのオブジェクトのサイズへのポインター。

*ピックス*<br/>
[アウト]オブジェクトのサイズ (ピクセル単位) を返す位置へのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#49](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="atlpixeltohimetric"></a><a name="atlpixeltohimetric"></a>アトルピクセルトヒメトリック

画面デバイス上のピクセル単位のオブジェクトのサイズを HIMETRIC 単位 (各単位は 0.01 mm) のサイズに変換します。

```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix,
    LPSIZEL lpSizeInHiMetric);
```

### <a name="parameters"></a>パラメーター

*ピックス*<br/>
[in]オブジェクトのサイズをピクセル単位で指定します。

*をクリックします。*<br/>
[アウト]HIMETRIC 単位でのオブジェクトのサイズが返される場所へのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
