---
title: cproj、cprojf、cprojl
description: Cproj、cprojf、cprojl の API リファレンスReimann 球の複素数の射影を取得します。
ms.date: 9/2/2020
api_name:
- cproj
- cprojf
- cprojl
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
- cproj
- cprojf
- cprojl
- complex/cproj
- complex/cprojf
- complex/cprojl
helpviewer_keywords:
- cproj function
- cprojf function
- cprojl function
ms.assetid: 32b49623-13bf-4cae-802e-7912d75030fe
ms.openlocfilehash: fcc3c0a42c8c6392130ad58ed12c4985e7ad4907
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555944"
---
# <a name="cproj-cprojf-cprojl"></a>cproj、cprojf、cprojl

リーマン球面上への複素数の射影を取得します。

## <a name="syntax"></a>構文

```C
_Dcomplex cproj(
   _Dcomplex z
);
_Fcomplex cproj(
   _Fcomplex z
);  // C++ only
_Lcomplex cproj(
   _Lcomplex z
);  // C++ only
_Fcomplex cprojf(
   _Fcomplex z
);
_Lcomplex cprojl(
   _Lcomplex z
);
#define cproj(X) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*方向*\
複素数。

## <a name="return-value"></a>戻り値

Reimann 球の *z* の投影。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、 **_Fcomplex**と **_Lcomplex**の値を受け取って返す**cproj**のオーバーロードを呼び出すことができます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除いて \<tgmath.h> 、 **cproj** は常に **_Dcomplex** 値を取得して返します。

マクロを使用する場合 \<tgmath.h> `cproj()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**cproj**、 **cprojf**、 **cprojl**|\<complex.h>|\<ccomplex>|
|**cproj** マクロ | \<tgmath.h> ||

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[norm、normf、norml](norm-normf-norml1.md)<br/>
[creal、crealf、creall](creal-crealf-creall.md)<br/>
[conj、conjf、conjl](conj-conjf-conjl.md)<br/>
[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)<br/>
[carg、cargf、cargl](carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
