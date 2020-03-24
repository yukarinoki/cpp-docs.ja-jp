---
title: creal、crealf、creall
ms.date: 03/30/2018
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
ms.openlocfilehash: 4dcdf60fee6d57b5561b72b477aa1a8bb31f35f4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171217"
---
# <a name="creal-crealf-creall"></a>creal、crealf、creall

複素数の実数部を取得します。

## <a name="syntax"></a>構文

```C
double creal( _Dcomplex z );
float crealf( _Fcomplex z );
long double creall( _Lcomplex z );
```

```cpp
float creal( _Fcomplex z );  // C++ only
long double creal( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>パラメーター

*方向*<br/>
複素数。

## <a name="return-value"></a>戻り値

*Z*の実数部。

## <a name="remarks"></a>解説

でC++はオーバーロードが可能であるため、 **_Fcomplex**または **_Lcomplex**値を受け取る**creal**のオーバーロードを呼び出し、 **float 型**または**long double 型**の値を返すことができます。 C プログラムでは、 **creal**は常に **_Dcomplex**値を受け取り、 **double**値を返します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**creal**、 **crealf**、 **creal**|\<complex.h>|\<ccomplex>|

**_Fcomplex**、 **_Dcomplex**、および **_Lcomplex**型は、それぞれ、実装されていないネイティブ C99 型**float _Complex**、 **double _Complex**、および**long double _Complex**に相当する、Microsoft 固有のものです。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>参照

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[_Cbuild、_FCbuild、_LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[norm、normf、norml](norm-normf-norml1.md)<br/>
[cproj、cprojf、cprojl](cproj-cprojf-cprojl.md)<br/>
[conj、conjf、conjl](conj-conjf-conjl.md)<br/>
[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)<br/>
[carg、cargf、cargl](carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
