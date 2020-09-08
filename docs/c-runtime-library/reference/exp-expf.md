---
title: exp、expf、expl
description: Exp、tf、および金の API リファレンス指数を計算します。
ms.date: 08/31/2020
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
ms.openlocfilehash: 44652e5d06d842bd2eb2e280409a1e55fc66f582
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555892"
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
#define exp(z) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*閉じる*\
自然対数 *の底を* exponentiate する浮動小数点値。

## <a name="return-value"></a>戻り値

**Exp**関数は、成功した場合は、浮動小数点パラメーター *x*の指数値を返します。 つまり、結果は *e*<sup>*x*</sup>になります。ここで、 *e* は自然対数の底です。 オーバーフローの場合、関数は INF (無限大) を返し、アンダーフローでは 0 **を返します** 。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± Quiet NaN、不確定|なし|_DOMAIN|
|±無限大|INVALID|_DOMAIN|
|x ≥ 7.097827e+002|INEXACT+OVERFLOW|OVERFLOW|
|X ≤ -7.083964e+002|INEXACT+UNDERFLOW|UNDERFLOW|

**Exp**関数には、ストリーミング SIMD 拡張命令 2 (SSE2) を使用する実装があります。 SSE2 実装の使い方の詳細および制約については、「[_set_SSE2_enable](set-sse2-enable.md)」をご覧ください。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、または引数を受け取る **exp** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 \<tgmath.h> **exp** は常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `exp()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|必須の C ヘッダー|必須の C++ ヘッダー|
|--------------|---------------------|---|
|**exp**, **、** **expl**|\<math.h>|\<cmath> または \<math.h>|
|**exp** マクロ| \<tgmath.h> || 

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

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[log、logf、log10、log10f](log-logf-log10-log10f.md)<br/>
[_CIexp](../../c-runtime-library/ciexp.md)<br/>
