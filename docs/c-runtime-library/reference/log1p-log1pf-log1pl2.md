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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: b4e077f5b806dbe38ed4a4f4e8eef0259170cb7e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341811"
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

*X*<br/>
浮動小数点引数。

## <a name="return-value"></a>戻り値

成功した場合は、自然 ( 底*e*) のログ (*x* + 1 ) を返します。

それ以外の場合は、次の値のいずれかを返します。

|入力|結果|SEH 例外|errno|
|-----------|------------|-------------------|-----------|
|+inf|+inf|||
|非正規化数|入力と同じ|UNDERFLOW||
|±0|入力と同じ|||
|-1|-inf|DIVBYZERO|ERANGE|
|< -1|nan|INVALID|EDOM|
|-inf|nan|INVALID|EDOM|
|±SNaN|入力と同じ|INVALID||
|±QNaN、無期限|入力と同じ|||

*x* = -1 の場合 **、errno**値は ERANGE に設定されます。 *x*が -1 の場合 **、errno**値は**EDOM**に設定<。

## <a name="remarks"></a>解説

**log1p**関数は`log(x + 1)`*、x*が 0 に近い場合よりも正確である可能性があります。

C++ ではオーバーロードが可能なため **、float**型と**長い****ダブル**型を取得および戻す**log1p**のオーバーロードを呼び出すことができます。 C プログラムでは **、log1p**は常に二**重**を受け取って返します。

*x*が自然数の場合、この関数は *、(x* - 1) の階乗の対数を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**ログ 1p**,**ログ1pf**,**ログ1pl**|\<math.h>|\<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[log2、log2f、log2l](log2-log2f-log2l.md)<br/>
[log、logf、log10、log10f](log-logf-log10-log10f.md)<br/>
