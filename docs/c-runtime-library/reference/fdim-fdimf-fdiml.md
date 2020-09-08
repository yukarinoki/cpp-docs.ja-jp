---
title: fdim、fdimf、fdiml
description: Fdim、fdimf、および fdiml の API リファレンス2つの値の間の正の差を決定します。
ms.date: 9/1/2020
api_name:
- fdim
- fdimf
- fdiml
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fdim
- fdimf
- fdiml
- math/fdim
- math/fdimf
- math/fdiml
helpviewer_keywords:
- fdim function
- fdimf function
- fdiml function
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
ms.openlocfilehash: 406fc5cfe543aa0865760df9ff780c62e78510fc
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89554787"
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

#define fdim(X) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*閉じる*\
最初の値。

*前年*\
2 番目の値。

## <a name="return-value"></a>戻り値

*X*と*y*の間の正の差を返します。

|戻り値|通信の種類|
|------------------|--------------|
|x-y|x > y の場合|
|0|x <= y の場合|

それ以外の場合は、次のエラーのいずれかを返すことがあります。

|問題|戻り値|
|-----------|------------|
|オーバーフロー範囲エラー|+HUGE_VAL、+HUGE_VALF、または +HUGE_VALL|
|アンダーフロー範囲エラー|丸めた後の正確な値|
|*x* または *y* が NaN|NaN|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、型と型を受け取って返す **fdim** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 \<tgmath.h> **fdim** は常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `fdim()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

NaN の処理を除き、この関数はと同じです `fmax(x - y, 0)` 。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fdim**、 **fdimf**、 **fdiml**|\<math.h>|\<cmath>|
|**fdim** マクロ | \<tgmath.h> ||

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[fmax、fmaxf、fmaxl](fmax-fmaxf-fmaxl.md)<br/>
[abs、labs、llabs、_abs64](abs-labs-llabs-abs64.md)<br/>
