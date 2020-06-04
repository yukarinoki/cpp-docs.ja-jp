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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: a610b0412b7e10949a810f4e360686292cff9ee3
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916441"
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

*x*<br/>
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
|オーバーフロー範囲エラー|± HUGE_VAL、± HUGE_VALF、または± HUGE_VALL|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、 **float**型および**long** **double**型を受け取って返す**lgamma**のオーバーロードを呼び出すことができます。 C プログラムでは、 **lgamma**は常に**倍精度浮動小数点数**を取得し、double を返します。

X が有理数の場合、この関数は (x-1) の階乗の対数を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**lgamma**、 **lgammaf**、 **lgammal**|\<math.h>|\<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[tgamma、tgammaf、tgammal](tgamma-tgammaf-tgammal.md)<br/>
