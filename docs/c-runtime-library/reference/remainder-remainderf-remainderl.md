---
title: remainder、remainderf、remainderl
ms.date: 04/05/2018
apiname:
- remainderl
- remainder
- remainderf
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
- remainderf
- remainder
- remainderl
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
ms.openlocfilehash: 9a9abe82e69122ca87f44e293e1da725c97045d4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357643"
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

浮動小数点の剰余*x* / *y*します。 場合の値*y* 0.0、**剰余**簡易な NaN を返します。 による簡易な NaN の表現については、 **printf**ファミリを参照してください[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)します。

## <a name="remarks"></a>Remarks

**剰余**関数は浮動小数点の剰余を計算*r*の*x* / *y*ように*x*  =  *n* \* *y* + *r*ここで、 *n*が、値を最も近い整数*x* / *y*と*n*偶数たびに&#124; *n*  - *x* / *y* &#124; = 1/2。 ときに*r* = 0、 *r*と同じ符号*x*します。

オーバー ロードを呼び出すことができますので、C++ ではオーバー ロード、**剰余**を受け取って返す**float**または**長い** **二重**値。 C プログラムで**剰余**常に 2 つは、**二重**引数を返す、**二重**。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー (C)|必須ヘッダー (C++)|
|--------------|---------------------|-|
|**残りの部分**、 **remainderf**、 **remainderl**|\<math.h>|\<cmath> または \<math.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
