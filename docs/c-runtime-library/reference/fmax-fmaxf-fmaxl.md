---
title: fmax、fmaxf、fmaxl
description: Fmax、fmaxf、fmaxl の API リファレンス2つの数値のうち、大きい方を決定します。
ms.date: 9/1/2020
api_name:
- fmax
- fmaxf
- fmaxl
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
- fmax
- fmaxf
- fmaxl
- math/fmax
- math/fmaxf
- math/fmaxl
helpviewer_keywords:
- fmax function
- fmaxf function
- fmaxl function
ms.assetid: a773ccf7-495e-4a9a-8c6d-dfb53e341e35
ms.openlocfilehash: 4f38db64b30598e7cfb4eb4d0f57dccf257dabc5
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556685"
---
# <a name="fmax-fmaxf-fmaxl"></a>fmax、fmaxf、fmaxl

指定された 2 つの数値のうち、大きい方を特定します。

## <a name="syntax"></a>構文

```C
double fmax(
   double x,
   double y
);

float fmax(
   float x,
   float y
); //C++ only

long double fmax(
   long double x,
   long double y
); //C++ only

float fmaxf(
   float x,
   float y
);

long double fmaxl(
   long double x,
   long double y
);

#define fmax(X, Y) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*閉じる*\
比較する最初の値です。

*前年*\
比較する 2 番目の値です。

## <a name="return-value"></a>戻り値

成功した場合、 *x* または *y*のうち、大きい方を返します。 返される値は正確であり、どの丸め処理の形式にも依存しません。

それ以外の場合は、次の値のいずれかを返します。

|問題|戻り値|
|-----------|------------|
|*x* = NaN|*y*|
|*y* = NaN|*x*|
|*x* および *y* = NaN|NaN|

この関数では、[_matherr](matherr.md) で指定されたエラーを使用しません。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、型と型を受け取って返す fmax のオーバーロードを呼び出すことができ `float` `long double` ます。 C プログラムでは、 \<tgmath.h> この関数を呼び出すためにマクロを使用している場合を除き、は `fmax` 常に double を取得して返します。

マクロを使用する場合 \<tgmath.h> `fmax()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fmax**、 **fmaxf**、 **fmaxl**|\<math.h>|\<cmath> または \<math.h>|
|**fmax** マクロ | \<tgmath.h> ||

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[fmin、fminf、fminl](fmin-fminf-fminl.md)<br/>
