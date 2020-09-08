---
title: fma、fmaf、fmal
description: Fma、fmaf、および f の API リファレンス2つの値を乗算し、3番目の値を加算した後、中間丸めによる精度を失うことなく結果を丸めます。
ms.date: 9/1/2020
api_name:
- fma
- fmaf
- fmal
- _o_fma
- _o_fmaf
- _o_fmal
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
ms.openlocfilehash: e9ae92c28f24b6281d73450c7cabaad775a84d42
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556698"
---
# <a name="fma-fmaf-fmal"></a>fma、fmaf、fmal

2つの値を乗算し、3番目の値を加算した後、中間丸めによる精度を失うことなく結果を丸めます。

## <a name="syntax"></a>構文

```C
double fma(
   double x,
   double y,
   double z
);

float fma(
   float  x,
   float  y,
   float z
); //C++ only

long double fma(
   long double  x,
   long double  y,
   long double z
); //C++ only

float fmaf(
   float  x,
   float  y,
   float z
);

long double fmal(
   long double  x,
   long double  y,
   long double z
);

#define fma(X, Y, Z) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*閉じる*\
乗算する 1 番目の値。

*前年*\
乗算する 2 番目の値。

*方向*\
加算する値。

## <a name="return-value"></a>戻り値

`(x * y) + z` を返します。 さらに戻り値は、現在の丸めの形式を使用して丸められます。

それ以外の場合は、次の値のいずれかを返します。

|問題|戻り値|
|-----------|------------|
|*x* = 無限大、 *y* = 0 または<br /><br /> *x* = 0、 *y* = 無限大|NaN|
|*x* または *y* = 正確な±無限大、 *z* = 無限大と逆の符号|NaN|
|*x* または *y* = NaN|NaN|
|not (*x* = 0、 *y*= 不定)、 *z* = NaN<br /><br /> not (*x*= 不定, *y*= 0) および *z* = NaN|NaN|
|オーバーフロー範囲エラー|± HUGE_VAL、± HUGE_VALF、または± HUGE_VALL|
|アンダーフロー範囲エラー|丸めた後の正確な値。|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、型と型を受け取って返す **fma** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 \<tgmath.h> **fma** は常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `fma()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

この関数は、値を無限の精度とするかのように計算し、最終的な結果を丸めます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fma**、 **fmaf**、 **fマル**|\<math.h>|\<cmath>|
|**fma** マクロ | \<tgmath.h> ||

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[remainder、remainderf、remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo、remquof、remquol](remquo-remquof-remquol.md)<br/>
