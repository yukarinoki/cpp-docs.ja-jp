---
title: round、roundf、roundl
description: Round、roundf、および roundl の API リファレンス浮動小数点値を最も近い整数に丸める。
ms.date: 9/1/2020
api_name:
- round
- roundl
- roundf
- _o_round
- _o_roundf
- _o_roundl
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
- roundf
- roundl
- round
helpviewer_keywords:
- roundl function
- round function
- roundf function
ms.assetid: 6be90877-193c-4b80-a32b-c3eca33f9c6f
ms.openlocfilehash: 0a7e47dd3a528e45abc8247a64bf5c4d81164e95
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556646"
---
# <a name="round-roundf-roundl"></a>round、roundf、roundl

浮動小数点値を最も近い整数に丸めます。

## <a name="syntax"></a>構文

```C
double round(
   double x
);
float round(
   float x
);  // C++ only
long double round(
   long double x
);  // C++ only
float roundf(
   float x
);
long double roundl(
   long double x
);
#define round(X) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*閉じる*\
丸める浮動小数点値。

## <a name="return-value"></a>戻り値

**Round**関数は、最も近い整数を表す浮動小数点値を*x*に返します。 中間の値は、浮動小数点丸めモードの設定にかかわらず、ゼロから離れる方向に丸められます。 エラーの戻り値はありません。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± **QNAN**、 **IND**|なし|**_DOMAIN**|

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、との値を受け取って返す **ラウンド** のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 \<tgmath.h> **round** は常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `round()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**round**、 **roundf**、 **roundl**|\<math.h>|
|**round** マクロ | \<tgmath.h> ||

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_round.c
// Build with: cl /W3 /Tc crt_round.c
// This example displays the rounded results of
// the floating-point values 2.499999, -2.499999,
// 2.8, -2.8, 2.5 and -2.5.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.499999;
   float y = 2.8f;
   long double z = 2.5;

   printf("round(%f) is %.0f\n", x, round(x));
   printf("round(%f) is %.0f\n", -x, round(-x));
   printf("roundf(%f) is %.0f\n", y, roundf(y));
   printf("roundf(%f) is %.0f\n", -y, roundf(-y));
   printf("roundl(%Lf) is %.0Lf\n", z, roundl(z));
   printf("roundl(%Lf) is %.0Lf\n", -z, roundl(-z));
}
```

```Output
round(2.499999) is 2
round(-2.499999) is -2
roundf(2.800000) is 3
roundf(-2.800000) is -3
roundl(2.500000) is 3
roundl(-2.500000) is -3
```

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[ceil、ceilf、ceill](ceil-ceilf-ceill.md)<br/>
[floor、floorf、floorl](floor-floorf-floorl.md)<br/>
[fmod、fmodf](fmod-fmodf.md)<br/>
[lrint、lrintf、lrintl、llrint、llrintf、llrintl](lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)<br/>
[lround、lroundf、lroundl、llround、llroundf、llroundl](lround-lroundf-lroundl-llround-llroundf-llroundl.md)<br/>
[nearbyint、nearbyintf、nearbyintl](nearbyint-nearbyintf-nearbyintl1.md)<br/>
[rint、rintf、rintl](rint-rintf-rintl.md)<br/>
