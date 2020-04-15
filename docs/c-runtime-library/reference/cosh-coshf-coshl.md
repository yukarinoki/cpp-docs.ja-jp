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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: d7d2050be406e7f2be66ca200d1e3cfd9c2960b0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348442"
---
# <a name="cosh-coshf-coshl"></a>cosh、coshf、coshl

双曲線コサインを計算します。

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

*X*<br/>
角度 (ラジアン)。

## <a name="return-value"></a>戻り値

*x*の双曲線余弦 .

既定では **、cosh** **、coshf**、または**coshl**呼び出しで結果が大きすぎる場合、関数は**HUGE_VAL**を返し **、errno**を**ERANGE**に設定します。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± **QNAN,IND** **IND**|none|**_DOMAIN**|
|*x* ≥ 7.104760e+002|**不正確な**+**オーバーフロー**|**オーバーフロー**|

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能なため **、float**値または**長い****倍精度**浮動小数点値を取得して返す**cosh**のオーバーロードを呼び出すことができます。 C プログラムでは **、cosh**は常に二**重**を取り、返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー (C)|必須ヘッダー (C++)|
|-------------|---------------------|-|
|**コスフ**,**コスル**,**コスル**|\<math.h>|\<cmath> または \<math.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[シン、シンフ、シンフル](sinh-sinhf-sinhl.md)の例を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[acosh、acoshf、acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh、asinhf、asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh、atanhf、atanhl](atanh-atanhf-atanhl.md)<br/>
[_matherr](matherr.md)<br/>
[sinh、sinhf、sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh、tanhf、tanhl](tanh-tanhf-tanhl.md)<br/>
