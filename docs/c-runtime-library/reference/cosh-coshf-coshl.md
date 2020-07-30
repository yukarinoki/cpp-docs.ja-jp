---
title: cosh、coshf、coshl
ms.date: 4/2/2020
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
ms.openlocfilehash: fb171d622d5bc187342054a74e8aa19f83c3c560
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213607"
---
# <a name="cosh-coshf-coshl"></a>cosh、coshf、coshl

ハイパーボリックコサインを計算します。

## <a name="syntax"></a>構文

```C
double cosh( double x );
float coshf( float x );
long double coshl( long double x );
```

```cpp
float cosh( float x );  // C++ only
long double cosh( long double x );  // C++ only
```

### <a name="parameters"></a>パラメーター

*x*<br/>
角度 (ラジアン)。

## <a name="return-value"></a>戻り値

*X*のハイパーボリックコサイン。

既定では、 **cosh**、 **coshf**、 **coshf**呼び出しで結果が大きすぎる場合、関数は**HUGE_VAL**を返し、 **errno**を**ERANGE**に設定します。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± **QNAN**、 **IND**|なし|**_DOMAIN**|
|*x* ≥ 7.104760 e + 002|**不正確** +**オーバーフロー**|**超え**|

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、またはの値を受け取って返す**cosh**のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、 **cosh**は常にを受け取り、を返し **`double`** ます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------|-|
|**coshf**、 **cosl**、 **coshf**|\<math.h>|\<cmath> または \<math.h>|

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
