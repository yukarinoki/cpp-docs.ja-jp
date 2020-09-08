---
title: clog、clogf、clogl
description: 待機、clogf、clogf の API リファレンス負の実数軸に沿って分岐を切り取って、複素数の自然対数を取得します。
ms.date: 11/04/2016
api_name:
- clog
- clogf
- clogl
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
- clog
- clogf
- clogl
- complex/clog
- complex/clogf
- complex/clogl
helpviewer_keywords:
- clog function
- clogf function
- clogl function
ms.assetid: 870b9b0b-6618-46f3-bfcf-da595cbd5e18
ms.openlocfilehash: 255f83a93c5c7a0c724fad143f028c2832be3173
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555073"
---
# <a name="clog-clogf-clogl"></a>clog、clogf、clogl

負の実軸に沿って分岐線法を使用して、複素数の自然対数を取得します。

## <a name="syntax"></a>構文

```C
_Dcomplex clog(
   _Dcomplex z
);
_Fcomplex clog(
   _Fcomplex z
);  // C++ only
_Lcomplex clog(
   _Lcomplex z
);  // C++ only
_Fcomplex clogf(
   _Fcomplex z
);
_Lcomplex clogl(
   _Lcomplex z
);
```

### <a name="parameters"></a>パラメーター

*方向*\
対数の底。

## <a name="return-value"></a>戻り値

*Z*の自然対数。 結果は、実数軸に沿って、虚数軸に沿って [-iπ, + iπ] の間隔で、無制限になります。

戻り値には次のようなものがあります。

|z パラメーター|戻り値|
|-----------------|------------------|
|正|z の底 10 の対数|
|ゼロ|- ∞|
|負|NaN|
|NaN|NaN|
|+ ∞|+ ∞|

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、 **_Fcomplex**と **_Lcomplex**の値を受け取って返す、オーバー**ロードのオーバーロード**を呼び出すことができます。 C プログラムでは、 **いっぱい** になると **_Dcomplex** 値が返されます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**いっぱい**、               **clogf**、 **clogf**|\<complex.h>|\<ccomplex>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[cexp、cexpf、cexpl](cexp-cexpf-cexpl.md)<br/>
[cpow、cpowf、cpowl](cpow-cpowf-cpowl.md)<br/>
[clog10、clog10f、clog10l](clog10-clog10f-clog10l.md)<br/>
