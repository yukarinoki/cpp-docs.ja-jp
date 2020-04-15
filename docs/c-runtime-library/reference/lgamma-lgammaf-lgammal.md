---
title: lgamma、lgammaf、lgammal
ms.date: 4/2/2020
api_name:
- lgamma
- lgammaf
- lgammal
- _o_lgamma
- _o_lgammaf
- _o_lgammal
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
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
ms.openlocfilehash: e2bdfbeac7b995be0b589156437a3ded39114adf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342159"
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma、lgammaf、lgammal

指定した値のガンマ関数の絶対値の自然対数を決定します。

## <a name="syntax"></a>構文

```C
double lgamma( double x );
float lgammaf( float x );
long double lgammal( long double x );
```

```cpp
float lgamma( float x ); //C++ only
long double lgamma( long double x ); //C++ only
```

### <a name="parameters"></a>パラメーター

*X*<br/>
計算される値です。

## <a name="return-value"></a>戻り値

成功した場合は、 *x*のガンマ関数の絶対値の自然対数を返します。

|問題|戻り値|
|-----------|------------|
|*x* = NaN|(NaN)|
|*x* = ±0|+INFINITY|
|*x*= 負の整数|+INFINITY|
|±無限大|+INFINITY|
|極エラー|+HUGE_VAL、+HUGE_VALF、または +HUGE_VALL|
|オーバーフロー範囲エラー|±HUGE_VAL、±HUGE_VALF、±HUGE_VALL|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能なため **、float**型と**長倍****double**精度浮動小数点型を取得および戻す**lgamma**のオーバーロードを呼び出すことができます。 C プログラムでは **、lgamma**は常に**二重**を取り、返します。

x が有理数の場合、この関数は(x - 1)の階乗の対数を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**lγ**, **lgammaf**, **lgammal**|\<math.h>|\<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[tgamma、tgammaf、tgammal](tgamma-tgammaf-tgammal.md)<br/>
