---
title: _cabs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _cabs
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
- cabsl
- _cabs
- _cabsl
dev_langs:
- C++
helpviewer_keywords:
- cabs function
- cabsl function
- absolute values
- _cabsl function
- _cabs function
- calculating absolute values
ms.assetid: fea292ee-1a39-4a0a-b416-4a189346ff26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80ea966b748407d51283823073a0c10a40717cf5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393538"
---
# <a name="cabs"></a>_cabs

複素数の絶対値を計算します。

## <a name="syntax"></a>構文

```C
double _cabs(
   struct _complex z
);
```

### <a name="parameters"></a>パラメーター

*z*<br/>
複素数。

## <a name="return-value"></a>戻り値

**_cabs**正常終了した場合、その引数の絶対値を返します。 オーバーフローについては、 **_cabs**返します**HUGE_VAL**設定と**errno**に**ERANGE**です。 エラー処理は [_matherr](matherr.md) で変更できます。

## <a name="remarks"></a>コメント

**_Cabs**関数型の構造にする必要があります複素数の絶対値を計算する[_complex型](../../c-runtime-library/standard-types.md)です。 構造体*z*が実数部から成る*x*と虚数*y*です。 呼び出し **_cabs**と等価の式の値を生成する`sqrt( z.x * z.x + z.y * z.y )`です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_cabs**|\<math.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_cabs.c
// Using _cabs, this program calculates
// the absolute value of a complex number.

#include <math.h>
#include <stdio.h>

int main( void )
{
   struct _complex number = { 3.0, 4.0 };
   double d;

   d = _cabs( number );
   printf( "The absolute value of %f + %fi is %f\n",
           number.x, number.y, d );
}
```

```Output
The absolute value of 3.000000 + 4.000000i is 5.000000
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[abs、labs、llabs、_abs64](abs-labs-llabs-abs64.md)<br/>
[fabs、fabsf、fabsl](fabs-fabsf-fabsl.md)   