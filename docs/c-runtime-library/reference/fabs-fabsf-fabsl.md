---
title: fabs、fabsf、fabsl
ms.date: 04/05/2018
apiname:
- fabsf
- fabs
- fabsl
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: 8df36c06fb3ca9af9be4cf704998946b3eaf9a6c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623562"
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
```

### <a name="parameters"></a>パラメーター

*x*<br/>
浮動小数点値。

## <a name="return-value"></a>戻り値

**Fabs**関数は引数の絶対値を返す*x*します。 エラーの戻り値はありません。

|入力|SEH 例外|Matherr 例外|
|-----------|-------------------|-----------------------|
|± QNAN、IND|none|_DOMAIN|

## <a name="remarks"></a>Remarks

C++ では、オーバー ロードのオーバー ロードを呼び出すことができますので**fabs**を含める場合、 \<cmath > ヘッダー。 C プログラムで**fabs**は、**二重**します。

## <a name="requirements"></a>必要条件

|関数|必須の C ヘッダー|必須の C++ ヘッダー|
|--------------|-----------------------|---------------------------|
|**fabs**、 **fabsf**、 **fabsl**|\<math.h>|\<cmath> または \<math.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[abs](abs-labs-llabs-abs64.md) 関数の例を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[abs、labs、llabs、_abs64](abs-labs-llabs-abs64.md)<br/>
[_cabs](cabs.md)<br/>
