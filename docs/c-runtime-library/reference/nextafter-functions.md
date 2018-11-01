---
title: nextafter、nextafterf、nextafterl、_nextafter、_nextafterf、nexttoward、nexttowardf、nexttowardl
ms.date: 04/05/2018
apiname:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
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
ms.openlocfilehash: 0e0a60dc9f7c068d8c18c10f3c6b819b9e06d3b7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444859"
---
# <a name="nextafter-nextafterf-nextafterl-nextafter-nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter、nextafterf、nextafterl、_nextafter、_nextafterf、nexttoward、nexttowardf、nexttowardl

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

*x*<br/>
開始する浮動小数点値。

*y*<br/>
移動する浮動小数点値。

## <a name="return-value"></a>戻り値

戻り値の型の後の次の表現可能な浮動小数点値を返します*x*の方向に*y*します。 場合*x*と*y*が等しいか、関数を返します*y*, ない例外をトリガーすると、戻り値の型に変換されます。 場合*x*が等しくない*y*、され、結果は、denormal または 0 の場合、 **FE_UNDERFLOW**と**FE_INEXACT**浮動小数点例外状態設定され、正しい結果が返されます。 いずれか*x*または*y*が NAN の場合、戻り値は入力 Nan のいずれか。 場合*x*が有限し、結果が無限、または型で表現できない、正しく署名された infinity または NAN が返されます、 **FE_OVERFLOW**と**FE_INEXACT**浮動小数点例外状態を設定、および**errno**に設定されている**ERANGE**します。

## <a name="remarks"></a>Remarks

**Nextafter**と**nexttoward**関数ファミリはそれと同等のパラメーターの型を除く*y*します。 場合*x*と*y*が返される値が等しい、 *y*戻り値の型に変換します。

C++ では、オーバー ロードを含める場合ため\<cmath > のオーバー ロードを呼び出すことができます**nextafter**と**nexttoward**を返す**float**と**長い****二重**型。 C プログラムで**nextafter**と**nexttoward**常に返す**二重**します。

**_Nextafter**と **_nextafterf**関数は、Microsoft 固有の仕様。 **_Nextafterf**関数は、x64 コンパイルするときにのみ使用できます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------------|-------------------------------|
|**nextafter**、 **nextafterf**、 **nextafterl**、 **_nextafterf**、 **nexttoward**、 **nexttowardf**、 **nexttowardl**|\<math.h>|\<math.h> または \<cmath>|
|**_nextafter**|\<float.h>|\<float.h> または \<cfloat>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
