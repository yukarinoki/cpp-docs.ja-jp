---
title: nearbyint、nearbyintf、nearbyintl
description: Nearbyint、nearbyintf、および nearbyintl の API リファレンス指定された浮動小数点値を整数に丸め、その値を浮動小数点形式で返します。
ms.date: 9/1/2020
api_name:
- nearbyint
- nearbyintf
- nearbyintl
- _o_nearbyint
- _o_nearbyintf
- _o_nearbyintl
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
- nearbyint
- nearbyintf
- nearbyintl
- math/nearbyint
- math/narbyintf
- math/narbyintl
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
ms.openlocfilehash: 9717559518032c6f1f2126c7ded7cb90603bce64
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556386"
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint、nearbyintf、nearbyintl

指定の浮動小数点値を整数に丸め、浮動小数点形式でその値を返します。

## <a name="syntax"></a>構文

```C
double nearbyint( double x );
float nearbyintf( float x );
long double nearbyintl( long double x );
#define nearbyint( X ) // Requires C11 or higher

float nearbyint( float x ); //C++ only
long double nearbyint( long double x ); //C++ only
```

### <a name="parameters"></a>パラメーター

*閉じる*\
丸める値。

## <a name="return-value"></a>戻り値

成功した場合は、 [fegetround](fegetround-fesetround2.md)によって報告される現在の丸め形式を使用して、最も近い整数に丸められた*x*を返します。 それ以外の場合は、関数から次の値のいずれかが返されます。

|問題|戻り値|
|-----------|------------|
|*x* = ±無限大|±無限大、未変更|
|*x* = ±0|±0、未変更|
|*x* = NaN|NaN|

エラーは [_matherr](matherr.md)によって報告されません。具体的には、この関数は **FE_INEXACT** 例外を報告しません。

## <a name="remarks"></a>解説

この関数と [rint](rint-rintf-rintl.md) の主な違いは、この関数では、不正確な浮動小数点例外が発生しないことです。

浮動小数点の最大値は正確な整数であるため、この関数が単独でオーバーフローすることはありません。むしろ、使用する関数のバージョンによっては、出力で戻り値がオーバーフローすることがあります。

C++ ではオーバーロードが可能であるため、またはパラメーターを受け取って返す **nearbyint** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き \<tgmath.h> 、 **nearbyint** は常に2つの double 値を受け取り、double 値を返します。

マクロを使用する場合 \<tgmath.h> `nearbyint()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**nearbyint**、 **nearbyintf**、 **nearbyintl**|\<math.h>|\<cmath> または \<math.h>|
|**nearbyint** マクロ | \<tgmath.h> ||

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[数値演算と浮動小数点のサポート](../floating-point-support.md)<br/>
