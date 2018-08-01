---
title: acosh、acoshf、acoshl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- acoshf
- acosh
- acoshl
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
- acosh
- acoshf
- acoshl
- math/acosh
- math/acoshf
- math/acoshl
dev_langs:
- C++
helpviewer_keywords:
- acoshf function
- acosh function
- acoshl function
ms.assetid: 6985c4d7-9e2a-44ce-9a9b-5a43015f15f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 546006fcf1c559317b4afff424976db8109442e7
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404753"
---
# <a name="acosh-acoshf-acoshl"></a>acosh、acoshf、acoshl

逆ハイパーボリック コサインを計算します。

## <a name="syntax"></a>構文

```C
double acosh( double x );
float acoshf( float x );
long double acoshl( long double x );
```

```cpp
float acosh( float x );  // C++ only
long double acosh( long double x );  // C++ only
```

### <a name="parameters"></a>パラメーター

*x*  
浮動小数点値。

## <a name="return-value"></a>戻り値

**Acosh**関数の逆ハイパーボリック コサイン (アーク ハイパーボリック コサイン) を返す*x*します。 ドメイン上でこれらの関数は有効な*x* ≥ 1。 場合*x*が 1 より小さい、`errno`に設定されている`EDOM`され、結果は簡易な NaN です。 場合*x*は簡易な NaN、不定値、または無限大の場合、同じ値が返されます。

|入力|SEH 例外|`_matherr` 例外|
|-----------|-------------------|--------------------------|
|± QNAN、IND、INF|none|none|
|*x* < 1|none|none|

## <a name="remarks"></a>Remarks

C++ を使用する場合のオーバー ロードを呼び出すことができます**acosh**を受け取って返す**float**または**長い****二重**値。 C プログラムで**acosh**は**二重**します。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**acosh**、 **acoshf**、 **acoshl**|\<math.h>|\<cmath>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_acosh.c
// Compile by using: cl /W4 crt_acosh.c
// This program displays the hyperbolic cosine of pi / 4
// and the arc hyperbolic cosine of the result.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x, y;

   x = cosh( pi / 4 );
   y = acosh( x );
   printf( "cosh( %f ) = %f\n", pi/4, x );
   printf( "acosh( %f ) = %f\n", x, y );
}
```

```Output
cosh( 0.785398 ) = 1.324609
acosh( 1.324609 ) = 0.785398
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)  
[asinh、asinhf、asinhl](asinh-asinhf-asinhl.md)  
[atanh、atanhf、atanhl](atanh-atanhf-atanhl.md)  
[cosh、coshf、coshl](cosh-coshf-coshl.md)  
[sinh、sinhf、sinhl](sinh-sinhf-sinhl.md)  
[tanh、tanhf、tanhl](tanh-tanhf-tanhl.md)  