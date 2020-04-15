---
title: modf、modff、modfl
ms.date: 4/2/2020
api_name:
- modff
- modf
- modfl
- _o_modf
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
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
ms.openlocfilehash: b509da5f18ea1f606b8a3b47ab66a78e4f595558
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338695"
---
# <a name="modf-modff-modfl"></a>modf、modff、modfl

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

*X*<br/>
浮動小数点値。

*Intptr*<br/>
格納された整数部分へのポインター。

## <a name="return-value"></a>戻り値

この関数は *x* の符号付き小数部を返します。 エラーの戻り値はありません。

## <a name="remarks"></a>解説

**modf**関数は浮動小数点値*x*を小数部と整数部分に分解し、各部分は*x*と同じ符号を持ちます。 *x*の符号付き小数部が返されます。 整数部分は*intptr*で浮動小数点値として格納されます。

**modf**はストリーミング SIMD 拡張 2 (SSE2) を使用する実装を持っています。 SSE2 実装の使い方の詳細および制約については、「[_set_SSE2_enable](set-sse2-enable.md)」をご覧ください。

C++ ではオーバーロードが可能なので **、float**または**long** **double**パラメータを受け取って返す**modf**のオーバーロードを呼び出すことができます。 C プログラムでは **、modf**は常に 2 つの倍精度値を受け取り、倍精度浮動小数点値を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**モドフ**、**モドフ**、**モドフル**|C: \<math.h><br /><br /> C++: \<cmath> または \<math.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
