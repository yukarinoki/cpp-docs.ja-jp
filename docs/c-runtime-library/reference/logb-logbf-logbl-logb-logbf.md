---
title: logb、logbf、logbl、_logb、_logbf
description: Logb、logb、logb、_logb、_logbf の API リファレンス浮動小数点引数の指数値を抽出します。
ms.date: 9/1/2020
api_name:
- logb
- _logb
- _logbl
- logbf
- _logbf
- logbl
- _o__logb
- _o_logb
- _o_logbf
- _o_logbl
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
- logb
- logbl
- _logb
- _logbf
- logbf
helpviewer_keywords:
- _logbf function
- mantissas, floating-point variables
- logbf function
- _logb function
- exponent, floating-point numbers
- logbl function
- logb function
- floating-point functions
- floating-point functions, mantissa and exponent
- exponents and mantissas
ms.assetid: 780c4daa-6fe6-4fbc-9412-4c1ba1a1766f
ms.openlocfilehash: 1131fda94e4748d2fb2f2197f68966aaacc11d05
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556215"
---
# <a name="logb-logbf-logbl-_logb-_logbf"></a>logb、logbf、logbl、_logb、_logbf

浮動小数点引数の指数の値を抽出します。

## <a name="syntax"></a>構文

```C
double logb(
   double x
);
float logb(
   float x
); // C++ only
long double logb(
   long double x
); // C++ only
float logbf(
   float x
);
long double logbl(
   long double x
);
double _logb(
   double x
);
float _logbf(
   float x
);
#define logb(X) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*閉じる*\
浮動小数点値。

## <a name="return-value"></a>戻り値

**logb** は、浮動小数点値として表される符号付き整数として、バイアスをかける *x* の指数値を返します。

## <a name="remarks"></a>解説

**Logb**関数は、浮動小数点引数*x*の指数値を抽出します。ただし、 *x*は無限範囲で表されます。 引数 *x* が非正規化されている場合は、正規化されているかのように扱われます。

C++ ではオーバーロードが可能であるため、またはの値を受け取って返す **logb** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除いて、 \<tgmath.h> **logb** は常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `logb()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± QNAN、IND|なし|_DOMAIN|
|±0|ZERODIVIDE|_SING|

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_logb**|\<float.h>|
|**logb**、 **logb**、 **logb**、 **_logbf**|\<math.h>|
|**logb** マクロ | \<tgmath.h> |

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
