---
title: fma、fmaf、fmal
ms.date: 4/2/2020
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 993ca4d57202b3789929161a964b3e41d48fd98f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346567"
---
# <a name="fma-fmaf-fmal"></a>fma、fmaf、fmal

2 つの値を乗算、3 番目の値を追加し、結果を丸めます。中間丸め処理による精度の低下はありません。

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
```

### <a name="parameters"></a>パラメーター

*X*<br/>
乗算する 1 番目の値。

*Y*<br/>
乗算する 2 番目の値。

*Z*<br/>
加算する値。

## <a name="return-value"></a>戻り値

`(x * y) + z` が返されます。 さらに戻り値は、現在の丸めの形式を使用して丸められます。

それ以外の場合は、次の値のいずれかを返します。

|問題|戻り値|
|-----------|------------|
|*x* = 無限大 *、y* = 0 または<br /><br /> *x* = 0、 *y* = 無限大|(NaN)|
|*x*または*y* = 正確な ± INFINITY、 *z* = 反対の符号を持つ INFINITY|(NaN)|
|*x*または*y* = NaN|(NaN)|
|ない *(x* = *0、y*= 無期限) および*z* = NaN<br /><br /> ない (*x*= 無期限、 *y*= 0) および*z* = NaN|(NaN)|
|オーバーフロー範囲エラー|±HUGE_VAL、±HUGE_VALF、±HUGE_VALL|
|アンダーフロー範囲エラー|丸めた後の正確な値。|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能なため **、float**型と**長い****ダブル**型を受け取り、戻す**fma**のオーバーロードを呼び出すことができます。 C プログラムでは **、fma**は常に二**重**を取り、返します。

この関数は、値を無限の精度とするかのように計算し、最終的な結果を丸めます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fma**, **fmaf**,**フマル**|\<math.h>|\<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[remainder、remainderf、remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo、remquof、remquol](remquo-remquof-remquol.md)<br/>
