---
title: fmin、fminf、fminl
description: Fmin、fminf、および fminl の API リファレンス2つの値のうち小さい方を決定します。
ms.date: 9/1/2020
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
ms.openlocfilehash: 6a070835d809c6adcb5b7bfd57b5373886b348ca
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556711"
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

#define fmin(x) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*閉じる*\
比較する最初の値です。

*前年*\
比較する 2 番目の値です。

## <a name="return-value"></a>戻り値

成功した場合、 *x* または *y*の小さい方を返します。

|入力|結果|
|-----------|------------|
|*x* は NaN|*y*|
|*y* は NaN|*x*|
|*x* と *y* は NaN|NaN|

関数は、 [_matherr](matherr.md) が呼び出されず、浮動小数点例外が発生することも、 **errno**の値を変更することもありません。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、およびの型を受け取って返す **fmin** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、 \<tgmath.h> この関数を呼び出すためにマクロを使用している場合を除き、 **fmin** は常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `fmin()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**fmin**、 **fminf**、 **fminl**|40u-c \<math.h><br />C++: \<math.h> または \<cmath>|
|**fmin** マクロ | \<tgmath.h> ||

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[fmax、fmaxf、fmaxl](fmax-fmaxf-fmaxl.md)<br/>
