---
title: exp、expf、expl
ms.date: 4/2/2020
api_name:
- expf
- expl
- exp
- _o_exp
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
- _expl
- expf
- expl
- exp
helpviewer_keywords:
- exponential calculations
- expf function
- expl function
- calculating exponentials
- exp function
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
ms.openlocfilehash: b6d4906212073ab8cb04a0ab77d1234d444a4c95
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909655"
---
# <a name="exp-expf-expl"></a>exp、expf、expl

指数を計算します。

## <a name="syntax"></a>構文

```C
double exp(
   double x
);
float exp(
   float x
);  // C++ only
long double exp(
   long double x
);  // C++ only
float expf(
   float x
);
long double expl(
   long double x
);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
自然対数*の底を*exponentiate する浮動小数点値。

## <a name="return-value"></a>戻り値

**Exp**関数は、成功した場合は、浮動小数点パラメーター *x*の指数値を返します。 つまり、結果は*e*<sup>*x*</sup>になります。ここで、 *e*は自然対数の底です。 オーバーフローの場合、関数は INF (無限大) を返し、アンダーフローでは 0**を返します**。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± Quiet NaN、不確定|None|_DOMAIN|
|±無限大|INVALID|_DOMAIN|
|x ≥ 7.097827e+002|INEXACT+OVERFLOW|OVERFLOW|
|X ≤ -7.083964e+002|INEXACT+UNDERFLOW|UNDERFLOW|

**Exp**関数には、ストリーミング SIMD 拡張命令 2 (SSE2) を使用する実装があります。 SSE2 実装の使い方の詳細および制約については、「[_set_SSE2_enable](set-sse2-enable.md)」をご覧ください。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、 **float**または**long double**引数を受け取る**exp**のオーバーロードを呼び出すことができます。 C プログラムでは、 **exp**は常に**倍精度浮動小数点数**を取得し、double を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|関数|必須の C ヘッダー|必須の C++ ヘッダー|
|--------------|---------------------|---|
|**exp**, **、** **expl**|\<math.h>|\<cmath> または \<math.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_exp.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.302585093, y;

   y = exp( x );
   printf( "exp( %f ) = %f\n", x, y );
}
```

```Output
exp( 2.302585 ) = 10.000000
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[log、logf、log10、log10f](log-logf-log10-log10f.md)<br/>
[_CIexp](../../c-runtime-library/ciexp.md)<br/>
