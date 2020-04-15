---
title: rint、rintf、rintl
ms.date: 4/2/2020
api_name:
- rintf
- rintl
- rint
- _o_rint
- _o_rintf
- _o_rintl
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
- rintf
- rintl
- rint
helpviewer_keywords:
- rintf function
- rint function
- rintl function
ms.assetid: 312ae3e6-278c-459a-9393-11b8f87d9184
ms.openlocfilehash: 6489b7ebed5246738fb660dffd07a0b8f8ed9743
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332768"
---
# <a name="rint-rintf-rintl"></a>rint、rintf、rintl

浮動小数点値を浮動小数点形式で最も近い整数に丸めます。

## <a name="syntax"></a>構文

```C
double rint( double x );
float rintf( float x );
long double rintl( long double x );
```

```cpp
float rint( float x );  // C++ only
long double rint( long double x );  // C++ only
```

### <a name="parameters"></a>パラメーター

*X*<br/>
丸める浮動小数点値。

## <a name="return-value"></a>戻り値

**rint**関数は *、x*に最も近い整数を表す浮動小数点値を返します。 中間値は、**浮動小数点**丸めモードの現在の設定に従って丸められます。 **近辺**の関数とは異なり **、rint**関数は、結果が引数と値が異なる場合に **、FE_INEXACT**浮動小数点例外を発生させる可能性があります。 エラーの戻り値はありません。

|入力|SEH 例外|**_matherr**例外|
|-----------|-------------------|--------------------------|
|± ∞、QNAN、IND|none|none|
|非正規化数|EXCEPTION_FLT_UNDERFLOW|none|

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能なため **、float**値と**長****い倍精度**浮動小数点値を取得および戻す**rint**のオーバーロードを呼び出すことができます。 C プログラムでは **、rint**は常に二**重**を受け取って返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**リント**,**リンtf**,**リントル**|\<math.h>|\<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_rint.c
// Build with: cl /W3 /Tc crt_rint.c
// This example displays the rounded results of
// the floating-point values 2.499999, -2.499999,
// 2.8, -2.8, 2.5 and -2.5.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.499999;
   float y = 2.8f;
   long double z = 2.5;

   printf("rint(%f) is %.0f\n", x, rint (x));
   printf("rint(%f) is %.0f\n", -x, rint (-x));
   printf("rintf(%f) is %.0f\n", y, rintf(y));
   printf("rintf(%f) is %.0f\n", -y, rintf(-y));
   printf("rintl(%Lf) is %.0Lf\n", z, rintl(z));
   printf("rintl(%Lf) is %.0Lf\n", -z, rintl(-z));
}
```

```Output
rint(2.499999) is 2
rint(-2.499999) is -2
rintf(2.800000) is 3
rintf(-2.800000) is -3
rintl(2.500000) is 3
rintl(-2.500000) is -3
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[ceil、ceilf、ceill](ceil-ceilf-ceill.md)<br/>
[floor、floorf、floorl](floor-floorf-floorl.md)<br/>
[fmod、fmodf](fmod-fmodf.md)<br/>
[lrint、lrintf、lrintl、llrint、llrintf、llrintl](lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)<br/>
[lround、lroundf、lroundl、llround、llroundf、llroundl](lround-lroundf-lroundl-llround-llroundf-llroundl.md)<br/>
[nearbyint、nearbyintf、nearbyintl](nearbyint-nearbyintf-nearbyintl1.md)<br/>
[rint](rint-rintf-rintl.md)<br/>
