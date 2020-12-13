---
description: 詳細については、cpow、cpowf、cpowl を参照してください。
title: cpow、cpowf、cpowl
ms.date: 11/04/2016
api_name:
- cpow
- cpowf
- cpowl
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
- cpow
- cpowf
- cpowl
- complex/cpow
- complex/cpowf
- complex/copwl
helpviewer_keywords:
- cpow function
- cpowf function
- complex/cpowl function
ms.assetid: 83fe2187-22b7-4295-ab16-4d77abdbb80b
ms.openlocfilehash: 3e12cab3a7ec8c7f3f4bf8cd4739e10f022de8fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339642"
---
# <a name="cpow-cpowf-cpowl"></a>cpow、cpowf、cpowl

数値を指定された値で累乗して返します。底と指数は複素数です。 この関数には、負の実数軸に沿った指数の分岐切断線があります。

## <a name="syntax"></a>構文

```C
_Dcomplex cpow(
   _Dcomplex x, _Dcomplex y
);
_Fcomplex cpow(
   _Fcomplex x, _Fcomplex y
);  // C++ only
_Lcomplex cpow(
   _Lcomplex x, _Lcomplex y
);  // C++ only
_Fcomplex cpowf(
   _Fcomplex x, _Fcomplex y
);
_Lcomplex cpowl(
   _Lcomplex x, _Lcomplex y
);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
底。

*y*<br/>
指数。

## <a name="return-value"></a>戻り値

X の分岐が負の実数軸 *に沿って* *y* の累乗に累乗された *x* の値。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、 **_Fcomplex** と **_Lcomplex** の値を受け取って返す **cpow** のオーバーロードを呼び出すことができます。 C プログラムでは、 **cpow** は常に **_Dcomplex** 値を取得して返します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**cpow**、               **cpowf**、 **cpowl**|\<complex.h>|\<ccomplex>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[cexp、cexpf、cexpl](cexp-cexpf-cexpl.md)<br/>
[clog10、clog10f、clog10l](clog10-clog10f-clog10l.md)<br/>
[clog、clogf、clogl](clog-clogf-clogl.md)<br/>
