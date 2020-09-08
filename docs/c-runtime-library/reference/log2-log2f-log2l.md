---
title: log2、log2f、log2l
description: Log2、log2f、および log2l の API リファレンス指定した値の2進 (2 進数) の対数を決定します。
ms.date: 9/1/2020
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
ms.openlocfilehash: 37319560891dbd64030495750aaf347d9dedd7e7
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555359"
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

#define log2(X) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*閉じる*\
2 を底とする対数を決定する値。

## <a name="return-value"></a>戻り値

成功した場合、は return log2 *x*を返します。

それ以外の場合は、次の値のいずれかを返します。

|問題|戻り値|
|-----------|------------|
|*x* < 0|NaN|
|*x* = ±0|-INFINITY|
|*x* = 1|+0|
|+INFINITY|+INFINITY|
|NaN|NaN|
|ドメイン エラー|NaN|
|極エラー|-HUGE_VAL、-HUGE_VALF、または -HUGE_VALL|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>解説

*X*が整数の場合、この関数は基本的に、 *x*の最上位1ビットの0から始まるインデックスを返します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**log2**、 **log2f**、 **log2l**|\<math.h>|\<cmath>|
|**log2** マクロ | \<tgmath.h> ||

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[exp2、exp2f、exp2l](exp2-exp2f-exp2l.md)<br/>
[log、logf、log10、log10f](log-logf-log10-log10f.md)<br/>
