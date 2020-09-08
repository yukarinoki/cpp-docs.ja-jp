---
title: cosh、coshf、coshl
description: Cosh、coshf、coshf の API リファレンス浮動小数点値のハイパーボリックコサインを計算する。
ms.date: 08/31/2020
api_name:
- cosh
- coshf
- coshl
- _o_cosh
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
- cosh
- coshf
- coshl
helpviewer_keywords:
- cosh function
- coshf function
- coshl function
- trigonometric functions
- hyperbolic functions
ms.openlocfilehash: 0ea4a5b77850e196c29519ac49b589a0c2b6c9a7
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555528"
---
# <a name="cosh-coshf-coshl"></a>cosh、coshf、coshl

ハイパーボリックコサインを計算します。

## <a name="syntax"></a>構文

```C
double cosh( double x );
float coshf( float x );
long double coshl( long double x );
#define cosh(X) // Requires C11 or higher

float cosh( float x );  // C++ only
long double cosh( long double x );  // C++ only
```

### <a name="parameters"></a>パラメーター

*閉じる*\
角度 (ラジアン)。

## <a name="return-value"></a>戻り値

*X*のハイパーボリックコサイン。

既定では、 **cosh**、 **coshf**、 **coshf** 呼び出しで結果が大きすぎる場合、関数は **HUGE_VAL** を返し、 **errno** を **ERANGE**に設定します。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± **QNAN**、 **IND**|なし|**_DOMAIN**|
|*x* ≥ 7.104760 e + 002|**不正確** +**オーバーフロー**|**超え**|

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、またはの値を受け取って返す **cosh** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 \<tgmath.h> **cosh** は常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `cosh()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------|-|
|**coshf**、 **cosl**、 **coshf**|\<math.h>|\<cmath> または \<math.h>|
|**coshf ()** マクロ | \<tgmath.h> ||

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[Sinh、sinhf、sinhf](sinh-sinhf-sinhl.md)の例を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[acosh、acoshf、acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh、asinhf、asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh、atanhf、atanhl](atanh-atanhf-atanhl.md)<br/>
[_matherr](matherr.md)<br/>
[sinh、sinhf、sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh、tanhf、tanhl](tanh-tanhf-tanhl.md)<br/>
