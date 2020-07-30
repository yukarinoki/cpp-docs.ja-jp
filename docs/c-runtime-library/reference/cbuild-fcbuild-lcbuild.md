---
title: _Cbuild、_FCbuild、_LCbuild
ms.date: 03/30/2018
api_name:
- _Cbuild
- _FCbuild
- _LCbuild
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
ms.openlocfilehash: d521fdb0d79e1e4ff6e6c1b01ce40941ed5c8c0a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221966"
---
# <a name="_cbuild-_fcbuild-_lcbuild"></a>_Cbuild、_FCbuild、_LCbuild

実数部および虚数部から複素数を構築します。

## <a name="syntax"></a>構文

```C
_Dcomplex _Cbuild( double real, double imaginary );
_Fcomplex _FCbuild( float real, float imaginary );
_Lcomplex _LCbuild( long double real, long double imaginary );
```

### <a name="parameters"></a>パラメーター

*real*<br/>
構築する複素数の実数部。

*仮想*<br/>
構築する複素数の虚数部。

## <a name="return-value"></a>戻り値

指定され **_Fcomplex**た浮動小 **_Lcomplex**数点型の値に対する複素数 (*実数*、*虚数*) を表す **_Dcomplex**、_Fcomplex、または _Lcomplex 構造体 \* 。

## <a name="remarks"></a>解説

**_Cbuild**、 **_FCbuild**、および **_LCbuild**の各関数は、複合型の作成を簡略化します。 表示される複素数の実数部と虚数部を取得するには、 [creal、crealf、creal](creal-crealf-creall.md) 、および[cimag、cimagf、cimagf](cimag-cimagf-cimagl.md)関数を使用します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**_Cbuild**、 **_FCbuild**、 **_LCbuild**|\<complex.h>|\<ccomplex>|

これらの関数は、Microsoft 固有の関数です。 **_Dcomplex**、 **_Fcomplex**、および **_Lcomplex**型はそれぞれ、実装されていない C99 ネイティブ型、、およびに相当し **`double _Complex`** **`float _Complex`** **`long double _Complex`** ます。 互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[_Cmulcc、_FCmulcc、_LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[_Cmulcr、_FCmulcr、_LCmulcr](cmulcr-fcmulcr-lcmulcr.md)<br/>
[norm、normf、norml](norm-normf-norml1.md)<br/>
[cproj、cprojf、cprojl](cproj-cprojf-cprojl.md)<br/>
[conj、conjf、conjl](conj-conjf-conjl.md)<br/>
[creal、crealf、creall](creal-crealf-creall.md)<br/>
[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)<br/>
[carg、cargf、cargl](carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
