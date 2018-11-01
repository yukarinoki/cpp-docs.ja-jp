---
title: _Cbuild、_FCbuild、_LCbuild
ms.date: 03/30/2018
apiname:
- _Cbuild
- _FCbuild
- _LCbuild
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
- _Cbuild
- _FCbuild
- _LCbuild
- complex/_Cbuild
- complex/_FCbuild
- complex/_LCbuild
helpviewer_keywords:
- _Cbuild function
- _FCbuild function
- _LCbuild function
ms.openlocfilehash: 5565c87a3cccd1715a1357f417238587f3fba4d5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511801"
---
# <a name="cbuild-fcbuild-lcbuild"></a>_Cbuild、_FCbuild、_LCbuild

実数部と虚数部から複素数を構築します。

## <a name="syntax"></a>構文

```C
_Dcomplex _Cbuild( double real, double imaginary );
_Fcomplex _FCbuild( float real, float imaginary );
_Lcomplex _LCbuild( long double real, long double imaginary );
```

### <a name="parameters"></a>パラメーター

*real*<br/>
構築する複素数の実数部。

*imaginary*<br/>
構築する複素数の虚数部。

## <a name="return-value"></a>戻り値

A **_Dcomplex**、 **_Fcomplex**、または **_Lcomplex**複素数を表す構造体 (*実際*、*虚数部* \*は) 指定した浮動小数点型の値。

## <a name="remarks"></a>Remarks

**_Cbuild**、 **_FCbuild**、および **_LCbuild**関数の複雑な種類の作成を簡略化します。 使用して、 [creal、crealf、creall](creal-crealf-creall.md)と[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)表される複素数の実数部と虚数部の部分を取得する関数。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**_Cbuild**、 **_FCbuild**、 **_LCbuild**|\<complex.h>|\<ccomplex>|

これらの関数は、Microsoft 固有です。 種類 **_Dcomplex**、 **_Fcomplex**、および **_Lcomplex**は実装されていない C99 のネイティブ型に対応する Microsoft 固有**double _Complex**、 **float _Complex**、および**long double _Complex**、それぞれします。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[_Cmulcc、_FCmulcc、_LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[_Cmulcr、_FCmulcr、_LCmulcr](cmulcr-fcmulcr-lcmulcr.md)<br/>
[norm、normf、norml](norm-normf-norml1.md)<br/>
[cproj、cprojf、cprojl](cproj-cprojf-cprojl.md)<br/>
[conj、conjf、conjl](conj-conjf-conjl.md)<br/>
[creal、crealf、creall](creal-crealf-creall.md)<br/>
[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)<br/>
[carg、cargf、cargl](carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
