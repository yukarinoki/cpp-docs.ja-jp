---
title: asin、asinf、asinl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- asinf
- asinl
- asin
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
- asin
- asinl
- asinf
dev_langs:
- C++
helpviewer_keywords:
- asin function
- asinl function
- asinf function
- trigonometric functions
- arcsine function
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee65e4c8ce884ac42de35a23c81dbf5009dd1185
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393278"
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

*x*<br/>
アークサインが計算される値。

## <a name="return-value"></a>戻り値

**Asin**のアークサイン (逆サ イン関数) を返します*x*範囲 - π/2 ~ π/2 ラジアンにします。

既定では場合、 *x*が-1 未満か、1 より大きい**asin**は不定値を返します。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± ∞|**無効です**|**_DOMAIN**|
|± **QNAN**、 **IND**|none|**_DOMAIN**|
|&#124;x&#124;>1|**無効です**|**_DOMAIN**|

## <a name="remarks"></a>コメント

C++ では、オーバー ロードできるよう、ためのオーバー ロードを呼び出すことができます**asin**で**float**と**長い****二重**値。 C プログラムでは、 **asin**常に受け取りを返す、**二重**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------|-|
|**asin**、 **asinf**、 **asinl**|\<math.h>|\<cmath> または \<math.h>|

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
