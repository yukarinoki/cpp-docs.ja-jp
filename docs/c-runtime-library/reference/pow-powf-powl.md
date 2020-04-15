---
title: pow、powf、powl
ms.date: 4/2/2020
api_name:
- powl
- pow
- powf
- _o_pow
- _o_powf
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
- powl
- pow
- _powl
- powf
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
ms.openlocfilehash: b181959ac05814a673ab11f33e4cfc5a39e3869e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333114"
---
# <a name="pow-powf-powl"></a>pow、powf、powl

*x*を*y*の累乗に対して計算します。

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

*X*<br/>
底。

*Y*<br/>
指数。

## <a name="return-value"></a>戻り値

*x*<sup>*y*</sup>の値を返します。 オーバーフローまたはアンダーフロー時に、エラー メッセージは印刷されません。

|x の値と y の値|pow の値を返す|
|-----------------------|-------------------------|
|*x* != 0.0 と*y* == 0.0|1|
|*x* == 0.0 と*y* == 0.0|1|
|*x* == 0.0 と*y* < 0|INF|

## <a name="remarks"></a>解説

**pow**は、2<sup>64</sup>より大きい整数の浮動小数点値を認識しません (例えば、1.0E100)。

**pow**にはストリーミング SIMD 拡張 2 (SSE2) を使用する実装があります。 SSE2 実装の使い方の詳細および制約については、「[_set_SSE2_enable](set-sse2-enable.md)」を参照してください。

C++ ではオーバーロードが可能なため、 **pow**のさまざまなオーバーロードを呼び出すことができます。 C プログラムでは **、pow**は常に 2 つの**倍精度**値を受け取り、**倍精度**浮動小数点値を返します。

`pow(int, int)` オーバーロードは使用できなくなりました。 このオーバーロードを使用すると、コンパイラが[C2668](../../error-messages/compiler-errors-2/compiler-error-c2668.md)を出力することがあります。 この問題を回避するには、最初のパラメータを**倍**精度**浮動小数点**型 、または**長倍**に**キャストします。**

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー (C)|必須ヘッダー (C++)|
|-|-|-|
|**パウ**,**ポウチ**,**パウチ**|\<math.h>|\<math.h> または \<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
