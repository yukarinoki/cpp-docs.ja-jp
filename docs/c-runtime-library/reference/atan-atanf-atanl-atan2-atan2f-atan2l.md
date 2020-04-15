---
title: atan、atanf、atanl、atan2、atan2f、atan2l
ms.date: 4/2/2020
api_name:
- atan2f
- atan2l
- atan2
- atanf
- atan
- atanl
- _o_atan
- _o_atan2
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
- atan
- atan2l
- atan2
- atanl
- atanf
- atan2f
helpviewer_keywords:
- atan function
- atanf function
- atanl function
- atan2 function
- atan2l function
- arctangent function
- trigonometric functions
- atan2f function
ms.assetid: 7a87a18e-c94d-4727-9cb1-1bb5c2725ae4
ms.openlocfilehash: 3b8411f9839022477dff3100792e271e2f0b572b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81334117"
---
# <a name="atan-atanf-atanl-atan2-atan2f-atan2l"></a>atan、atanf、atanl、atan2、atan2f、atan2l

**x** (**atan**、 **atanf**、 **atanl 、 atanl**) のアークタンジェントまたは**y**/**x** ( atan2 、**atan2f**、および**atan2l**) のアークタンジェントを計算します。 **atan2f**

## <a name="syntax"></a>構文

```C
double atan( double x );
float atanf( float x );
long double atanl( long double x );

double atan2( double y, double x );
float atan2f( float y, float x );
long double atan2l( long double y, long double x );
```

```cpp
float atan( float x );  // C++ only
long double atan( long double x );  // C++ only

float atan2( float y, float x );  // C++ only
long double atan2( long double y, long double x );  // C++ only
```

### <a name="parameters"></a>パラメーター

*x*, *y*<br/>
任意の数値。

## <a name="return-value"></a>戻り値

**atan は**、-π/2 から π/2 ラジアンの範囲で*x*のアークタンジェントを返します。 **atan2 は**、-π から π ラジアンまでの範囲の*y*/*x*のアークタンジェントを返します。 *x*が 0 の場合 **、atan は**0 を返します。 **atan2**の両方のパラメーターが 0 の場合、関数は 0 を返します。 すべての結果はラジアンにあります。

**atan2**は両方のパラメータの符号を使用して、戻り値の象限を決定します。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± **QNAN,IND** **IND**|none|**_DOMAIN**|

## <a name="remarks"></a>解説

**atan**関数は x のアークタンジェント (逆正接関数)*を計算*します。 **atan2**は*y*/*x*のアークタンジェントを計算します *(x*が 0 の場合 *、y*が正の場合は π/2、y が負の場合は -π/2、y が 0 の場合は 0 を返します)。 **atan2** *y* *y*

**atan**には、ストリーミング SIMD 拡張 2 (SSE2) を使用する実装があります。 SSE2 実装の使い方の詳細および制約については、「[_set_SSE2_enable](set-sse2-enable.md)」を参照してください。

C++ ではオーバーロードが可能なため **、float**引数または**長い****二重**引数を受け取る**atan**および**atan2**のオーバーロードを呼び出すことができます。 C プログラムでは **、atan**と**atan2**は常に**二重**引数を取り、**倍精度浮動小数点数**を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------|-|
|**アタン**,**アタン2**,**アタンフ**, **atan2f**,**アタンル**, **atan2l**|\<math.h>|\<cmath> または \<math.h>|

## <a name="example"></a>例

```C
// crt_atan.c
// arguments: 5 0.5
#include <math.h>
#include <stdio.h>
#include <errno.h>

int main( int ac, char* av[] )
{
   double x, y, theta;
   if( ac != 3 ){
      fprintf( stderr, "Usage: %s <x> <y>\n", av[0] );
      return 1;
   }
   x = atof( av[1] );
   theta = atan( x );
   printf( "Arctangent of %f: %f\n", x, theta );
   y = atof( av[2] );
   theta = atan2( y, x );
   printf( "Arctangent of %f / %f: %f\n", y, x, theta );
   return 0;
}
```

```Output
Arctangent of 5.000000: 1.373401
Arctangent of 0.500000 / 5.000000: 0.099669
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[acos、acosf、acosl](acos-acosf-acosl.md)<br/>
[asin、asinf、asinl](asin-asinf-asinl.md)<br/>
[cos、cosf、cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin、sinf、sinl](sin-sinf-sinl.md)<br/>
[tan、tanf、tanl](tan-tanf-tanl.md)<br/>
[_CIatan](../../c-runtime-library/ciatan.md)<br/>
[_CIatan2](../../c-runtime-library/ciatan2.md)<br/>
