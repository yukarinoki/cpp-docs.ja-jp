---
title: fma、fmaf、fmal
ms.date: 04/05/2018
apiname:
- fma
- fmaf
- fmal
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: f96592e245e443bae2f3334da51cae5572753708
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51517801"
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

*x*<br/>
乗算する 1 番目の値。

*y*<br/>
乗算する 2 番目の値。

*z*<br/>
加算する値。

## <a name="return-value"></a>戻り値

`(x * y) + z` を返します。 さらに戻り値は、現在の丸めの形式を使用して丸められます。

それ以外の場合は、次の値のいずれかを返します。

|懸案事項|Return|
|-----------|------------|
|*x* = INFINITY、 *y* = 0 または<br /><br /> *x* = 0、 *y* = INFINITY|NaN|
|*x*または*y* = 正確な ± 無限大、 *z*符号は逆の無限大を =|NaN|
|*x*または*y* = NaN|NaN|
|しない (*x* = 0、 *y*/a 1 >= indefinite) と*z* = NaN<br /><br /> しない (*x*= indefinite, *y*= 0) と*z* = NaN|NaN|
|オーバーフロー範囲エラー|±HUGE_VAL、±HUGE_VALF、または ±HUGE_VALL|
|アンダーフロー範囲エラー|丸めた後の正確な値。|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>Remarks

オーバー ロードを呼び出すことができますので、C++ ではオーバー ロード、 **fma**を受け取って返す**float**と**長い****二重**型。 C プログラムで**fma**は、**二重**します。

この関数は、値を無限の精度とするかのように計算し、最終的な結果を丸めます。

## <a name="requirements"></a>必要条件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fma**、 **fmaf**、 **fmal**|\<math.h>|\<cmath>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[remainder、remainderf、remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo、remquof、remquol](remquo-remquof-remquol.md)<br/>
