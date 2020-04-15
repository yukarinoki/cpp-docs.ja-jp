---
title: nearbyint、nearbyintf、nearbyintl
ms.date: 4/2/2020
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 92e3a744ef8069d45733c06b7a2681905c3eab55
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338583"
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint、nearbyintf、nearbyintl

指定の浮動小数点値を整数に丸め、浮動小数点形式でその値を返します。

## <a name="syntax"></a>構文

```C
double nearbyint( double x );
float nearbyintf( float x );
long double nearbyintl( long double x );
```

```cpp
float nearbyint( float x ); //C++ only
long double nearbyint( long double x ); //C++ only
```

### <a name="parameters"></a>パラメーター

*X*<br/>
丸める値。

## <a name="return-value"></a>戻り値

成功した場合は、 [fegetround](fegetround-fesetround2.md)で報告されている現在の丸め形式を使用して *、x*を最も近い整数に丸めた値を返します。 それ以外の場合は、関数から次の値のいずれかが返されます。

|問題|戻り値|
|-----------|------------|
|*x* = ±無限大|±INFINITY、未変更|
|*x* = ±0|±0、未変更|
|*x* = NaN|(NaN)|

エラーは[_matherr](matherr.md)を通じて報告されません。具体的には、この関数は**FE_INEXACT**例外を報告しません。

## <a name="remarks"></a>解説

この関数と[rint](rint-rintf-rintl.md)の主な違いは、この関数が不正確な浮動小数点例外を発生させならない点です。

浮動小数点の最大値は正確な整数であるため、この関数が単独でオーバーフローすることはありません。むしろ、使用する関数のバージョンによっては、出力で戻り値がオーバーフローすることがあります。

C++ ではオーバーロードが可能なので **、float**または**long** **double**パラメータを受け取って返す**近くの**オーバーロードを呼び出すことができます。 C プログラムでは、**近辺の値**は常に 2 つの倍精度浮動小数点値を受け取り、倍精度浮動小数点値を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**近くの**,**近くの**,**近くの**|\<math.h>|\<cmath> または \<math.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[数値演算と浮動小数点のサポート](../floating-point-support.md)<br/>
