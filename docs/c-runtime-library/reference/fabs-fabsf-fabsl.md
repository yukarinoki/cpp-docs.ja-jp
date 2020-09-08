---
title: fabs、fabsf、fabsl
description: Fabs、fabsf、および fabsl の API リファレンス浮動小数点値の絶対値を計算する。
ms.date: 08/31/2020
api_name:
- fabsf
- fabs
- fabsl
- _o_fabs
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
ms.assetid: 23bca210-f408-4f5e-b46b-0ccaaec31e36
ms.openlocfilehash: a819172fc94224ff4c51c8fc342b142ffbe05ae7
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89554839"
---
# <a name="fabs-fabsf-fabsl"></a>fabs、fabsf、fabsl

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

*閉じる*\
浮動小数点値。

## <a name="return-value"></a>戻り値

**Fabs**関数は、引数*x*の絶対値を返します。 エラーの戻り値はありません。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± QNAN、IND|なし|_DOMAIN|

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、ヘッダーをインクルードすると、 **fabs** のオーバーロードを呼び出すことができ \<cmath> ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き、 \<tgmath.h> **fabs** は常にを受け取り、を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `fabs()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|必須の C ヘッダー|必須の C++ ヘッダー|
|--------------|-----------------------|---------------------------|
|**fabs**、 **fabsf**、 **fabsl**|\<math.h>|\<cmath> または \<math.h>|
|**fabs** マクロ | \<tgmath.h> ||

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[abs](abs-labs-llabs-abs64.md) 関数の例を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[abs、labs、llabs、_abs64](abs-labs-llabs-abs64.md)<br/>
[_cabs](cabs.md)<br/>
