---
title: remquo、remquof、remquol
description: Remquo remquof、remquol の API リファレンス2つの整数値の剰余を計算し、パラメーターで指定された位置に、商の符号とおおよその大きさを持つ整数値を格納します。
ms.date: 9/1/2020
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: d99204ad9a80c6320869cbb72aee905981a5224d
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89554969"
---
# <a name="remquo-remquof-remquol"></a>remquo、remquof、remquol

2 個の整数値の剰余を計算し、パラメーターに指定された位置に、整数値を符号と商の近似値と共に格納します。

## <a name="syntax"></a>構文

```C
double remquo( double numer, double denom, int* quo );
float remquof( float numer, float denom, int* quo );
long double remquol( long double numer, long double denom, int* quo );
#define remquo(X, Y, INT_PTR) // Requires C11 or higher

float remquo( float numer, float denom, int* quo ); /* C++ only */
long double remquo( long double numer, long double denom, int* quo ); /* C++ only */
```

### <a name="parameters"></a>パラメーター

*数値*\
分子。

*デ om*\
分母。

*従来*\
符号と商の近似値を持つ値を格納する整数へのポインター。

## <a name="return-value"></a>戻り値

その後、 *x*y の浮動小数点の剰余**を返し**  /  *y*ます。 *Y*の値が0.0 の場合、 **Remquo** quiet NaN を返します。 **Printf**ファミリによる簡易な NaN の表現については、「 [printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)」を参照してください。

## <a name="remarks"></a>解説

**Remquo** *は x y の浮動*小数点の剰余*f*を計算します。ここで、  /  *y* *x*  =  *i* \* *y*  +  *f* *i*は整数、 *f*は*x*と同じ符号、 *f*の絶対値は*y*の絶対値よりも小さくなっています。

C++ ではオーバーロードが可能であるため、またはの値を受け取って返す、 **remquo** オーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除いて、 \<tgmath.h> **remquo** 常に2つの引数を受け取り、を **`double`** 返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `remquo()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|必須ヘッダー (C)|必須ヘッダー (C++)|
|--------------|---------------------|-|
|**remquo** **remquof**、 **remquol**|\<math.h>|\<cmath> または \<math.h>|
|**remquo** | \<tgmath.h> ||

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

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv、lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod、fmodf](fmod-fmodf.md)<br/>
[remainder、remainderf、remainderl](remainder-remainderf-remainderl.md)<br/>
