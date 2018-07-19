---
title: _Cmulcr、_FCmulcr、_LCmulcr |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- _Cmulcr
- _FCmulcr
- _LCmulcr
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
- _Cmulcr
- _FCmulcr
- _LCmulcr
- complex/_Cmulcr
- complex/_FCmulcr
- complex/_LCmulcr
dev_langs:
- C++
helpviewer_keywords:
- _Cmulcr function
- _FCmulcr function
- _LCmulcr function
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbd42e4c543d4bc42afa023d62b328a143c90374
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395026"
---
# <a name="cmulcr-fcmulcr-lcmulcr"></a>_Cmulcr、_FCmulcr、_LCmulcr

浮動小数点数によっての複素数を乗算します。

## <a name="syntax"></a>構文

```C
_Dcomplex _Cmulcr( _Dcomplex x, double y );
_Fcomplex _FCmulcr( _Fcomplex x, float y );
_Lcomplex _LCmulcr( _Lcomplex x, long double y );
```

### <a name="parameters"></a>パラメーター

*x*<br/>
乗算する複雑なオペランドの 1 つです。

*y*<br/>
乗算する浮動小数点のオペランドです。

## <a name="return-value"></a>戻り値

A **_Dcomplex**、 **_Fcomplex**、または **_Lcomplex**複素数の複雑な製品を表す構造*x*とflaoting ポイント数*y*です。

## <a name="remarks"></a>コメント

組み込みの算術演算子は、複合型の Microsoft による実装では動作しないため、 **_Cmulcr**、 **_FCmulcr**、および **_LCmulcr**関数浮動小数点型での複合型の乗算を簡略化します。

## <a name="requirements"></a>要件

|ルーチン|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**_Cmulcr**、 **_FCmulcr**、 **_LCmulcr**|\<complex.h>|\<complex.h>|

これらの関数は、Microsoft 固有です。 種類 **_Dcomplex**、 **_Fcomplex**、および **_Lcomplex**未実装 C99 ネイティブ型に対応する Microsoft 固有の仕様は、**二重 _complex型**、 **float _complex型**、および**long double _complex型**、それぞれします。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[_Cbuild、_FCbuild、_LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[_Cmulcc、_FCmulcc、_LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[norm、normf、norml](norm-normf-norml1.md)<br/>
[cproj、cprojf、cprojl](cproj-cprojf-cprojl.md)<br/>
[conj、conjf、conjl](conj-conjf-conjl.md)<br/>
[creal、crealf、creall](creal-crealf-creall.md)<br/>
[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)<br/>
[carg、cargf、cargl](carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
