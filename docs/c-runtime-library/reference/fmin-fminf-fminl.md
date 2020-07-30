---
title: fmin、fminf、fminl
ms.date: 04/05/2018
api_name:
- fmin
- fminf
- fminl
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
- fmin
- fminf
- fminl
- math/fmin
- math/fminf
- math/fminl
helpviewer_keywords:
- fmin function
- fminf function
- fminl function
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
ms.openlocfilehash: d6cd16c298c3f4bedb8064d66efd2d4bbe20c22b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216987"
---
# <a name="fmin-fminf-fminl"></a>fmin、fminf、fminl

指定された 2 つの値のうち、小さい方を特定します。

## <a name="syntax"></a>構文

```C
double fmin(
   double x,
   double y
);

float fmin(
   float x,
   float y
); //C++ only

long double fmin(
   long double x,
   long double y
); //C++ only

float fminf(
   float x,
   float y
);

long double fminl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
比較する最初の値です。

*y*<br/>
比較する 2 番目の値です。

## <a name="return-value"></a>戻り値

成功した場合、 *x*または*y*の小さい方を返します。

|入力|結果|
|-----------|------------|
|*x*は NaN|*y*|
|*y*は NaN|*x*|
|*x*と*y*は NaN|NaN|

関数は、 [_matherr](matherr.md)が呼び出されず、浮動小数点例外が発生することも、 **errno**の値を変更することもありません。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、およびの型を受け取って返す**fmin**のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、 **fmin**は常にを受け取り、を返し **`double`** ます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**fmin**、 **fminf**、 **fminl**|40u-c\<math.h><br />C++: \<math.h> または\<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[fmax、fmaxf、fmaxl](fmax-fmaxf-fmaxl.md)<br/>
