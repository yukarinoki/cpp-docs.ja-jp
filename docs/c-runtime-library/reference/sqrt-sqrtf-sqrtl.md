---
title: sqrt、sqrtf、sqrtl
ms.date: 6/5/2020
api_name:
- sqrtl
- sqrtf
- sqrt
- _o_sqrt
- _o_sqrtf
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 8983d0854b82d532aad57fa80b03bbe3313970f0
ms.sourcegitcommit: fe146adb3a02872538637196bb3c45aeeeaaf5c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84506885"
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

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、 **float**型または**long** **double**型を受け取る**sqrt**のオーバーロードを呼び出すことができます。 C プログラムでは、 **sqrt**は常にを受け取り、 **double**を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="return-value"></a>戻り値

**Sqrt**関数は*x*の平方根を返します。 既定では、 *x*が負の場合、 **sqrt**は無限の NaN を返します。

|入力|SEH 例外|**_matherr**例外的|
|-----------|-------------------|--------------------------|
|± QNAN、IND|なし|_DOMAIN|
|- ∞|なし|_DOMAIN|
|x<0|なし|_DOMAIN|

## <a name="requirements"></a>要件

|機能|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**sqrt**、 **sqrtf**、 **sqrtf**|\<math.h>|\<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[exp、expf、expl](exp-expf.md)<br/>
[log、logf、log10、log10f](log-logf-log10-log10f.md)<br/>
[pow、powf、powl](pow-powf-powl.md)<br/>
[_CIsqrt](../../c-runtime-library/cisqrt.md)<br/>
