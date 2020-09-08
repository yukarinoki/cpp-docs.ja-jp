---
title: carg、cargf、cargl
description: Carg、cargf、cargf の API リファレンス負の実数軸に沿って分岐を切り取って、複素数の引数を取得します。
ms.date: 9/2/2020
api_name:
- carg
- cargf
- cargl
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
- carg
- cargf
- cargl
- complex/carg
- complex/cargf
- complex/cargl
helpviewer_keywords:
- carg function
- cargf function
- cargl function
ms.assetid: 610d6a93-b929-46ab-a966-b77db0b804be
ms.openlocfilehash: 907694904b260c44dde84724c739c62dfe46dbde
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555814"
---
# <a name="carg-cargf-cargl"></a>carg、cargf、cargl

負の実数軸に沿って分岐を切り取って、複素数の引数を取得します。

## <a name="syntax"></a>構文

```C
double carg(
   _Dcomplex z
);
float carg(
   _Fcomplex z
);  // C++ only
long double carg(
   _Lcomplex z
);  // C++ only
float cargf(
   _Fcomplex z
);
long double cargl(
   _Lcomplex z
);
#define carg(X) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*方向*\
複素数。

## <a name="return-value"></a>戻り値

*Z*の引数 (フェーズとも呼ばれます)。 結果は [-π, + π] の範囲内にあります。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、 **_Fcomplex**または **_Lcomplex**値を受け取る**carg**のオーバーロードを呼び出し、または値を返すことができ **`float`** **`long double`** ます。 C プログラムでは、 \<tgmath.h> この関数を呼び出すためにマクロを使用している場合を除き、 **carg** は常に **_Dcomplex** 値を受け取り、値を返し **`double`** ます。

マクロを使用する場合 \<tgmath.h> `carg()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**carg**、 **cargf**、 **cargf**|\<complex.h>|\<ccomplex>|
|**carg** マクロ | \<tgmath.h> ||

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[norm、normf、norml](norm-normf-norml1.md)<br/>
[creal、crealf、creall](creal-crealf-creall.md)<br/>
[cproj、cprojf、cprojl](cproj-cprojf-cprojl.md)<br/>
[conj、conjf、conjl](conj-conjf-conjl.md)<br/>
[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
