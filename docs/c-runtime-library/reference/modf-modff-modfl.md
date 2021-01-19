---
title: modf、modff、modfl
description: Modf、modff、および modff の API リファレンス浮動小数点値を小数部と整数部に分割します。
ms.date: 1/15/2021
api_name:
- modff
- modf
- modfl
- _o_modf
- _o_modff
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
- modff
- _modfl
- modf
- modfl
- math/modf
- math/modff
- math/modfl
helpviewer_keywords:
- modf function
- modff function
- modfl function
ms.openlocfilehash: fbc68c3369e8b992350534e3baa5f19b0f2a5e39
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564019"
---
# <a name="modf-modff-modfl"></a>`modf`, `modff`, `modfl`

浮動小数点値を小数部と整数部に分割します。

## <a name="syntax"></a>構文

```C
double modf( double x, double * intptr );
float modff( float x, float * intptr );
long double modfl( long double x, long double * intptr );
```

```cpp
float modf( float x, float * intptr );  // C++ only
long double modf( long double x, long double * intptr );  // C++ only
```

### <a name="parameters"></a>パラメーター

*`x`*\
浮動小数点値。

*`intptr`*\
格納された整数部分へのポインター。

## <a name="return-value"></a>戻り値

この関数は、の符号付き小数部を返し *`x`* ます。 エラーの戻り値はありません。

## <a name="remarks"></a>注釈

**Modf** 関数は、浮動小数点値を *`x`* 小数部と整数部に分割します。それぞれの符号はと同じ *`x`* です。 の符号付き小数部分 *`x`* が返されます。 整数部分は、に浮動小数点値として格納され *`intptr`* ます。

**modf** には、ストリーミング SIMD 拡張命令 2 (SSE2) を使用する実装があります。 [`_set_SSE2_enable`](set-sse2-enable.md)SSE2 実装の使用に関する情報と制限については、「」を参照してください。

C++ ではオーバーロードが可能であるため、 **`modf`** またはパラメーターを受け取って返すのオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、は **`modf`** 常に2つの double 値を受け取り、double 値を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**`modf`**, **`modff`**, **`modfl`**|40u-c `<math.h>`<br /><br /> C++:、 `<cmath>` または `<math.h>`|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_modf.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x, y, n;

   x = -14.87654321;      /* Divide x into its fractional */
   y = modf( x, &n );     /* and integer parts            */

   printf( "For %f, the fraction is %f and the integer is %.f\n",
           x, y, n );
}
```

```Output
For -14.876543, the fraction is -0.876543 and the integer is -14
```

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)\
[`frexp`](frexp.md)\
[`ldexp`](ldexp.md)