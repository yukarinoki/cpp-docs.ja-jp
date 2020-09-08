---
title: lrint、lrintf、lrintl、llrint、llrintf、llrintl
description: Lrint ()、lrintf ()、lrintl ()、llrint ()、llrintf ()、および llrintl (); の API リファレンス現在の丸めモードと方向を使用して、指定した浮動小数点値を最も近い整数値に丸めます。
ms.date: 9/1/2020
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: f208c183400aac7a110bb6fd87398d4377fe8f06
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555021"
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

#define lrint(X) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*閉じる*\
丸める値。

## <a name="return-value"></a>戻り値

成功した場合は、 *x*の丸められた整数値を返します。

|問題|戻り値|
|-----------|------------|
|*x* が戻り値の型の範囲外です。<br /><br /> *x* = ±∞<br /><br /> *x* = NaN|**FE_INVALID**を発生させ、ゼロ (0) を返します。|

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、型と型を受け取る **lrint** と **llrint** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 \<tgmath.h> **lrint** と **llrint** は常にを受け取り **`double`** ます。

マクロを使用する場合 \<tgmath.h> `llrint()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

*X*が整数値に相当する浮動小数点値を表さない場合、これらの関数は**FE_INEXACT**を発生させます。

**Microsoft 固有**: 結果が戻り値の型の範囲外の場合、またはパラメーターが NaN または無限大の場合、戻り値は実装定義になります。 Microsoft コンパイラは0 の値を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**lrint**、 **lrintf**、 **lrintl**、 **llrint**、 **llrintf**、 **llrintl**|\<math.h>|\<cmath>|
|**lrint** マクロ | \<tgmath.h> ||

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)
