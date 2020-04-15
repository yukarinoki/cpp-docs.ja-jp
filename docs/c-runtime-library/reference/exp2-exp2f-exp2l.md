---
title: exp2、exp2f、exp2l
ms.date: 4/2/2020
api_name:
- exp2
- exp2f
- exp2l
- _o_exp2
- _o_exp2f
- _o_exp2l
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
- exp2
- math/exp2
- exp2f
- math/exp2f
- exp2l
- math/exp2l
helpviewer_keywords:
- exp2 function
- exp2f function
- exp2l function
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
ms.openlocfilehash: a5df1a216b4565f013a4c42b4ef4369b5b7f9b04
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347579"
---
# <a name="exp2-exp2f-exp2l"></a>exp2、exp2f、exp2l

指定した値に 2 を計算します。

## <a name="syntax"></a>構文

```C
double exp2(
   double x
);

float exp2(
   float x
);  // C++ only

long double exp2(
   long double x
); // C++ only

float exp2f(
   float x
);

long double exp2l(
   long double x
);
```

### <a name="parameters"></a>パラメーター

*X*<br/>
指数部の値です。

## <a name="return-value"></a>戻り値

成功した場合は *、x*の底 2 部数 、つまり 2<sup>x</sup>を返します。 それ以外の場合は、次のいずれかの値を返します。

|問題|戻り値|
|-----------|------------|
|*x* = ±0|1|
|*x* = -無限大|+0|
|*x* = +無限大|+INFINITY|
|*x* = NaN|(NaN)|
|オーバーフロー範囲エラー|+HUGE_VAL、+HUGE_VALF、または +HUGE_VALL|
|アンダーフロー範囲エラー|丸め後の正しい結果|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能なため **、float**型と**長いダブル**型を取得および戻す**exp2**のオーバーロードを呼び出すことができます。 C プログラムでは **、exp2**は常に二**重**を受け取って返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**exp**, **expf**, **expl**|\<math.h>|\<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[exp、expf、expl](exp-expf.md)<br/>
[log2、log2f、log2l](log2-log2f-log2l.md)<br/>
