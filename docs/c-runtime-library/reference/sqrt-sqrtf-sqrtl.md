---
title: sqrt、sqrtf、sqrtl
ms.date: 04/05/2018
apiname:
- sqrtl
- sqrtf
- sqrt
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
- sqrt
- sqrtf
- _sqrtl
helpviewer_keywords:
- sqrtf function
- sqrt function
- sqrtl function
- _sqrtl function
- calculating square roots
- square roots, calculating
ms.assetid: 2ba9467b-f172-41dc-8f10-b86f68fa813c
ms.openlocfilehash: c44f8813812b2aeffc2680a0a666d968bb2b4da6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560577"
---
# <a name="sqrt-sqrtf-sqrtl"></a>sqrt、sqrtf、sqrtl

平方根を計算します。

## <a name="syntax"></a>構文

```C
double sqrt(
   double x
);
float sqrt(
   float x
);  // C++ only
long double sqrt(
   long double x
);  // C++ only
float sqrtf(
   float x
);
long double sqrtl(
   long double x
);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
負でない浮動小数点値

## <a name="remarks"></a>Remarks

オーバー ロードを呼び出すことができますので、C++ ではオーバー ロード、 **sqrt**を受け取る**float**または**長い****二重**型。 C プログラムで**sqrt**は**二重**します。

## <a name="return-value"></a>戻り値

**Sqrt**関数の平方根を返します*x*します。 既定では場合、 *x*が負の値、 **sqrt**は不定値 NaN を返します。

|入力|SEH 例外|**_matherr**例外|
|-----------|-------------------|--------------------------|
|± QNAN、IND|none|_DOMAIN|
|- ∞|none|_DOMAIN|
|x<0|none|_DOMAIN|

## <a name="requirements"></a>必要条件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**sqrt**、 **sqrtf**、 **sqrtl**|\<math.h>|\<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_sqrt.c
// This program calculates a square root.

#include <math.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   double question = 45.35, answer;
   answer = sqrt( question );
   if( question < 0 )
      printf( "Error: sqrt returns %f\n", answer );
   else
      printf( "The square root of %.2f is %.2f\n", question, answer );
}
```

```Output
The square root of 45.35 is 6.73
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[exp、expf、expl](exp-expf.md)<br/>
[log、logf、log10、log10f](log-logf-log10-log10f.md)<br/>
[pow、powf、powl](pow-powf-powl.md)<br/>
[_CIsqrt](../../c-runtime-library/cisqrt.md)<br/>
