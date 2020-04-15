---
title: asinh、asinhf、asinhl
ms.date: 4/2/2020
api_name:
- asinh
- asinhf
- asinhl
- _o_asinh
- _o_asinhf
- _o_asinhl
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
- asinhf
- asinhl
- asinh
helpviewer_keywords:
- asinh function
- asinhl function
- asinhf function
ms.assetid: 4488babe-1a7e-44ca-8b7b-c2db0a70084f
ms.openlocfilehash: 299ee0ff3014dcfd2f6ab712d01766119fab5894
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350468"
---
# <a name="asinh-asinhf-asinhl"></a>asinh、asinhf、asinhl

逆ハイパーボリック サインを計算します。

## <a name="syntax"></a>構文

```C
double asinh( double x );
float asinhf( float x );
long double asinhl( long double x );
```

```cpp
float asinh( float x );  // C++ only
long double asinh( long double x );  // C++ only
```

### <a name="parameters"></a>パラメーター

*X*<br/>
浮動小数点値。

## <a name="return-value"></a>戻り値

**asinh**関数は*x*の逆ハイベルボリックサイン (アーク双曲線正弦) を返します。 この関数は浮動小数点ドメインで有効です。 *x*が静かな NaN、無期限、または無限大の場合は、同じ値が返されます。

|入力|SEH 例外|**_matherr**例外|
|-----------|-------------------|--------------------------|
|± QNAN、IND、INF|none|none|

## <a name="remarks"></a>解説

C++ を使用すると **、float**または**long** **double**値を受け取って返す**asinh**のオーバーロードを呼び出すことができます。 C プログラムでは **、asinh は**常に二**重**を取り、返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須の C ヘッダー|必須の C++ ヘッダー|
|--------------|--------------|------------------|
|**アシン**,**アシンフ**,**アシンル**|\<math.h>|\<cmath>\<または数学.h<|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_asinh.c
// Compile by using: cl /W4 crt_asinh.c
// This program displays the hyperbolic sine of pi / 4
// and the arc hyperbolic sine of the result.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x, y;

   x = sinh( pi / 4 );
   y = asinh( x );
   printf( "sinh( %f ) = %f\n", pi/4, x );
   printf( "asinh( %f ) = %f\n", x, y );
}
```

```Output
sinh( 0.785398 ) = 0.868671
asinh( 0.868671 ) = 0.785398
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[acosh、acoshf、acoshl](acosh-acoshf-acoshl.md)<br/>
[atanh、atanhf、atanhl](atanh-atanhf-atanhl.md)<br/>
[cosh、coshf、coshl](cosh-coshf-coshl.md)<br/>
[sinh、sinhf、sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh、tanhf、tanhl](tanh-tanhf-tanhl.md)<br/>
