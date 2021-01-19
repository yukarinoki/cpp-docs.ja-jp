---
title: cosh、coshf、coshl
description: Cosh、coshf、coshf の API リファレンス浮動小数点値のハイパーボリックコサインを計算する。
ms.date: 1/15/2021
api_name:
- cosh
- coshf
- coshl
- _o_cosh
- _o_coshf
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
- cosh
- coshf
- coshl
helpviewer_keywords:
- cosh function
- coshf function
- coshl function
- trigonometric functions
- hyperbolic functions
ms.openlocfilehash: c010dcdc30b16f94f55fca99d67b58e5c19370c7
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564096"
---
# <a name="cosh-coshf-coshl"></a>`cosh`, `coshf`, `coshl`

ハイパーボリックコサインを計算します。

## <a name="syntax"></a>構文

```C
double cosh( double x );
float coshf( float x );
long double coshl( long double x );
#define cosh(X) // Requires C11 or higher

float cosh( float x );  // C++ only
long double cosh( long double x );  // C++ only
```

### <a name="parameters"></a>パラメーター

*`x`*\
角度 (ラジアン)。

## <a name="return-value"></a>戻り値

のハイパーボリックコサイン *`x`* 。

既定では、、、またはの呼び出しで結果が大きすぎる場合、 **`cosh`** **`coshf`** **`coshl`** 関数はを返し、 **`HUGE_VAL`** **`errno`** をに設定 **`ERANGE`** します。

|入力|SEH 例外|`Matherr` 例外的|
|-----------|-------------------|-----------------------|
|± **`QNAN`**, **`IND`**|なし|**`_DOMAIN`**|
|*`x`* ≥ 7.104760 e + 002|**`INEXACT`**+**`OVERFLOW`**|**`OVERFLOW`**|

## <a name="remarks"></a>注釈

C++ ではオーバーロードが可能であるため、 **`cosh`** またはの値を受け取って返すのオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、 `<tgmath.h>` この関数を呼び出すためにマクロを使用している場合を除き、は **`cosh`** 常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 `<tgmath.h>` `cosh()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------|-|
|**`coshf`**, **`cosl`**, **`coshl`**|`<math.h>`|`<cmath>` または `<math.h>`|
|**`coshf()`** マクロ | `<tgmath.h>` ||

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

「」、「 [ `sinh` 」 `sinhf` `sinhl` ](sinh-sinhf-sinhl.md)の例を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)\
[`acosh, acoshf, acoshl`](acosh-acoshf-acoshl.md)\
[`asinh, asinhf, asinhl`](asinh-asinhf-asinhl.md)\
[`atanh, atanhf, atanhl`](atanh-atanhf-atanhl.md)\
[`_matherr`](matherr.md)\
[`sinh, sinhf, sinhl`](sinh-sinhf-sinhl.md)\
[`tanh, tanhf, tanhl`](tanh-tanhf-tanhl.md)