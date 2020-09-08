---
title: conj、conjf、conjl
description: Conj、conjf、および conjl の API リファレンス複素数の複素共役を取得します。
ms.date: 9/2/2020
api_name:
- conj
- conjf
- conjl
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
- conj
- conjf
- conjl
- complex/conj
- complex/conjf
- complex/conjl
helpviewer_keywords:
- conj function
- conjf function
- conjl function
ms.assetid: 792fccfa-19c6-4890-99f9-a3b89effccd6
ms.openlocfilehash: b779eb2d92893b204a73b2fa4f5c89928933ffeb
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556354"
---
# <a name="conj-conjf-conjl"></a>conj、conjf、conjl

複素数の複素共役を取得します。

## <a name="syntax"></a>構文

```C
_Dcomplex conj(
   _Dcomplex z
);
_Fcomplex conj(
   _Fcomplex z
);  // C++ only
_Lcomplex conj(
   _Lcomplex z
);  // C++ only
_Fcomplex conjf(
   _Fcomplex z
);
_Lcomplex conjl(
   _Lcomplex z
);
#define conj(X) // Requires C11 or higher
```

### <a name="parameters"></a>パラメーター

*方向*\
複素数。

## <a name="return-value"></a>戻り値

*Z*の複素共役。  結果の実数部と虚数部は *z*と同じですが、符号が逆になっています。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、 **_Fcomplex**と **_Lcomplex**の値を受け取って返す**conj**のオーバーロードを呼び出すことができます。 C プログラムでは、この関数を呼び出すためにマクロを使用している場合を除き \<tgmath.h> 、 **conj** は常に **_Dcomplex** 値を取得して返します。

マクロを使用する場合 \<tgmath.h> `conj()` 、引数の型によって、どのバージョンの関数が選択されているかが決まります。 詳細については [、「型汎用の算術演算](../../c-runtime-library/tgmath.md) 」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**conj**、 **conjf**、 **conjl**|\<complex.h>|\<ccomplex>|
|**conj** マクロ | \<tgmath.h> ||

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[norm、normf、norml](norm-normf-norml1.md)<br/>
[creal、crealf、creall](creal-crealf-creall.md)<br/>
[cproj、cprojf、cprojl](cproj-cprojf-cprojl.md)<br/>
[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)<br/>
[carg、cargf、cargl](carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
