---
title: tanh、tanhf、tanhl
description: Tanh、tanhf、および tanhl の API リファレンス浮動小数点値のハイパーボリックタンジェントを計算する。
ms.date: 1/15/2021
api_name:
- tanh
- tanhf
- tanhl
- _o_tanh
- _o_tanhf
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
- tanh
- tanhf
- tanhl
- _tanhl
helpviewer_keywords:
- tanhl function
- _tanhl function
- tanh function
- tanhf function
- trigonometric functions
- hyperbolic functions
ms.openlocfilehash: c09655b4a86010ff6a476f7dacbce4f9f73ab3cc
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564122"
---
# <a name="tanh-tanhf-tanhl"></a>`tanh`, `tanhf`, `tanhl`

ハイパーボリックタンジェントを計算します。

## <a name="syntax"></a>構文

```C
double tanh( double x );
float tanhf( float x );
long double tanhl( long double x );
#define tanh(x) // Requires C11 or higher
```

```cpp
float tanh( float x );  // C++ only
long double tanh( long double x );  // C++ only
```

### <a name="parameters"></a>パラメーター

*`x`*\
角度 (ラジアン)。

## <a name="return-value"></a>戻り値

関数は、 **`tanh`** のハイパーボリックタンジェントを返し *`x`* ます。 エラーの戻り値はありません。

|入力|SEH 例外|**`Matherr`** 例外的|
|-----------|-------------------|-------------------------|
|± `QNAN`,`IND`|なし|`_DOMAIN`|

## <a name="remarks"></a>注釈

C++ ではオーバーロードが可能であるため、 **`tanh`** またはの値を受け取って返すのオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、 `<tgmath.h>` この関数を呼び出すためにマクロを使用している場合を除き、は **`tanh`** 常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 `<tgmath.h>` `tanh()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C)|
|-------------|---------------------|-|
|**`tanh`**, **`tanhf`**, **`tanhl`**|`<math.h>`|`<cmath>` または `<math.h>`|
|**`tanh()`** マクロ | `<tgmath.h>` ||

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_tanh.c
// This program displays the tangent of pi / 4
// and the hyperbolic tangent of the result.
// Compile by using: cl crt_tanh.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x, y;

   x = tan( pi / 4 );
   y = tanh( x );
   printf( "tan( %f ) = %f\n", pi/4, x );
   printf( "tanh( %f ) = %f\n", x, y );
}
```

```Output
tan( 0.785398 ) = 1.000000
tanh( 1.000000 ) = 0.761594
```

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)\
[`acosh, acoshf, acoshl`](acosh-acoshf-acoshl.md)\
[`asinh, asinhf, asinhl`](asinh-asinhf-asinhl.md)\
[`atanh, atanhf, atanhl`](atanh-atanhf-atanhl.md)\
[`cosh, coshf, coshl`](cosh-coshf-coshl.md)\
[`sinh, sinhf, sinhl`](sinh-sinhf-sinhl.md)