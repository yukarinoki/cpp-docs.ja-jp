---
title: fmod、fmodf、fmodl
ms.date: 4/2/2020
api_name:
- fmod
- fmodf
- fmodl
- _o_fmod
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
- fmod
- _fmodl
- fmodf
helpviewer_keywords:
- calculating floating-point remainders
- fmodf function
- fmodl function
- fmod function
- floating-point numbers, calculating remainders
ms.assetid: 6962d369-d11f-40b1-a6d7-6f67239f8a23
ms.openlocfilehash: 0cf25e2029f06c2e02a24ca84926e1a8b8f30159
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346555"
---
# <a name="fmod-fmodf-fmodl"></a>fmod、fmodf、fmodl

浮動小数点の剰余を計算します。

## <a name="syntax"></a>構文

```C
double fmod(
   double x,
   double y
);
float fmod(
   float x,
   float y
);  // C++ only
long double fmod(
   long double x,
   long double y
);  // C++ only
float fmodf(
   float x,
   float y
);
long double fmodl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>パラメーター

*x*, *y*<br/>
浮動小数点値。

## <a name="return-value"></a>戻り値

**fmod は** *x* / *y*の浮動小数点の剰余を返します。 *y*の値が 0.0 の場合 **、fmod**は静止 NaN を返します。 **printf**ファミリによる静かな NaN の表現については、 [printf](printf-printf-l-wprintf-wprintf-l.md)を参照してください。

## <a name="remarks"></a>解説

**fmod**関数は*i*\**y* +  *x* / *y の*浮動小数点剰余*f**を計算*し、ここで*i**x* = は整数 *、f*は x と同じ*符号を持*ち *、f*の絶対値は*y*の絶対値より小さい。

C++ ではオーバーロードが可能なので、**浮動小数点**値と**長****倍**数の値を取得および戻す**fmod**のオーバーロードを呼び出すことができます。 C プログラムでは **、fmod**は常に 2 つの**二重**引数を取り、**倍精度浮動小数点数**を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**フモド**,**フモドフ**,**フモドル**|\<math.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_fmod.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;

   z = fmod( w, x );
   printf( "The remainder of %.2f / %.2f is %f\n", w, x, z );
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[ceil、ceilf、ceill](ceil-ceilf-ceill.md)<br/>
[fabs、fabsf、fabsl](fabs-fabsf-fabsl.md)<br/>
[floor、floorf、floorl](floor-floorf-floorl.md)<br/>
[_CIfmod](../../c-runtime-library/cifmod.md)<br/>
