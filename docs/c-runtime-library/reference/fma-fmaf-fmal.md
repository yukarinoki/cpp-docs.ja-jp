---
title: fma、fmaf、fmal | Microsoft ドキュメント
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b28009a9c3cc4edceb9032660a0c2a71916dfb2f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401478"
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
|*x* 、無限大*y* = 0 または<br /><br /> *x* = 0、 *y*無限大を =|NaN|
|*x*または*y* = 正確な ± の無限大、 *z*逆の符号を持つ無限大を =|NaN|
|*x*または*y* NaN を =|NaN|
|されません (*x* = 0、 *y*= 無制限) と*z* NaN を =<br /><br /> されません (*x*= 不定値、 *y*= 0) と*z* NaN を =|NaN|
|オーバーフロー範囲エラー|±HUGE_VAL、±HUGE_VALF、または ±HUGE_VALL|
|アンダーフロー範囲エラー|丸めた後の正確な値。|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>コメント

C++ では、オーバー ロードできるよう、ためのオーバー ロードを呼び出すことができます**fma**を受け取り、返します**float**と**長い****二重**型です。 C プログラムでは、 **fma**常に受け取りを返す、**二重**です。

この関数は、値を無限の精度とするかのように計算し、最終的な結果を丸めます。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fma**、 **fmaf**、 **fmal**|\<math.h>|\<cmath>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[remainder、remainderf、remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo、remquof、remquol](remquo-remquof-remquol.md)<br/>
