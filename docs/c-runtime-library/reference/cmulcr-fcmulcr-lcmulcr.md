---
description: 詳細については、「_Cmulcr、_FCmulcr、_LCmulcr」を参照してください。
title: _Cmulcr、_FCmulcr、_LCmulcr
ms.date: 03/30/2018
api_name:
- _Cmulcr
- _FCmulcr
- _LCmulcr
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _Cmulcr
- _FCmulcr
- _LCmulcr
- complex/_Cmulcr
- complex/_FCmulcr
- complex/_LCmulcr
helpviewer_keywords:
- _Cmulcr function
- _FCmulcr function
- _LCmulcr function
ms.openlocfilehash: ea1dbbcea6890246b1e318da238fb8cc2ee3abb0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260723"
---
# <a name="_cmulcr-_fcmulcr-_lcmulcr"></a>_Cmulcr、_FCmulcr、_LCmulcr

複素数を浮動小数点数で乗算します。

## <a name="syntax"></a>構文

```C
_Dcomplex _Cmulcr( _Dcomplex x, double y );
_Fcomplex _FCmulcr( _Fcomplex x, float y );
_Lcomplex _LCmulcr( _Lcomplex x, long double y );
```

### <a name="parameters"></a>パラメーター

*x*<br/>
乗算する複合オペランドの1つ。

*y*<br/>
乗算する浮動小数点演算オペランド。

## <a name="return-value"></a>戻り値

複素数 *x* と flaoting number *y* の複雑な積を表す、 **_Dcomplex**、 **_Fcomplex**、または **_Lcomplex** 構造体。

## <a name="remarks"></a>解説

組み込みの算術演算子は、複合型の Microsoft 実装では機能しないため、 **_Cmulcr**、 **_FCmulcr**、および **_LCmulcr** の各関数は、浮動小数点型によって複合型の乗算を簡略化します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**_Cmulcr**、 **_FCmulcr**、 **_LCmulcr**|\<complex.h>|\<complex.h>|

これらの関数は、Microsoft 固有の関数です。 **_Dcomplex**、 **_Fcomplex**、および **_Lcomplex** 型は、それぞれ、実装されていない C99 ネイティブ型の **double _Complex**、 **float _Complex**、および **long double _Complex** に相当します。 互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[_Cbuild、_FCbuild、_LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[_Cmulcc、_FCmulcc、_LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[norm、normf、norml](norm-normf-norml1.md)<br/>
[cproj、cprojf、cprojl](cproj-cprojf-cprojl.md)<br/>
[conj、conjf、conjl](conj-conjf-conjl.md)<br/>
[creal、crealf、creall](creal-crealf-creall.md)<br/>
[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)<br/>
[carg、cargf、cargl](carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
