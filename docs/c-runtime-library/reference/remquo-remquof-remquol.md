---
title: remquo、remquof、remquol
ms.date: 04/05/2018
apiname:
- remquof
- remquo
- remquol
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
- remquof
- remquol
- remquo
helpviewer_keywords:
- remquol function
- remquof function
- remquo function
ms.assetid: a1d3cb8b-8027-4cd3-8deb-04eb17f299fc
ms.openlocfilehash: 4c7e93806600ff674baf186a66662aafdeceeaca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357552"
---
# <a name="remquo-remquof-remquol"></a>remquo、remquof、remquol

2 個の整数値の剰余を計算し、パラメーターに指定された位置に、整数値を符号と商の近似値と共に格納します。

## <a name="syntax"></a>構文

```C
double remquo( double numer, double denom, int* quo );
float remquof( float numer, float denom, int* quo );
long double remquol( long double numer, long double denom, int* quo );
```

```cpp
float remquo( float numer, float denom, int* quo ); /* C++ only */
long double remquo( long double numer, long double denom, int* quo ); /* C++ only */
```

### <a name="parameters"></a>パラメーター

*数値*<br/>
分子。

*denom*<br/>
分母。

*quo*<br/>
符号と商の近似値を持つ値を格納する整数へのポインター。

## <a name="return-value"></a>戻り値

**remquo**の浮動小数点の剰余を返します*x* / *y*します。 場合の値*y* 0.0、 **remquo**簡易な NaN を返します。 による簡易な NaN の表現については、 **printf**ファミリを参照してください[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)します。

## <a name="remarks"></a>Remarks

**Remquo**関数は浮動小数点の剰余を計算*f*の*x* / *y*ように*x*  = *は* \* *y* + *f*ここで、*は*整数、 *f*と同じ符号*x*、との絶対値*f*がの絶対値より小さい*y*します。

C++ では、オーバー ロードのオーバー ロードを呼び出すことができますので**remquo**を受け取って返す**float**または**長い****二重**値。 C プログラムで**remquo**常に 2 つ受け取る**二重**引数を返す、**二重**。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー (C)|必須ヘッダー (C++)|
|--------------|---------------------|-|
|**remquo**、 **remquof**、 **remquol**|\<math.h>|\<cmath> または \<math.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_remquo.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;
   int quo = 0;

   z = remquo(w, x, &quo);
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);
   printf("Approximate signed quotient is %d\n", quo);
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
Approximate signed quotient is -3
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv、lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod、fmodf](fmod-fmodf.md)<br/>
[remainder、remainderf、remainderl](remainder-remainderf-remainderl.md)<br/>
