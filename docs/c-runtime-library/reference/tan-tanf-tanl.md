---
title: tan、tanf、tanl
ms.date: 04/10/2018
apiname:
- tan
- tanf
- tanl
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
- tan
- tanf
- _tanl
- tanl
helpviewer_keywords:
- tanl function
- _tanl function
- tan function
- calculating tangents
- tangent
- tanf function
- trigonometric functions
ms.assetid: 36cc0ce8-9c80-4653-b354-ddb3b378b6bd
ms.openlocfilehash: 79a374142a914e8c2c7cf5c094d443b16e4bce88
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258627"
---
# <a name="tan-tanf-tanl"></a>tan、tanf、tanl

タンジェントを計算します。

## <a name="syntax"></a>構文

```C
double tan( double x );
float tanf( float x );
long double tanl( long double x );
```

```cpp
float tan( float x );  // C++ only
long double tan( long double x );  // C++ only
```

### <a name="parameters"></a>パラメーター

*x*<br/>
角度 (ラジアン)。

## <a name="return-value"></a>戻り値

**Tan**のタンジェントを返します関数*x*します。 場合*x*が 263 以上で、または少ないよりまたは-263 等しくは、結果の有効桁数の損失が発生します。

|入力|SEH 例外|**Matherr**例外|
|-----------|-------------------|-------------------------|
|± QNAN、IND|none|_DOMAIN|
|± INF|**無効です**|_DOMAIN|

## <a name="remarks"></a>Remarks

オーバー ロードを呼び出すことができますので、C++ ではオーバー ロード、 **tan**を受け取って返す**float**または**長い****二重**値。 C プログラムで**tan**は**二重**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------|-|
|**tan**、 **tanf**、 **tanl**|\<math.h>|\<cmath> または \<math.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_tan.c
// This program displays the tangent of pi / 4
// Compile by using: cl crt_tan.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x;

   x = tan( pi / 4 );
   printf( "tan( %f ) = %f\n", pi/4, x );
}
```

```Output
tan( 0.785398 ) = 1.000000
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[acos、acosf、acosl](acos-acosf-acosl.md)<br/>
[asin、asinf、asinl](asin-asinf-asinl.md)<br/>
[atan、atanf、atanl、atan2、atan2f、atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos、cosf、cosl](cos-cosf-cosl.md)<br/>
[sin、sinf、sinl](sin-sinf-sinl.md)<br/>
[_CItan](../../c-runtime-library/citan.md)<br/>