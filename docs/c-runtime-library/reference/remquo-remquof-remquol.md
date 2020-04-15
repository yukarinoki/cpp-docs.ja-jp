---
title: remquo、remquof、remquol
ms.date: 4/2/2020
api_name:
- remquof
- remquo
- remquol
- _o_remquo
- _o_remquof
- _o_remquol
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
- remquof
- remquol
- remquo
helpviewer_keywords:
- remquol function
- remquof function
- remquo function
ms.assetid: a1d3cb8b-8027-4cd3-8deb-04eb17f299fc
ms.openlocfilehash: e6a6f211e83118379e0697464d21f5968ea68cee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332841"
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

*数字*<br/>
分子。

*デノム*<br/>
分母。

*現状*<br/>
符号と商の近似値を持つ値を格納する整数へのポインター。

## <a name="return-value"></a>戻り値

**remquo は** *x* / *y*の浮動小数点の剰余を返します。 *y*の値が 0.0 の場合 **、remquo は**静止 NaN を返します。 printf ファミリによる静かな NaN の表現については[、「printf、_printf_l、wprintf、_wprintf_l」](printf-printf-l-wprintf-wprintf-l.md)を参照してください。 **printf**

## <a name="remarks"></a>解説

**remquo**関数は*f**i*\**y**x* = *x* /  + *y の*浮動小数点剰余*f*を計算し *、i*は整数 *、f*は x と同じ*符号を持*ち *、f*の絶対値は*y*の絶対値より小さい。

C++ ではオーバーロードが可能なので **、float**または**long** **double**値を受け取って返す**remquo**のオーバーロードを呼び出すことができます。 C プログラムでは **、remquo**は常に 2 つの**二重**引数を取り、**倍精度浮動小数点数**を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー (C)|必須ヘッダー (C++)|
|--------------|---------------------|-|
|**レムクォー**,**レムクォーク** **, レムクォール**|\<math.h>|\<cmath> または \<math.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
