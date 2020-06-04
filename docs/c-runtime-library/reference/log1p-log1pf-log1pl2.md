---
title: log1p、log1pf、log1pl2
ms.date: 4/2/2020
api_name:
- log1p
- log1pf
- log1pl
- _o_log1p
- _o_log1pf
- _o_log1pl
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
- log1p
- log1pf
- log1pl
- math/log1p
- math/log1pf
- math/log1pl
helpviewer_keywords:
- log1p function
- log1pf function
- log1pl function
ms.assetid: a40d965d-b4f6-42f4-ba27-2395546f7c12
ms.openlocfilehash: 21bba72b204f975b806e43cdc6d36d8efa173b9b
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911425"
---
# <a name="log1p-log1pf-log1pl"></a>log1p、log1pf、log1pl

1 に指定された値を加えた値の自然対数を計算します。

## <a name="syntax"></a>構文

```C
double log1p(
   double x
);

float log1p(
   float x
); //C++ only

long double log1p(
   long double x
); //C++ only

float log1pf(
   float x
);

long double log1pl(
   long double x
);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
浮動小数点引数。

## <a name="return-value"></a>戻り値

成功した場合は、(*x* + 1) の自然 (底*e*) ログを返します。

それ以外の場合は、次の値のいずれかを返します。

|入力|結果|SEH 例外|errno|
|-----------|------------|-------------------|-----------|
|+inf|+inf|||
|非正規化数|入力と同じ|UNDERFLOW||
|±0|入力と同じ|||
|-1|-inf|DIVBYZERO|ERANGE|
|< -1|nan|INVALID|EDOM|
|-inf|nan|INVALID|EDOM|
|± SNaN|入力と同じ|INVALID||
|± QNaN、不定|入力と同じ|||

*X* =-1 の場合、 **ERRNO**値は ERANGE に設定されます。 *X* <-1 の場合、 **Errno**値は**EDOM**に設定されます。

## <a name="remarks"></a>解説

*X*が0に近い場合、 **log1p**関数`log(x + 1)`はを使用するよりも正確な場合があります。

C++ ではオーバーロードが可能であるため、 **float**型および**long** **double**型を受け取って返す**log1p**のオーバーロードを呼び出すことができます。 C プログラムでは、 **log1p**は常に**double**を受け取り、返します。

*X*が自然数の場合、この関数は (*x* -1) の階乗の対数を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**log1p**、 **log1pf**、 **log1pl**|\<math.h>|\<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[log2、log2f、log2l](log2-log2f-log2l.md)<br/>
[log、logf、log10、log10f](log-logf-log10-log10f.md)<br/>
