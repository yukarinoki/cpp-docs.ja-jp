---
title: fmod、fmodf、fmodl |Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fmod
- fmodf
- fmodl
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
- fmod
- _fmodl
- fmodf
dev_langs:
- C++
helpviewer_keywords:
- calculating floating-point remainders
- fmodf function
- fmodl function
- fmod function
- floating-point numbers, calculating remainders
ms.assetid: 6962d369-d11f-40b1-a6d7-6f67239f8a23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c473b5cb6822df07f4972ff2c964c828b14b5966
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207534"
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

*x*、 *y*<br/>
浮動小数点値。

## <a name="return-value"></a>戻り値

**fmod**の浮動小数点の剰余を返します*x* / *y*します。 場合の値*y* 0.0、 **fmod**簡易な NaN を返します。 による簡易な NaN の表現については、 **printf**ファミリを参照してください[printf](printf-printf-l-wprintf-wprintf-l.md)します。

## <a name="remarks"></a>Remarks

**Fmod**関数は浮動小数点の剰余を計算*f*の*x* / *y*ように*x* = *は* \* *y* + *f*ここで、*は*整数*f*と同じ符号*x*との絶対値*f*がの絶対値より小さい*y*します。

C++ では、オーバー ロードのオーバー ロードを呼び出すことができますので**fmod**を受け取って返す**float**と**長い****二重**値。 C プログラムで**fmod**常に 2 つ受け取る**二重**引数を返す、**二重**。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**fmod**、 **fmodf**、 **fmodl**|\<math.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
