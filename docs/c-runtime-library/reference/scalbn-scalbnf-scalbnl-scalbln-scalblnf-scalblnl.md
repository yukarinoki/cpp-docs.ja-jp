---
title: scalbn、scalbnf、scalbnl、scalbln、scalblnf、scalblnl
description: Scalbn、scalbnf、btree bnl、スケール bln、、およびスケール blnl の API リファレンス浮動小数点数をの整数の累乗で乗算 `FLT_RADIX` します。
ms.date: 9/1/2020
api_name:
- scalblnl
- scalbnl
- scalbnf
- scalblnf
- scalbn
- scalbln
- _o_scalbln
- _o_scalblnf
- _o_scalblnl
- _o_scalbn
- _o_scalbnf
- _o_scalbnl
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
ms.openlocfilehash: 1a01811e5fcfb28c0557e0232d76649c867748b1
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556672"
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

#define scalbn(X, INT) // Requires C11 or higher

double scalbln(
   double x,
   long exp
);

float scalblnf(
   float x,
   long exp
);
long double scalblnl(
   long double x,
   long exp
);

#define scalbln(X, LONG) // Requires C11 or higher

float scalbln(
   float x,
   long exp
);  // C++ only
long double scalbln(
   long double x,
   long exp
);  // C++ only
```

### <a name="parameters"></a>パラメーター

*閉じる*\
浮動小数点値。

*期限*\
整数の指数。

## <a name="return-value"></a>戻り値

**Scalbn**関数は、 *x* \* 成功した場合に x **FLT_RADIX**<sup>exp</sup>の値を返します。 オーバーフロー時 ( *x*の符号によって異なります)、 **scalbn** は +/- **HUGE_VAL**; を返します。 **errno** 値は **ERANGE**に設定されます。

**Errno**および考えられるエラーの戻り値の詳細については、「 [errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**FLT_RADIX** は \<float.h> 、ネイティブ浮動小数点基数としてで定義されます。バイナリシステムでは、値は2で、 **scalbn** は [ldexp](ldexp.md)と等価です。

C++ ではオーバーロードが可能であるため、または型を受け取って返す **scalbn** の **オーバーロードを呼び** 出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 \<tgmath.h> **scalbn** は常にとを受け取り、を **`double`** **`int`** 返し **`double`** ます。また、 **スケール bln** は常にとを受け取り、を **`double`** **`long`** 返し **`double`** ます。

\<tgmath.h> `scalbn()` マクロまたはマクロを使用する場合 `scalbln` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**scalbn**、 **scalbnf**、 **btree bnl**、 **スケール bln**、 **、スケール** **blnl**|\<math.h>|\<cmath>|
|**scalbn () または** マクロ | \<tgmath.h> ||

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
[modf、modff、modfl](modf-modff-modfl.md)<br/>
