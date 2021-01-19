---
title: atan、atanf、atanl、atan2、atan2f、atan2l
description: Atan、atanf、atanl、atan2、atan2f、および atan2l の API リファレンス浮動小数点値のアークタンジェントを計算する。
ms.date: 1/15/2021
api_name:
- atan2f
- atan2l
- atan2
- atanf
- atan
- atanl
- _o_atan
- _o_atan2
- _o_atan2f
- _o_atanf
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
ms.openlocfilehash: bbfc08507bd48e1b9eb0b91350b2b39948d19a5f
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564070"
---
# <a name="atan-atanf-atanl-atan2-atan2f-atan2l"></a>`atan`, `atanf`, `atanl`, `atan2`, `atan2f`, `atan2l`

(、、および) のアークタンジェント、 **`x`** **`atan`** **`atanf`** **`atanl`** または **`y`** / **`x`** ( **`atan2`** 、 **`atan2f`** 、および **`atan2l`** ) のアークタンジェントを計算します。

## <a name="syntax"></a>構文

```C
double atan( double x );
float atanf( float x );
long double atanl( long double x );
#define atan(X) // Requires C11 or higher

float atan( float x );  // C++ only
long double atan( long double x );  // C++ only

double atan2( double y, double x );
float atan2f( float y, float x );
long double atan2l( long double y, long double x );
#define atan2(Y, X) // Requires C11 or higher

float atan2( float y, float x );  // C++ only
long double atan2( long double y, long double x );  // C++ only
```

### <a name="parameters"></a>パラメーター

*`x`*, *`y`*\
任意の数値。

## <a name="return-value"></a>戻り値

**`atan`***`x`*-π/2 ~ π/2 ラジアンの範囲ののアークタンジェントを返します。 **`atan2`***`y`* / *`x`* -π ~ πラジアンの範囲ののアークタンジェントを返します。 *`x`* が0の場合、は **`atan`** 0 を返します。 の両方のパラメーター **`atan2`** が0の場合、この関数は0を返します。 すべての結果はラジアンにあります。

**`atan2`** は、両方のパラメーターの符号を使用して、戻り値のクアドラントを決定します。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± **`QNAN`**, **`IND`**|なし|**`_DOMAIN`**|

## <a name="remarks"></a>注釈

関数は、 **`atan`** のアークタンジェント (逆タンジェント関数) を計算し *`x`* ます。 **`atan2`** のアークタンジェントを計算します (が0の場合は *`y`* / *`x`* *`x`* **`atan2`** π/2 を返します。が負の場合はπ/2、が負の場合は-π/2、が0の場合 *`y`* は0を返し *`y`* *`y`* ます)。

`<tgmath.h>` `atan()` マクロまたはマクロを使用する場合 `atan2()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

**`atan`** には、ストリーミング SIMD 拡張命令 2 (SSE2) を使用する実装があります。 SSE2 実装の使用に関する情報と制限については、「」を参照してください [`_set_SSE2_enable`](set-sse2-enable.md) 。

C++ ではオーバーロードが可能であるため、 **`atan`** **`atan2`** または引数を受け取るおよびのオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 `<tgmath.h>` **`atan`** **`atan2`** は常に引数を受け取り、 **`double`** を返し **`double`** ます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------|-|
|**`atan`**, **`atan2`**, **`atanf`**, **`atan2f`**, **`atanl`**, **`atan2l`**|`<math.h>`|`<cmath>` または `<math.h>`|
|**`atan()`**、 **`atan2`** マクロ | `<tgmath.h>` ||

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

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)\
[`acos`, `acosf`, `acosl`](acos-acosf-acosl.md)\
[`asin`, `asinf`, `asinl`](asin-asinf-asinl.md)\
[`cos`, `cosf`, `cosl`](cos-cosf-cosl.md)\
[`_matherr`](matherr.md)\
[`sin`, `sinf`, `sinl`](sin-sinf-sinl.md)\
[`tan`, `tanf`, `tanl`](tan-tanf-tanl.md)\
[`_CIatan`](../../c-runtime-library/ciatan.md)\
[`_CIatan2`](../../c-runtime-library/ciatan2.md)