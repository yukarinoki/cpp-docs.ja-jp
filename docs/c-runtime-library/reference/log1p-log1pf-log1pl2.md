---
title: log1p、log1pf、log1pl2 | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- log1p
- log1pf
- log1pl
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 650fb8f7567b4f2f3b0b9032397c2b54a99013dd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402749"
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

成功した場合、自然を返します (基本 -*e*) のログ (*x* + 1)。

それ以外の場合は、次の値のいずれかを返します。

|入力|結果|SEH 例外|errno|
|-----------|------------|-------------------|-----------|
|+inf|+inf|||
|非正規化数|入力と同じ値。|UNDERFLOW||
|±0|入力と同じ値。|||
|-1|-inf|DIVBYZERO|ERANGE|
|< -1|nan|INVALID|EDOM|
|-inf|nan|INVALID|EDOM|
|±SNaN|入力と同じ値。|INVALID||
|±QNaN、不定値|入力と同じ値。|||

**Errno**場合は、値を ERANGE に設定*x* -1 を = です。 **Errno**に値が設定されている**EDOM**場合*x* <-1 です。

## <a name="remarks"></a>コメント

**Log1p**関数を使用するよりもより正確になる可能性があります`log(x + 1)`とき*x*が 0 に近いです。

C++ では、オーバー ロードできるよう、ためのオーバー ロードを呼び出すことができます**log1p**を受け取り、返します**float**と**長い****二重**型です。 C プログラムでは、 **log1p**常に受け取りを返す、**二重**です。

場合*x*自然数は、この関数は、数値の階乗の対数を返します (*x* - 1)。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**log1p**、 **log1pf**、 **log1pl**|\<math.h>|\<cmath>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[log2、log2f、log2l](log2-log2f-log2l.md)<br/>
[log、logf、log10、log10f](log-logf-log10-log10f.md)<br/>
