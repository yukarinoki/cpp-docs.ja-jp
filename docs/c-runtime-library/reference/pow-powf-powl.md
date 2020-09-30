---
title: pow、powf、powl
description: Pow、powf、および powl の API リファレンス計算によって指数演算が発生します。
ms.date: 08/31/2020
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 8fb6679e2b509274b4ea60c410a81b54df866416
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91505566"
---
# <a name="pow-powf-powl"></a>pow、powf、powl

*X*の累乗を*y*で計算します。

## <a name="syntax"></a>構文

```C
double pow( double x, double y );
float powf( float x, float y );
long double powl( long double x, long double y );
define pow(X, Y) // Requires C11 or higher

double pow( double x, int y );  // C++ only
float pow( float x, float y );  // C++ only
float pow( float x, int y );  // C++ only
long double pow( long double x, long double y );  // C++ only
long double pow( long double x, int y );  // C++ only
```

### <a name="parameters"></a>パラメーター

*閉じる*\
底。

*前年*\
指数。

## <a name="return-value"></a>戻り値

*X*<sup>*y*</sup>の値を返します。 オーバーフローまたはアンダーフロー時に、エラー メッセージは印刷されません。

|x の値と y の値|pow の値を返す|
|-----------------------|-------------------------|
|*x* ! = 0.0 および *y* = = 0.0|1|
|*x* = = 0.0 および *y* = = 0.0|1|
|*x* = = 0.0 および *y* < 0|INF|

## <a name="remarks"></a>注釈

**pow** は、2<sup>64</sup> を超える整数の浮動小数点値を認識しません (たとえば、1.0 e100)。

**pow** には、ストリーミング SIMD 拡張命令 2 (SSE2) を使用する実装があります。 SSE2 実装の使い方の詳細および制約については、「[_set_SSE2_enable](set-sse2-enable.md)」を参照してください。

C++ ではオーバーロードが可能であるため、 **pow**のさまざまなオーバーロードを呼び出すことができます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き \<tgmath.h> 、 **pow** は常に2つの値を受け取り、 **`double`** 値を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `pow()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

`pow(int, int)` オーバーロードは使用できなくなりました。 このオーバーロードを使用する場合、コンパイラは [C2668](../../error-messages/compiler-errors-2/compiler-error-c2668.md)を生成することがあります。 この問題を回避するには、最初のパラメーターを **`double`** 、、 **`float`** またはにキャスト **`long double`** します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-|-|-|
|**pow**、 **powf**、 **powl**|\<math.h>|\<math.h> または \<cmath>|
|**pow** マクロ | \<tgmath.h> ||

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

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md) <br/>
[exp、expf、expl](exp-expf.md) <br/>
[log、logf、log10、log10f](log-logf-log10-log10f.md) <br/>
[sqrt、sqrtf、sqrtl](sqrt-sqrtf-sqrtl.md) <br/>
[_CIpow](../../c-runtime-library/cipow.md)<br/>
