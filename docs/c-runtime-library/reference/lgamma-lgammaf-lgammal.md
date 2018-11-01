---
title: lgamma、lgammaf、lgammal
ms.date: 04/05/2018
apiname:
- lgamma
- lgammaf
- lgammal
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
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
ms.openlocfilehash: 43ce1599ab9161b9fadf5643ddd2ec739ab2d8b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533485"
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma、lgammaf、lgammal

指定した値のガンマ関数の絶対値の自然対数を決定します。

## <a name="syntax"></a>構文

```C
double lgamma( double x );
float lgammaf( float x );
long double lgammal( long double x );
```

```cpp
float lgamma( float x ); //C++ only
long double lgamma( long double x ); //C++ only
```

### <a name="parameters"></a>パラメーター

*x*<br/>
計算される値です。

## <a name="return-value"></a>戻り値

成功した場合、値のガンマ関数の絶対値の自然対数を返す*x*します。

|懸案事項|Return|
|-----------|------------|
|*x* = NaN|NaN|
|*x* ±0 を =|+INFINITY|
|*x*負の整数を =|+INFINITY|
|±INFINITY|+INFINITY|
|極エラー|+HUGE_VAL、+HUGE_VALF、または +HUGE_VALL|
|オーバーフロー範囲エラー|±HUGE_VAL、±HUGE_VALF、または ±HUGE_VALL|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>Remarks

オーバー ロードを呼び出すことができますので、C++ ではオーバー ロード、 **lgamma**を受け取って返す**float**と**長い****二重**型。 C プログラムで**lgamma**は、**二重**します。

X が有理数の場合は、この関数は、(x - 1) の階乗の対数を返します。

## <a name="requirements"></a>必要条件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**lgamma**、 **lgammaf**、 **lgammal**|\<math.h>|\<cmath>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[tgamma、tgammaf、tgammal](tgamma-tgammaf-tgammal.md)<br/>
