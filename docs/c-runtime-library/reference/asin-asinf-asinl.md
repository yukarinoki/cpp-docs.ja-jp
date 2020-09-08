---
title: asin、asinf、asinl
description: アークサイン、asinf、および asinl の API リファレンス浮動小数点値のアークサインを計算する。
ms.date: 08/31/2020
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
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
ms.openlocfilehash: 7167debcfb605ab05720d9441943439ea9982324
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556659"
---
# <a name="asin-asinf-asinl"></a>asin、asinf、asinl

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

*閉じる*\
アークサインが計算される値。

## <a name="return-value"></a>戻り値

**アーク**サイン関数は、-π/2 ~ π/2 ラジアンの範囲の*x*のアークサイン (逆正弦関数) を返します。

既定では、 *x* が-1 より小さいか、または1より大きい場合、 **アークサイン** は不定を返します。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± ∞|**無効です**|**_DOMAIN**|
|± **QNAN**、 **IND**|なし|**_DOMAIN**|
|&#124;x&#124;>1|**無効です**|**_DOMAIN**|

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、との値を使用して、 **アークサイン** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 \<tgmath.h> **アークサイン** は常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `asin()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------|-|
|**アークサイン**、 **asinf**、 **asinl**|\<math.h>|\<cmath> または \<math.h>|
|**アークサイン ()** マクロ | \<tgmath.h> ||

## <a name="example"></a>例

詳細については、「[acos、acosf、acosl](acos-acosf-acosl.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[acos、acosf、acosl](acos-acosf-acosl.md)<br/>
[atan、atanf、atanl、atan2、atan2f、atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos、cosf、cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin、sinf、sinl](sin-sinf-sinl.md)<br/>
[tan、tanf、tanl](tan-tanf-tanl.md)<br/>
