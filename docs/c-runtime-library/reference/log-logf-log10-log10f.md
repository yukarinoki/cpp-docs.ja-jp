---
title: log、logf、logl、log10、log10f、log10l
ms.date: 04/05/2018
apiname:
- log10f
- logf
- log10
- log
- log10l
- logl
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
- logf
- logl
- _log10l
- log
- _logl
- log10f
- log10l
- log10
helpviewer_keywords:
- calculating logarithms
- log10f function
- log10 function
- log function
- log10l function
- logl function
- logf function
- logarithms
ms.assetid: 7adc77c2-04f7-4245-a980-21215563cfae
ms.openlocfilehash: c8e3f73e61fefa7a39a6d53d63739b094d78c499
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543300"
---
# <a name="log-logf-logl-log10-log10f-log10l"></a>log、logf、logl、log10、log10f、log10l

対数を計算します。

## <a name="syntax"></a>構文

```C
double log( double x );
float logf( float x );
long double logl( double x );
double log10( double x );
float log10f ( float x );
long double log10l( double x );
```

```cpp
float log( float x );  // C++ only
long double log( long double x );  // C++ only
float log10( float x );  // C++ only
long double log10( long double x );  // C++ only
```

### <a name="parameters"></a>パラメーター

*x*<br/>
対数を検索する対象の値。

## <a name="return-value"></a>戻り値

**ログ**関数は、自然対数を返します (基本*e*) の*x*成功した場合。 **Log10**関数は、底 10 の対数を返します。 場合*x*が負の場合、これらの関数、不定値 (IND)、既定で返します。 場合*x*が 0 の場合 (INF) の無限大が返されます。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± QNAN、IND|none|_DOMAIN|
|± 0|ZERODIVIDE|_SING|
|*x* < 0|INVALID|_DOMAIN|

**ログ**と**log10**ストリーミング SIMD 拡張命令 2 (SSE2) を使用する実装します。 SSE2 実装の使い方の詳細および制約については、「[_set_SSE2_enable](set-sse2-enable.md)」をご覧ください。

## <a name="remarks"></a>Remarks

C++ では、オーバー ロードのオーバー ロードを呼び出すことができますので**ログ**と**log10**を受け取って返す**float**または**long double**値。 C プログラムで**ログ**と**log10**は、**二重**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**ログ**、 **logf**、 **logl**、 **log10**、 **log10f**、 **log10l**|\<math.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_log.c
/* This program uses log and log10
* to calculate the natural logarithm and
* the base-10 logarithm of 9,000.
*/

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 9000.0;
   double y;

   y = log( x );
   printf( "log( %.2f ) = %f\n", x, y );
   y = log10( x );
   printf( "log10( %.2f ) = %f\n", x, y );
}
```

```Output
log( 9000.00 ) = 9.104980
log10( 9000.00 ) = 3.954243
```

他の底の対数を生成するには、数学的関係を使用します。b を底とする a の対数== 自然対数 (a) / 自然対数 (b)。

```cpp
// logbase.cpp
#include <math.h>
#include <stdio.h>

double logbase(double a, double base)
{
   return log(a) / log(base);
}

int main()
{
   double x = 65536;
   double result;

   result = logbase(x, 2);
   printf("Log base 2 of %lf is %lf\n", x, result);
}
```

```Output
Log base 2 of 65536.000000 is 16.000000
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md) <br/>
[exp、expf、expl](exp-expf.md) <br/>
[_matherr](matherr.md) <br/>
[pow、powf、powl](pow-powf-powl.md) <br/>
[_CIlog](../../c-runtime-library/cilog.md) <br/>
[_CIlog10](../../c-runtime-library/cilog10.md)<br/>
