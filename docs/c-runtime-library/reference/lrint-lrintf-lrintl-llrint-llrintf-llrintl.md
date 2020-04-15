---
title: lrint、lrintf、lrintl、llrint、llrintf、llrintl
ms.date: 4/2/2020
api_name:
- lrint
- lrintl
- lrintf
- llrint
- llrintf
- llrintl
- _o_llrint
- _o_llrintf
- _o_llrintl
- _o_lrint
- _o_lrintf
- _o_lrintl
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
- lrint
- lrintf
- lrintl
- llrint
- llrintf
- llrintl
- math/lrint
- math/lrintf
- math/lrintl
- math/llrint
- math/llrintf
- math/llrintl
helpviewer_keywords:
- lrint function
- lrintf function
- lrintl function
- llrint function
- llrintf function
- llrintl function
ms.assetid: 28ccd5b3-5e6f-434f-997d-a21d51b8ce7f
ms.openlocfilehash: 6283cffaa094af4484d48781b5bb92d0339d38d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341665"
---
# <a name="lrint-lrintf-lrintl-llrint-llrintf-llrintl"></a>lrint、lrintf、lrintl、llrint、llrintf、llrintl

現在の丸めモードと方向を使用して、指定された浮動小数点値を最も近い整数値に丸めます。

## <a name="syntax"></a>構文

```C
long int lrint(
   double x
);

long int lrint(
   float x
); //C++ only

long int lrint(
   long double x
); //C++ only

long int lrintf(
   float x
);

long int lrintl(
   long double x
);

long long int llrint(
   double x
);

long long int llrint(
   float x
); //C++ only

long long int llrint(
   long double x
); //C++ only

long long int llrintf(
   float x
);

long long int llrintl(
   long double x
);
```

### <a name="parameters"></a>パラメーター

*X*<br/>
丸める値。

## <a name="return-value"></a>戻り値

成功した場合は、x*の丸*められた整数値を返します。

|問題|戻り値|
|-----------|------------|
|*x*は戻り値の型の範囲外です<br /><br /> *x* = ±∞<br /><br /> *x* = NaN|**FE_INVALID**を発生させ、ゼロ (0) を返します。|

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能なため **、float**型と**長い****ダブル**型を使用する**lint**および**llrint**のオーバーロードを呼び出すことができます。 Cプログラムでは **、rint**と**rrint**は常に**ダブル**を取ります.

*x*が整数値に相当する浮動小数点を表さない場合、これらの関数は**FE_INEXACT**を発生させます。

**マイクロソフト固有 :** 結果が戻り値の型の範囲外の場合、またはパラメーターが NaN または無限大の場合、戻り値は実装が定義されます。 Microsoft コンパイラは0 の値を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**リント**,**リンtf**,**リントル**, **llrint**, **llrintf**, **llrintl**|\<math.h>|\<cmath>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
