---
title: cexp、cexpf、cexpl
description: Cexp、ctf、cexp の API リファレンスこれは、複素数の底 e 指数を計算します。
ms.date: 11/04/2016
api_name:
- cexp
- cexpf
- cexpl
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
- cexp
- cexpf
- cexpl
- complex/cepx
- complex/cexpf
- complex/cexpl
helpviewer_keywords:
- cexp function
- cexpl function
- cexpf function
ms.assetid: f27fd5a9-70c7-4957-a7ee-5256d19bd1da
ms.openlocfilehash: 66f7b687e8da12473abef4dbc44831e175956ac0
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555216"
---
# <a name="cexp-cexpf-cexpl"></a>cexp、cexpf、cexpl

複素数の e を底とするべき乗を計算します。

## <a name="syntax"></a>構文

```C
_Dcomplex cexp( _Dcomplex z );
_Fcomplex cexpf( _Fcomplex z );
_Lcomplex cexpl( _Lcomplex z );

_Fcomplex cexp( _Fcomplex z );  // C++ only
_Lcomplex cexp( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>パラメーター

*方向*\
指数を表す複素数。

## <a name="return-value"></a>戻り値

**E**の値が*z*の累乗になりました。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、 **_Fcomplex**と **_Lcomplex**の値を受け取って返す**cexp**のオーバーロードを呼び出すことができます。 C プログラムでは、 **cexp** は常に **_Dcomplex** 値を取得して返します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**cexp**、 **cexpf** **ctk**|\<complex.h>|\<complex.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)\
[cpow、cpowf、cpowl](cpow-cpowf-cpowl.md)\
[clog10、clog10f、clog10l](clog10-clog10f-clog10l.md)\
[clog、clogf、clogl](clog-clogf-clogl.md)
