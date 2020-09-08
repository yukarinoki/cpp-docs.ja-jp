---
title: creal、crealf、creall
description: Creal、crealf、creal の API リファレンス複素数の実数部を取得します。
ms.date: 9/2/2020
api_name:
- creal
- crealf
- creall
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
- creal
- crealf
- creall
- complex/creal
- complex/crealf
- complex/creall
helpviewer_keywords:
- creal function
- crealf function
- creall function
ms.assetid: fa3ac62f-7aa3-4238-a71f-d6b00cd0c7c8
ms.openlocfilehash: 4f375bbe8813ba67130f8b56d8e2c99d5b734764
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555931"
---
# <a name="creal-crealf-creall"></a>creal、crealf、creall

複素数の実数部を取得します。

## <a name="syntax"></a>構文

```C
double creal( _Dcomplex z );
float crealf( _Fcomplex z );
long double creall( _Lcomplex z );
#define creal(X) // Requires C11 or higher

float creal( _Fcomplex z );  // C++ only
long double creal( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>パラメーター

*方向*<br/>
複素数。

## <a name="return-value"></a>戻り値

*Z*の実数部。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、 **_Fcomplex**または **_Lcomplex**値を受け取り、または値を返す**creal**のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き \<tgmath.h> 、 **creal** は常に **_Dcomplex** 値を受け取り、値を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `creal()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**creal**、 **crealf**、 **creal**|\<complex.h>|\<ccomplex>|
|**creal** マクロ | \<tgmath.h> ||

**_Fcomplex**、 **_Dcomplex**、および **_Lcomplex**型は、それぞれ、実装されていないネイティブ C99 型**float _Complex**、 **double _Complex**、および**long double _Complex**に相当する、Microsoft 固有のものです。 互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[_Cbuild、_FCbuild、_LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[norm、normf、norml](norm-normf-norml1.md)<br/>
[cproj、cprojf、cprojl](cproj-cprojf-cprojl.md)<br/>
[conj、conjf、conjl](conj-conjf-conjl.md)<br/>
[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)<br/>
[carg、cargf、cargl](carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
