---
title: sinh、sinhf、sinhl
description: 浮動小数点値のハイパーボリックサインを計算するための API リファレンスです。
ms.date: 08/31/2020
api_name:
- sinh
- sinhl
- sinhf
- sinhl
- _o_sinh
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
- sinh
- sinhf
- sinhl
helpviewer_keywords:
- sinh function
- sinhl function
- sinhf function
- calculating hyperbolic sines
- trigonometric functions
- sinhf function
- sinhl function
- hyperbolic functions
ms.openlocfilehash: 6a8c9c4195eab66a46230e7a3baf6194e17c4519
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556178"
---
# <a name="sinh-sinhf-sinhl"></a>sinh、sinhf、sinhl

ハイパーボリックサインを計算します。

## <a name="syntax"></a>構文

```C
double sinh(double x);
float sinhf(float x);
long double sinhl(long double x);
#define sinh(x) // Requires C11 or higher

float sinh(float x);  // C++ only
long double sinh(long double x);  // C++ only
```

### <a name="parameters"></a>パラメーター

*閉じる*\
角度 (ラジアン)。

## <a name="return-value"></a>戻り値

**Sinh**関数は、 *x*のハイパーボリックサインを返します。 既定では、結果が大きすぎる場合、 **sinh** は **errno** を **ERANGE** に設定し、±**HUGE_VAL**を返します。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± QNAN、IND|なし|_DOMAIN|
|&#124;x&#124; ≥ 7.104760 e + 002|OVERFLOW+INEXACT|OVERFLOW|

リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、またはの値を受け取って返す **sinh** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き \<tgmath.h> 、 **sinh** は常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `sinh()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-|-|-|
|**sinh**、 **sinhf**、 **sinhf**|\<math.h>|\<cmath> または \<math.h>|
|**sinh ()** マクロ | \<tgmath.h> ||

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_sinhcosh.c
// This program displays the hyperbolic
// sine and hyperbolic cosine of pi / 2.
// Compile by using: cl /W4 crt_sinhcosh.c

#include <math.h>
#include <stdio.h>

int main( void)
{
   double pi = 3.1415926535;
   double x, y;

   x = pi / 2;
   y = sinh( x );
   printf( "sinh( %f ) = %f\n",x, y );
   y = cosh( x );
   printf( "cosh( %f ) = %f\n",x, y );
}
```

```Output
sinh( 1.570796 ) = 2.301299
cosh( 1.570796 ) = 2.509178
```

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[acosh、acoshf、acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh、asinhf、asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh、atanhf、atanhl](atanh-atanhf-atanhl.md)<br/>
[cosh、coshf、coshl](cosh-coshf-coshl.md)<br/>
[tanh、tanhf、tanhl](tanh-tanhf-tanhl.md)<br/>
