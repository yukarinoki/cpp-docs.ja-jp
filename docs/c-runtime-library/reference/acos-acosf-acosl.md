---
title: acos、acosf、acosl
ms.date: 4/2/2020
api_name:
- acosf
- acos
- acosl
- _o_acos
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
- acos
- acosl
- acosf
- math/acosf
- math/acosl
helpviewer_keywords:
- acos function
- acosl function
- acosf function
- trigonometric functions
- arccosine function
ms.assetid: 00b89c48-8faf-4824-aa95-fa4349a4975d
ms.openlocfilehash: b6188c585d2f3b7f2bce1a50569e6bae60ee4942
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220770"
---
# <a name="acos-acosf-acosl"></a>acos、acosf、acosl

アークコサインを計算します。

## <a name="syntax"></a>構文

```C
double acos( double x );
float acosf( float x );
long double acosl( long double x );
```

```cpp
float acos( float x );   // C++ only
long double acos( long double x );   // C++ only
```

### <a name="parameters"></a>パラメーター

*x*<br/>
アークコサイン (逆余弦) を計算する-1 ~ 1 の範囲の値。

## <a name="return-value"></a>戻り値

**Acos**関数は、0 ~ πラジアンの範囲の*x*のアークコサインを返します。

既定では、 *x*が-1 より小さいか、または1より大きい場合、 **acos**は不定を返します。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± ∞|INVALID|_DOMAIN|
|± QNAN、IND|なし|_DOMAIN|
|&#124;x&#124;>1|INVALID|_DOMAIN|

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、型と型を受け取って返す**acos**のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、 **acos**は常にを受け取り、を返し **`double`** ます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|省略可能なヘッダー|
|-------------|---------------------|----------------------|
|**acos**、 **acosf**、 **acosl**|\<math.h>|\<errno.h>|

## <a name="example"></a>例

このプログラムは、-1 ～ 1 の範囲の値の入力を求めます。 入力値がこの範囲外の場合、`_DOMAIN` エラー メッセージを生成します。 有効な値が入力された場合、プログラムはその値のアークサインとアークコサインを出力します。

```C
// crt_asincos.c
// arguments: 0

#include <math.h>
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main( int ac, char* av[] )
{
    double  x,
            y;
    errno_t err;

    // argument checking
    if (ac != 2)
    {
        fprintf_s( stderr, "Usage: %s <number between -1 and 1>\n",
                   av[0]);
        return 1;
    }

    // Convert argument into a double value
    if ((err = sscanf_s( av[1], "%lf", &x )) != 1)
    {
        fprintf_s( stderr, "Error converting argument into ",
                   "double value.\n");
        return 1;
    }

    // Arcsine of X
    y = asin( x );
    printf_s( "Arcsine of %f = %f\n", x, y );

    // Arccosine of X
    y = acos( x );
    printf_s( "Arccosine of %f = %f\n", x, y );
}
```

```Output
Arcsine of 0.000000 = 0.000000
Arccosine of 0.000000 = 1.570796
```

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[asin、asinf、asinl](asin-asinf-asinl.md)<br/>
[atan、atanf、atanl、atan2、atan2f、atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos、cosf、cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin、sinf、sinl](sin-sinf-sinl.md)<br/>
[tan、tanf、tanl](tan-tanf-tanl.md)
