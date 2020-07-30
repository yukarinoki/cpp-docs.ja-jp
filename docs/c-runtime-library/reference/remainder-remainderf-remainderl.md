---
title: remainder、remainderf、remainderl
ms.date: 4/2/2020
api_name:
- remainderl
- remainder
- remainderf
- _o_remainder
- _o_remainderf
- _o_remainderl
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
- remainderf
- remainder
- remainderl
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
ms.openlocfilehash: b880054430574b6ea1e8bc456774acc35cf116ad
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216805"
---
# <a name="remainder-remainderf-remainderl"></a>remainder、remainderf、remainderl

2 つの浮動小数点値の商の剰余を最も近い整数値に丸めて計算します。

## <a name="syntax"></a>構文

```C
double remainder( double x, double y );
float remainderf( float x, float y );
long double remainderl( long double x, long double y );
```

```cpp
float remainder( float x, float y ); /* C++ only */
long double remainder( long double x, long double y ); /* C++ only */
```

### <a name="parameters"></a>パラメーター

*x*<br/>
分子。

*y*<br/>
分母。

## <a name="return-value"></a>戻り値

*X*y の浮動小数点の剰余  /  *y*。 *Y*の値が0.0 の場合、**剰余**は簡易な NaN を返します。 **Printf**ファミリによる簡易な NaN の表現については、「 [printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)」を参照してください。

## <a name="remarks"></a>解説

**剰余**関数は x y*の浮動小数点の剰余* *r*を計算します。  /  *y* *x*  =  *n* \* *y*  +  *r*ここで、 *n*は x y の値に最も近い*x*整数、n は  /  *y* &#124; *n* *n*  -  *x*  /  *y* &#124; = 1/2 になるたびに n になります。 *R* = 0 の場合、 *r*は*x*と同じ符号を持ちます。

C++ ではオーバーロードが可能であるため、またはの値を受け取って返す**剰余**のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、**剰余**は常に2つの引数を受け取り、を **`double`** 返し **`double`** ます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー (C)|必須ヘッダー (C++)|
|--------------|---------------------|-|
|**残り、残りの部分**は **、** 残って**います。**|\<math.h>|\<cmath> または \<math.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_remainder.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;

   z = remainder(w, x);
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
```

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv、lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod、fmodf](fmod-fmodf.md)<br/>
[remquo、remquof、remquol](remquo-remquof-remquol.md)<br/>
