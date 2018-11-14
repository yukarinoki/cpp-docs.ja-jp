---
title: fmax、fmaxf、fmaxl
ms.date: 04/05/2018
apiname:
- fmax
- fmaxf
- fmaxl
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
- fmax
- fmaxf
- fmaxl
- math/fmax
- math/fmaxf
- math/fmaxl
helpviewer_keywords:
- fmax function
- fmaxf function
- fmaxl function
ms.assetid: a773ccf7-495e-4a9a-8c6d-dfb53e341e35
ms.openlocfilehash: 371d53257427f2235048807968c82fec1b8bf699
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523703"
---
# <a name="fmax-fmaxf-fmaxl"></a>fmax、fmaxf、fmaxl

指定された 2 つの数値のうち、大きい方を特定します。

## <a name="syntax"></a>構文

```C
double fmax(
   double x,
   double y
);

float fmax(
   float x,
   float y
); //C++ only

long double fmax(
   long double x,
   long double y
); //C++ only

float fmaxf(
   float x,
   float y
);

long double fmaxl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
比較する最初の値です。

*y*<br/>
比較する 2 番目の値です。

## <a name="return-value"></a>戻り値

成功した場合のうち、大きい方を返します*x*または*y*します。 返される値は正確であり、どの丸め処理の形式にも依存しません。

それ以外の場合は、次の値のいずれかを返します。

|懸案事項|Return|
|-----------|------------|
|*x* = NaN|*y*|
|*y* = NaN|*x*|
|*x*と*y* = NaN|NaN|

この関数では、[_matherr](matherr.md) で指定されたエラーを使用しません。

## <a name="remarks"></a>Remarks

C++ ではオーバーロードが可能であるため、float 型および long double 型を受け取って返す fmax のオーバーロードを呼び出すことができます。 C プログラムでは、fmax は常に double を受け取って返します。

## <a name="requirements"></a>必要条件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fmax**、 **fmaxf**、 **fmaxl**|\<math.h>|\<cmath> または \<math.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[fmin、fminf、fminl](fmin-fminf-fminl.md)<br/>
