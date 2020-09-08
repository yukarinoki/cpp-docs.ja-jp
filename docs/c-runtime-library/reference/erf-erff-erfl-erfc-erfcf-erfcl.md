---
title: erf、erff、erfl、erfc、erfcf、erfcl
description: '% 1>、erff、erff、erfc、erfcf、erff; の API リファレンスこれにより、値のエラー関数または相補的なエラー関数が計算されます。'
ms.date: 9/1/2020
api_name:
- erff
- erfl
- erf
- erfc
- erfcf
- erfcl
- _o_erf
- _o_erfc
- _o_erfcf
- _o_erfcl
- _o_erff
- _o_erfl
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
- erfl
- erf
- erff
- erfc
- erfcf
- erfcl
helpviewer_keywords:
- erfl function
- erff function
- erf function
- erfcl function
- erfcf function
- erfc function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
ms.openlocfilehash: ef83275515c66341798395bbfc2bb5b088e6cfb7
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555645"
---
# <a name="erf-erff-erfl-erfc-erfcf-erfcl"></a>erf、erff、erfl、erfc、erfcf、erfcl

値の誤差関数または相補誤差関数を計算します。

## <a name="syntax"></a>構文

```C
double erf(
   double x
);
float erf(
   float x
); // C++ only
long double erf(
   long double x
); // C++ only
float erff(
   float x
);
long double erfl(
   long double x
);
double erfc(
   double x
);
float erfc(
   float x
); // C++ only
long double erfc(
   long double x
); // C++ only
float erfcf(
   float x
);
long double erfcl(
   long double x
);
#define erf(X) // Requires C11 or higher
#define erfc(X) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*閉じる*\
浮動小数点値。

## <a name="return-value"></a>戻り値

誤差 **関数は、** *x*のガウス誤差 error 関数を返します。 **Erfc**関数は、 *x*の相補的なガウス誤差 error 関数を返します。

## <a name="remarks"></a>解説

誤差 **関数は** *x*のガウス誤差 error 関数を計算します。これは次のように定義されています。

![x の誤差関数](media/crt_erf_formula.PNG "x の誤差関数")

相補的なガウス誤差 error 関数は、1-誤差 (x) として定義されています。 -1.0 ~ 1.0 の範囲の値が **返されます** 。 エラーの戻り値はありません。 **Erfc**関数は、0 ~ 2 の範囲の値を返します。 *X*が**erfc**に対して大きすぎる場合、 **errno**変数は**ERANGE**に設定されます。

C++ ではオーバーロードが可能であるため、型と型を受け取って返す、 **erfc** **のオーバーロードを呼び**出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 \<tgmath.h> **erfc**とは常にを受け取り、を返し**erf** **`double`** ます。

マクロを使用する場合 \<tgmath.h> `erf()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|必須ヘッダー|
|--------------|---------------------|
|**erf**erfc、 **erff**、 **erff**、 **erfc**、 **erfcf**、 **erff**|\<math.h>|
|を**持つマクロ** | \<tgmath.h> |

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
