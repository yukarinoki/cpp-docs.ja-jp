---
title: trunc、truncf、truncl
description: Trunc、truncf、truncl の API リファレンス最も近い整数が、指定した浮動小数点値以下であるかどうかを判断します。
ms.date: 9/1/2020
api_name:
- trunc
- truncf
- truncl
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- trunc
- truncf
- truncl
- math/trunc
- math/truncf
- math/truncl
helpviewer_keywords:
- trunc function
- truncf function
- truncl function
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
ms.openlocfilehash: f1f2fde95bb944aa461bb95a9ad30fac204552b9
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556633"
---
# <a name="trunc-truncf-truncl"></a>trunc、truncf、truncl

指定した浮動小数点以下に最も近い整数を指定します。

## <a name="syntax"></a>構文

```C
double trunc( double x );
long double truncl( long double x );
#define trunc(X) // Requires C11 or higher

long double trunc( long double x ); //C++ only
float trunc( float x ); //C++ only
```

### <a name="parameters"></a>パラメーター

*閉じる*\
切り捨てる値。

## <a name="return-value"></a>戻り値

正常に終了した場合は、0の方向に丸められた *x*の整数値を返します。

それ以外の場合は、次のいずれかを返します。

|問題|戻り値|
|-----------|------------|
|*x* = ±無限大|x|
|*x* = ±0|x|
|*x* = NaN|NaN|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、型と型を受け取って返す **trunc** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、 \<tgmath.h> この関数を呼び出すためにマクロを使用している場合を除き、 **trunc** はを受け取り、を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `trunc()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

浮動小数点の最大値はちょうど整数であるため、この関数は単独ではオーバーフローしません。 ただし、整数型に値を返すことによって、関数のオーバーフローが発生する場合があります。

浮動小数点から整数に暗黙的に変換することで切り捨てることもできますが、これは対象の型に格納できる値に限ります。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**trunc**、 **truncf**、 **truncl**|\<math.h>|\<cmath>|
|**trunc** マクロ | \<tgmath.h> ||

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[floor、floorf、floorl](floor-floorf-floorl.md)<br/>
[ceil、ceilf、ceill](ceil-ceilf-ceill.md)<br/>
[round、roundf、roundl](round-roundf-roundl.md)<br/>
