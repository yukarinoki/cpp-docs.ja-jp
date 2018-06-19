---
title: pow、powf、powl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- powl
- pow
- powf
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
- powl
- pow
- _powl
- powf
dev_langs:
- C++
helpviewer_keywords:
- exponential calculations
- powl function
- _powl function
- exponentiation
- powers, calculating
- calculating exponentials
- powf function
- pow function
ms.assetid: e75c33ed-2e59-48b1-be40-81da917324f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5daf7348198cb6f3ba0186eb4586b2486548f6f5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403831"
---
# <a name="pow-powf-powl"></a>pow、powf、powl

計算*x*の累乗*y*です。

## <a name="syntax"></a>構文

```C
double pow( double x, double y );
float powf( float x, float y );
long double powl( long double x, long double y );
```

```cpp
double pow( double x, int y );  // C++ only
float pow( float x, float y );  // C++ only
float pow( float x, int y );  // C++ only
long double pow( long double x, long double y );  // C++ only
long double pow( long double x, int y );  // C++ only
```

### <a name="parameters"></a>パラメーター

*x*<br/>
底。

*y*<br/>
指数。

## <a name="return-value"></a>戻り値

値を返します*x*<sup>*y*</sup>です。 オーバーフローまたはアンダーフロー時に、エラー メッセージは印刷されません。

|x の値と y の値|pow の値を返す|
|-----------------------|-------------------------|
|*x* ! = 0.0 と*y* = = 0.0|1|
|*x* 0.0 を = = と*y* = = 0.0|1|
|*x* 0.0 を = = と*y* < 0|INF|

## <a name="remarks"></a>コメント

**pow** 2 より大きい整数の浮動小数点値は認識されません<sup>64</sup> (たとえば、1.0E100)。

**pow**ストリーミング SIMD 拡張命令 2 (SSE2) を使用する実装があります。 SSE2 実装の使い方の詳細および制約については、「[_set_SSE2_enable](set-sse2-enable.md)」をご覧ください。

C++ では、オーバー ロードできるよう、ためのさまざまなオーバー ロードのいずれかを呼び出すことができます**pow**です。 C プログラムでは、 **pow**常に受け取って 1 つ**二重**、値を返します、**二重**値。

`pow(int, int)` オーバーロードは使用できなくなりました。 このオーバー ロードを使用する場合、コンパイラが出力[C2668](../../error-messages/compiler-errors-2/compiler-error-c2668.md)です。 この問題を避けるためには、最初のパラメーターをキャスト**二重**、 **float**、または**長い****二重**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー (C)|必須ヘッダー (C++)|
|-|-|-|
|**pow**、 **powf**、 **powl**|\<math.h>|\<math.h> または \<cmath>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_pow.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.0, y = 3.0, z;

   z = pow( x, y );
   printf( "%.1f to the power of %.1f is %.1f\n", x, y, z );
}
```

```Output
2.0 to the power of 3.0 is 8.0
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md) <br/>
[exp、expf、expl](exp-expf.md) <br/>
[log、logf、log10、log10f](log-logf-log10-log10f.md) <br/>
[sqrt、sqrtf、sqrtl](sqrt-sqrtf-sqrtl.md) <br/>
[_CIpow](../../c-runtime-library/cipow.md)<br/>
