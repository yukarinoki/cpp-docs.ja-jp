---
title: exp、expf、expl
ms.date: 04/05/2018
apiname:
- expf
- expl
- exp
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
ms.openlocfilehash: b9fb38adcc442e60864ec632cd92793f16e47502
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288189"
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
自然対数の底 exponentiate に浮動小数点値*e*でします。

## <a name="return-value"></a>戻り値

**Exp**関数は浮動小数点のパラメーターの指数値を返す*x*成功した場合、します。 つまり、結果が*e*<sup>*x*</sup>ここで、 *e*自然対数の底です。 関数は INF (無限) を返し、オーバーフロー、アンダー フロー、 **exp** 0 を返します。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± 簡易な NaN、不定|なし|_DOMAIN|
|± 無限大|INVALID|_DOMAIN|
|x ≥ 7.097827e+002|INEXACT+OVERFLOW|OVERFLOW|
|X ≤ -7.083964e+002|INEXACT+UNDERFLOW|UNDERFLOW|

**Exp**関数には、ストリーミング SIMD 拡張命令 2 (SSE2) を使用する実装。 SSE2 実装の使い方の詳細および制約については、「[_set_SSE2_enable](set-sse2-enable.md)」をご覧ください。

## <a name="remarks"></a>Remarks

C++ では、オーバー ロードのオーバー ロードを呼び出すことができますので**exp**を受け取る、 **float**または**long double**引数。 C プログラムで**exp**は、**二重**します。

## <a name="requirements"></a>必要条件

|関数|必須の C ヘッダー|必須の C++ ヘッダー|
|--------------|---------------------|---|
|**exp**、 **expf**、 **expl**|\<math.h>|\<cmath> または \<math.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
