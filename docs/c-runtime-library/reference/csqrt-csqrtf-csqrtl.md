---
title: csqrt、csqrtf、csqrtl
ms.date: 11/04/2016
apiname:
- csqrt
- csqrtf
- csqrtl
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
- csqrt
- csqrtf
- csqrtl
- complex/csqrt
- complex/csqrtf
- complex/csqrtl
helpviewer_keywords:
- csqrt function
- csqrtf function
- csqrtl function
ms.assetid: b65f086b-0f55-4622-a7a3-4e79d9c9c05c
ms.openlocfilehash: 00fe12d4f9c136278e56ceaf3fa62443092d0ec4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288837"
---
# <a name="csqrt-csqrtf-csqrtl"></a>csqrt、csqrtf、csqrtl

負の実軸に沿って分岐線法を使用して、複素数の平方根を取得します。

## <a name="syntax"></a>構文

```C
_Dcomplex csqrt(
   _Dcomplex z
);
_Fcomplex csqrt(
   _Fcomplex z
);  // C++ only
_Lcomplex csqrt(
   _Lcomplex z
);  // C++ only
_Fcomplex csqrtf(
   _Fcomplex z
);
_Lcomplex csqrtl(
   _Lcomplex z
);
```

### <a name="parameters"></a>パラメーター

*z*<br/>
複素数。

## <a name="return-value"></a>戻り値

平方根*z*します。 結果は右の半平面です。

|入力|SEH 例外|**_matherr**例外|
|-----------|-------------------|--------------------------|
|± QNAN、IND|none|_DOMAIN|
|- ∞|none|_DOMAIN|

## <a name="remarks"></a>Remarks

C++では、オーバー ロードのオーバー ロードを呼び出すことができます**csqrt**を受け取って返す **_Fcomplex**と **_Lcomplex**値。 C プログラムで**csqrt**は、 **_Dcomplex**値。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**csqrt**、 **csqrtf**、 **csqrtl**|\<complex.h>|\<ccomplex>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[catanh、catanhf、catanhl](catanh-catanhf-catanhl.md)<br/>
[ctanh、ctanhf、ctanhl](ctanh-ctanhf-ctanhl.md)<br/>
[catan、catanf、catanl](catan-catanf-catanl.md)<br/>
[csinh、csinhf、csinhl](csinh-csinhf-csinhl.md)<br/>
[casinh、casinhf、casinhl](casinh-casinhf-casinhl.md)<br/>
[ccosh、ccoshf、ccoshl](ccosh-ccoshf-ccoshl.md)<br/>
[cacosh、cacoshf、cacoshl](cacosh-cacoshf-cacoshl.md)<br/>
[cacos、cacosf、cacosl](cacos-cacosf-cacosl.md)<br/>
[ctan、ctanf、ctanl](ctan-ctanf-ctanl.md)<br/>
[csin、csinf、csinl](csin-csinf-csinl.md)<br/>
[casin、casinf、casinl](casin-casinf-casinl.md)<br/>
[ccos、ccosf、ccosl](ccos-ccosf-ccosl.md)<br/>
