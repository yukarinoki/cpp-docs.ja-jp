---
title: fdim、fdimf、fdiml | Microsoft ドキュメント
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- fdim
- fdimf
- fdiml
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
- fdim
- fdimf
- fdiml
- math/fdim
- math/fdimf
- math/fdiml
dev_langs:
- C++
helpviewer_keywords:
- fdim function
- fdimf function
- fdiml function
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cdcad02c94717715fdda1b3a9d2e820fc16d0bf4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397507"
---
# <a name="fdim-fdimf-fdiml"></a>fdim、fdimf、fdiml

1 番目と 2 番目の値の間の正の値の差を求めます。

## <a name="syntax"></a>構文

```C
double fdim(
   double x,
   double y
);

float fdim(
   float x,
   float y
); //C++ only

long double fdim(
   long double x,
   long double y
); //C++ only

float fdimf(
   float x,
   float y
);

long double fdiml(
   long double x,
   long double y
);

```

### <a name="parameters"></a>パラメーター

*x*<br/>
最初の値。

*y*<br/>
2 番目の値。

## <a name="return-value"></a>戻り値

正の値の差を返します*x*と*y*:

|戻り値|シナリオ|
|------------------|--------------|
|x-y|x > y の場合|
|0|x <= y の場合|

それ以外の場合は、次のエラーのいずれかを返すことがあります。

|懸案事項|Return|
|-----------|------------|
|オーバーフロー範囲エラー|+HUGE_VAL、+HUGE_VALF、または +HUGE_VALL|
|アンダーフロー範囲エラー|丸めた後の正確な値|
|*x*または*y* nan|NaN|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>コメント

C++ では、オーバー ロードできるよう、ためのオーバー ロードを呼び出すことができます**fdim**を受け取り、返します**float**と**長い****二重**型です。 C プログラムでは、 **fdim**常に受け取りを返す、**二重**です。

この関数は NaN 処理を除くと同じで、`fmax(x - y, 0)`です。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fdim**、 **fdimf**、 **fdiml**|\<math.h>|\<cmath>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[fmax、fmaxf、fmaxl](fmax-fmaxf-fmaxl.md)<br/>
[abs、labs、llabs、_abs64](abs-labs-llabs-abs64.md)<br/>
