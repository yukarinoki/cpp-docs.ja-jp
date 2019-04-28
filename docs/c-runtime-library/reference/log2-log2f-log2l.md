---
title: log2、log2f、log2l
ms.date: 04/05/2018
apiname:
- log2
- log2l
- log2f
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
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
ms.openlocfilehash: d70d074b13b0f24f1f040ef0e861e073e303ac7b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285940"
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

*x*<br/>
2 を底とする対数を決定する値。

## <a name="return-value"></a>戻り値

成功した場合、戻り値が返さ log2 *x*します。

それ以外の場合は、次の値のいずれかを返します。

|懸案事項|Return|
|-----------|------------|
|*x* < 0|NaN|
|*x* = ±0|-INFINITY|
|*x* = 1|+0|
|+INFINITY|+INFINITY|
|NaN|NaN|
|ドメイン エラー|NaN|
|極エラー|-HUGE_VAL、-HUGE_VALF、または -HUGE_VALL|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>Remarks

この関数は基本的の最上位 1 ビットの 0 から始まるインデックスを返します x が整数である場合は、 *x*します。

## <a name="requirements"></a>必要条件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**log2**、 **log2f**、 **log2l**|\<math.h>|\<cmath>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[exp2、exp2f、exp2l](exp2-exp2f-exp2l.md)<br/>
[log、logf、log10、log10f](log-logf-log10-log10f.md)<br/>
