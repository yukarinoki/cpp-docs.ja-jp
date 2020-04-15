---
title: log2、log2f、log2l
ms.date: 4/2/2020
api_name:
- log2
- log2l
- log2f
- _o_log2
- _o_log2f
- _o_log2l
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
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
ms.openlocfilehash: 29a1a9e2003091944a4587036c62a49d76333080
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341722"
---
# <a name="log2-log2f-log2l"></a>log2、log2f、log2l

指定した値の 2 進 (2 を底とする) 対数を決定します。

## <a name="syntax"></a>構文

```C
double log2(
   double x
);

float log2(
   float x
); //C++ only

long double log2(
   long double x
); //C++ only

float log2f(
   float x
);

long double log2l(
   long double x
);
```

### <a name="parameters"></a>パラメーター

*X*<br/>
2 を底とする対数を決定する値。

## <a name="return-value"></a>戻り値

成功すると、log2 *x*を返します。

それ以外の場合は、次の値のいずれかを返します。

|問題|戻り値|
|-----------|------------|
|*x* < 0|(NaN)|
|*x* = ±0|-INFINITY|
|*x* = 1|+0|
|+INFINITY|+INFINITY|
|(NaN)|(NaN)|
|ドメイン エラー|(NaN)|
|極エラー|-HUGE_VAL、-HUGE_VALF、または -HUGE_VALL|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>解説

x が整数の場合、この関数は基本的に x の最上位の 1 ビットの 0 から始まる*インデックスを返*します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**ログ 2**,**ログ2f**, **log2l**|\<math.h>|\<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[exp2、exp2f、exp2l](exp2-exp2f-exp2l.md)<br/>
[log、logf、log10、log10f](log-logf-log10-log10f.md)<br/>
