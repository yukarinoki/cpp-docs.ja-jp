---
title: nextafter、nextafterf、nextafterl、_nextafter、_nextafterf、nexttoward、nexttowardf、nexttowardl
ms.date: 4/2/2020
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
- api-ms-win-crt-private-l1-1-0
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
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
ms.openlocfilehash: 7b1416147ed000dd3dd9a13bd52e41a474a8e9d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338561"
---
# <a name="nextafter-nextafterf-nextafterl-_nextafter-_nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter、nextafterf、nextafterl、_nextafter、_nextafterf、nexttoward、nexttowardf、nexttowardl

次の表現可能な浮動小数点値を返します。

## <a name="syntax"></a>構文

```C
double nextafter( double x, double y );
float nextafterf( float x, float y );
long double nextafterl( long double x, long double y );

double _nextafter( double x, double y );
float _nextafterf( float x, float y ); /* x64 only */

double nexttoward( double x, long double y );
float nexttowardf( float x, long double y );
long double nexttowardl( long double x, long double y );
```

```cpp
float nextafter( float x, float y ); /* C++ only, requires <cmath> */
long double nextafter( long double x, long double y ); /* C++ only, requires <cmath> */

float nexttoward( float x, long double y ); /* C++ only, requires <cmath> */
long double nexttoward( long double x, long double y ); /* C++ only, requires <cmath> */
```

### <a name="parameters"></a>パラメーター

*X*<br/>
開始する浮動小数点値。

*Y*<br/>
移動する浮動小数点値。

## <a name="return-value"></a>戻り値

*y*の方向の*x*の後の戻り値型の次の表現可能な浮動小数点値を返します。 *x*と*y*が等しい場合、関数は*y*を返し、戻り値の型に変換され、例外は発生しません。 *x*が*y*と等しくならず、結果が非正規値またはゼロの場合 **、FE_UNDERFLOW**と**FE_INEXACT**浮動小数点例外状態が設定され、正しい結果が返されます。 *x*または*y*が NAN である場合、戻り値は入力 NAN のいずれかになります。 *x*が有限であり、その結果が無限であるか、その型で表現できない場合、正しく符号付きの無限大または NAN が返され **、FE_OVERFLOW**と**FE_INEXACT**浮動小数点例外状態が設定され **、errno**が**ERANGE**に設定されます。

## <a name="remarks"></a>解説

関数ファミリの**次**と**次の**方は *、y*のパラメータタイプを除いて同じです。 *x*と*y*が等しい場合、返される値は*戻*り値の型に変換されます。

C++ ではオーバーロードが可能なので、cmath>を\<含める場合は、その戻り値**float**型と**long** **double**型**に対して****次**のオーバーロードを呼び出すことができます。 Cプログラムでは、**次の次**と**次の方は**常に**二重**を返します。

**_nextafter**および **_nextafterf**機能は、マイクロソフト固有のものです。 **_nextafterf**関数は、x64 用にコンパイルする場合にのみ使用できます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------------|-------------------------------|
|**次に**,**次のアフターフ**,**次の後に**, **_nextafterf**,**次へ ,** 次**へ方へ ,****次へ方へ**|\<math.h>|\<math.h> または \<cmath>|
|**_nextafter**|\<float.h>|\<float.h> または \<cfloat>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
