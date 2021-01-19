---
title: nextafter、nextafterf、nextafterl、_nextafter、_nextafterf、nexttoward、nexttowardf、nexttowardl
description: Nextafter、nextafterf、nextafterl、_nextafter、_nextafterf、nextafter、nexttowardf、および nexttowardl の API リファレンスこれは、次の表現可能な浮動小数点値を返します。
ms.date: 1/15/2021
api_name:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
- _o__nextafter
- _o_nextafter
- _o_nextafterf
- _o_nextafterl
- _o_nexttoward
- _o_nexttowardf
- _o_nexttowardl
- _o__nextafterf
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.openlocfilehash: 664ddb204fa089f83acebf6a9042b17a776ea306
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564135"
---
# <a name="nextafter-nextafterf-nextafterl-_nextafter-_nextafterf-nexttoward-nexttowardf-nexttowardl"></a>`nextafter`, `nextafterf`, `nextafterl`, `_nextafter`, `_nextafterf`, `nexttoward`, `nexttowardf`, `nexttowardl`

次の表現可能な浮動小数点値を返します。

## <a name="syntax"></a>構文

```C
double nextafter( double x, double y );
float nextafterf( float x, float y );
long double nextafterl( long double x, long double y );

double _nextafter( double x, double y );
float _nextafterf( float x, float y ); /* x64 only */

#define nextafter(X, Y) // Requires C11 or higher

double nexttoward( double x, long double y );
float nexttowardf( float x, long double y );
long double nexttowardl( long double x, long double y );

#define nexttoward(X, Y) // Requires C11 or higher

float nextafter( float x, float y ); /* C++ only, requires <cmath> */
long double nextafter( long double x, long double y ); /* C++ only, requires <cmath> */

float nexttoward( float x, long double y ); /* C++ only, requires <cmath> */
long double nexttoward( long double x, long double y ); /* C++ only, requires <cmath> */
```

### <a name="parameters"></a>パラメーター

*`x`*\
開始する浮動小数点値。

*`y`*\
移動する浮動小数点値。

## <a name="return-value"></a>戻り値

の後に戻り値の型の次の表現可能な浮動小数点値を返し *`x`* *`y`* ます。 *`x`* と *`y`* が等しい場合、関数は戻り値の *`y`* 型に変換されたを返します。例外は発生しません。 *`x`* がと等しくなく、 *`y`* 結果が denormal または0の場合、 **`FE_UNDERFLOW`** および **`FE_INEXACT`** 浮動小数点例外の状態が設定され、正しい結果が返されます。 またはのいずれかが NAN の場合、 *`x`* *`y`* 戻り値は入力 nan の1つになります。 *`x`* が有限で、結果が無限であるか、型で表現できない場合は、正しく符号付き無限大または NAN が返され、 **`FE_OVERFLOW`** と **`FE_INEXACT`** 浮動小数点例外状態が設定され、 **`errno`** がに設定され **`ERANGE`** ます。

## <a name="remarks"></a>注釈

**`nextafter`** と **`nexttoward`** の各関数ファミリは、のパラメーターの型を除き、同じです *`y`* 。 *`x`* と *`y`* が等しい場合、返される値は *`y`* 戻り値の型に変換されます。

C++ ではオーバーロードが可能であるため、を含めると、 `<cmath>` および型を返すとのオーバーロードを呼び出すことができ **`nextafter`** **`nexttoward`** **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 `<tgmath.h>` **`nextafter`** **`nexttoward`** 常にを返し **`double`** ます。

`<tgmath.h>` `nextafter()` マクロまたはマクロを使用する場合 `nexttoward()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

**_Nextafter** 関数と **_nextafterf** 関数は、Microsoft 固有の関数です。 **_Nextafterf** 関数は、x64 用にコンパイルする場合にのみ使用できます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------------|-------------------------------|
|**`nextafter`**, **`nextafterf`**, **`nextafterl`**, **`_nextafterf`**, **`nexttoward`**, **`nexttowardf`**, **`nexttowardl`**|`<math.h>`|`<math.h>` または `<cmath>`|
|**`_nextafter`**|`<float.h>`|`<float.h>` または `<cfloat>`|
|**`nextafter`** マクロ、  **`nexttoward`** マクロ| `<tgmath.h>` ||

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)\
[`isnan`, `_isnan`, `_isnanf`](isnan-isnan-isnanf.md)
