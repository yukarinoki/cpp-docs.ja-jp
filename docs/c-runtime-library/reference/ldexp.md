---
title: ldexp、ldexpf、ldexpl
ms.date: 4/2/2020
api_name:
- ldexp
- ldexpf
- ldexpl
- _ldexpl
- _o_ldexp
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
- ldexp
- ldexpf
- ldexpl
- _ldexpl
helpviewer_keywords:
- calculating real numbers
- computing real numbers
- mantissas, floating-point variables
- ldexp function
- ldexpf function
- ldexpl function
- exponent, floating-point numbers
- floating-point functions, mantissa and exponent
ms.assetid: aa7f5310-3879-4f63-ae74-86a39fbdedfa
ms.openlocfilehash: bbd1742cdace30d5bc3bd5e9d592bb24a86f917f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216922"
---
# <a name="ldexp-ldexpf-ldexpl"></a>ldexp、ldexpf、ldexpl

浮動小数点数に整数である 2 の累乗を乗算します。

## <a name="syntax"></a>構文

```C
double ldexp(
   double x,
   int exp
);
float ldexp(
   float x,
   int exp
);  // C++ only
long double ldexp(
   long double x,
   int exp
);  // C++ only
float ldexpf(
   float x,
   int exp
);
long double ldexpl(
   long double x,
   int exp
);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
浮動小数点値。

*exp*<br/>
整数の指数。

## <a name="return-value"></a>戻り値

**Ldexp**関数は、 *x* \* 成功した場合、x 2<sup>*exp*</sup>の値を返します。 オーバーフローでは、 *x*の符号によっては、 **ldexp**は +/- **HUGE_VAL**; を返します。**errno**値は**ERANGE**に設定されます。

**Errno**および考えられるエラーの戻り値の詳細については、「 [errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、または型を受け取る**ldexp**のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、 **ldexp**は常にとを受け取り、を **`double`** **`int`** 返し **`double`** ます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**ldexp**、 **ldexp**、 **ldexp**|\<math.h>|\<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_ldexp.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 4.0, y;
   int p = 3;

   y = ldexp( x, p );
   printf( "%2.1f times two to the power of %d is %2.1f\n", x, p, y );
}
```

## <a name="output"></a>出力

```Output
4.0 times two to the power of 3 is 32.0
```

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[modf、modff、modfl](modf-modff-modfl.md)<br/>
