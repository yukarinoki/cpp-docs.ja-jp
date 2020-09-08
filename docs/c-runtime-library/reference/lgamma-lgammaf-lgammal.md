---
title: lgamma、lgammaf、lgammal
description: Lgamma、lgammaf、lgammal の API リファレンス指定された値のガンマ関数の絶対値の自然対数を決定します。
ms.date: 9/1/2020
api_name:
- lgamma
- lgammaf
- lgammal
- _o_lgamma
- _o_lgammaf
- _o_lgammal
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
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
ms.openlocfilehash: 202250f3575f61fcef1cf29a687b8fdf36e6db33
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555398"
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma、lgammaf、lgammal

指定した値のガンマ関数の絶対値の自然対数を決定します。

## <a name="syntax"></a>構文

```C
double lgamma( double x );
float lgammaf( float x );
long double lgammal( long double x );
#define lgammal(X) // Requires C11 or higher

float lgamma( float x ); //C++ only
long double lgamma( long double x ); //C++ only
```

### <a name="parameters"></a>パラメーター

*閉じる*\
計算される値です。

## <a name="return-value"></a>戻り値

成功した場合は、 *x*のガンマ関数の絶対値の自然対数を返します。

|問題|戻り値|
|-----------|------------|
|*x* = NaN|NaN|
|*x* = ±0|+INFINITY|
|*x*= 負の整数|+INFINITY|
|±無限大|+INFINITY|
|極エラー|+HUGE_VAL、+HUGE_VALF、または +HUGE_VALL|
|オーバーフロー範囲エラー|± HUGE_VAL、± HUGE_VALF、または± HUGE_VALL|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、型と型を受け取って返す **lgamma** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 \<tgmath.h> **lgamma** は常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `lgamma()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

X が有理数の場合、この関数は (x-1) の階乗の対数を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**lgamma**、 **lgammaf**、 **lgammal**|\<math.h>|\<cmath>|
|**lgamma** マクロ | \<tgmath.h> ||

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[tgamma、tgammaf、tgammal](tgamma-tgammaf-tgammal.md)<br/>
