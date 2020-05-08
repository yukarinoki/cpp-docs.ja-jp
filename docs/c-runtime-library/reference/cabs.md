---
title: _cabs
ms.date: 4/2/2020
api_name:
- _cabs
- _o__cabs
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
- _cabs
helpviewer_keywords:
- cabs function
- absolute values
- _cabs function
- calculating absolute values
ms.assetid: fea292ee-1a39-4a0a-b416-4a189346ff26
ms.openlocfilehash: 6e769d2caf65ef3c084bcb6add701f78b03a1b17
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913349"
---
# <a name="_cabs"></a>_cabs

複素数の絶対値を計算します。

## <a name="syntax"></a>構文

```C
double _cabs(
   struct _complex z
);
```

### <a name="parameters"></a>パラメーター

*方向*<br/>
複素数。

## <a name="return-value"></a>戻り値

**_cabs**は、成功した場合、引数の絶対値を返します。 オーバーフローの場合、 **_cabs**は**HUGE_VAL**を返し、 **errno**を**ERANGE**に設定します。 エラー処理は [_matherr](matherr.md) で変更できます。

## <a name="remarks"></a>解説

**_Cabs**関数は、複素数の絶対値を計算します。この値は[_complex](../../c-runtime-library/standard-types.md)型の構造体である必要があります。 構造体*z*は、実際のコンポーネント*x*と虚数成分*y*で構成されています。 **_Cabs**を呼び出すと、式`sqrt( z.x * z.x + z.y * z.y )`の値と等価の値が生成されます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_cabs**|\<math.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

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
