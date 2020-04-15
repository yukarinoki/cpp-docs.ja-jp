---
title: tgamma、tgammaf、tgammal
ms.date: 4/2/2020
api_name:
- tgamma
- tgammaf
- tgammal
- _o_tgamma
- _o_tgammaf
- _o_tgammal
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
- tgamma
- tgammaf
- tgammal
- math/tgamma
- math/tgammaf
- math/tgammal
helpviewer_keywords:
- tgamma function
- tgammaf function
- tgammal function
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
ms.openlocfilehash: d7e27e8b818a16cb0c18f58e2f40c0090dd13ecf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362502"
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma、tgammaf、tgammal

指定した値のガンマ関数を決定します。

## <a name="syntax"></a>構文

```C
double tgamma(
   double x
);

float tgamma(
   float x
); //C++ only

long double tgamma(
   long double x
); //C++ only

float tgammaf(
   float x
);

long double tgammal(
   long double x
);
```

### <a name="parameters"></a>パラメーター

*X*<br/>
ガンマを検索する値。

## <a name="return-value"></a>戻り値

成功した場合は、 *x*のガンマを返します。

*x*の大きさがデータ型に対して大きすぎるか小さすぎる場合は、範囲エラーが発生することがあります。 *x* <= 0 の場合、ドメイン エラーまたは範囲エラーが発生することがあります。

|問題|戻り値|
|-----------|------------|
|x = ±0|±無限大|
|x = 負の整数|(NaN)|
|x = -無限大|(NaN)|
|x = +INFINITY|+INFINITY|
|x = NaN|(NaN)|
|ドメイン エラー|(NaN)|
|極エラー|±HUGE_VAL、±HUGE_VALF、±HUGE_VALL|
|オーバーフロー範囲エラー|±HUGE_VAL、±HUGE_VALF、±HUGE_VALL|
|アンダーフロー範囲エラー|丸めた後の正確な値。|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能なため **、float**型と**長倍****double**精度浮動小数点型を取得および戻す**tgamma**のオーバーロードを呼び出すことができます。 C プログラムでは **、tgamma**は常に二**重**を取り、返します。

x が自然数の場合、この関数は (x-1) の階乗を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**tgamma**,**ガンマフ**,**ガンマル**|\<math.h>|\<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[lgamma、lgammaf、lgammal](lgamma-lgammaf-lgammal.md)<br/>
