---
title: fabs、fabsf、fabsl
description: Fabs、fabsf、および fabsl の API リファレンス浮動小数点値の絶対値を計算する。
ms.date: 1/15/2021
api_name:
- fabsf
- fabs
- fabsl
- _o_fabs
- _o_fabsf
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
- fabs
- fabsf
- fabsl
- "math\fabs"
- "math\fabsf"
- "math\fabsl"
helpviewer_keywords:
- absolute values
- fabsf function
- calculating absolute values
- fabs function
- fabsl function
ms.openlocfilehash: 453965b846dff9affb3fa6dce99ea8b6189a5d6c
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2021
ms.locfileid: "98563927"
---
# <a name="fabs-fabsf-fabsl"></a>`fabs`, `fabsf`, `fabsl`

浮動小数点引数の絶対値を計算します。

## <a name="syntax"></a>構文

```C
double fabs(
   double x
);
float fabs(
   float x
); // C++ only
long double fabs(
   long double x
); // C++ only
float fabsf(
   float x
);
long double fabsl(
   long double x
);

#define fabs(X) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*`x`*\
浮動小数点値。

## <a name="return-value"></a>戻り値

関数は、 **`fabs`** 引数 *x* の絶対値を返します。 エラーの戻り値はありません。

|入力|SEH 例外|`Matherr` 例外的|
|-----------|-------------------|-----------------------|
|± `QNAN`,`IND`|なし|`_DOMAIN`|

## <a name="remarks"></a>注釈

C++ ではオーバーロードが可能であるため、ヘッダーをインクルードすると、のオーバーロードを呼び出すことができ **`fabs`** `<cmath>` ます。 C プログラムでは、 `<tgmath.h>` この関数を呼び出すためにマクロを使用している場合を除き、は **`fabs`** 常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 `<tgmath.h>` `fabs()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|必須の C ヘッダー|必須の C++ ヘッダー|
|--------------|-----------------------|---------------------------|
|**`fabs`**, **`fabsf`**, **`fabsl`**|`<math.h>`|`<cmath>` または `<math.h>`|
|**`fabs`** マクロ | `<tgmath.h>` ||

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

の例を参照してください [`abs`](abs-labs-llabs-abs64.md) 。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)\
[`abs, labs, llabs, _abs64`](abs-labs-llabs-abs64.md)\
[`_cabs`](cabs.md)
