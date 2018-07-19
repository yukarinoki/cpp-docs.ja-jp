---
title: frexp、frexpf、frexpl |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- frexp
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
- frexp
- _frexpl
dev_langs:
- C++
helpviewer_keywords:
- _frexpl function
- mantissas, floating-point variables
- frexpl function
- exponent, floating-point numbers
- frexp function
- floating-point functions, mantissa and exponent
ms.assetid: 9b020f2e-3967-45ec-a6a8-d467a071aa55
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3bf79e954274b1cedb104ed637ad14b8e1c6431
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32400090"
---
# <a name="frexp-frexpf-frexpl"></a>frexp、frexpf、frexpl

浮動小数点数の仮数と指数を取得します。

## <a name="syntax"></a>構文

```C
double frexp(
   double x,
   int *expptr
);
float frexpf(
   float x,
   int * expptr
);
long double frexpl(
   long double x,
   int * expptr
);
float frexp(
   float x,
   int * expptr
);  // C++ only
long double frexp(
   long double x,
   int * expptr
);  // C++ only
```

### <a name="parameters"></a>パラメーター

*x*<br/>
浮動小数点値。

*expptr*<br/>
格納された整数の指数へのポインター。

## <a name="return-value"></a>戻り値

**frexp**仮数部を返します。 場合*x*が 0 の場合、仮数と指数部の両方の場合は 0 を返します。 場合*expptr*は**NULL**、」の説明に従って、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**は 0 を返します。

## <a name="remarks"></a>コメント

**Frexp**関数は浮動小数点値を分割 (*x*)、仮数部に (*m*) と指数部 (*n*) になるよう、絶対値*m*は 0.5 以上 1.0 未満と*x* = *m* * 2<sup>*n*</sup>. 整数の指数*n*が指す位置に格納されて*expptr*です。

C++ では、オーバー ロードのオーバー ロードを呼び出すことができますので**frexp**です。 C プログラムでは、 **frexp**は常に、**二重**と**int**ポインターを返す、**二重**です。

## <a name="requirements"></a>要件

|関数|必須ヘッダー|
|--------------|---------------------|
|**frexp**、 **frexpf**、 **frexpl**|\<math.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_frexp.c
// This program calculates frexp( 16.4, &n )
// then displays y and n.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x, y;
   int n;

   x = 16.4;
   y = frexp( x, &n );
   printf( "frexp( %f, &n ) = %f, n = %d\n", x, y, n );
}
```

```Output
frexp( 16.400000, &n ) = 0.512500, n = 5
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[ldexp](ldexp.md)<br/>
[modf、modff、modfl](modf-modff-modfl.md)<br/>
