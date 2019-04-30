---
title: scalbn、scalbnf、scalbnl、scalbln、scalblnf、scalblnl
ms.date: 04/05/2018
apiname:
- scalblnl
- scalbnl
- scalbnf
- scalblnf
- scalbn
- scalbln
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
- scalblnf
- scalbnl
- scalblnl
- scalbln
- scalbn
- scalbnf
helpviewer_keywords:
- scalbn function
- scalbln function
- scalblnl function
- scalbnl function
- scalbnf function
- scalblnf function
ms.assetid: df2f1543-8e39-4af4-a5cf-29307e64807d
ms.openlocfilehash: 7109340afaa634fc21177380d015c9eace506081
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357162"
---
# <a name="scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl"></a>scalbn、scalbnf、scalbnl、scalbln、scalblnf、scalblnl

浮動小数点数に整数である FLT_RADIX の累乗を乗算します。

## <a name="syntax"></a>構文

```C
double scalbn(
   double x,
   int exp
);
float scalbn(
   float x,
   int exp
);  // C++ only
long double scalbn(
   long double x,
   int exp
);  // C++ only
float scalbnf(
   float x,
   int exp
);
long double scalbnl(
   long double x,
   int exp
);
double scalbln(
   double x,
   long exp
);
float scalbln(
   float x,
   long exp
);  // C++ only
long double scalbln(
   long double x,
   long exp
);  // C++ only
float scalblnf(
   float x,
   long exp
);
long double scalblnl(
   long double x,
   long exp
);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
浮動小数点値。

*exp*<br/>
整数の指数。

## <a name="return-value"></a>戻り値

**Scalbn**関数の値を返す*x* \* **FLT_RADIX**<sup>exp</sup>成功するとします。 オーバーフローが発生 (の符号に応じて*x*)、 **scalbn** +/-返します**HUGE_VAL**、 **errno**値に設定されて**ERANGE**.

詳細については**errno**および考えられるエラー戻り値は、「 [errno _doserrno _sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)します。

## <a name="remarks"></a>Remarks

**FLT_RADIX**で定義されている\<float.h > ネイティブ浮動小数点基数としてバイナリ システムで、そのは値 2 と**scalbn**と等価[ldexp](ldexp.md)します。

オーバー ロードを呼び出すことができますので、C++ ではオーバー ロード、 **scalbn**と**scalbln**を受け取って返す**float**または**長い** **二重**型。 C プログラムで**scalbn**は常に、**二重**と**int**を返します、**二重**、および**scalbln**は常に、**二重**と**長い**を返します、**二重**します。

## <a name="requirements"></a>必要条件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**scalbn**、 **scalbnf**、 **scalbnl**、 **scalbln**、 **scalblnf**、 **scalblnl**|\<math.h>|\<cmath>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_scalbn.c
// Compile using: cl /W4 crt_scalbn.c
#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 6.4, y;
   int p = 3;

   y = scalbn( x, p );
   printf( "%2.1f times FLT_RADIX to the power of %d is %2.1f\n", x, p, y );
}
```

### <a name="output"></a>出力

```Output
6.4 times FLT_RADIX to the power of 3 is 51.2
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
[modf、modff、modfl](modf-modff-modfl.md)<br/>
