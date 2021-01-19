---
title: asin、asinf、asinl
description: アークサイン、asinf、および asinl の API リファレンス浮動小数点値のアークサインを計算する。
ms.date: 1/15/2021
api_name:
- asinf
- asinl
- asin
- _o_asin
- _o_asinf
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
- asin
- asinl
- asinf
helpviewer_keywords:
- asin function
- asinl function
- asinf function
- trigonometric functions
- arcsine function
ms.openlocfilehash: 04b68e9b5933d763cecbdc06af3e34a5b7c01223
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564044"
---
# <a name="asin-asinf-asinl"></a>`asin`, `asinf`, `asinl`

アークサインを計算します。

## <a name="syntax"></a>構文

```C
double asin( double x );
float asinf ( float x );
long double asinl( long double x );
#define asin(X) // Requires C11 or higher

float asin( float x );  // C++ only
long double asin( long double x );  // C++ only
```

### <a name="parameters"></a>パラメーター

*`x`*\
アークサインが計算される値。

## <a name="return-value"></a>戻り値

関数は、 **`asin`** *`x`* -π/2 ~ π/2 ラジアンの範囲のアークサイン (逆正弦関数) を返します。

既定では、 *`x`* が-1 未満または1より大きい場合、は **`asin`** 不定を返します。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± ∞|**`INVALID`**|**`_DOMAIN`**|
|± **`QNAN`**, **`IND`**|なし|**`_DOMAIN`**|
|&#124;x&#124;>1|**`INVALID`**|**`_DOMAIN`**|

## <a name="remarks"></a>注釈

C++ ではオーバーロードが可能であるため、との値を使用してのオーバーロードを呼び出すことができ **`asin`** **`float`** **`long double`** ます。 C プログラムでは、 `<tgmath.h>` この関数を呼び出すためにマクロを使用している場合を除き、は **`asin`** 常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 `<tgmath.h>` `asin()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------|-|
|**`asin`**, **`asinf`**, **`asinl`**|`<math.h>`|`<cmath>` または `<math.h>`|
|**`asin()`** マクロ | `<tgmath.h>` ||

## <a name="example"></a>例

詳細については、「」、「」を[参照して `acos` `acosf` `acosl` ください。 ](acos-acosf-acosl.md)

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)\
[`acos`, `acosf`, `acosl`](acos-acosf-acosl.md)\
[`atan`, `atanf`, `atanl`, `atan2`, `atan2f`, `atan2l`](atan-atanf-atanl-atan2-atan2f-atan2l.md)\
[`cos`, `cosf`, `cosl`](cos-cosf-cosl.md)\
[`_matherr`](matherr.md)\
[`sin`, `sinf`, `sinl`](sin-sinf-sinl.md)\
[`tan`, `tanf`, `tanl`](tan-tanf-tanl.md)