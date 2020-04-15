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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 4b70d3175a125d72ff67710c83899c44dbf72015
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332865"
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

*X*<br/>
分子。

*Y*<br/>
分母。

## <a name="return-value"></a>戻り値

*x* / *y*の浮動小数点の剰余。 *y*の値が 0.0 の場合、**残りは**静止 NaN を返します。 printf ファミリによる静かな NaN の表現については[、「printf、_printf_l、wprintf、_wprintf_l」](printf-printf-l-wprintf-wprintf-l.md)を参照してください。 **printf**

## <a name="remarks"></a>解説

**剰余**関数は*x* /  *x* / *x* / *y*の浮動小数点剰余*r*を計算し *、x* = *n* \* *y* + *r*、n x y &#124; = 1/2 &#124;*n* - 場合でも n が x*y に*最も近い*整数である。* *n**y* *r* = 0 の場合 *、r*は x と同じ符号を*持*つ。

C++ ではオーバーロードが可能なため **、float**値または**長倍**精度浮動小数点値を取得して返す**剰余**のオーバーロード**を**呼び出すことができます。 C プログラムでは、**剰余**は常に 2 つの**二重**引数を取り、**倍精度浮動小数点数**を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー (C)|必須ヘッダー (C++)|
|--------------|---------------------|-|
|**剰余**,**剰余 ,****剰余**|\<math.h>|\<cmath> または \<math.h>|

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

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv、lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod、fmodf](fmod-fmodf.md)<br/>
[remquo、remquof、remquol](remquo-remquof-remquol.md)<br/>
