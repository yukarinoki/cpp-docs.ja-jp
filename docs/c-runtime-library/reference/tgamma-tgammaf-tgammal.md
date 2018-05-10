---
title: tgamma、tgammaf、tgammal | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- tgamma
- tgammaf
- tgammal
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
- tgamma
- tgammaf
- tgammal
- math/tgamma
- math/tgammaf
- math/tgammal
dev_langs:
- C++
helpviewer_keywords:
- tgamma function
- tgammaf function
- tgammal function
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7861b297646f4a704134e0d874fad8c924a7ebc8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma、tgammaf、tgammal

指定した値のガンマ関数を決定します。

## <a name="syntax"></a>構文

```C
double tgamma(
   double x
);

float tgamma(
   float x
); //C++ only

long double tgamma(
   long double x
); //C++ only

float tgammaf(
   float x
);

long double tgammal(
   long double x
);

```

### <a name="parameters"></a>パラメーター

*x*<br/>
ガンマを検索する値。

## <a name="return-value"></a>戻り値

成功した場合は、ガンマ値を返します*x*です。

場合に、範囲のエラーが発生する可能性がありますの大きさ*x*が大きすぎるか小さすぎるため、データ型。 場合に、ドメイン エラーまたは範囲エラーが発生する*x* < 0 を = です。

|懸案事項|Return|
|-----------|------------|
|x = ±0|±INFINITY|
|x = 負の整数|NaN|
|x = - 無限大|NaN|
|x = +INFINITY|+INFINITY|
|x = NaN|NaN|
|ドメイン エラー|NaN|
|極エラー|±HUGE_VAL、±HUGE_VALF、または ±HUGE_VALL|
|オーバーフロー範囲エラー|±HUGE_VAL、±HUGE_VALF、または ±HUGE_VALL|
|アンダーフロー範囲エラー|丸めた後の正確な値。|

エラーは、[_matherr](matherr.md) で指定されたとおりに報告されます。

## <a name="remarks"></a>コメント

C++ では、オーバー ロードできるよう、ためのオーバー ロードを呼び出すことができます**tgamma**を受け取り、返します**float**と**長い****二重**型です。 C プログラムでは、 **tgamma**常に受け取りを返す、**二重**です。

x が自然数の場合、この関数は (x-1) の階乗を返します。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**tgamma**、 **tgammaf**、 **tgammal**|\<math.h>|\<cmath>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[lgamma、lgammaf、lgammal](lgamma-lgammaf-lgammal.md)<br/>
