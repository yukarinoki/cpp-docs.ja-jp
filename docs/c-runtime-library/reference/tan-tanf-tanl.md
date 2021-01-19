---
title: tan、tanf、tanl
description: Tan、tanf、および tanl の API リファレンス浮動小数点値のタンジェントを計算する。
ms.date: 1/15/2021
api_name:
- tan
- tanf
- tanl
- _o_tan
- _o_tanf
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
ms.openlocfilehash: 056afdf0bbac422c498bd54c2a154472bfd97c34
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564057"
---
# <a name="tan-tanf-tanl"></a>`tan`, `tanf`, `tanl`

タンジェントを計算します。

## <a name="syntax"></a>構文

```C
double tan( double x );
float tanf( float x );
long double tanl( long double x );
#define tan(x) // Requires C11 or higher
```

```cpp
float tan( float x );  // C++ only
long double tan( long double x );  // C++ only
```

### <a name="parameters"></a>パラメーター

*`x`*\
角度 (ラジアン)。

## <a name="return-value"></a>戻り値

関数は、 **`tan`** のタンジェントを返し *`x`* ます。 *`x`* が263以上、または-263 以下の場合は、結果の有意性が失われます。

|入力|SEH 例外|**`Matherr`** 例外的|
|-----------|-------------------|-------------------------|
|`± QNAN`,`IND`|なし|`_DOMAIN`|
|`± INF`|**無効です**|`_DOMAIN`|

## <a name="remarks"></a>注釈

C++ ではオーバーロードが可能であるため、 **`tan`** またはの値を受け取って返すのオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、 `<tgmath.h>` この関数を呼び出すためにマクロを使用している場合を除き、は **`tan`** 常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 `<tgmath.h>` `tan()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------|-|
|**`tan`**, **`tanf`**, **`tanl`**|`<math.h>`|`<cmath>` または `<math.h>`|
|**`tan()`** マクロ | `<tgmath.h>` ||

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

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

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)\
[`acos, acosf, acosl`](acos-acosf-acosl.md)\
[`asin, asinf, asinl`](asin-asinf-asinl.md)\
[`atan, atanf, atanl, atan2, atan2f, atan2l`](atan-atanf-atanl-atan2-atan2f-atan2l.md)\
[`cos, cosf, cosl`](cos-cosf-cosl.md)\
[`sin, sinf, sinl`](sin-sinf-sinl.md)\
[`_CItan`](../../c-runtime-library/citan.md)