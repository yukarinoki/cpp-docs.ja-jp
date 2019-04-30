---
title: atan、atanf、atanl、atan2、atan2f、atan2l
ms.date: 04/05/2018
apiname:
- atan2f
- atan2l
- atan2
- atanf
- atan
- atanl
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
ms.openlocfilehash: 59a67b0d213a11630f551fd7582b44aab60e314f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341718"
---
# <a name="atan-atanf-atanl-atan2-atan2f-atan2l"></a>atan、atanf、atanl、atan2、atan2f、atan2l

アーク タンジェントを計算**x** (**atan**、 **atanf**、および**atanl**) のアーク タンジェントまたは**y** /**x** (**atan2**、 **atan2f**、および**atan2l**)。

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

*x*、 *y*<br/>
任意の数値。

## <a name="return-value"></a>戻り値

**atan**のアーク タンジェントを返します*x* π/2 ラジアンの範囲 - π/2 でします。 **atan2**のアーク タンジェントを返します*y*/*x*範囲 π ~ π ラジアンにします。 場合*x*は 0 です。 **atan** 0 を返します。 場合の両方のパラメーター **atan2** 0、0 を返します。 すべての結果はラジアンにあります。

**atan2**の両方のパラメーターの符号を使用して、戻り値のクアドラントを判断します。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± **QNAN**、 **IND**|none|**_DOMAIN**|

## <a name="remarks"></a>Remarks

**Atan**関数のアーク タンジェント (逆タンジェント関数) を計算する*x*します。 **atan2**のアーク タンジェントを計算*y*/*x* (場合*x* 0 に等しい**atan2** π/2 を返します*y*が正の値、- π/2 の場合*y* 、負の値または 0 の場合は、 *y*は 0 です)。

**atan**ストリーミング SIMD 拡張命令 2 (SSE2) を使用して実装されています。 SSE2 実装の使い方の詳細および制約については、「[_set_SSE2_enable](set-sse2-enable.md)」をご覧ください。

オーバー ロードを呼び出すことができますので、C++ ではオーバー ロード、 **atan**と**atan2**を受け取る**float**または**長い** **double**引数。 C プログラムで**atan**と**atan2**常に**二重**引数と戻り値、**二重**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------|-|
|**atan**、 **atan2**、 **atanf**、 **atan2f**、 **atanl**、 **atan2l**|\<math.h>|\<cmath> または \<math.h>|

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
