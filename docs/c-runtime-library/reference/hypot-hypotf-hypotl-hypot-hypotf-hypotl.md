---
title: hypot、hypotf、hypotl、_hypot、_hypotf、_hypotl
ms.date: 4/2/2020
api_name:
- _hypotf
- hypot
- hypotf
- _hypot
- _hypotl
- hypotl
- _o__hypot
- _o__hypotf
- _o_hypot
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
- hypotf
- hypotl
- _hypotl
- hypot
- _hypot
- _hypotf
helpviewer_keywords:
- hypotenuse calculation
- hypot function
- hypotf function
- triangles, calculating hypotenuse
- hypotl function
- calculating hypotenuses
- _hypot function
ms.assetid: 6a13887f-bd53-43fc-9d77-5b42d6e49925
ms.openlocfilehash: 16db920d6e7d3836eb4a395b2029e2f9329f2681
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919841"
---
# <a name="hypot-hypotf-hypotl-_hypot-_hypotf-_hypotl"></a>hypot、hypotf、hypotl、_hypot、_hypotf、_hypotl

斜辺を計算します。

## <a name="syntax"></a>構文

```C
double hypot(
   double x,
   double y
);
float hypotf(
   float x,
   float y
);
long double hypotl(
   long double x,
   long double y
);
double _hypot(
   double x,
   double y
);
float _hypotf(
   float x,
   float y
);
long double _hypotl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>パラメーター

*x*、 *y*<br/>
浮動小数点値。

## <a name="return-value"></a>戻り値

成功した場合、 **hypot**は斜辺の長さを返します。オーバーフローの場合、 **hypot**は INF (無限大) を返し、 **Errno**変数は**ERANGE**に設定されます。 **_Matherr**を使用すると、エラー処理を変更できます。

リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>解説

**Hypot**関数は、2辺の*x*と*y*の長さ (つまり、 *x*<sup>2</sup> + *y*<sup>2</sup>の平方根) を指定して、直角三角形の斜辺の長さを計算します。

以前の標準との互換性のために、先頭にアンダースコアがある関数のバージョンが用意されています。 これらの動作は、先頭にアンダースコアがないバージョンと同じです。 新しいコードには、先頭にアンダースコアがないバージョンを使用することをお勧めします。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**hypot**、 **hypotf**、 **hypotl**、 **_hypot**、 **_hypotf**、 **_hypotl**|\<math.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_hypot.c
// This program prints the hypotenuse of a right triangle.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 3.0, y = 4.0;

   printf( "If a right triangle has sides %2.1f and %2.1f, "
           "its hypotenuse is %2.1f\n", x, y, _hypot( x, y ) );
}
```

```Output
If a right triangle has sides 3.0 and 4.0, its hypotenuse is 5.0
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[_cabs](cabs.md)<br/>
[_matherr](matherr.md)<br/>
