---
title: asin、asinf、asinl
ms.date: 4/2/2020
api_name:
- asinf
- asinl
- asin
- _o_asin
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
- asin
- asinl
- asinf
helpviewer_keywords:
- asin function
- asinl function
- asinf function
- trigonometric functions
- arcsine function
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
ms.openlocfilehash: 424fee6995fae4a7f878054ede1bb85d33d1706d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81334124"
---
# <a name="asin-asinf-asinl"></a>asin、asinf、asinl

アークサインを計算します。

## <a name="syntax"></a>構文

```C
double asin( double x );
float asinf ( float x );
long double asinl( long double x );
```

```cpp
float asin( float x );  // C++ only
long double asin( long double x );  // C++ only
```

### <a name="parameters"></a>パラメーター

*X*<br/>
アークサインが計算される値。

## <a name="return-value"></a>戻り値

**asin**関数は、-π/2 から π/2 ラジアンの範囲内の*x*のアークシン (逆正弦関数) を戻します。

デフォルトでは *、x*が -1 より小さいか 1 より大きい場合 **、asin**は無期限を返します。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± ∞|**無効です**|**_DOMAIN**|
|± **QNAN,IND** **IND**|none|**_DOMAIN**|
|&#124;x&#124;>1|**無効です**|**_DOMAIN**|

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能なため **、float**値と**長い****倍精度**浮動小数点値を使用して**asin**のオーバーロードを呼び出すことができます。 C プログラムでは **、asin**は常に二**重**を受け取り、返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------|-|
|**アシン**,**アシンフ**,**アシンル**|\<math.h>|\<cmath> または \<math.h>|

## <a name="example"></a>例

詳細については、「[acos、acosf、acosl](acos-acosf-acosl.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[acos、acosf、acosl](acos-acosf-acosl.md)<br/>
[atan、atanf、atanl、atan2、atan2f、atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos、cosf、cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin、sinf、sinl](sin-sinf-sinl.md)<br/>
[tan、tanf、tanl](tan-tanf-tanl.md)<br/>
