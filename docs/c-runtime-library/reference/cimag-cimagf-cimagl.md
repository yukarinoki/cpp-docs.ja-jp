---
title: cimag、cimagf、cimagl
description: Cimag、cimagf、cimagf の API リファレンス複素数の虚数部を取得します。
ms.date: 9/2/2020
api_name:
- cimag
- cimagf
- cimagl
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
- cimagf
- cimagl
- complex/cimag
- complex/cimagf
- complex/cimagl
- cimag
helpviewer_keywords:
- cimag function
- cimagf function
- cimagl function
ms.assetid: 0d8836f5-d61d-44cd-8731-6f75cb776def
ms.openlocfilehash: 41631a161a47e247b12a39e312a3f40084c8f22f
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555841"
---
# <a name="cimag-cimagf-cimagl"></a>cimag、cimagf、cimagl

複素数の虚数部を取得します。

## <a name="syntax"></a>構文

```C
double cimag( _Dcomplex z );
float cimagf( _Fcomplex z );
long double cimagl( _Lcomplex z );
#define cimag(X) // Requires C11 or higher

float cimag( _Fcomplex z );  // C++ only
long double cimag( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>パラメーター

*方向*\
複素数。

## <a name="return-value"></a>戻り値

*Z*の虚数部。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、 **_Fcomplex**または **_Lcomplex**値を受け取り、または値を返す**cimag**のオーバーロードを呼び出すことができ **`float`** **`long double`** ます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き \<tgmath.h> 、 **cimag** は常に **_Dcomplex** 値を受け取り、値を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `cimag()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**cimag**、 **cimagf**、 **cimagf**|\<complex.h>|\<ccomplex>|
|**cimag** マクロ | \<tgmath.h> ||

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[norm、normf、norml](norm-normf-norml1.md)<br/>
[creal、crealf、creall](creal-crealf-creall.md)<br/>
[cproj、cprojf、cprojl](cproj-cprojf-cprojl.md)<br/>
[conj、conjf、conjl](conj-conjf-conjl.md)<br/>
[carg、cargf、cargl](carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
